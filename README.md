# Multimodálna detekcia deepfake videí pomocou kombinácie metód strojového učenia a neurónových sietí

Tento repozitár obsahuje implementáciu a systémovú príručku k bakalárskej práci zameranej na multimodálnu detekciu deepfake videí.

## Štruktúra repozitára

- `notebooks/Bakalarka_aktual_FINAL.ipynb` – hlavný notebook obsahujúci predspracovanie dát, tréning modelu, evaluáciu, threshold tuning, Grad-CAM a audio saliency analýzu
- `notebooks/exp4b_audio_clean.ipynb` – samostatný notebook zameraný na vysvetliteľnosť zvukovej modality
- `docs/SYSTEMOVA_PRIRUCKA.md` – systémová príručka
- `requirements.txt` – zoznam použitých Python knižníc

## Téma práce

Bakalárska práca sa zaoberá multimodálnou detekciou deepfake videí s využitím:
- vizuálnej vetvy založenej na architektúre EfficientNet-B0
- zvukovej vetvy založenej na LSTM sieti spracúvajúcej MFCC príznaky
- fúznej vrstvy pre výslednú binárnu klasifikáciu videa na reálne alebo manipulované

## Dataset

Implementácia využíva dataset Celeb-DF v2.

## Hlavné experimenty

V práci boli realizované tieto experimenty:
- základný multimodálny experiment
- úprava tréningovej konfigurácie a optimalizácia modelu
- analýza vplyvu rozhodovacieho prahu
- vysvetliteľnosť vizuálnej modality pomocou Grad-CAM
- vysvetliteľnosť zvukovej modality pomocou gradientovej saliency analýzy nad MFCC vstupom

## Výstupy

Notebooky generujú:
- checkpointy natrénovaného modelu
- klasifikačné metriky
- confusion matrix
- ROC krivku
- výsledky threshold tuningu
- Grad-CAM vizualizácie
- audio saliency mapy

## Autor

Andrej Bujňák