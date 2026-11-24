# Cas Kaggle · Estimació de la despesa mèdica facturada

Projecte d'Aprenentatge Computacional, APC GEI 2026–27. Versió de seguiment.

Estudiem si es pot estimar el cost individual facturat (`charges`) a partir de l'edat, l'IMC, el nombre de dependents, el sexe registrat, el tabaquisme i la regió. La font és **Medical Cost Personal Datasets**, publicada per mirichoi0218. El repositori inclou una còpia intacta d'`insurance.csv` (1.338 files, 7 columnes). Kaggle indica Open Database License per a la base i Database Contents License per als continguts. [Fitxa original i llicència a Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance).

El notebook presenta la distribució del cost, absències, correlacions i relacions per grup. S'elimina una fila duplicada exacta i s'agrupen els perfils de predictors que coincideixen perquè no apareguin a parts diferents. Les transformacions s'ajusten dins de cada fold.

| Model | MAE mitjà en validació creuada ($) |
|---|---:|
| Mediana | 8.236,19 |
| Ridge | 4.165,64 |
| KNN | 3.372,18 |
| Random Forest | 2.476,47 |
| Gradient Boosting | 2.478,99 |

Random Forest es va triar pel menor MAE en validació creuada. La diferència amb Gradient Boosting és petita en relació amb la dispersió entre folds. En test reservat, Random Forest obté MAE de 2.623,71 $, RMSE de 4.789,27 $ i R² de 0,853. El notebook inclou gràfiques, exemples d'errors i una auditoria descriptiva per grup. L'ús és acadèmic i caldria validació externa abans de considerar qualsevol aplicació real.

## Reproducció

Amb Python 3.12, des de la carpeta del repositori:

```sh
python -m venv .venv
# Activeu l'entorn virtual.
python -m pip install -r requirements.txt
python -m jupyter notebook insurance_apc.ipynb
```

Executeu totes les cel·les en ordre. A Colab, obriu el notebook i pugeu `insurance.csv` al directori de treball. La llavor és 42.

**Ús d'IA.** S'ha utilitzat OpenAI Codex per preparar el codi, les explicacions i les comprovacions de la versió de seguiment.
