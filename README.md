# Namu-darbas-nr.2</br></br>
**Naudoti Metodai ir Bibliotekos**</br>

Projektas naudoja šias pagrindines bibliotekas ir metodus:</br>

OpenCV (cv2) – Vaizdų apdorojimui ir vizualizacijai.</br>

PyTorch & Torchvision – Modelių įkėlimui ir giliojo mokymosi operacijoms.</br>

YOLOv8 (Ultralytics) – Objektų aptikimui vaizdo įrašuose.</br>

DeepSORT – Sekimo algoritmo įgyvendinimui.</br>

NumPy – Skaičiavimams ir matricų operacijoms.</br>

PIL (Pillow) – Vaizdų transformacijoms ir apdorojimui.</br>

Google Colab cv2_imshow – Vaizdų peržiūrai Colab aplinkoje.</br></br>

**Sistemos Veikimo Aprašymas**</br>

1. Duomenų paruošimas</br>

Sistema ieško vaizdo įrašų aplanke input_videos ir pavyzdinių automobilių nuotraukų aplanke car.</br>

Automobilio pavyzdinės nuotraukos yra įkeliamos ir iš jų išgaunamos savybės naudojant „MobileNetV2“ modelį.</br>

2. Vaizdo analizė</br>

Kiekvienas vaizdo įrašas yra įkeltas, ir iš jo kadrų išskiriamos transporto priemonės naudojant YOLOv8 modelį.</br>

Kiekviena aptikta transporto priemonė palyginama su pavyzdinių automobilių duomenų baze naudojant L2 atstumą ir kosinuso panašumo matą.</br>

3. Sekimas ir vizualizacija</br>

Aptiktos transporto priemonės sekamos naudojant DeepSORT algoritmą.</br>

Jei transporto priemonė atitinka pavyzdines nuotraukas, ji pažymima ir sekama per visą vaizdo įrašą.</br>

Apdorotas vaizdo įrašas išsaugomas output_videos aplanke.</br></br>

**Iškilusios Problemos ir Jų Sprendimai**</br>

Lėtas vaizdų analizės procesas → Naudotas mobilenet_v2 vietoj resnet18, nes tai greitesnis modelis su panašia klasifikavimo kokybe.</br>

Objektų aptikimo klaidos → Pridėtas papildomas filtravimas, kad būtų atmetamos neautomobilių klasės.</br>

Neteisingas sekimas → Pagerinta DeepSORT konfigūracija (max_age=50, max_iou_distance=0.4), kad būtų stabiliau sekami objektai.</br>
