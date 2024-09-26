Was ist RAG ?

RAG steht für Retrieval-Augmented Generation und bezieht sich auf eine Technik in der Künstlichen Intelligenz, die die Stärken von Informationsabruf und Textgenerierung kombiniert. 
Hier sind die wesentlichen Punkte zu RAG:
Abruf von Informationen: Wenn du eine Frage stellst, sucht das RAG-Modell zuerst in einer externen Datenbank oder Wissensquelle nach relevanten Informationen, ähnlich wie eine Suchmaschine.

Kombination von Daten: Es holt die gefundenen Informationen und kombiniert sie mit seinem eigenen Wissen, das es während des Trainings gelernt hat.

Generierung einer Antwort: Schließlich erstellt das Modell eine Antwort, die sowohl die abgerufenen Informationen als auch seine eigenen Kenntnisse nutzt, 
um eine präzise und kontextuelle Antwort zu liefern.

Im Wesentlichen nutzt RAG die besten Teile von Wissen abrufen und Text generieren, um informierte Antworten zu geben.
![Alt-Text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRq3hEGHDF0zMPBdOQZk32oGUW0HLGyxZdXPQ&s)

Was ist ein Large Language Model ?

Ein Large Language Model (LLM) ist ein KI-System, das durch das Training mit großen Mengen an Text Sprache verstehen und erzeugen kann. Es nutzt Embedding-Modelles, um Wörter in numerische Vektoren umzuwandeln, die deren Bedeutung im Kontext erfassen. Mithilfe neuronaler Netzwerke verarbeitet es diese Vektoren, lernt sprachliche Strukturen und generiert darauf basierend Antworten, Texte oder neue Informationen.

<img src="https://www.wisecube.ai/wp-content/uploads/2023/05/Featured-Blog-Image-A-Comprehensive-Overview-of-Large-Language-Models-1024x768.jpg" alt="Alt-Text" width="400">

RAG Architektur

Der *User* stellt eine Frage (Frage...).
Diese Frage wird an ein Large Language Model (LLM) weitergeleitet.
Parallel dazu wird eine Indexierung der relevanten Dokumente durchgeführt:
   - Die Dokumente werden in kleinere *Chunks* aufgeteilt.
   - Ein *Embedding-Modell* erstellt für jeden Chunk eine numerische Darstellung (Embeddings), zum Beispiel in Form eines Vektors wie [0.3, 0.1, 0.7].
Die Embeddings werden dann durch einen *Vector Store* gespeichert.
Basierend auf der ursprünglichen Frage des Nutzers, wird eine Suche nach den relevanten Dokumenten durchgeführt.
Die relevanten Dokumente werden an das LLM zurückgegeben, welches die Antwort darauf vorbereitet.
Schließlich erhält der User eine Antwort, die auf den relevanten Dokumenten basiert.

![RAG Architektur Grafik] (https://github.com/patricschmidtf/topfact-AG-API-Test/blob/3e22fa4713c51acdd4a368fdf869b3096fc2cf44/Diagramm.png)
