# ÖPNV in Heidelberg – ein Zusammenspiel aus Wahrnehmung und Berechnungen

## Wie gut ist der Bus wirklich? Warum Gefühl und Fahrplan nicht immer übereinstimmen

<div align="justify">
Wer in Heidelberg im Neckartal wohnt, findet wenige Meter entfernt eine Straßenbahnhaltestelle. Wer am Emmertsgrund oder in Ziegelhausen lebt, kennt das gegenteilige Gefühl: der Bus kommt selten, und bis zur nächsten Haltestelle ist es ein Stück zu laufen. Doch wie gut ist das Heidelberger Nahverkehrsnetz eigentlich wirklich – und deckt sich das, was die Menschen empfinden, mit dem, was die Fahrplandaten zeigen?

Genau dieser Frage sind wir im Rahmen des Seminars <em>„GIS for Sustainable Cities and Climate Action"</em> an der Universität Heidelberg nachgegangen. Unser Ziel: die ÖPNV-Angebotsqualität in Heidelberg sowohl aus der Perspektive der Bevölkerung als auch anhand objektiver Daten zu untersuchen – und beides miteinander zu vergleichen.
</div>

<div align="justify">
<p>Der Hintergrund ist nicht trivial. Der Verkehrssektor verursacht in Deutschland rund 22 % aller CO₂-Emissionen, und der motorisierte Individualverkehr ist mit Abstand der größte Verursacher. Damit die Klimaziele bis 2045 erreicht werden können, braucht es eine echte Verkehrswende hin zum öffentlichen Nahverkehr – den sogenannten „Modal Shift". Doch dafür muss der ÖPNV nicht nur gut sein, sondern auch als gut wahrgenommen werden.</p>
</div>

<div style="border-left: 4px solid #b8b9ba; padding: 0.5em 1em; margin: 1em 0;">
  <p style="margin: 0 0 0.75em 0;"><strong>Ziel des Projekts:</strong> Vergleich der subjektiv wahrgenommenen und der objektiv messbaren ÖPNV-Versorgungsqualität im gesamten Stadtgebiet Heidelberg.</p>
  <p style="margin: 0;"><strong>Untersuchungsgebiet:</strong> Heidelberg mit seinen 15 Stadtteilen und rund 154.000 Einwohnerinnen und Einwohnern – von der dicht bebauten Weststadt bis zu den Hanglagen am Odenwald.</p>
</div>

---

## Methodik

### Zwei Perspektiven auf dasselbe Netz

<div align="justify">
Um sowohl die gefühlte als auch die messbare Seite der ÖPNV-Qualität zu erfassen, haben wir zwei grundlegend verschiedene Methoden kombiniert.
</div>

#### 1. Die subjektive Seite: Passantenbefragung mit dem SketchMapTool

<div align="justify">
<p>Für die Befragung haben wir das <strong>SketchMapTool</strong> des Heidelberg Instituts für Geoinformationstechnologie (HeiGIT) genutzt. Das Tool erstellt automatisch eine auf OpenStreetMap basierende Karte des Untersuchungsgebiets. Diese Karte haben wir ausgedruckt und zwischen dem 2. und 5. März 2026 insgesamt <strong>31 Passantinnen und Passanten</strong> an vier verschiedenen Standorten im Stadtgebiet vorgelegt.</p>

<p>Die Befragten wurden gebeten, auf der Karte einzuzeichnen, welche Orte in Heidelberg ihrer Meinung nach <span style="color:green;"><strong>gut</strong></span>, <span style="color:#b8a000;"><strong>mittelmäßig</strong></span> oder <span style="color:red;"><strong>schlecht</strong></span> durch den ÖPNV erschlossen sind. Die ausgefüllten Karten wurden anschließend digital erfasst, georeferenziert und in einem GIS zu einer gemeinsamen Rasterkarte zusammengeführt.</p>
</div>

#### 2. Die objektive Seite: Fahrplandaten und der Güteklassenansatz

<div align="justify">
<p>Für die datengestützte Analyse haben wir auf <strong>GTFS-Daten</strong> (General Transit Feed Specification) zurückgegriffen – ein standardisiertes Format, das alle Fahrplandaten des öffentlichen Nahverkehrs enthält: Haltestellen, Linien, Abfahrtszeiten und Linienverläufe.</p>

<p>Auf Grundlage dieser Daten haben wir den <strong>Güteklassenansatz</strong> angewendet, ein in der Schweiz und Österreich etabliertes Verfahren zur Bewertung der ÖPNV-Erschließung. Der Ansatz funktioniert in zwei Schritten:</p>

