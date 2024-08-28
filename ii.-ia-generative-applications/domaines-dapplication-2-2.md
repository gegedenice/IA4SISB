# Domaines d'application (2/2)

{% tabs %}
{% tab title="Extraction de données structurées" %}
## Extraction de données structurées (à partir de données non structurées)

### Principes

L’extraction de données structurées à partir de données non structurées consiste pour un algorithme ou un modèle à reconnaître et catégoriser des classes d’objets spécifiques dans du texte ou à partir d’images. En NLP, les tâches de reconnaissance d’entités nommées en (NER) sont centrales car très utilisées en sciences de l’information, humanités numériques…

Avec un LLM de fondation standard et un prompt adéquat, les systèmes d’IA générative sont donc capables d'ingérer de grandes quantités de données non structurées et d’identifier sémantiquement certaines entités afin de les renvoyer dans un format structuré cohérent (cf partie précédente).

Ceci dit, avec la tendance en cours de création de modèles plus légers car spécifiquement entraînés sur un corpus limité à faire certaines catégories de tâches bien précises, les Small models dédiés à l’extraction de données structurées représentent un champ de la recherche très actif, rendant ce type de tâche beaucoup plus techniquement abordable, facilement intégrable dans des workflows existant, tout cela dans nécessairement mobiliser un gros LLM consommant beaucoup de GPU.

### Exemples

#### Extraction de données structurées à partir de textes

{% embed url="https://huggingface.co/spaces/numind/NuExtract" %}

#### Extraction de données structurées à partir d'images

{% embed url="https://huggingface.co/spaces/OpenGVLab/InternVL" %}

#### Extraction de données strcuturées à partir de pages web

### Remarques

* Possibilité de fine-tuning en mode no-code avec l’application Numind -> création de SLM customisé pour la reconnaissance et l’extraction de certaines entités
* En post-processing de l’extraction de texte par des VLM, et au cas où l’océrisation n’est pas propre, possibilité de corriger avec un autre LLM (cf Pleias)

### SISB

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/pipelines-dextraction-de-donnees.md">pipelines-dextraction-de-donnees.md</a></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

\

{% endtab %}

{% tab title="Agents et fonctions" %}
## Principes des agents LLM

Les agents à base de LLM, appelés agents LLM, sont des systèmes d'IA avancés conçus pour permettre à un modèle d’accomplir une ou plusieurs tâches complexes nécessitant un raisonnement séquentiel. En général les architectures des agents LLM impliquent et articulent plusieurs composants (ou modules) tels que le raisonnement par étapes, la planification, la mémoire ou encore des bases de connaissances ou services externes.

## Principes des "tools" (ajout de fonctionnalités)

Les outils (“Tools”) correspondent à ces ensemble d'outils tiers qui permettent à l'agent LLM d'interagir avec des environnements externes tels que des API, des KBs, des interpréteurs de code (capable d’exécuter des blocs de code), le moteur “Math” pour les opérations mathématiques, et tout autre outil customisé. Les appels à ces outils durant le flux de travail de l’agent l’aide à obtenir des observations ou des informations nécessaires pour compléter la réalisation des sous-tâches.

## Exemple : data analyst agent

{% embed url="https://huggingface.co/spaces/m-ric/agent-data-analyst" %}

## SISB

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/agent-llm-avec-tools.md">agent-llm-avec-tools.md</a></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>
{% endtab %}

{% tab title="Systèmes multi-agents" %}
## Principes

Les systèmes d'IA multi-agents consistent à associer plusieurs agents décisionnels interagissant les uns avec les autres pour résoudre des tâches complexes nécessitant la mise en oeuvre de raisonnements et de planification, chaque agent assumant un rôle unique dans le processus de génération.

## Exemples

### Génération de rapports/notes/études/analyses

{% embed url="https://app.wordware.ai/share/264a8a63-5128-44e7-8947-acb755aa90e5/playground" %}

## SISB

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/systemes-multi-agents.md">systemes-multi-agents.md</a></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>
{% endtab %}

{% tab title="Cartographie" %}
## Principes

Convertir un corpus textuel en embeddings revient à dresser une spatialisation sémantique de ce corpus, mais la représentation d'espaces multidimensionnels dépasse (pour l'instant) nos capacités cognitives de perception. Par contre il est tout à fait possible, par le biais d'algorithme de réduction de dimensions, de projeter un tel espace dans un plan (un espace à 2 dimensions) afin de visualiser ces embeddings transformés en datapoints.

## Exemples

{% embed url="https://atlas.nomic.ai/" %}

## SISB

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/cartographies-semantiques-de-collection.md">cartographies-semantiques-de-collection.md</a></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>
{% endtab %}
{% endtabs %}



