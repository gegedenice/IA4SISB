# Plateforme HuggingFace et modalités d'accès aux LLM

## Types d'accès

Les modalités d'ouverture, donc d'accès, des LLM déterminent les possibilités d’implémentation en local, et diffèrent évidemment d’un modèle à l’autre.

Néanmoins, en lien avec la standardisation des environnements et outils, on peut distinguer trois catégories de situation&#x20;

### Modèle fermé, hebergé par le producteur (cloud) accessible via une UI web mais sans protocole d'exposition

Le seul interfacage homme-machine est l’application en ligne proposée par le producteur du modèle, sans possibilité d'installation locale ou d'inférence via un service d'API

### LLM en SaaS : modèle hebergé par le producteur (cloud), et accessible par API web (en général selon le standard du client OpenAI).

En général l'inférence sur le modèle en mode no-code est également possible par une application web

* API payante

{% embed url="https://openai.com/api/" %}

{% embed url="https://www.anthropic.com/" %}

{% embed url="https://chat.mistral.ai/chat" %}

* API gratuite jusqu’à un certain nombre de requêtes

{% embed url="https://build.nvidia.com/explore/discover" %}

* API gratuite sans restriction d’usage

{% embed url="https://console.groq.com/docs/quickstart" %}

### Modèle ouvert sur HuggingFace

* Téléchargeable en local dans sa version originale : selon la taille du modèle, nécessite un serveur avec GPU
* Si disponible, téléchargeable en local dans une version quantisée  (compressée) : modèle moins précis, peut nécessiter aussi du GPU
* Si disponible, accessible par l’API d’inférence de la plateforme HuggingFace : gratuit, pratique pour des tests mais trop instable pour une application en production

{% embed url="https://huggingface.co/meta-llama/Meta-Llama-3.1-8B" %}

{% hint style="info" %}
Une des bibliothèque open source la plus utilisée pour le déploiement de LLM en local est [Ollama](https://ollama.com/)
{% endhint %}

## Particularités de la plateforme HuggingFace

{% embed url="https://huggingface.co/" %}

La plateforme HuggingFace, souvent comparée aux forges logicielles de type Github ou Gitlab pour le dépôt et le versioning de LLM, propose en plus de l'aspect repository des fonctionnalités et des intégrations qui en font une véritable ressource centrale dans l'écosystème des modèles d'IA génératives.&#x20;

Il est ainsi par exemple possible depuis le site&#x20;

* bien sûr de rechercher des modèles (la plateforme en héberge plusieurs centaines de milliers) : [https://huggingface.co/models](https://huggingface.co/models)

{% hint style="info" %}
Modèles déposés par l'EPFL : [https://huggingface.co/models?search=EPFL](https://huggingface.co/models?search=EPFL)
{% endhint %}

* de créer et/ou lancer très simplement des environnements d'exécution pour faire tourner des applications web : [https://huggingface.co/spaces](https://huggingface.co/spaces)
* bénéficier du client d'inférence mis en place par HuggingFace pour requêter des modèles par API sans les installer localement
* déployer des endpoints d'inférence sur des services tiers type Amazon
* déposer et versioner les datasets d'entraînement
* créer des notebooks Python et proposer des cookbooks
* rédiger des billets de blog...

## En pratique

Comme souligné [ici](domaines-dapplications.md), la plupart des modèles de langage sont ouverts et documentés sur HuggingFace puisque l'open weight (similairement à l'open source) est autant dans l'intérêt du producteur du modèle que de l'utilisateur.

De plus, en lien avec la standardisation des pratiques et outils, un certain nombre de packages ou librairies (open source) facilitent grandement l’installation et le déploiement de LLM en local, la plupart fournissant même le service web d’exposition par API compatible OpenAI, pour une intégration fluidifiée avec des applications web. Dans les faits donc, à partir du moment où un modèle est ouvert, et en dehors des critères relatifs à l’infrastructure de stockage nécessaire, il est relativement aisé d’installer et d’interagir localement avec un LLM.

## Point de vigilance : data privacy

Par construction, quel que soit le type de l’application qui mobilise un LLM (chatbot ou autre) et quel que soit le mode d’accès au LLM (plateforme ou API), toute requête sur un LLM est convertie en embeddings puis projetée dans l’espace du modèle. Par conséquent, il faut bien avoir conscience qu’à partir du moment où le modèle n’est pas hébergé localement, les données transitent vers l’hébergement tiers. La seule garantie de protection des données consiste donc à stocker le modèle sur son infrastructure locale.
