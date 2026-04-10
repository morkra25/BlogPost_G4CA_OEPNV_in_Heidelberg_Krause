# ÖPNV in Heidelberg: ein Zusammenspiel aus Wahrnehmung und Berechnungen

## Wie gut ist der Bus wirklich? Warum Gefühl und Fahrplan nicht immer übereinstimmen

<div align="justify">
Wer in Heidelberg in der Innenstadt wohnt, hat meist eine Straßenbahnhaltestelle in unmittelbarer Nähe. Wer dagegen am Emmertsgrund oder in Ziegelhausen lebt, kennt eine andere Realität: Der Bus kommt selten, und bis zur nächsten Haltestelle ist es ein gutes Stück zu laufen. Aber wie gut ist das Heidelberger ÖPNV-Netz insgesamt eigentlich? Und stimmt das, was die Menschen gefühlt wahrnehmen, mit dem überein, was die Fahrplandaten tatsächlich zeigen?

Genau dieser Frage sind wir im Rahmen des Seminars <em>„GIS for Sustainable Cities and Climate Action"</em> nachgegangen. Unser Ziel war es, die ÖPNV-Angebotsqualität in Heidelberg sowohl aus der Perspektive der Bevölkerung als auch anhand objektiver Daten zu untersuchen und die Ergebnisse beider Ansätze miteinander zu vergleichen.
</div>

<div align="justify">
<p>Der Hintergrund ist dabei nicht trivial. Der Verkehrssektor verursacht in Deutschland rund 22 % aller CO2-Emissionen, und der motorisierte Individualverkehr trägt den größten Teil davon bei. Um die deutschen Klimaziele bis 2045 noch zu erreichen, braucht es eine Verkehrswende hin zum öffentlichen Nahverkehr, den sogenannten „Modal Shift". Damit das gelingt, muss der ÖPNV aber nicht nur objektiv gut sein, sondern auch als solcher wahrgenommen werden (hier QUELLE!)</p>
</div>

<div style="border-left: 4px solid #b8b9ba; padding: 0.5em 1em; margin: 1em 0;">
  <p style="margin: 0 0 0.75em 0;"><strong>Ziel des Projekts:</strong> Vergleich der subjektiv wahrgenommenen und der objektiv messbaren ÖPNV-Versorgungsqualität im gesamten Stadtgebiet Heidelberg.</p>
  <p style="margin: 0;"><strong>Untersuchungsgebiet:</strong> Heidelberg mit seinen 15 Stadtteilen und rund 154.000 Einwohnerinnen und Einwohnern, von der dicht bebauten Weststadt bis zu den Hanglagen am Odenwald.</p>
</div>


**BATTY noch nennen!!!!!**


---

## Methodik

### Zwei Perspektiven auf dasselbe Netz

<div align="justify">
Um sowohl die gefühlte als auch die messbare Seite der ÖPNV-Qualität zu erfassen, haben wir zwei grundlegend verschiedene Methoden kombiniert.
</div>

#### 1. Die subjektive Seite: Passantenbefragung mit dem SketchMapTool

<div align="justify">
<p>Für die Befragung haben wir das <strong>SketchMapTool</strong> des Heidelberger Instituts für Geoinformationstechnologie (HeiGIT) genutzt. Das Tool erstellt automatisch einen auf OpenStreetMap basierenden Kartenausschnitt des Untersuchungsgebiets. Diese Karte haben wir ausgedruckt und zwischen dem 2. und 5. März 2026 insgesamt <strong>31 Passantinnen und Passanten</strong> an vier verschiedenen Standorten im Stadtgebiet vorgelegt.</p>

<p>Die Befragten wurden gebeten, auf der Karte einzuzeichnen, welche Orte in Heidelberg ihrer Meinung nach <span style="color:green;"><strong>gut</strong></span>, <span style="color:#b8a000;"><strong>mittelmäßig</strong></span> oder <span style="color:red;"><strong>schlecht</strong></span> durch den ÖPNV erschlossen sind. Die ausgefüllten Karten wurden anschließend digital erfasst, georeferenziert und in einem GIS zu einer gemeinsamen Rasterkarte zusammengeführt.</p>
</div>

** HIER BILD VON SKETCHMAP **


#### 2. Die objektive Seite: Fahrplandaten und der Güteklassenansatz

<div align="justify">
<p>Für die datengestützte Analyse haben wir <strong>GTFS-Daten</strong> (General Transit Feed Specification) verwendet, ein standardisiertes Format, das alle Fahrplandaten des öffentlichen Nahverkehrs enthält: Haltestellen, Linien, Abfahrtszeiten und Linienverläufe.</p>

<p>Auf dieser Grundlage haben wir den <strong>Güteklassenansatz</strong> angewendet, ein aus der Schweiz und Österreich bekanntes Verfahren zur Bewertung der ÖPNV-Erschließung. Der Ansatz läuft in zwei Schritten ab:</p>

