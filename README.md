# ASL - Erkennung

https://bw-ki.de/

## Quellen

Deep Learning with Python by François Chollet

https://pytorch.org/docs/stable/nn.html

https://github.com/LeanManager/PyTorch_Image_Classifier

https://www.pyimagesearch.com/2014/08/18/skin-detection-step-step-example-using-python-opencv/

## Intro

Stellen sie sich vor, sie wollen sich mit einem Taubstummen unterhalten, aber beherrschen die Zeichensprache nicht. Unsere Applikation bietet ihnen eine real-time Lösung, die mit einer Bilderkennung Handzeichen in Buchstaben übersetzt. 

## Architektur unseres Neuronales Netzwerks

Die Basis unseres neuronalem Netzwerks bildet das Modell VGG16, das mit 14 Millionen Bildern vortrainiert ist und Features extrahieren kann. Diese Features nutzt unser eigens erstellter Klassifizierer um ein Eingabebild einem Buchstaben zuzuordnen. 

## Entwicklungsprozess

Angefangen haben damit die Bilder des Trainingsdatensatzes zu importieren und mit den richtigen Labels zu versehen und ein erstes Netzwerk zu trainieren. Dabei haben wir uns anfangs nur auf "A", "B" und "Nichts" beschränkt um das Problem klein zu halten und mögliche Probleme frühzeitig zu erkennen. Daraufhin haben wir das Netzwerk exportiert damit wir es in unserer Applikation als Prediction Machine nutzen können. Mit pygame Modul haben wir dann das Interface gebaut und die Webcam als live Input implementiert. Als alles funktionierte konnten wir zum ersten Mal unser Programm in der echten Welt testen und wir bemerkten schnell, dass die korrekte Klassifizierung niedrig war. Aufgrund dessen experimentierten wir mit Hauttonerkennung um Hintergrundstörungen zu entfernen. Doch es stellte sich schnell heraus, dass aufgrund der Schatten, die bei manchen Handzeichen entstehen, die Erkennung nur mittelmäßig funktionierte und das Ergebnis verschlechterte. Dafür erweiterten wir den Datensatz mit eigens aufgenommen Daten und verbesserten somit das Ergebnis erheblich. Dann nahmen wir immmer mehr Buchstaben in unser Netzwerk auf. Erst sechs, dann zwölf, dann 21 und letzendlich 29, aber je mehr Klassen hinzu kamen desto ungenauer wurde unser Ergebnis. 
Unser Plan ist, durch Ausnutzung \\ mehrerer Bilder in einem kleinen Zeitintervall die Vorhersage zu verbessern.

## Reflektion

Leider funktioniert unser NN letzendlich nicht so gut wie wir uns es anfangs ausgemalt haben. Solange wir uns nur auf wenige Zeichen beschränken funktioniert unsere Applikation genau so wie wir uns es auch vorgestellt haben. Bei fast 30 Klassen wird es aber unumgänglich sein deutlich mehr Trainingsdaten hinzuzufügen. Ein komplexeres Netzwerk (reinforcement learning) oder Fine Tuning des ganzen Modells um das Erebnis leicht zu verbessern. 

## Ausblick

Sobald das Programm auf dem Computer sehr zuverlässig funktioniert, planen wir eine mobile App zu bauen.
