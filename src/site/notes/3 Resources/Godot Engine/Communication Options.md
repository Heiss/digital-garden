---
{"dg-publish":true,"permalink":"/3-resources/godot-engine/communication-options/","created":"2024-06-23T19:53:54.496+02:00","updated":"2024-04-15T08:30:11.493+02:00"}
---


Es gibt viele verschiede Möglichkeiten, dass Objekte miteinander reden. Wichtig ist, dass Signale für die Kommunikation nach oben benutzt wird, aber nach unten dann Contracts. Durch Composition können Nodes neue Eigenschaften beigebracht werden können ohne das sich ständig neu erfunden werden muss.

# Kommunikation

- Signal
	- inner events
		- das Objekt gibt Signale über innere Änderungen
		- andere können sich verbinden
	- Signal Relay
		- der Spawner signalisiert als Zentrale die Signale dessen gespawnten Objekte
	- Signal Singleton
		- Events in AutoLoad (als Singleton fungiert es als Event Bus)
- [Contract](https://docs.godotengine.org/en/stable/tutorials/physics/using_character_body_2d.html#bouncing-reflecting)
	- has_method & call method
	- alternativ schaut man in die Szene hinein und guckt, ob die gewünschte Komponente vorhanden ist und ruft dort die Methode direkt auf 
- [propagate_call](https://docs.godotengine.org/en/stable/classes/class_node.html#class-node-method-propagate-call)
	- Ruft die übergebene Methode aller Kinder und dessen Kinder auf
	- durch Composition durch Components kann so von außen die Methoden aufgerufen werden
	- Achtung: die Methoden werden bei ALLEN Kindern aufgerufen, nicht bei der ersten
- global var (eher kritisch)
	- AutoLoad ressourcen checken, ob diese variable vorhanden ist und ruft dann Methoden auf
- [Custom Resources](https://docs.godotengine.org/en/stable/tutorials/scripting/resources.html#creating-your-own-resources) als Singleton Datenspeicher und Events Bus System
	- diese sind immer zentral und können Daten halten
	- sind serialisierbar
	- können Signale und Methoden haben
- [Notification](https://docs.godotengine.org/en/stable/classes/class_object.html#class-object-method-notification)
	- jedes Object kann das aufnehmen
	- mittels Enums können dann Signale verschickt werden, man kann sich also das verdrahten sparen
	- [Tutorial](https://docs.godotengine.org/en/stable/tutorials/best_practices/godot_notifications.html)
- [Groups](https://docs.godotengine.org/en/stable/tutorials/scripting/groups.html#using-code)
	- call_group
		- calls method einer Gruppe (ähnlich propagate_call, nur für Gruppen)
	- ein Label für ein Element, womit es selektierbar ist
	- bedeutet auch, dass das Element schon weiß das es das braucht
- [get_configuration_warnings](https://docs.godotengine.org/en/4.2/tutorials/best_practices/scene_organization.html) (Suche auf der Seite danach)
	- wenn der zurückgegebene String nicht leer ist, generiert der Editor eine Warnung
	- [Node — Godot Engine (4.2) documentation in English](https://docs.godotengine.org/en/4.2/classes/class_node.html#class-node-private-method-get-configuration-warnings)
	- [@tools](https://docs.godotengine.org/en/stable/tutorials/plugins/running_code_in_the_editor.html#how-to-use-tool)
		- [is_editor_hint in godot::engine - Rust](https://godot-rust.github.io/docs/gdext/master/godot/engine/struct.Engine.html#method.is_editor_hint)
		- [Instancing scenes](https://docs.godotengine.org/en/stable/tutorials/plugins/running_code_in_the_editor.html#instancing-scenes)

- use free() instead of queue_free() whereever possible
- [Das wichtigste Dokument für godot-rust](https://godot-rust.github.io/docs/gdext/master/godot/prelude/derive.GodotClass.html)
- Following snipped makes it easier to manage component and their default values
```rust
fn init(base: Base<Node>) -> Self {
	let player_object = base
		.get_parent()
		.and_then(|p| p.try_cast::<CharacterBody2D>().ok());
```

# Design Patterns

- Inheritance
	- vor allem extends, um Spezialisierungen auszuschreiben
- Composition
	- Components stellen die generischen Eigenschaften dar, welche einem Node beigefügt werden können
	- das Node kann dann als Relay fungieren, mittels leichten Scripts (z.B. hittable)
- Parent Nodes are responsible for Child Nodes
	- get_node down, signal up