<ul>
  <li>Zunächst wird jede Haltestelle anhand des besten verfügbaren Verkehrsmittels und der Taktfrequenz werktags zwischen 6 und 20 Uhr einer <strong>Haltestellenkategorie</strong> zugeordnet. Straßenbahn und S-Bahn werden dabei höher bewertet als der Busverkehr.</li>
  <li>Im zweiten Schritt wird die fußläufige Erreichbarkeit einbezogen. Um jede Haltestelle werden Isochronen berechnet, also Zonen mit gleicher Gehzeit. Daraus ergibt sich für jeden Punkt der Stadt eine <strong>Güteklasse</strong> von "sehr gut" (a) bis "unzureichend" (f).</li>
</ul>

<p>Beide Ergebnisse wurden abschließend mit einem Bevölkerungsraster verschnitten, um zu beziffern, wie viele Menschen in welcher Versorgungsqualität leben.</p>
</div>


<p align="center">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/GTFS_Skizze.png" width="45%" />
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Ermittlung_GK_Isochronen.png" width="45%" />
</p>


**HIER KLEINE ABBILDUNGEN VON DATENBESCHREIBUNG und Methoden!!!**

---

## Ergebnisse

### Was die Befragten sagen und was die Daten zeigen

<div align="justify">
<p>Die Passantenbefragung ergibt ein räumlich recht eindeutiges Bild. Die zentralen Stadtteile Heidelbergs, also Altstadt, Bergheim, Weststadt, Neuenheim und Bahnstadt, werden von den Befragten überwiegend als gut angebunden wahrgenommen. Periphere Stadtteile wie <strong>Emmertsgrund, Boxberg, Schlierbach und Ziegelhausen</strong> schneiden hingegen deutlich schlechter ab. Grundsätzlich gilt: Je weiter ein Stadtteil vom Zentrum entfernt liegt, desto schlechter wird die ÖPNV-Versorgung empfunden.</p>
</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Befragung_Ergebnisse_zusammen.jpg" title="Ergebnisse der Passantenbefragung" alt="Karte der Passantenbefragungsergebnisse" width="850px">
<div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em; padding-top: 0;"><em>Abbildung 1: Ergebnisse der Passantenbefragung (zusammengefasste Eintragungen)</em></div>

<div align="justify">
<p>Die GIS-basierte Güteklassenanalyse bestätigt das räumliche Grundmuster, kommt aber zu quantitativ deutlich positiveren Ergebnissen. Laut Befragung haben nur rund <strong>34 % der Bevölkerung</strong> das Gefühl, gut angebunden zu sein. Die Güteklassenanalyse zeigt dagegen, dass objektiv betrachtet <strong>77 % der Bevölkerung</strong> in gut bis sehr gut erschlossenen Bereichen wohnen.</p>
</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Karte_Gueteklassen.jpg" title="Güteklassen-Isochronen" alt="Karte der ÖPNV-Güteklassen in Heidelberg" width="105%">
<div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em; padding-top: 0;"><em>Abbildung 2: ÖPNV-Güteklassen in Heidelberg (Isochronen-basierte Analyse)</em></div>

---

## Fazit und Ausblick

<div align="justify">
<p>Beide Methoden kommen zum selben räumlichen Grundbefund: Zentrale Lagen sind besser versorgt als periphere, und die Straßenbahn spielt eine wichtige Rolle für eine positive Bewertung. Der deutliche zahlenmäßige Unterschied zwischen gefühlter und gemessener Versorgungsqualität ist dabei interessant. Er zeigt, dass ein gut ausgebautes ÖPNV-Angebot allein nicht ausreicht, solange es von den Menschen nicht entsprechend wahrgenommen wird.</p>

<p>Besonders in den Außenstadtteilen, wo ein Umstieg vom Auto auf Bus und Bahn besonders relevant wäre, fühlen sich viele schlecht angebunden, auch wenn die Datenlage ein differenzierteres Bild ergibt. Nicht zuletzt haben wir bei der Befragung viele genervte Kommentare zum Heidelberger ÖPNV gehört, was diesen Eindruck nochmal unterstreicht. Die Stadtplanung sollte daher nicht nur das Angebot weiterentwickeln, sondern auch überlegen, wie sie besser darüber informiert, was bereits vorhanden ist.</p>

<p>Für weiterführende Untersuchungen wären größere Befragungsstichproben, besser aufeinander abgestimmte Klassifikationssysteme und Zeitreihenanalysen sinnvoll, um zu beobachten, wie sich Angebot und Wahrnehmung über die Zeit gemeinsam entwickeln.</p>
</div>

---

### *Literatur*

<p>BUNDESNETZAGENTUR / UMWELTBUNDESAMT (UBA) (2025): Klimaschutz im Verkehr. https://www.umweltbundesamt.de/themen/verkehr/klimaschutz-im-verkehr (19.03.2026).</p>
<p>BATTY, P., PALACIN, R., GONZÁLEZ-GIL, A. (2015): Challenges and opportunities in developing urban modal shift. In: Travel Behaviour and Society 2: 2, S. 109–123.</p>
<p>HEIDELBERG INSTITUTE FOR GEOINFORMATION TECHNOLOGY (HeiGIT) (2026): SketchMap Tool. https://sketch-map-tool.heigit.org/ (19.03.2026).</p>
<p>PLAN4BETTER (2026): ÖV-Güteklassen. https://goat.plan4better.de/docs/de/toolbox/accessibility_indicators/oev_gueteklassen (19.03.2026).</p>
