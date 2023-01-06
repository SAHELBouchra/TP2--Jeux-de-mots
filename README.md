# TP2-Jeux-de-mots

## Synthèse et analyse spectrale d’une gamme de musique


<a name="retour"></a>
## Sommaire :
1. [ Objectifs. ](#objectif)
2. [ Jeux de mots.](#part1)
3. [ Synthèse et analyse spectrale d’une gamme de musique. ](#part2)

  3.a. [ Synthèse d’une gamme de musique. ](#part2-1)

  3.b. [ Spectre de la gamme de musique. ](#part2-2)

  3.c. [ Approximation du spectre d’un signal sinusoïdal à temps continu par      FFT. ](#part2-3)

<a name="objectif"></a>
### **1. Objectifs:**

 Comprendre comment manipuler un signal audio avec Matlab, en effectuant certaines opérations classiques sur un fichier audio d’une phrase enregistrée via un smartphone.

 Comprendre la notion des sons purs à travers la synthèse et l’analyse spectrale d’une gamme de musique.

#### Commentaires :
Il est à remarquer que ce TP traite en principe des signaux continus.Or, l'utilisation de Matlab suppose l'échantillonnage du signal. Il faudra donc être vigilant par rapport aux différences de traitement entre le temps continu et le temps discret.

#### Tracé des figures :
toutes les figures devront être tracées avec les axes et les légendes des axes appropriés.

#### Travail demandé :
 un script Matlab commenté contenant le travail réalisé et des commentaires sur ce que vous avez compris et pas compris, ou sur ce qui vous a semblé intéressant ou pas, bref tout commentaire pertinent sur le TP.
 
 <a name="part1"></a>
### **2. Jeux de mots:**

« phrase.wave » est un fichier audio enregistré à l’aide d’un smartphone, en prononçant lentement la phrase :
###### - « Rien ne sert de courir, il faut partir à point »

####  **1- Sauvegardez ce fichier sur votre répertoire de travail, puis charger-le dans MATLAB à l’aide de la commande « audioread ».**

```matlab
[a,f] = audioread("phrase.wave");
```
####  **2- Tracez le signal enregistré en fonction du temps, puis écoutez-le en utilisant la commande « sound ».**

```matlab
N=length(a)
ts=1/f
t=(0:N-1)*ts;
plot(t,a)
```
<img width="797" alt="tp2 1" src="https://user-images.githubusercontent.com/93081417/211015126-3c67c6fb-d891-408c-89e7-b35c679b23b8.png">

####  **3- Cette commande permet d’écouter la phrase à sa fréquence d’échantillonnage d’enregistrement. Ecoutez la phrase en modifiant la fréquence d’échantillonnage à double ou deux fois plus petite pour vous faire parler comme « Terminator » ou « Donald Duck ». En effet, modifier la fréquence d’échantillonnage revient à appliquer un changement d’échelle y(t) = x(at) en fonction de la valeur du facteur d’échelle, cela revient à opérer une compression ou une dilatation du spectre initial d’où la version plus grave ou plus aigüe du signal écouté.**
```matlab
sound(a,f*2) % Donald Duck (audio compressé) 

sound(a,f*0.5) %Terminator audio dilaté
```
####  **4- Tracez le signal en fonction des indices du vecteur x, puis essayez de repérer les indices de début et de fin de la phrase « Rien ne sert de ».**
 
 
 
 
 
 

