---
{"dg-publish":true,"permalink":"/3-resources/nix-and-nix-os/publish-hugo-blog-with-asciidoc-and-nix/","tags":["blog","lang-en"],"created":"2024-11-11T08:59:44.067+01:00","updated":"2024-07-28T23:19:00.604+02:00"}
---


In this post, i want to give you a brief introduction how you can publish your very own blog with hugo and asciidoc as your primary markup language. Why i would like to show this? Mh…​ well mostly, because this blog is mostly created by it. At the end, i will show you how you can use nix to build your blog as an easy-to-use all-in-one dependency-management tool.

>[!NOTE] Published
>This post is also available on [medium.com](https://medium.com/@peter.heiss/publish-hugo-blog-with-asciidoc-and-nix-fcc0eed15362).

# Why you should want to publish your own blog

First it is always a good idea to learn something new. Second a lot of people do not write a diary but a lot of learning researchers recommends it. So if you want to start with it, you could also make it open for everyone, so they can learn from you and your thoughts. Some philosophic perspectives were created by people who wrote their thoughts down. So why not start with it aswell? Maybe you are the next emperor. :)

# Why you should do this with hugo, asciidoc and nix

First hugo is a very fast and popular static page generator. You find a lot of tutorials, themes and other stuff for hugo, so you shouldn’t have any problems to setup.

AsciiDoc is a not so popular markup language, comparable to markdown, but with a lot more features. You can use it to create books, presentations, articles and so on. It is very powerful, but you need to learn some syntax. For technical writers it is a better choice than markdown, because it is better to refer to or include code snippets into your text.

Nix is a dependency management tool, which you can use like you used package.json for npm in your javascript or cargo.toml for cargo in your rust project. It is a declarative language, which means you can describe your dependencies and environment and nix will build it for you, so you do not install any stuff into your operating system. So you d not have to worry about any conflicts with other software. In fact you can use it to build your blog, but also to build your whole operating system.

In combination it is a powerful toolset to create your whole workflow. With asciidoc you can write your articles, with hugo you can create your blog and with nix you can build it and publish it. Also it makes easy to create a github action.

# Prepare your environment

Sadly something you need always to install. Nix will handle it for you later, but first you need to install nix to do the management stuff for you. So please direct your browser to the [official Site](https://nixos.org/download.html) and follow the instructions. Mostly it is just a curl command or an instruction for your software manager from your distro.

Now we can start. Nix help us to use hugo without installing it. I will call the folder `blog` in this post. After this, we need to configure our nix environment. I want to use the new, at this time, experimental feature `flakes`. For easier usage, we activate it globally.

```
mkdir -p ~/.config/nix  
echo 'experimental-features = nix-command flakes' >> ~/.config/nix/nix.conf # activate flakes  
nix-shell -p hugo --command "hugo new site blog" # init a new hugo blog  
cd blog  
touch flake.nix
```

Now we can configure our nix environment. Paste the following into your `flake.nix` file. This installs hugo, the ruby bundler for asciidoc and 2 scripts for easier usage. If you want to understand the nix language, you should learn it and come back later. I will not refer to it any longer and will use the commandline tool only.

```
{  
   inputs = {  
	 nixpkgs.url = "github:NixOS/nixpkgs/nixos-unstable";  
	 flake-utils.url = "github:numtide/flake-utils";  
   };  
   outputs = { self, nixpkgs, flake-utils }:  
	 flake-utils.lib.eachDefaultSystem  
	   (system:  
		 let  
			pkgs = import nixpkgs {  
				inherit system;  
				overlays = [];  
			};  
		 in  
		 with pkgs;  
		 {  
		   devShells.default = mkShell {  
			 buildInputs = [ hugo bundler  
			 (writeScriptBin "build"  
			  ''  
				#!${pkgs.stdenv.shell}  
				bundle install  
				env PATH=$PWD/bin:$PATH hugo --gc --minify // (1)  
			  '')  
			 (writeScriptBin "server"  
			  ''  
				#!${pkgs.stdenv.shell}  
				bundle install  
				env PATH=$PWD/bin:$PATH hugo server --disableFastRender  
			  '')];  
			};  
		 }  
	   );  
}
```

(1) In a few moments, we will take care that this $path manipulation will be makes sense. :)

Now we need a gemfile for ruby’s bundler to install all asciidoc dependencies. Paste the following into a file called `Gemfile`.

```
source 'https://rubygems.org'  
gem 'asciidoctor'  
gem 'asciidoctor-diagram'  
gem 'asciidoctor-html5s'
```

Because of some problems with hugo and asciidoc in combination, we need a helper file. Paste the following into a file called `bin/asciidoctor`. This is a workaround for a bug in hugo, which will be fixed in the next release.

