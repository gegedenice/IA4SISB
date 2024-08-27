---
description: Fondements (théoriques) de l’IA
---

# Bases théorique : IA classique, IA générative, AGI

Les algorithmes d’IA au sens large reposent sur des fondements statistiques du siècle dernier (voire avant) et sont utilisés couramment dans des systèmes informatiques depuis une quinzaine d’années.

Ceux relevant de que l’on appelle désormais “IA classique” ou “IA de 1ère génération” se divisent en deux branches

* Le Machine Learning : modèles d’IA adaptés aux données “simples”, structurées et linéaires
* Le Deep Learning (réseaux de neurones artificiels) : modèles d’IA adaptés aux données complexes, non structurées et non linéaires (images, audio…)\


L’IA générative se réfère à des modèles d’un type nouveau, basé sur des réseaux de neurones spécifiques et dont les processus calculatoires sont calibrés pour apprendre le langage naturel à partir de corpus textuels de très grande dimension.

La “compréhension” et la “maîtrise” des complexités du langage par des machines ouvrent tout un nouveau champ de domaines d’applications basés sur des interactions homme-machine élargies et fluidifiées, faisant entrevoir pour certains un horizon de type “AGI”\


{% tabs %}
{% tab title="Machine Learning" %}
## Machine Learning (ML) : apprentissage machine

### Typologie

La typologie des algorithmes peut se décliner selon plusieurs approches

* algorithmes supervisés : le jeu de données d’entraînement est dit étiquetté, c’est-à dire que la variable cible à prédire fait partie du dataset de départ et que l’algorithme apprend en mappant les inputs (les valeurs des variables prédictives) sur les outputs (les valeurs de la variables cible)
* algorithmes non supervisés : le jeu de données d’entraînement n’est pas étiquetté, c’est-à dire que la variable à prédire ne fait pas partie des données d’apprentissage et que l’algorithme apprend seul par exploration  la structure des données
* algorithmes de régression : la variable de sortie à prédire est un nombre
* algorithmes de classification : la variable de sortie à prédire est une catégorie
* algorithme probabiliste
* algorithme géométrique



<table><thead><tr><th width="170"></th><th width="196">Supervisé/probabiliste</th><th>Supervisé/géométrique</th><th>Non supervisé</th></tr></thead><tbody><tr><td>Régression</td><td></td><td></td><td></td></tr><tr><td>Classification</td><td></td><td></td><td></td></tr><tr><td>Clusterisation</td><td></td><td></td><td></td></tr></tbody></table>

### Le NLP : branche du Machine Learning

Le Natural Language Processing (Traitement automatique du langage - TAL - en français) désigne l’ensemble des technologies de machine learning qui permet aux ordinateurs d'interpréter, de manipuler et de comprendre le langage humain.

L’objectif fondamental du NLP est donc de parvenir à capturer la sémantique du langage en transformant de manière la plus statistiquement adéquate du texte en nombres.&#x20;

