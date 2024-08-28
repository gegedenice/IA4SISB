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

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/pipelines-dextraction-de-donnees.md">pipelines-dextraction-de-donnees.md</a></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

\

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}