```
#!/bin/sh  
  
ad="bundle exec asciidoctor"  
  
$ad --trace --verbose \  
  --base-dir ./content \  
  --no-header-footer \  
  --attribute nofooter \  
  --attribute docinfo=shared \  
  --attribute icons=font \  
  --attribute source-highlighter=highlightjs \  
  --attribute sectlinks \  
  --attribute sectanchors \  
  --attribute figure-caption! \  
  --attribute toc-title! \  
  --require asciidoctor-diagram \  
  --require asciidoctor-html5s \  
  -
```

The `flake.nix` assumes that this file already exists. So you are now ready to spin up your hugo preview server the first time.

```
nix develop --command server
```

This was easy, isn’t it? You do not have to install any of the dependencies or manage them on your own. Also you have a lot of generated lock files for your dependencies, so you can always reproduce your environment with a simple command. This is the beauty of nix. You can interact with the environment like a normal shell, you only need to execute `nix develop`.

Now you can configure your hugo page and create posts like in any other hugo tutorial. The main difference is, that the content posts have to have the ending `.adoc` instead of `.md`. Also you can use asciidoc syntax instead of markdown. I will not explain it here, because you can find a lot of tutorials for it. But I will give you a short example. Copy the following snippet into the file `content/posts/first-post.adoc`.

```
This is a preamble.  
  
== First level heading  
  
This is a paragraph.
```

If you have started the preview server before, you should find this post now on [http://localhost:1313/post/first-post/](http://localhost:1313/post/first-post/).

# Add github actions for easy publishing

Now comes the fun part: We create a github action to build and publish your new blog. This is very easy, because we already have a nix environment. We only need to create a new file called `.github/workflows/hugo.yml` and paste the following into it. Do not forget to enable the pages feature in your github repository settings. This is using the pages features via github actions instead of branches.

# Sample workflow for building and deploying a Hugo site to GitHub Pages

```
name: Deploy Hugo site to Pages  
  
on:  

# Runs on pushes targeting the default branch

  push:  
	branches:  
	  - main  
  

# Allows you to run this workflow manually from the Actions tab

  workflow_dispatch:  
  

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages

permissions:  
  contents: read  
  pages: write  
  id-token: write  
  

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.

# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.

concurrency:  
  group: "pages"  
  cancel-in-progress: false  
  

# Default to bash

defaults:  
  run:  
	shell: bash  
  
jobs:  

# Build job

  build:  
	runs-on: ubuntu-latest  
	steps:  
	  - name: Checkout  
		uses: actions/checkout@v3  
		with:  
		  submodules: recursive  
		  fetch-depth: 0  
	  - name: Setup Pages  
		id: pages  
		uses: actions/configure-pages@v3  
	  - name: Install Nix  
		uses: cachix/install-nix-action@v17  
		with:  

# Mostly to avoid GitHub rate limiting

          extra_nix_config: |  
            access-tokens = github.com=${{ secrets.GITHUB_TOKEN }}  
          github_access_token: ${{ secrets.GITHUB_TOKEN }}  

# Note: this would only work if Cargo is included in the Nix shell

      - name: Build with Hugo  
        env:  

# For maximum backward compatibility with Hugo modules

          HUGO_ENVIRONMENT: production  
          HUGO_ENV: production  
        run: |  
          nix develop --command build // (1)  
      - name: Upload artifact  
        uses: actions/upload-pages-artifact@v1  
        with:  
          path: ./public  
  

# Deployment job

  deploy:  
	environment:  
	  name: github-pages  
	  url: ${{ steps.deployment.outputs.page_url }}  
	runs-on: ubuntu-latest  
	needs: build  
	steps:  
	  - name: Deploy to GitHub Pages  
		id: deployment  
		uses: actions/deploy-pages@v2
```

(1) This is the command to build your hugo page. It is using the same nix environment we created before and used locally.

So now you can commit your files to a git repository and push it to your wanted github account. But this blogpost is already long enough, so I will not explain this here. There are too many tutorials out there, which are doing this better than me. Take a look in the next section, maybe there is a helpful link for you to solve any issues you have.

## More links to read or other sources of informations

- [https://blog.arkey.fr/2020/04/23/tackling-hugo-integration-of-asciidoctor/](https://blog.arkey.fr/2020/04/23/tackling-hugo-integration-of-asciidoctor/)
- [https://github.com/marketplace/actions/install-nix](https://github.com/marketplace/actions/install-nix)
- [https://rgielen.net/posts/2019/creating-a-blog-with-hugo-and-asciidoctor/](https://rgielen.net/posts/2019/creating-a-blog-with-hugo-and-asciidoctor/)
- [https://www.banjocode.com/post/hugo/custom-css#3-add-to-headhtml](https://www.banjocode.com/post/hugo/custom-css#3-add-to-headhtml)
