# ÖPNV in Heidelberg: ein Zusammenspiel aus Wahrnehmung und Analyse

## Wie gut ist der ÖPNV wirklich? Warum Gefühl und Fahrplan nicht immer übereinstimmen

<div align="justify">
Wer in Heidelberg in der Innenstadt wohnt, hat meist eine Straßenbahnhaltestelle in der Nähe. In Stadtteilen wie Emmertsgrund oder Ziegelhausen sieht das anders aus: Der Bus fährt seltener, und zur nächsten Haltestelle ist es oft ein längerer Weg. Aber wie gut ist das Heidelberger ÖPNV-Netz wirklich? Und stimmt die gefühlte Wahrnehmung mit den Fahrplandaten überein?
</div>

<div align="justify">
<p>
Genau dieser Frage sind wir im Rahmen des Seminars <em>„GIS for Sustainable Cities and Climate Action"</em> nachgegangen. Unser Ziel war es, die ÖPNV-Angebotsqualität in Heidelberg sowohl aus der Perspektive der Bevölkerung als auch anhand objektiver Daten zu untersuchen und die Ergebnisse beider Ansätze miteinander zu vergleichen.
</p>
</div>

<div align="justify">
<p>
Hintergrund ist dabei ein dringend notwendiges Umdenken in der Mobilität zugunsten des Klimaschutzes: Der Verkehrssektor verursacht rund 22 % der CO₂-Emissionen in Deutschland, vor allem durch den motorisierten Individualverkehr (UBA 2025). Für die Klimaziele bis 2045 ist ein „Modal Shift“ zum ÖPNV erforderlich. Dafür muss der ÖPNV nicht nur gut sein, sondern auch so wahrgenommen werden (Batty et al. 2015; Lättman et al. 2016).
</p>
</div>

<div style="border-left: 4px solid #b8b9ba; padding: 0.5em 1em; margin: 1em 0;">
  <p style="margin: 0 0 0.75em 0;"><strong>Ziel des Projekts:</strong> Vergleich der subjektiv wahrgenommenen und der objektiv messbaren ÖPNV-Versorgungsqualität im gesamten Stadtgebiet Heidelberg.</p>
  <p style="margin: 0;"><strong>Untersuchungsgebiet:</strong> Heidelberg mit seinen 15 Stadtteilen und rund 154.000 Einwohnerinnen und Einwohnern, von der dicht bebauten Weststadt bis zu den Hanglagen am Odenwald.</p>
</div>

---

## Methodik

### Zwei Perspektiven auf dasselbe Netz

<div align="justify">
Um sowohl die gefühlte als auch die messbare Seite der ÖPNV-Qualität zu erfassen, haben wir zwei grundlegend verschiedene Methoden kombiniert.
</div>

#### 1. Die subjektive Seite: Passantenbefragung mit dem SketchMapTool

<div align="justify">
<p>Für die Befragung haben wir das <strong>SketchMapTool</strong> des Heidelberger Instituts für Geoinformationstechnologie (HeiGIT) genutzt. Das Tool erstellt automatisch einen auf OpenStreetMap basierenden Kartenausschnitt des Untersuchungsgebiets. Diese Karte haben wir ausgedruckt und zwischen dem 2. und 5. März 2026 insgesamt <strong>31 Passantinnen und Passanten</strong> an vier verschiedenen Standorten im Stadtgebiet vorgelegt.</p>

<p>Die Befragten wurden gebeten, auf der Karte einzuzeichnen, welche Orte in Heidelberg ihrer Meinung nach <span style="color:green;"><strong>gut</strong></span>, <span style="color:#b8a000;"><strong>mittelmäßig</strong></span> oder <span style="color:red;"><strong>schlecht</strong></span> durch den ÖPNV erschlossen sind. Die ausgefüllten Karten wurden anschließend digital erfasst, georeferenziert und in einem GIS zu einer gemeinsamen Karte zusammengeführt.</p>
</div>

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Befragungbeispiel_SketchMap.png" style="width: 75%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 1: Beispiel einer Befragung im SketchMapTool</em></div>
</div>




#### 2. Die objektive Seite: Fahrplandaten und der Güteklassenansatz

