# TP2- Jeux de mots / Synthèse et analyse spectrale d’une gamme de musique
#### Réalisé par: 
- Fatima  Ennassiri (Filière: Cyber Security)
- Marwa El Kamil(Filière: Artficial Intelligence)
### Encadré par:
- Mr Alae Ammour

### Objectifs:
- Comprendre comment manipuler un signal audio avec Matlab, en effectuant 
certaines opérations classiques sur un fichier audio d’une phrase enregistrée via 
un smartphone.
- Comprendre la notion des sons purs à travers la synthèse et l’analyse spectrale 
d’une gamme de musique.
### Introduction:
L'analyse spectrale d'un son repose sur la décomposition de Fourier, 
elle permet de connaître les fréquences des différentes fonctions 
sinusoïdales présentes dans un son (appelées harmoniques). Dans ce 
TP, nous allons travailler sur 2 exercices qui vont nous permettre 
de se familiariser avec des outils d’analyse spectrale dont Matlab 
dispose
 # Jeux de mots 
 
 
 # Synthèse et analyse spectrale d’une gamme de musique
 
 ### Synthèse d’une gamme de musique
Les notes de musique produites par un piano peuvent être synthétisées
approximativement numériquement. En effet, chaque note peut être considérée comme étant un son
pur produit par un signal sinusoïdal. La fréquence de la note La est par exemple de 440 Hz.
Créez un programme td2_1.mlx qui permet de jouer une gamme de musique. La
fréquence de chaque note est précisée dans le tableau ci-dessous

### 1- Créez un programme qui permet de jouer une gamme de musique. La fréquence
de chaque note est précisée dans le tableau ci-dessous. Chaque note aura une durée
de 1s. La durée de la gamme sera donc de 8s. La fréquence d’échantillonnage fe sera
fixée à 8192 Hz.


<img width="503" alt="Screenshot 2023-01-05 222737" src="https://user-images.githubusercontent.com/87017143/210883657-0d9dd201-ec22-4bca-a73b-885b5ae5d8f6.png">

<img width="400" alt="Screenshot 2023-01-05 223401" src="https://user-images.githubusercontent.com/87017143/210884317-42501d36-e106-47bd-ad66-730d96754998.png">

## Spectre de la gamme de musique

### 2- Utilisez l’outil graphique d’analyse de signaux signalAnalyzer pour visualiser le 
spectre de votre gamme. Observez les 8 fréquences contenues dans la gamme et 
vérifiez leur valeur numérique à l’aide des curseurs.

<img width="207" alt="Screenshot 2023-01-05 222736" src="https://user-images.githubusercontent.com/87017143/210885082-0d0e0af0-cb91-4d9a-86ec-434e83080906.png">

Matlab dispose à présent d’un outil graphique d’analyse de signaux signalAnalyzer
qui permet de visualiser les caractéristiques d’un signal dans les domaines temporel et
spectral.

<img width="556" alt="Screenshot 2023-01-05 224149" src="https://user-images.githubusercontent.com/87017143/210885567-be96ed51-27fe-461f-82b5-79f1aa31541c.png">


=>On observe 8 pics de fréquences caractérisant les 8 notes
formant notre gamme de musique .

### 3-Tracez le spectrogramme qui permet de visualiser le contenu fréquentiel du
### signal au cours du temps (comme le fait une partition de musique) .

<img width="372" alt="Screenshot 2023-01-05 224635" src="https://user-images.githubusercontent.com/87017143/210886418-98d7a822-0e62-4b94-9278-18394a1e83b8.png">


Le spectrogramme est un diagramme représentant le spectre d'un phénomène
périodique, associant à chaque fréquence une intensité ou une puissance1.

## Approximation du spectre d’un signal sinusoïdal à temps 
## continu par FFT

### 4- Le spectre d’un signal à temps continu peut être approché par transformée de
### Fourier discrète (TFD) ou sa version rapide (Fast Fourier Transform (FFT). Afficher le
### spectre de fréquence de la gamme musicale crée en échelle linéaire, puis avec une
### échelle en décibels.

<img width="305" alt="Screenshot 2023-01-05 225437" src="https://user-images.githubusercontent.com/87017143/210887415-8e7097d5-f996-4c32-a9b9-69f273ceea92.png">

<img width="527" alt="Screenshot 2023-01-05 230236" src="https://user-images.githubusercontent.com/87017143/210888992-27cee848-11da-4a9f-b893-d0e66296e4dd.png">

N=length(music);
tfd=fftshift(fft(music))
f=(-N/2:(N/2)-1)*(8192/N);
plot(f,abs(tfd));

Pour tracer le spectre de fréquence en dB, on utilise la fonction mag2db() qui utilise 
la formule suivante :

tfdb=mag2db(abs(tfd));
figure(2)
plot(f,tfdb);


On obtient la figure suivante :

<img width="450" alt="Screenshot 2023-01-05 231102" src="https://user-images.githubusercontent.com/87017143/210889922-b94e15c1-64dd-415e-a3f1-26be7862476c.png">

### Conclusion :
Dans ce TP nous avons pu comprendre comment manipuler un signal audio avec 
Matlab, en effectuant certaines opérations classiques sur un fichier audio d’une 
phrase enregistrée via un smartphone. Ainsi que de comprendre la notion des sons 
purs à travers la synthèse et l’analyse spectrale d’une gamme de musique
