---
{"dg-publish":true,"permalink":"/3-resources/softwarearchitektur/arc42-in-ascii-doc/arc42-in-ascii-doc/","tags":["blog"],"created":"2024-07-07T12:55:03.316+02:00","updated":"2024-07-08T08:56:50.037+02:00"}
---


AsciiDoc is a good markup language and an alternative for dominant markdown, which has some flaws for software developer and architects. [[3 Resources/Führungsrolle/Technical Writing/arc42 in Aktion von Gernot Starke/arc42 in Aktion von Gernot Starke\|arc42]] is a beautiful way to write down a document about software architecture. In this post, i want to show you a complete example of, how to get a full-fledged pipeline and asciidoc environment in a declarative way.

First of all, you need a folder, where you place all following files in it. Maybe you should also initialize a git repo.

 In this example i use gitlab-ci. So we need a `gitlab-ci.yml`:
 
```yaml
pages:
  image: nixos/nix
  script:
    - mkdir -p ~/.config/nix && echo "experimental-features = nix-command flakes" >> ~/.config/nix/nix.conf && nix-channel --update
    - nix develop --command web
    - mkdir -p public/images
    - cp images/* public/images

  artifacts:
    paths:
      - public
```

You see, we are using nix, like in [[3 Resources/Nix & NixOS/Publish hugo blog with asciidoc and Nix\|Publish hugo blog with asciidoc and Nix]]. So we need a `flake.nix` file.

```nix
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
             buildInputs = [ bundler
             (writeScriptBin "web"
              ''
                #!${pkgs.stdenv.shell}
                export LANG=C.UTF-8
                export LANGUAGE=C.UTF-8
                export LC_ALL=C.UTF-8

                bundle exec asciidoctor \
                  --trace --verbose \
                 -a allow-uri-read \
                 -r asciidoctor-kroki \
                 -r asciidoctor-bibtex \
                 -r asciidoctor-lists \
                 -a kroki-default-format=svg \
                 -b html \
                 -o public/index.html \
                 arc42-template.adoc
              '')
             (writeScriptBin "build"
              ''
                #!${pkgs.stdenv.shell}
                export LANG=C.UTF-8
                export LANGUAGE=C.UTF-8
                export LC_ALL=C.UTF-8

                bundle exec asciidoctor \
                  --trace --verbose \
                 -a allow-uri-read \
                 -r asciidoctor-kroki \
                 -r asciidoctor-bibtex \
                 -r asciidoctor-lists \
                 -r asciidoctor-pdf -b pdf \
                 arc42-template.adoc
              '')];
              shellHook = ''
                # Install required configuration
                bundle install
              '';
            };
         }
       );
}
```

With this, you get 2 options to work with: The `build` command builds a pdf file, the `web`command a html website, which we will use in our pipeline. The pdf is excellent, if you want to publish a book, too. 

>[NOTE]
> I use `build` in my workflow to write scientific paper, so i let it in... maybe you want to reuse it.)

Because asciidoctor was written in Ruby, you need a `Gemfile`:

```ruby
source 'https://rubygems.org'
gem 'asciidoctor'
gem 'asciidoctor-pdf'
gem 'asciidoctor-kroki'
gem 'asciidoctor-bibtex'
gem 'asciidoctor-lists'
gem 'rouge'
```

Next, you download the [asciidoc arc42 template](https://arc42.org/download) in your wanted language. Place the content of it beneath the files you already created.

Now you should have this in your folder structure

```bash
$ ls -lah .
- images/
- src/
- .gitlab-ci.yml
- arc42-template.adoc
- Gemfile
- flake.nix
```

Now you are already able to push this to a gitlab instance and get a webite with your documentation.

If you want to run it local, you have to use docker (easy for any OS) or run a nix environment (not existing for windows without WSL).
The following command should do the trick.

```bash
$ docker run -it --rm -v .:/app -w /app nixos/nix nix develop --experimental-features 'nix-command flakes' --command web
```

Replace `web` with `build` to get a pdf file.

# Features

The previous setup has enabled some more features for asciidoc for better workflow. I show you them now.

## Kroki & c4 model

Because you want to show some diagrams, this configuration integrates [Kroki](https://kroki.io) already. In my case, i wanted to dynamic generate a [c4 nodel](https://c4model.com) with a given workspace.dsl file. Create a new folder `c4model` and place your `workspace.dsl` in it, for example created with the [web editor](https://structurizr.com/dsl).

If you are using multiple views, you can select the integrated view with `view-key`. Here is an example from the [official github repo](https://github.com/structurizr/examples/blob/main/dsl/big-bank-plc/workspace.dsl).

```asciidoc
[structurizr,view-key=SystemLandscape]
....
include::../c4model/workspace.dsl[]
....

[structurizr,view-key=Containers]
....
include::../c4model/workspace.dsl[]
....
```

This asciidoc example show two different diagrams, generated from the same file. Nice!
In the future, if my [PR](https://github.com/yuzutech/kroki/pull/1684) got merged, you can also use [[3 Resources/Anforderungsmanagement/Wardley Mapping\|Wardley Maps]] easily in your arc42 doc for example created by [OnlineWardleyMaps.com](https://onlinewardleymaps.com).

```asciidoc
[wardleymap]
....
include::../wardleymap/wardley.map
....
```

## Bibtex

If you are using [Zotero](https://retorque.re/zotero-better-bibtex/) or other tools for research, you can use bibtex as file format to cite stuff in your document. In asciidoc you can cite stuff with `cite:[BibtexRefKey(page)` ([See doc for more](https://github.com/asciidoctor/asciidoctor-bibtex?tab=readme-ov-file#macros)).

For a complete bibliography of used literature, you can add `bibliography::[]` to your document wherever you want (maybe at the bottom, i guess. :))

## Lists

If you have a big document, you want to have an appendix with all your listings, images and tables. This is already enabled. [See the repo](https://github.com/Alwinator/asciidoctor-lists?tab=readme-ov-file#code) which snippets you can add to get this lists inserted. Mostly they are at the end of your document, but feel free to place them wherever you want. :)
