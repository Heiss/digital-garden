---
{"dg-publish":true,"permalink":"/3-resources/self-hosted/matrix-support-page/","created":"2026-03-28T19:04:09.610+01:00","updated":"2026-03-28T20:04:03.966+01:00"}
---


Die [netzmuffel.de](http://matrix.netzmuffel.de) Instanz ist nur für die private Nutzung und nur für Freunde und die Familie gedacht. Für andere User ist die Instanz nicht zugreifbar und durch eine SSO-Plattform, sowie weiteren Sichterheitsmechanismen, geschützt.

## Zugang erhalten

Damit ich ein Konto für Dich anlegen kann, brauche ich eine E-Mailadresse von Dir, welche ich hinterlegen kann. Dann erhältst Du per Mail einen Link, womit Du dich auf meiner Plattform Authentik anmelden kannst. Diese wird verwendet, um für sämtliche Dienste von mir die Konten und Zugänge zu verwalten. Damit ist es Dir möglich auch die anderen Dienste von mir zu verwenden.
## Installation

### Android

Auf dem Handy die App "Element Classic" ([https://play.google.com/store/apps/details?id=im.vector.app](https://play.google.com/store/apps/details?id=im.vector.app)) herunterladen.

> ​Wichtig ist, dass man die Classic Variante installiert, denn wir verwenden eine zentrale Plattform für die Authentifizierung, welche mit der neuen Variante (Element X) noch nicht unterstützt wird.​

![3 Resources/Self-Hosted/qrcode-1.png](/img/user/3%20Resources/Self-Hosted/qrcode-1.png)

### PC

Auf dem PC kann die App "Element X" ([https://element.io/de/download](https://element.io/de/download)) verwendet werden, da es hier die Funktionalität mit der zentralen Konto-Plattform bereits gibt. Achtung: Nicht die Android-App von dort laden!

## Konfiguration

### tl;dr

- Server: [netzmuffel.de](http://netzmuffel.de)
- Login via authentik als SSO-Provider

### Beschreibung

Nach der Installation kommt die Konfiguration der Anwendung. Egal ob PC oder Android, die App muss nun ausgeführt werden auf dem Gerät. Im ersten Bildschirm wird man gefragt, ob man sich einloggen oder registrieren möchte.

​Wir drücken auf "einloggen" / "Sign in" und geben dann den Server [netzmuffel.de](http://matrix.netzmuffel.de) an. (Es ist möglich, dass zuerst der Server "matrix.org" als Standard angegeben ist. Man muss dann auf Bearbeiten / "Edit" drücken, um den Server zu bearbeiten.)

Sobald der Server geändert ist, steht nun ein Button da, welcher auf den Service "Authentik" hinweist: "Continue with authentik". Dort drücken wir drauf. Der Browser öffnet sich und schickt einen zum Service [auth.netzmuffel.de](http://auth.netzmuffel.de) wo wir uns nun einloggen können mit den selbst eingegeben Daten - falls Du bereits auf der Plattform eingeloggt bist, wirst Du auch bei Matrix direkt eingeloggt und nichts von der Plattform sehen.

> Du hast nur Credentials, wenn ich Dich eingeladen habe! Alle Konten sind per Hand eingepflegt. Wenn ich das gemacht habe, erhälst Du eine Mail von dem System, wo Du deine eigenen Credentials eingeben kannst, die du jetzt beim Matrix Client brauchst.

Nachdem Du Dich in Authentik eingeloggt hast, wirst Du automatisch wieder an deine Matrix Anwendung weitergeleitet und eingeloggt. Vielleicht fragt dein Browser noch, dass Daten an deine Anwendung weitergeschickt werden soll: Akzeptiere dies. Nun wird dein Matrix Client Dich eingeloggen und Du bist drin.

Mir kannst Du direkt schreiben via [@physicx:netzmuffel.de](https://matrix.to/#/@physicx:netzmuffel.de) auf dem Server.

Denselben Prozess musst Du nun auch auf anderen Geräten machen, um dich überall einzuloggen. Um verschlüsselte Nachrichten auf allen Geräten lesen zu können, musst Du deine Geräten gegeneinander verifizieren. Die Clients fragen dich und zeigen Dir, wie du das machst.