<div align="justify">
<p>Für die datengestützte Analyse haben wir <strong>GTFS-Daten</strong> (General Transit Feed Specification) verwendet, ein standardisiertes Format, das alle Fahrplandaten des öffentlichen Nahverkehrs enthält: Haltestellen, Linien, Abfahrtszeiten, Linienverläufe und weitere Informationen.</p>

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/GTFS_Skizze.png"  style="width: 72%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 2: Skizze GTFS-Daten</em></div>
</div>



<p>Auf dieser Grundlage haben wir den <strong>Güteklassenansatz</strong> angewendet, ein aus der Schweiz und Österreich bekanntes Verfahren zur Bewertung der ÖPNV-Erschließung. Der Ansatz läuft in zwei Schritten ab:</p>

<ul>
  <li>Zunächst wird jede Haltestelle anhand des besten verfügbaren Verkehrsmittels und der Taktfrequenz werktags zwischen 6 und 20 Uhr einer <strong>Haltestellenkategorie</strong> zugeordnet. Straßenbahn und S-Bahn werden dabei höher bewertet als der Busverkehr.</li>

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Ermittlung_HS_Kategorie.png" style="width: 72%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 3: Logik Haltestellenkategorie</em></div>
</div>

  <li>Im zweiten Schritt wird die fußläufige Erreichbarkeit einbezogen. Um jede Haltestelle werden Isochronen berechnet, also Zonen mit gleicher Gehzeit. Daraus ergibt sich für jeden Punkt der Stadt eine <strong>Güteklasse</strong> von "sehr gut"<span style="color:#00b050;"> (a)</span>  bis "unzureichend" <span style="color:#c00000;"> (f)</span>.</li>

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Ermittlung_GK_Isochronen.png" style="width: 72%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 4: Logik Güteklassenisochronen</em></div>
</div>
</ul>

<p>Beide Ergebnisse wurden abschließend mit einem Bevölkerungsraster verschnitten, um zu beziffern, wie viele Menschen in welcher Versorgungsqualität leben.</p>
</div>

---

## Ergebnisse

### Was die Befragten sagen und was die Daten zeigen

<div align="justify">
<p>Die Passantenbefragung zeigt ein klares räumliches Muster: Zentrale Stadtteile wie Altstadt, Bergheim, Weststadt, Neuenheim und Bahnstadt werden überwiegend als gut angebunden wahrgenommen, während periphere Lagen wie <strong>Emmertsgrund, Boxberg, Schlierbach und Ziegelhausen</strong> deutlich schlechter abschneiden. Grundsätzlich gilt: Mit zunehmender Entfernung vom Zentrum sinkt die wahrgenommene ÖPNV-Qualität. Besonders die Nähe zu Straßenbahnlinien spielt dabei eine wichtige Rolle.</p>

<p>In Zahlen: Laut Befragung leben <strong>34 % der Bevölkerung</strong> in Bereichen, die in der Befragung überwiegend als gut bewertet wurden, <strong>56 %</strong> in mittelmäßig und <strong>10 %</strong> in schlecht bewerteten Bereichen. Interessant ist dabei, dass Stadtteile wie Rohrbach, Wieblingen oder Handschuhsheim teils sehr unterschiedlich eingeschätzt wurden, was auf eine heterogene Alltagserfahrung innerhalb dieser Stadtteile hindeutet.</p>
</div>

<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Befragung_Ergebnisse_zusammen.jpg" style="width: 100%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 5: Ergebnisse der Passantenbefragung (zusammengefasste Eintragungen)</em></div>
</div>

<div align="justify">
<p>Die GIS-basierte Güteklassenanalyse bestätigt das räumliche Grundmuster, kommt aber zu quantitativ deutlich positiveren Ergebnissen. Die höchsten Güteklassen konzentrieren sich in den dicht besiedelten, zentralen Bereichen und entlang der Schienenachsen. Mit zunehmender Entfernung vom Zentrum nimmt die Angebotsqualität ab. Gleichzeitig zeigt sich, dass einzelne Haltestellen mit hoher Bedienfrequenz auch in peripheren Stadtteilen wie Boxberg oder Emmertsgrund lokal gute Bewertungen erzeugen.</p>

<p>In Zahlen: <strong>77 % der Bevölkerung</strong> leben in gut bis sehr gut erschlossenen Bereichen (Güteklassen a und b), weitere <strong>21 %</strong> in mittleren Klassen (c und d), und lediglich <strong>0,6 %</strong> in schwach erschlossenen Bereichen. Rund <strong>1,2 %</strong> der Bevölkerung sind nach den zugrunde gelegten Intervallen gar nicht mit ÖPNV versorgt.</p>
</div>


