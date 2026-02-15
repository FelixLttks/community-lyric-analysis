# Project Sheet: Spotify & Genius

Team-Mitglieder:

* Redacted: redacted
* Redacted: redacted
* Redacted: redacted

## Motivation / Szenario
In unserem Projekt beschäftigen wir uns mit der Analyse von Spotify Song Lyrics und den zugehörigen Song-Eigenschaften wie Popularität, Erscheinungsjahr, Danceability, Energy, Key, Loudness, Mode, Speechiness, Acousticness, Instrumentalness, Liveness, Valence und Tempo. Ziel ist es, ein Modell zu entwickeln, das auf Basis eines Songtextes diese Eigenschaften möglichst präzise vorhersagen kann.
Unsere Motivation liegt darin, zu erforschen, inwieweit sich emotionale, strukturelle oder stilistische Merkmale eines Liedtextes auf die wahrgenommenen oder gemessenen musikalischen Eigenschaften eines Songs übertragen lassen.

Als Anwendungsszenario stellen wir uns eine Funktion innerhalb von Musikstreaming-Diensten wie Spotify oder Apple Music vor, bei der Nutzern Songs mit ähnlichen Text- und Stimmungseigenschaften vorgeschlagen werden können – auch über Genregrenzen hinweg. Ein hypothetischer Kunde wäre somit ein Musikstreaming-Anbieter, der sein Empfehlungssystem verbessern möchte, indem nicht nur Klangmerkmale, sondern auch inhaltliche Aspekte der Lyrics in die Songauswahl einbezogen werden.

Wir wollen dabei folgende Fragestellungen beantworten:
* Welche Zusammenhänge bestehen zwischen lyrischen Merkmalen und musikalischen Eigenschaften?
* Können wir allein auf Basis eines Songtextes Eigenschaften wie Energy oder Danceability zuverlässig vorhersagen?
* Welche Textmuster oder Begriffe sind besonders stark mit bestimmten musikalischen Eigenschaften verknüpft?
* Ist es möglich Songtexte durch gegebene Metrik zu generieren?

## Daten

### Quelldatan

Für unser Projekt greifen wir auf zwei Datensätze von **Kaggle** zurück:  

#### **1. Genius Song Lyrics mit Sprachinformationen**  
**Quelle:** [Kaggle Dataset](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information)  
**Inhalt:**  
- Künstler (Artist)  
- Songtitel  
- **Songtexte** (Lyrics), erstellt von der Community  
- Tag

#### **2. Spotify 1 Million Tracks**  
**Quelle:** [Kaggle Dataset](https://www.kaggle.com/datasets/amitanshjoshi/spotify-1million-tracks)  
**Inhalt:**  
- Künstler (Artist)  
- Songtitel  
- **Tanzbarkeit (Danceability)**  
- **Genre**  
- **Jahr der Veröffentlichung**  
- Und viele weitere musikalische/akustische Merkmale

### **Datenfusion & Erweiterung**  
- Beide Datansetze werden durch das Vergleichen von **Songtitel & Artist** zusammengeführt
- Dadurch entsteht ein circa 360.000 Einträge großer Datensatz, welches sowohl Songtexte (Genius), als auch Audiofeatures (Spotify) besitzt.


## Vorgehen
1. Datenbereinigung und -verknüpfung
    - Normalisierung von Artist und Song Title in beiden Datensätzen
    - Bildung der Schnittmenge auf Basis von Artist und Song Title
2. Statistische Analyse
    - Analyse der Genreverteilung und Vergleich mit der Tag-Spalte von Genius
    - Untersuchung der Verteilung und Korrelation der Audiofeatures im Datensatz
    - Vergleich der Audiofeatures vor und nach der Zusammenführung der Rohdaten
    - Identifikation und Interpretation auffälliger Einträge
    - Zeitliche Verteilung der Datenpunkte (historische Entwicklung)
3. Analyse der Lyrics
    - Sprachverteilung und Worthäufigkeiten
    - Themenanalyse (Topic Modeling)
4. Spezifische Analysen für ML-Anwendungen
    - Detailanalysen abgestimmt auf nachfolgende Machine-Learning-Aufgaben
5. Regression
    - Untersuchung, ob sich Audio-Metriken wie ***Danceability*** aus gegebenen Lyrics vorhersagen lassen.
    - Evaluation der Performance eines BERT-Modells für diese Aufgabe.
6. Textgenerierung
    - Generierung von Lyrics auf Basis vorgegebener Audio-Metriken.
    - Bewertung der Qualität durch Rückführung in einen zuvor trainierten Klassifikator.
    - Ausprobieren verschiedner generativen Modelle (z.B N-Gram und RNN)
7. Interpretation der Ergebnisse

