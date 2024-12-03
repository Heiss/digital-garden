---
{"dg-publish":true,"permalink":"/3-resources/pkm/p-obsidian-git/p-obsidian-git/","tags":["git"],"created":"2024-11-04T19:52:38.650+01:00","updated":"2024-11-04T21:01:30.098+01:00"}
---

- folgend der [Anleitung](https://publish.obsidian.md/git-doc/Installation) lässt sich relativ schnell das Plugin in ein neu installiertes Obsidian installieren
- bei Windows ist noch folgendes notwendig
	- `git config --system core.longpaths true`, da die Länger der Ordner und Dateien teils den kompilierten Längen übersteigt
- außerdem muss bei Initialisierung das Plugin `local-images-plus` deaktiviert sein, was aber bei einem frischen Obsidian eh kein Problem ist
	- mein Mobilgerät konnte ich leider noch nicht hinzufügen
- falls Signing aktiviert ist und Probleme gibt, dann kann es lokal deaktiviert werden
	- `git config --local commit.gpgsign false`