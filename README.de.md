# Digivice-Gehäuse für Waveshare ESP32-S3-Touch-LCD-2.1

English: [README.md](README.md)

Ein druckbares Gehäuse im Stil des Digimon-Adventure-Digivice für das runde
Waveshare-Touch-Display (2,1″, 480 × 480) und einen LiPo-Akku. Alles wird gesteckt: kein
Kleber, keine Schrauben, kein Löten.

**Stand:** Version 1.1 (überarbeitet nach dem ersten Probedruck, v1.0). Ein Probedruck dieser
Version steht noch aus.

![Digivice Reveal](media/reveal.gif)

Als Video: [reveal.mp4](media/reveal.mp4). Zusammenbau Schritt für Schritt mit Bildern:
[ANLEITUNG.md](ANLEITUNG.md).

| Vorderseite | Explosion | Rückdeckel innen |
|---|---|---|
| ![Vorderseite](images/front.png) | ![Explosionsbild](images/exploded.png) | ![Rückdeckel innen](images/back_inside.png) |

Außenmaß ca. 113 × 100 × 27 mm mit Antenne, ohne Clip.

Dieses Repo enthält das Gehäuse: Druckdateien, Druckprofile, Anleitung und Animationen.
Firmware und CAD-Quellen gehören nicht dazu.

## Was du brauchst

| Teil | Menge | Quelle |
|---|---|---|
| Waveshare ESP32-S3-Touch-LCD-2.1 (flache Variante) | 1 | Amazon, ASIN B0DDPQSKJD |
| LiPo 803040, 3,7 V, 1000 mAh, 1,25-mm-Stecker, mit Schutzschaltung | 1 | Amazon, ASIN B0DPZNZ4D6 |
| PLA-Filament, alle Teile | ca. 100 g | |

Werkzeug: Seitenschneider oder Zange für die Stützen, eine Büroklammer für BOOT und RESET.

Der Akkustecker passt direkt in die Buchse `BAT` der Platine. Ein- und ausgeschaltet wird mit
einem gedruckten Schieber an der rechten Flanke, der den Schalter der Platine bedient. Ein
zusätzlicher Schalter ist nicht nötig.

## Druckdateien

| Datei | Inhalt | Druck |
|---|---|---|
| `stl/front_multicolor.stl` | Frontschale; Gehäuse, drei Knöpfe und Antenne als getrennte Körper (AMS) | Gesicht oben, normale Stützen nur auf der Druckplatte |
| `stl/front_single_color.stl` | dieselbe Front als ein Körper | wie oben |
| `stl/back_clip_slider.stl` | Rückdeckel, Gürtelclip und Ein-Aus-Schieber auf einer Platte | ohne Stützen (Clip: siehe unten) |
| `stl/single/back.stl`, `clip.stl`, `slider.stl` | dieselben Teile einzeln, zum Nachdrucken | ohne Stützen (Clip: siehe unten) |

Beide Platten passen auf 180 × 180 mm.

| Platte 1 | Platte 2 |
|---|---|
| ![Platte 1: Front](images/plate1.png) | ![Platte 2: Deckel, Clip, Schieber](images/plate2.png) |

## Drucken

- **Material:** PLA für alle Teile, auch für Deckel und Rasthaken.
- **Schichthöhe:** 0,16 mm, für scharfe Glyphen und gleichmäßige Haken.
- **Platte 1 (Front):** **normale** Stützen, „Nur auf Druckplatte“, Schwellenwinkel 30°.
  Keine Baumstützen: Sie wachsen von außen in die acht Rastfenster, und Reste dort blockieren
  später die Haken.
- **Platte 2 (Deckel, Clip, Schieber):** keine Stützen. Bambu Studio warnt hier trotzdem vor
  „schwebenden Regionen“. Die liegen am Clip: Sein Arm beginnt 6 mm über der Platte, und die
  zwei Zapfen stehen seitlich ab. Deckel und Schieber brauchen keine Stützen; zum Clip siehe
  „Einstellungen für den Clip“ unten.

Die Front braucht Stützen nur in der Kammer unter der Frontplatte, wo später das Displayglas
liegt, unter der Antenne und in der Hebelkerbe an der Unterkante.

### Profile für Bambu Studio (P1S)

In `bambu-p1s/` liegen fertige Profile für den Drucker „Bambu Lab P1S 0.4 nozzle“. In Bambu
Studio den P1S mit 0,4-mm-Düse auswählen und über **Datei > Importieren > Konfigurationen
importieren …** alle drei Dateien laden.

| Profil | Art | für | Einstellungen |
|---|---|---|---|
| `Digivice Front 0.16mm` | Prozess | Platte 1 | normale Stützen nur auf der Druckplatte, 30°, 3 Schnittstellenschichten; 3 Wände, 15 % Gyroid; erste Schicht 10 mm/s; Elefantenfuß 0,15 mm |
| `Digivice Back 0.16mm` | Prozess | Platte 2 | keine Stützen; 4 Wände, je 5 obere und untere Schichten, 30 % Gyroid; erste Schicht 10 mm/s, innere Wände 100 mm/s; Elefantenfuß 0,15 mm |
| `Digivice PLA Back` | Filament | Platte 2 | 230 °C, Lüfter 40–70 %, Zusatzlüfter 30 %: bessere Schichthaftung in den Rasthaken |