Le double processus d’encodage (de conversion texte-chiffres pour rendre les données “machine-understandable“) puis de décodage (chiffres-texte pour restituer les calculs sous une forme “human-understandable”) constitue donc le coeur des technologies de NLP, qui recourent pour cela à des processus de création d’embeddings (“plongements lexicaux" en français) c’est-à dire de transformation de mots en vecteurs numériques : convertir du texte en embeddings aboutit à représenter un espace de mots en espace vectoriel multidimensionnel, sur lequel dès lors peuvent être appliqués des processus calculatoires.

Le degré de captation de la sémantique du texte dépend donc fortement de la méthode d’encodage utilisée : avant l’apparition des LLM, les types d’approche pour la création des embeddings allaient du “basique” bags of words au word embeddings word2vec de Google, et un des enjeux majeur de la recherche en NLP était justement de parvenir à encoder non pas seulement des mots mais des séquences de mots en vertu de principe de linguistique bien connu selon lequel le sens d'un mot découle autant de sa définition stricte que de son contexte
{% endtab %}

{% tab title="Deep Learning" %}
## Deep Learning : apprentissage profond

Afin de pouvoir apprendre de manière autonome à partir de jeux de données non structurés, les algorithmes de deep learning imitent le fonctionnement du cerveau humain et s’appuient sur une modélisation en couches de neurones interconnectés ::&#x20;

* la 1ère couche d’entrée (contenant un ou plusieurs neurones) traite et encode les données fournies en input (texte, image…) et transfère l’information à la couche suivante adjacente
* les couches suivantes (dites cachées) qui peuvent être en nombre variable (potentiellement des centaines) contenant chacune un nombre également variable de neurones (possiblement infini) décomposent l’information en caractéristiques atomiques et encodent-décodent successivement ces caractéristiques par des processus d’activation ou non de chaque neurone de manière à transférer de manière itérative  les données d’une couche à l’autre
* la dernière couche de sortie produit les prédictions sur la variable cible, et se composent d’autant de neurones que de valeurs possibles pour cette variable (2 neurones par exemple pour un système de classification binaire)\


<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc-uSp7zlNl87Jyx3x5MMKo-14GKrMycfVEnRqzRM9xtNUoy6VgWu3u0-e_mm6ohYOOS-I002JEkeVc8QAXO1QlcEZiwHvOwM4E7vOhVKUEb9UGOQ2BE1_W7iCETPMlp8GTRd8vhMCFasuTHt8EuQQtyb7n?key=JZxbkjoqTKMyhoWVNJpl-g" alt=""><figcaption></figcaption></figure>

Les méthodes d’apprentissage profond sont très efficaces pour détecter les relations même très faibles entre les variables prédictives, ce qui les rend très performants sur des données complexes et/ou pour réaliser de l’apprentissage non supervisé sur des données linéaires
{% endtab %}

{% tab title="IA générative" %}
{% embed url="https://doi.org/10.48550/arXiv.1706.03762" %}
Article (preprint) fondateur
{% endembed %}

## Principes

Les Large Language Models sont des modèles de NLP  basés sur une catégorie spécifique de réseaux de neurones artificiels (les Transformer) dont l’architecture permet l’encodage parallélisé de séquences entières de mots selon le mécanisme de “l’attention” qui prend en compte les positions et les relations mutuelles de chaque mot dans une séquence (y compris les mots vides) tout en les pondérant différemment selon la séquence dans laquelle ils se trouvent (le contexte).&#x20;

L’apport de ce nouveau type de réseau de neurones capable de plus d’effectuer de l’encodage positionnel simultané, c’est-à-dire d’exécuter des calculs bidirectionnels et paraléllisés, a considérablement accru la “qualité” des embeddings produits, améliorant ainsi capacité des modèles de NLP à décrypter la complexité grammaticale du langage naturel et capter le sens des mots en fonction de leur contexte.&#x20;

***

_Ressources sur la conversion de textes en embeddings sémantisés_

{% embed url="https://ig.ft.com/generative-ai/" %}

{% embed url="https://poloclub.github.io/transformer-explainer/" %}

***

\
Entraîné sur de très grandes quantités d’exemples de phrases, ce dispositif, qui permet au réseau de neurones d’élaborer une représentation interne des données porteuses des relations grammaticales et sémantiques entre chaque occurrence de chaque mot, conduit donc à convertir et à projeter un espace de mots en un espace vectoriel sémantique de très grande dimension : ce qui est exactement la définition d’un LLM.

Ces espaces de très grande dimension dépassent nos capacités cognitives de représentation, mais on tout de même saisir à quoi ressemble un espace d'embeddings en utilisant des techniques de [réduction dimensionnelle](https://en.wikipedia.org/wiki/Dimensionality\_reduction) qui donnent ce genre de cartographie tridimensionnelle

{% embed url="https://projector.tensorflow.org/" %}

Faire de l’inférence sur des LLM consiste ainsi à interagir avec le modèle (ie exploiter les embeddings) afin d’exécuter l’opération fondamentale de l’IA : faire des prédictions, en l’occurrence ici générer du contenu. Lorsque l’on pose une question à un LLM, la question est elle-même convertie en embeddings, puis projetée dans l'espace vectoriel du modèle, qui génère ainsi la suite du contenu (la réponse, mot après mot dans une boucle rétroactive) en calculant les distances entre tous les vecteurs du voisinage de celui représentant le prompt et choisit le plus proche. C'est le fonctionnement de base des modèles dits de fondation, qui permet à l'algorithme de produire des phrases qui font sens grammaticalement.

## Corollaires

1. Un LLM n’est pas une intelligence
2. Un LLM n’est pas une encyclopédie
3. Le phénomène des “hallucinations” est consubstantiel aux LLM : au gré de l’inférence avec un LLM (de l’interaction homme-modèle), la fenêtre de contexte dans laquelle s’opèrent les calculs de distance entre vecteurs se déplace dans l’espace vectoriel du modèle, et rien ne peut garantir que chaque nouveau mot prédit conserve la cohérence d’une réponse du modèle, au mieux la structure grammaticale sera correcte mais le texte généré ne peut être tenu pour crédible.
4. Open source et LLM : l’open source à propos des LLMs est un sujet en soi. Pour résumer néanmoins, on peut relever deux points

\-> le NLP est historiquement ancré dans une dynamique portée par une communauté open source à laquelle participe d’ailleurs largement les GAFA (les modèles Bert de Google ont été ouverts dès le début), et même si les 1ers LLM de fondation qui sont le fait des GAFAM ou autres entreprises de la Tech type OpenIA ne sont pas tous ouverts, le dynamisme de la recherche fondamentale et appliquée qui fait évoluer si rapidement l’écosystème économique et applicatif autour des LLM est largement porté par l’open source

\-> Qualifier un LLM d’ouvert n’est pas aussi simple que pour un logiciel, une publication ou un dataset issu de la recherche : au-delà des questions de licences d’utilisation, la notion d’ouverture se rapproche plus d’un degré sur une échelle que d’un état binaire fermé/ouvert, dans la mesure où rendre accessible un LLM implique de publier le modèle en lui-même (les poids et les biais du réseau de neurones), les datasets complets d’entraînement et le code utilisé pour l’entraînement du modèle. Ainsi, en pratique et si l’on suit cette déclinaison, seul un modèle sur les centaines de milliers existants peut être qualifié de complètement ouvert. Néanmoins, pour pouvoir concrètement réutiliser localement un modèle, seusl les fichiers des paramètres (des poids des neurones) sont réellement nécessaires.

## Tendances

1. Standardisation des outils : au fil du temps on observe tout à la fois une forte démocratisation de l’accès aux LLM et leur environnement technique, une homogénéisation des pratiques en lien avec un socle commun de guidelines ainsi que l’émergence de plateformes et frameworks reconnus et massivement utilisés

\-> Plateforme HuggingFace (le “github des LLM”) pour la diffusion et la documentation des modèles et des datasets d’entraînement

\-> Inférence sur LLM via des API

* API de bas niveau : librairie sentence-transformers
* API de type Rest : client OpenAI, client d’inférence HuggingFace

\-> Deux frameworks Python et Javascript principaux : Langchain et Llamaindex

2. On observe également une double évolution en parallèle mais dans des directions opposées entre&#x20;

\-> des modèles de plus en plus lourds et multimodaux : ces modèles produits à partir de corpus d’entraînement de plus en plus vastes et multi-support sont capables de traiter et générer en même temps du texte, de l’image, de l’audio, de la vidéo…

\-> des modèles de plus en plus légers (SLM pour Small Language Models) : ces modèles avec un nombre limité de paramètres sont spécifiquement entraînés sur des corpus réduits dans le but d’accomplir des tâches bien précises (I can clearly see in future smaller models with very specific roles working as agents and solving such problems, we are not very far from it.)

3. En corollaire aux SLM nécessitant peu ou pas de GPU, il devient possible de recourir  à un SLM sur le GPU d’un navigateur ou de développer des applications mobiles supportant des SLM nativement : certains types d’applications IA pour la réalisation de tâches bien spécifiques sont donc de plus en plus légères, portables et facilement déployables
4. “Garbage In Garbage out” : la question de la qualité des données d’entraînement devient prégnante en tant que garant fondamental de la pertinence et la fiabilité des modèles. De plus en plus, l’ouverture, la réutilisation et l’amélioration collaborative des corpus d’entraînement est un champ d’activité à part entière de l’éecosystème de l’IA générative (ex : Pleias)

\

{% endtab %}

{% tab title="AGI" %}

{% endtab %}
{% endtabs %}



{% hint style="info" %}
IA classique : à retenir

* Les systèmes d'IA classiques (données+modèles) ne sont pas généralisables : valables sur des structures de données et un objectif prédictif strictement comparables aux données d’entraînement
* Systèmes mobilisant de fortes compétences en Data Science alliées  à la connaissance métier des données manipulées
{% endhint %}



{% hint style="info" %}
IA générative : à retenir

Les LLM sont des modèles

* Génératifs : ce sont des modèles d’IA dont l’objectif reste la prédiction, en l’occurrence la prédiction itérative du token suivant une séquence de tokens par calcul de proximité entre vecteurs
* Pré-entraînés : un LLM est la représentation vectorielle de corpus textuels gigantesques ayant servi de données d’entraînement. Ils sont donc utilisables tels quels, sans phase technique d’entraînement supplémentaire.
* Transformer-based : basé sur des réseaux de neurones de type Transformers
{% endhint %}