<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/morkra25/BlogPost_G4CA_OEPNV_in_Heidelberg_Krause/refs/heads/main/images/Karte_Gueteklassen.jpg" title="Güteklassen-Isochronen" alt="Karte der ÖPNV-Güteklassen in Heidelberg" style="width: 100%; display: block; margin: 0 auto;">
  <div style="font-size: 0.85em; margin-top: 0; margin-bottom: 1.2em;"><em>Abbildung 6: ÖPNV-Güteklassen in Heidelberg (Isochronen-basierte Analyse)</em></div>
</div>


---

## Fazit und Ausblick

<div align="justify">
<p>Beide Methoden kommen zum selben räumlichen Grundbefund: Zentrale Lagen sind besser versorgt als periphere, und die Straßenbahn spielt eine entscheidende Rolle für eine positive Bewertung. Die auffälligsten Unterschiede treten in den Randbereichen der Stadt auf, wo periphere Stadtteile in der subjektiven Wahrnehmung deutlich kritischer eingeschätzt werden als in der modellbasierten Analyse. Das spiegelt sich auch in den Zahlen wider: Während die Befragung nur 34 % der Bevölkerung in gut angebundenen Bereichen verortet, kommt die Güteklassenanalyse auf 77 %. Dieser Unterschied erklärt sich vor allem methodisch: Der Güteklassenansatz bewertet kleinräumig und haltestellenbezogen, während die Befragung eher den allgemeinen Eindruck ganzer Stadtbereiche und Linienräume einfängt, welche dann flächendeckend negativ bewertet werden. Hinzu kommt, dass die subjektive Wahrnehmung stark durch individuelle Alltagserfahrungen und Erwartungen geprägt ist.</p>

<p>Beide Ansätze haben Grenzen: Die Befragung ist mit 31 Personen und drei Bewertungsklassen nur eingeschränkt belastbar und anfällig für subjektive Verzerrungen. Die GTFS-Daten bilden dagegen nur das theoretische Fahrplanangebot ab, nicht Verspätungen, Ausfälle oder Ferienfahrpläne. Auch die gewählten Schwellenwerte bleiben teilweise willkürlich.</p>

<p>Was die Ergebnisse dennoch klar zeigen: Ein gut ausgebautes ÖPNV-Angebot allein reicht nicht aus, solange es nicht als solches wahrgenommen wird. Bei der Befragung haben wir viele genervte Kommentare zum Heidelberger ÖPNV gehört, was den Eindruck einer Lücke zwischen objektivem Angebot und subjektiver Erfahrung unterstreicht. Gerade in Außenstadtteilen sollte die Versorgung weiter verbessert werden, um den Modal Shift zu fördern.</p>

<p>Für weiterführende Untersuchungen wären größere und differenziertere Befragungsstichproben, stärker harmonisierte Klassifikationssysteme sowie Zeitreihenanalysen sinnvoll, um zu beobachten, wie sich Angebot und Wahrnehmung gemeinsam entwickeln.</p>
</div>

---

### *Literatur*

<p>BATTY, P., PALACIN, R., GONZÁLEZ-GIL, A. (2015): Challenges and opportunities in developing urban modal shift. In: Travel Behaviour and Society 2: 2, S. 109–123.</p>
<p>HEIDELBERG INSTITUTE FOR GEOINFORMATION TECHNOLOGY (HeiGIT) (2026): SketchMap Tool. https://sketch-map-tool.heigit.org/ (19.03.2026).</p>
<p>LÄTTMAN, K., FRIMAN, M.; OLSSON, L. E. (2016): Perceived Accessibility of Public Transport as a Potential Indicator of Social Inclusion. In: Social Inclusion 3: 4, S. 36–45.</p>
<p>PLAN4BETTER (2026): ÖV-Güteklassen. https://goat.plan4better.de/docs/de/toolbox/accessibility_indicators/oev_gueteklassen (19.03.2026).</p>
<p>UMWELTBUNDESAMT (UBA) (2025): Klimaschutz im Verkehr. https://www.umweltbundesamt.de/themen/verkehr/klimaschutz-im-verkehr#rolle (19.03.2026).</p>