Die Front druckst du mit einem PLA-Systemprofil, z. B. „Bambu PLA Basic“ oder „Generic PLA“.
Beide Prozessprofile bauen auf „0.16mm High Quality @BBL X1C“ auf (0,16 mm Schichthöhe) und
nutzen Arachne-Wände mit „Präzise Wand“. Beide Platten slicen auf dem Standard-P1S ohne
Fehler; bei Platte 2 kommt die oben beschriebene Warnung zum Clip. Schätzung von
Bambu Studio 2.8:

| Platte | Profile | Zeit | Filament |
|---|---|---|---|
| 1 | `Digivice Front 0.16mm` + „Generic PLA“ | ca. 3 h 20 min | ca. 64 g |
| 2 | `Digivice Back 0.16mm` + `Digivice PLA Back` | ca. 1 h 50 min | ca. 33 g |

**Einstellungen für den Clip (optional):** Der Clip steht hochkant auf der Platte.
`back_clip_slider.stl` per Rechtsklick > **Teilen > Zu Objekten** in drei Objekte teilen, dann
dem Clip in der Objektliste per Rechtsklick Einstellungen hinzufügen:

- „Stützstrukturen aktivieren“ setzt Stützen unter den Arm und die zwei Zapfen. Die Warnung vor
  schwebenden Regionen verschwindet. Kostet etwa 5 Minuten und 0,5 g.
- „Randtyp“ mit „Nur äußerer Rand“ hilft, falls der Clip beim Druck kippelt.

**Anderer Drucker oder Slicer:** Die Tabelle nennt die wichtigsten Werte. Die JSON-Dateien in
`bambu-p1s/` enthalten jede Einstellung, die vom Grundprofil abweicht.

### Mehrfarbig mit AMS

1. `stl/front_multicolor.stl` in Bambu Studio oder OrcaSlicer laden.
2. Rechtsklick auf das Objekt, **Teilen > Zu Teilen**. Es entstehen genau fünf Teile:
   Gehäuse, drei Knöpfe, Antenne.
3. Jedem Teil in der Objektliste ein Filament zuweisen.

Die Knöpfe liegen in den obersten rund 12 Schichten, dort kostet der Farbwechsel wenig. Die
Antenne reicht über rund 37 Schichten in der Mitte der Front; eine eigene Antennenfarbe
bedeutet dort je zwei Farbwechsel pro Schicht. Wer Spülmaterial sparen will, gibt der Antenne
die Gehäusefarbe. Den Schieber gibt es auf Platte 2, er passt gut in der Knopffarbe.

## Bedienung

- **Ein/Aus:** Schieber an der rechten Flanke nach oben ist EIN, nach unten AUS. Der Griff
  sitzt in einer Mulde und hat eine Rippe für den Fingernagel.
- **Laden:** USB-C unten rechts (von vorn gesehen). Unten links liegt der UART-Port.
- **BOOT und RESET:** mit einer Büroklammer durch die zwei Nadellöcher oberhalb des Schiebers.
- **TF-Karte:** Schlitz oben links.
- **Öffnen:** siehe [ANLEITUNG.md](ANLEITUNG.md#öffnen). Die Haken aus PLA nicht mit Gewalt
  hebeln.

## Film

[digivice_film.mp4](media/digivice_film.mp4): 90 Sekunden, 1080p, mit Musik.

Music: “Go Cart” Kevin MacLeod (incompetech.com)\
Licensed under Creative Commons: By Attribution 4.0 License\
http://creativecommons.org/licenses/by/4.0/\
Ausschnitt, gekürzt und ein- und ausgeblendet, zum Bild synchronisiert.

Die Videodatei trägt dieselbe Angabe in ihren Metadaten.

## Lizenz und Quellen

- Die eigenen Inhalte dieses Projekts (Druckdateien, Profile, Bilder, Animationen, Film und
  Texte): [CC BY-NC-SA 4.0](LICENSE). Die Lizenz gilt nur für diese eigenen Inhalte und räumt
  keine Rechte an Figuren, Namen, Designs oder Modellen Dritter ein, siehe unten.
- Musik im Film: CC BY 4.0, siehe [Film](#film).
- Vorbilder für Form und Proportionen:
  [„Digivice from Digimon“](https://pinshape.com/items/43091-digivice-from-digimon) von Devin
  Gentner (CC BY-NC-SA 4.0) und
  [„digivice removable back“](https://www.thingiverse.com/thing:2754641) von jpek13 (CC BY-SA).
  Keine Dateien oder Geometrie daraus übernommen; das Gehäuse ist von Grund auf in OpenSCAD
  modelliert.
- Platine: Maße aus dem STEP-Modell und der Maßzeichnung des Waveshare ESP32-S3-Touch-LCD-2.1.
  Die Platine in den Renderbildern, Animationen und im Film beruht auf diesem STEP-Modell
  (© Waveshare, nicht Teil dieser Lizenz).
- Digivice und Digimon sind Marken von Bandai. Digimon und seine Figuren, auch Agumon:
  © Akiyoshi Hongo, Toei Animation. Die Pixelfigur auf dem Display in den Animationen und im
  Film ist Fan-Art. Fanprojekt, nicht mit Bandai oder Toei Animation verbunden und nicht von
  ihnen unterstützt.
