# **Comparaison de différents micro MEMS** 

## Nous allons matcher 3 micros MEMS afin de voir le quel d'entre eux est le meilleur pour notre cas d'utilisation.

### 1. Les micros 
Voici la liste des micros que nous mettons en concurence : 
- Infineon IM69D128SV01
- Infineon IM70D122V01
- Harman E999
- ST MP34DT06J 

Les datasheets de chaque micro : 

[IM69](https://www.infineon.com/dgdl/Infineon-IM69D128S-DataSheet-v01_00-EN.pdf?fileId=8ac78c8c85c5e5aa0185dfa527036dad)

[IM70](https://www.infineon.com/dgdl/Infineon-IM70D122-DataSheet-v01_00-EN.pdf?fileId=8ac78c8c85c5e5aa0185dfa52e616db0)

[Harman] sur l'ordinateur 

[ST] sur l'ordinateur


### 2. Quels sont les critères importnants ?

 Dans notre cas, Les paramètres que l'on va comparer sur chaque micro pour notre étude sont : 
 - La consomation (en µA), le but étant que les micros ne soient pas trop énergivores. 
 - La sensibilité (en dBFS), il faut trouver le juste milieu entre une sensibilté haute mais sans trop l'être car le taux de distortion est plus élevé dans des de hauts volumes de sortie et la range est plus réduite avec une haute sensibilité. 
 - Rapport signal-bruit (en dB(A)), il faut avoir la valeur en dB, sur la pondération A, la plus élevé possible.
 - La réponse en fréquence (en Hz), la réponse en fréquence du micro doit être la plus plate possible pour restituer un signal au plus proche possible de la réalité. 
 - La dimension (en mm), il faut que le micro soit au meilleur format pour facilité son intégration.

### 3. Benchmark 

| Modèle micro | Consomation (en µA) | Sensibilité (en dBFS) | SNR (en dB(A)) | Réponse en fréquence (en Hz) | Dimensions (en mm) |
| :----------: | :-----------------: | :-------------------: | :------------: | :--------------------------: | :----------------: |
| IM 69        | 180 à 520 suivant la clock | -37 | 66 à 69 | voir le PDF de la datasheet | 2,65 * 3,5 |
| IM70         | 280 à 920 suivant la clock | -26 | 67 à 70 | voir le PDF de la datasheet | 2,65 * 3,5 |
| Harman       | <800 en 1.8V, Fclk  2.4MHz | -34 | 65 | voir le PDF de la datasheet | 2,65 * 3,5 |
| ST           | 650 en normal mode | -26 | 64 |  voir le PDF de la datasheet | 3 * 4 |

## IM69
### *advantages* 
 - Plus faible consomation par rapport aux autres. 
 - Utilisé dans les casques et écouteurs (Active Noise Cancellation).
 - Longue autonomie. 
 - Robuste dans un petit pakage.

## IM70 
### *advantages* 
- Une sensibilité plus élevée que les autres. 
- Meilleur rapport signal bruit. 
- Même form factor que le IM69. 
- Parfaitement adapté pour de la capture audio pour les pc, tablettes, etc ... 
- Mois de distortion que le IM69 sur une amplitude de 110 dBSPL 

## ST  
### *advantages* 
- Utiliser dans la reconnaissance vocale 
- Une même sensibilité que le IM70 mais avec un plus faible rapport signal bruit 
- Meilleur pourcentage de distorsion sur les hauts volumes 

### 4. Matrice de décision 

Le but de cette matrice est de définir de manière mathématique le meilleur micro en notant de 1 à 4 le niveau de puissancede chaque paramètre en les matchants entre eux. 

| Consomation                              | 
| :---------------------------------------:| 
|              | IM69 | IM70 | Harman | ST |  
| IM 69        | / | 3 | 3 | 2 | 
| IM70         | 0 | / | 0 | 0 | 
| Harman       | 0 | 2 | / | 1 | 
| ST           | 2 | 2 | 2 | / |   

| Sensibilité                              | 
| :---------------------------------------:| 
|              | IM69 | IM70 | Harman | ST |  
| IM 69        | / | 0 | 0 | 0 | 
| IM70         | 3 | / | 2 | 0 | 
| Harman       | 1 | 0 | / | 0 | 
| ST           | 3 | 0 | 2 | / | 

| SNR                                      | 
| :---------------------------------------:| 
|              | IM69 | IM70 | Harman | ST |  
| IM 69        | / | 0 | 2 | 2 | 
| IM70         | 1 | / | 2 | 3 | 
| Harman       | 0 | 0 | / | 1 | 
| ST           | 0 | 0 | 0 | / | 

Au niveau des réponses en fréquences, elles se ressemblent toutes. 

Au niveau des dimensions, seul le micro de ST est plus grand que les autres donc, les autres prennent 1 point. 

Total : 
IM69 = 12
IM70 = 11
Harman = 5 
ST = 11

D'après les totaux calculé, le IM69 a le plus de points sur l'ensemble des autres micros. 
