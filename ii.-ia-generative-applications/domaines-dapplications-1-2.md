# Domaines d'applications (1/2)

{% tabs %}
{% tab title="Chatbot" %}


## Applications de 1er niveau : chatbots basés sur de l'inférence basique

### Principes

Les chatbots (agents logiciels conversationnels simulant une conversation humaine) sont les applications historiques de premier niveau ayant démocratisé les LLM : elles consistent basiquement à mobiliser le concept d’inférence pour interagir avec l’espace de mots qui sous-tend le modèle.

### Aspects techniques

* En général, les LLM utilisés pour les chatbots sont des variantes conversationnelles des LLM de base : le modèle de langage “primaire” est fine-tuné (sur-entraîné) sur un corpus additionnel de type conversationnel puis soumis à un processus de renforcement humain (RLHF) pour affiner sa pertinence. Ces variantes conversationnelles sont portent la plupart du temps le nom du modèle suivi du suffixe "-chat" (exemple : [https://huggingface.co/meta-llama/Llama-2-7b-chat](https://huggingface.co/meta-llama/Llama-2-7b-chat))
* Lorsque l'utilisateur envoie un prompt au modèle via une interface web ou en ligne de commande, le prompt est lui-même converti en vecteurs puis projeté dans l'espace vectoriel du LLM, afin que les calculs de proximité entre vecteurs soient opérés et que le mot le plus proche du prompt (le plus probable) soit généré par le modèle

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% embed url="https://projector.tensorflow.org/" %}

### Exemples

* Chatbot classique

{% embed url="https://chat.lmsys.org/" %}

* Chatbot avec mindmap

{% embed url="https://www.heuristi.ca/" %}
{% endtab %}

{% tab title="RAG" %}
## Applications RAG : chatbots avec Retrieval-augmented generation

### Principes

Le RAG (Retrieval Augmented Generation) est probablement à ce jour le use-case d’inférence sur des LLM le plus populaire. Aussi appelé “In-context learning”, ce dispositif de requêtage sur un LLM a pour but d’augmenter la précision et la pertinence des réponses du modèle en palliant aux limitations “natives” d’un modèle de langage : domaine de connaissances hors de son corpus d’apprentissage, corpus statique constitué à un instant T, hallucinations…

Pour ce faire, il s'agit de combiner le pouvoir génératif des modèles de langage avec la capacité à récupérer des informations pertinentes issues de sources de données externes, autrement dit d’exploiter les capacités de calculs appliquées au langage naturel des LLMs sur des documents externes choisis par l'utilisateur.

Le RAG consiste donc à intégrer des données externes (choisies par l’utilisateur) qui ne font pas partie du corpus d’apprentissage du LLM dans le processus de génération de contenu.

### Aspects techniques : les 4 étapes du RAG



* Data loading : la récupération des données là où elles se trouvent -- qu’il s’agisse de fichiers texte, de fichiers PDF, d’un autre site Web, d’une base de données ou d’une API -- pour constituer le corpus personnalisé qui va venir compléter les données d'entraînement du LLM
* Indexing & embedding & storing : le corpus additionnel (les données contextuelles de l’utilisateur) est tout d’abord découpé en une suite de séquences de mots, chacune de ces séquences est ensuite convertie en vecteurs sémantiques avec un modèle d’embeddings, puis le tout est enfin stocké dans un index ou une base de données vectorielle (un vectorstore)
* Query & retriever : le prompt de l’utilisateur, transformé en embedings avec le même modèle que l’étape 2, n’est pas envoyé directement au LLM mais d’abord vers le vectorstore afin d’y opérer des calculs de similarité sur les vecteurs du contexte et d'en extraire les segments les plus proches (considérés comme les plus pertinents, en accord avec le principe selon lequel des concepts similaires ont des embeddings similaires )
* Content generation : au final, la prompt initial de l’utilisateur et les segments du contexte retenus en tant que données sémantiques les plus pertinentes sont plugés dans un même système d’instructions qui est alors envoyé au LLM, de manière à ce le contenu généré (ie les calculs de distance réalisés dans l’espace vectoriel du LLM) prenne en compte les informations contextuelles complémentaires préalablement sélectionnées.

### Implémentations

On peut distinguer trois modes d'implémentation d'application de RAG sur ses propres corpus ou bases de connaissances

* Utiliser une application en ligne (avec LLM en SaaS) permettant d'uploader ses documents

{% embed url="https://chatgpt.com/" %}

{% embed url="https://gemini.google.com/app" %}

{% embed url="https://aistudio.google.com/app/prompts/new_chat" %}

Il est assez facile de développer from scratch une application de RAG, néanmoins il existe une foultitude d’applications de RAG, notamment open source, qui évitent d’avoir à réinventer la roue

* RAG avec interface graphique

{% embed url="https://flowiseai.com/" %}

* Frameworks open source de RAG

{% embed url="https://anythingllm.com/" %}

{% embed url="https://openwebui.com/" %}

{% embed url="https://ragflow.io/" %}

## SISB

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/applications-de-rag/">applications-de-rag</a></td><td></td><td></td></tr><tr><td>Primo Research Assistant</td><td><a href="https://swisscovery.slsp.ch/discovery/search?vid=41SLSP_NETWORK:VU1_UNION">https://swisscovery.slsp.ch/discovery/search?vid=41SLSP_NETWORK:VU1_UNION</a></td><td></td></tr></tbody></table>
{% endtab %}

{% tab title="Moteurs de recherche sémantiques" %}
## Moteurs de recherche sémantiques

### Principes

Adossée à la recherche vectorielle par similarité, la recherche sémantique est une technologie de moteur de recherche qui interprète le sens et l’intention d’une requête en langage naturel et renvoie les contenus contextuellement les plus pertinents.

Le principe de la recherche ne repose plus sur la reconnaissance de chaînes de caractères entre des mots-clés en entrée et des champs statiques préalablement indexés, mais sur la projection du contexte et de la signification d'une requête dans un espace de données sémantiquement encodées, rendant possible l'obtention de résultats de recherche plus pertinents quand bien même ils ne contiendraient aucun des mots de la requête initiale.

### Aspects techniques

La requête est transformée en embeddings (vecteurs sémantiques) puis projetée dans l’espace vectoriel d’un contexte donné, afin que soient opérés des calculs géométriques de distance entre vecteurs, des distances de faibles valeurs représentant alors des similarités sémantiques et non plus de simples proximités syntaxiques.

Pour les moteurs de recherche généraliste (basés sur le web en temps réel), le processus est un peu plus complexe : en même temps que la requête est convertie en embeddings, les mots-clés les plus pertinents extrait de la requête (par un LLM) sont lancés pour une recherche classique sur le web. Le but de cette recherche est de collecter des informations supplémentaires sur le sujet qui pourraient aider le modèle de langage à générer une réponse plus précise et contextuelle. Les résultats de la recherche sont ensuite utilisés pour enrichir les embeddings de la question (de nouveaux embeddings -le contexte -  sont créés , le tout étant projeté dans l’espace vectoriel du LLM qui dispose alors de plus d'informations pour générer la réponse.

### Exemples



{% embed url="https://www.perplexity.ai/" %}

{% embed url="https://exa.ai/search" %}

## SISB (idées)

<table data-view="cards"><thead><tr><th align="center"></th><th></th><th></th></tr></thead><tbody><tr><td align="center"><a data-mention href="../iii.-presentation-equipe-dir/ia-generatives-pistes-dimplementation-sisb/moteur-de-recherche-semantique.md">moteur-de-recherche-semantique.md</a></td><td></td><td></td></tr><tr><td align="center"></td><td></td><td></td></tr></tbody></table>
{% endtab %}

{% tab title="Prompt Engineering" %}
## Exécution de tâches via le prompt engineering

### Principes

Le prompt engineering, aussi appelé « ingénierie de requête », est une technique qui consiste à fournir des instructions détaillées aux LLM  afin d’améliorer leurs performances.

Concrètement, le prompt engineering permet de guider plus précisément LLM en lui donnant des indications sur la tâche à effectuer et le contexte dans lequel elle s’inscrit. Plutôt que de laisser le modèle répondre de manière générique à une question posée, le prompt engineering permet de cadrer la réponse attendue.

En apparence simple, les différentes techniques et stratégies de prompt sont un un moyen assez robuste et sophistiqué d’exploiter les capacités d’un modèle de langage à comprendre une requête et à réaliser une tâche.

### Aspects techniques



Les techniques d’optimisation de la structure des prompts sont liées au concept d’In-context learning, c’est-à-dire d’apprentissage par le contexte (le RAG est également fondé sur cette notion). Afin de mieux guider le LLM en lui fournissant en input un contexte enrichi, on peut ainsi ajouter dans un prompt des instructions précises, l'historique des conversations, des spécifications de style, des exemples de format de réponse attendue, ou encore lui attribuer un rôle.

Concrètement et très synthétiquement,on peut distinguer deux manières d’appliquer des techniques d’apprentissage par le contexte

* One-shot Learning ou Few-shot learning : désigne le fait de fournir dans le prompt un exemple clair et précis (ou plusieurs exemples clairs et précis) de ce que le modèle doit imiter pour générer sa réponse afin de conditionner explicitement le contenu généré à suivre ces exemples
* Chain-of-Thought Prompting (CoT) : désigne le fait de combiner des instructions très précises sur le processus de raisonnement attendu et du Few-Shot learning afin d’inciter un modèle de langage à articuler le même type de raisonnement avant de répondre à une question finale. Dans cette situation, le LLM répond à la question en expliquant pas à pas les étapes suivies pour aboutir au résultat.

### Exemples

{% embed url="https://huggingface.co/spaces/Geraldine/prompts_library" %}
{% endtab %}
{% endtabs %}

