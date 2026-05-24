# Systémová príručka

## 1. Účel systému

Systém slúži na detekciu deepfake videí pomocou multimodálneho prístupu, ktorý kombinuje vizuálne a zvukové príznaky. Výsledkom je binárna klasifikácia videa na reálne alebo manipulované.

## 2. Použité technológie

Pri implementácii boli použité najmä tieto technológie a knižnice:
- Python
- PyTorch
- torchvision
- librosa
- OpenCV
- scikit-learn
- matplotlib
- seaborn
- Jupyter Notebook / Google Colab

## 3. Vstupy systému

Vstupom systému sú videá z datasetu Celeb-DF v2.

Zo vstupných videí sa získavajú:
- tvárové snímky pre vizuálnu vetvu modelu
- MFCC príznaky zo zvukovej stopy pre zvukovú vetvu modelu

## 4. Architektúra riešenia

Navrhnutý systém pozostáva z troch hlavných častí:
1. vizuálna vetva založená na architektúre EfficientNet-B0
2. zvuková vetva založená na sieti LSTM
3. fúzna vrstva, ktorá kombinuje výstupy oboch modalít a realizuje finálnu klasifikáciu

## 5. Postup spracovania

Spracovanie dát a klasifikácia prebiehajú v týchto krokoch:
1. načítanie datasetu
2. extrakcia tvárí z vybraných snímok videa
3. extrakcia MFCC príznakov zo zvukovej stopy
4. vytvorenie dátovej množiny
5. rozdelenie dát na trénovaciu, validačnú a testovaciu časť
6. tréning multimodálneho modelu
7. vyhodnotenie modelu
8. analýza vysvetliteľnosti modelu

## 6. Súbory v repozitári

- `notebooks/Bakalarka_aktual_FINAL.ipynb`  
  Hlavný notebook obsahujúci kompletný tok spracovania od predspracovania dát cez tréning až po evaluáciu a explainability.

- `notebooks/exp4b_audio_clean.ipynb`  
  Notebook zameraný na vysvetliteľnosť zvukovej modality pomocou gradientovej saliency analýzy.

## 7. Spustenie systému

Odporúčané prostredie:
- Google Colab
- alebo lokálne Python prostredie s nainštalovanými knižnicami z `requirements.txt`

### Základný postup spustenia:
1. otvoriť notebook `Bakalarka_aktual_FINAL.ipynb`
2. nastaviť cesty k datasetu a výstupným súborom
3. spúšťať bunky zhora nadol
4. po natrénovaní modelu spustiť evaluačné a explainability bloky

## 8. Výstupy systému

Systém generuje:
- checkpointy modelu
- metriky klasifikácie
- confusion matrix
- ROC krivku
- výsledky threshold tuningu
- Grad-CAM vizualizácie
- audio saliency mapy

## 9. Obmedzenia systému

Systém bol testovaný na datasete Celeb-DF v2.

Výsledky sú ovplyvnené najmä:
- kvalitou detekcie tváre
- kvalitou zvukovej stopy
- zvoleným rozdelením dát
- tréningovými nastaveniami modelu

## 10. Poznámka

Táto systémová príručka bola vytvorená ako príloha k bakalárskej práci zameranej na multimodálnu detekciu deepfake videí.