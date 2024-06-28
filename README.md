# Erkennung KI-generierter Bilder – Welchen Einfluss hat die Promptlänge auf die Leistung von Detektoren?
Mit dem Aufkommen von öffentlich verfügbaren KI-basierten text-to-image-Systemen wie Stable Diffusion, DALL-E oder Midjourney wurde der Prozess, fotorealistische aber tatsächlich vollständig synthetische Bilder zu erstellen, weitgehend demokratisiert. Was eine Chance für Medienproduktionen sein kann, stellt auf der anderen Seite eine Gefahr durch Desinformation für die Öffentlichkeit dar.
Maschinelle Detektoren sowie menschliche Medienkompetenz können helfen, KI-generierte von echten Bildern zu unterscheiden und dieser Gefahr entgegenzuwirken. 

In dieser Arbeit soll überprüft werden, welchen Einfluss Nutzer von text-to-image-Sys\-te\-men über den Prompt auf die Erkennbarkeit der resultierenden Bilder haben. Im Speziellen wird überprüft, ob die Promptlänge einen Einfluss auf die Erkennungsleistung von maschinellen Detektoren und Menschen für die KI-generierten Bilder hat.
Dafür wurde der Datensatz COCOXGEN erstellt, der neben echten COCO-Fotos aus SDXL- und Fooocus-Bildern besteht, die mit Prompts zweier standardisierter Längen erstellt wurden. Es wurde eine Studie mit 200 menschlichen Probanden durchgeführt sowie ein maschineller Detektor auf den Bildern getestet.

Es konnte beobachtet werden, dass Bilder, die mit kurzen Prompts generiert wurden, signifikant schlechter von den Probanden erkannt wurden, als solche, die mit längeren Prompts generiert wurden. Auch der maschinelle Detektor erkannte long-prompted Bilder tendenziell leichter als short-prompted Bilder. Das Ergebnis zeigt, dass die Nutzer aktueller text-to-image-Systeme über die Formulierung des Prompts einen Einfluss darauf haben, wie leicht die Bilder als "KI-generiert" erkannt werden können.

Der Datensatz COCOXGEN kann hier heruntergeladen werden:
https://drive.google.com/file/d/1bYnWH0TajuTc2Iqec1bFZa-j5WkhCoSM

### Was dieses Repository enthält:
Es befinden sich zwei Jupyter-Notebooks in diesem Repository, in denen der Code für diese Arbeit entwickelt wurde:
1. ```main.ipynb```
   In diesem File ist der Code
   - zum Aufbau des Datensatzes COCOXGEN (Auswwahl der COCO-Bilder aus COCO-val2017 und Generierung der Bilder mit Fooocus und SDXL)
   - zur Auswahl der Studienbilder aus COCOXGEN
   - zum Test des maschinellen Detektors
   - zur Auswertung der Daten der Studienteilnehmer und des maschinellen Detektors
  zu finden
2. ```detection_model_output_visualization.ipynb```
   Dieses Notebook enthält den Code, mit dem die Heatmaps des Detektors für alle Testbilder erstellt wurden.

Um den maschinellen Detektor in ```main.ipynb``` testen und die Heatmaps in ```detection_model_output_visualization.ipynb``` erstellen zu können, müssen das Repository und die Gewichte des Detektors heruntergeladen und diesem Repository beigefügt werden.
Der Detektor entstammt der Arbeit von Corvi et al. (2023) und ist hier verfügbar: https://github.com/grip-unina/DMimageDetection/
Er sollte in einem Ordner mit dem Namem ```detection_model``` in diesem Repository abgelegt werden.