<ul>
  <li>Zunächst wird jede Haltestelle anhand des besten verfügbaren Verkehrsmittels und der Taktfrequenz werktags zwischen 6 und 20 Uhr in eine <strong>Haltestellenkategorie</strong> eingeteilt. Straßenbahn und S-Bahn werden dabei höher bewertet als Busse.</li>
  <li>Anschließend wird die fußläufige Erreichbarkeit berücksichtigt: Um jede Haltestelle werden Isochronen – also Zonen mit gleicher Gehzeit – berechnet. So entsteht für jeden Punkt der Stadt eine <strong>Güteklasse</strong> von „sehr gut" (a) bis „unzureichend" (f).</li>
</ul>

<p>Beide Ergebnisse wurden abschließend mit einem Bevölkerungsraster verschnitten, um zu beziffern, wie viele Menschen in welcher Versorgungsqualität leben.</p>
</div>

---

## Ergebnisse

### Was die Befragten sagen – und was die Daten zeigen

<div align="justify">
<p>Die Ergebnisse der Passantenbefragung zeichnen ein klares räumliches Bild: Die zentralen Stadtteile Heidelbergs – Altstadt, Bergheim, Weststadt, Neuenheim und Bahnstadt – werden von den Befragten überwiegend als gut angebunden wahrgenommen. Periphere Stadtteile wie <strong>Emmertsgrund, Boxberg, Schlierbach und Ziegelhausen</strong> schneiden hingegen deutlich schlechter ab. Je weiter ein Stadtteil vom Zentrum entfernt liegt, desto schlechter wird die ÖPNV-Versorgung empfunden.</p>
</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Befragung_Ergebnisse_zusammen.jpg" title="Ergebnisse der Passantenbefragung" alt="Karte der Passantenbefragungsergebnisse" width="100%">
<div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em; padding-top: 0;"><em>Abbildung 1: Ergebnisse der Passantenbefragung (zusammengefasste Eintragungen)</em></div>

<div align="justify">
<p>Die GIS-basierte Güteklassenanalyse bestätigt dieses räumliche Grundmuster – kommt aber zu quantitativ deutlich positiveren Ergebnissen. Während laut Befragung nur rund <strong>34 % der Bevölkerung</strong> das Gefühl hat, gut angebunden zu sein, zeigt die Güteklassenanalyse, dass objektiv betrachtet <strong>77 % der Bevölkerung</strong> in gut bis sehr gut erschlossenen Bereichen wohnt.</p>
</div>

<img src="BILD_GUETEKLASSEN_EINFÜGEN.png" title="Güteklassen-Isochronen" alt="Karte der ÖPNV-Güteklassen in Heidelberg" width="100%">
<div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em; padding-top: 0;"><em>Abbildung 2: ÖPNV-Güteklassen in Heidelberg (Isochronen-basierte Analyse)</em></div>

---

## Fazit und Ausblick

<div align="justify">
<p>Beide Methoden zeichnen dasselbe Grundbild: Zentrale Lagen werden besser versorgt, periphere schlechter – und die Straßenbahn spielt eine entscheidende Rolle für eine gute Bewertung. Doch der ausgeprägte quantitative Unterschied zwischen gefühlter und gemessener Versorgungsqualität ist bemerkenswert und zeigt: <strong>Guter ÖPNV allein reicht nicht aus</strong> – er muss auch als gut wahrgenommen werden, damit Menschen ihn tatsächlich nutzen.</p>

<p>Diese Lücke zwischen Wahrnehmung und Realität ist kein Randproblem. Gerade in den Außenstadtteilen, wo der Umstieg vom Auto auf Bus und Bahn besonders wichtig wäre, fühlen sich viele Menschen schlecht angebunden – selbst wenn die Datenlage ein differenzierteres Bild ergibt. Hier sollte die Stadtplanung ansetzen: nicht nur das Angebot verbessern, sondern auch die Kommunikation über das, was bereits vorhanden ist.</p>

<p>Für künftige Untersuchungen wären größere Befragungsstichproben, stärker harmonisierte Klassifikationssysteme sowie Zeitreihenanalysen sinnvoll – um zu beobachten, wie sich Angebot und Wahrnehmung gemeinsam entwickeln.</p>
</div>

---

### *Ausgewählte Literatur*

<p>BUNDESNETZAGENTUR / UMWELTBUNDESAMT (UBA) (2025): Klimaschutz im Verkehr. https://www.umweltbundesamt.de/themen/verkehr/klimaschutz-im-verkehr (19.03.2026).</p>
<p>BATTY, P., PALACIN, R., GONZÁLEZ-GIL, A. (2015): Challenges and opportunities in developing urban modal shift. In: Travel Behaviour and Society 2: 2, S. 109–123.</p>
<p>HEIDELBERG INSTITUTE FOR GEOINFORMATION TECHNOLOGY (HeiGIT) (2026): SketchMap Tool. https://sketch-map-tool.heigit.org/ (19.03.2026).</p>
<p>PLAN4BETTER (2026): ÖV-Güteklassen. https://goat.plan4better.de/docs/de/toolbox/accessibility_indicators/oev_gueteklassen (19.03.2026).</p>
