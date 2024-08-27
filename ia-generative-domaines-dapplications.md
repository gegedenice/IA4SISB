# IA générative : domaines d'applications

{% tabs %}
{% tab title="Chatbot" %}


## Applications de 1er niveau : chatbots basés sur de l'inférence basique

### Principes

Les chatbots (agents logiciels conversationnels simulant une conversation humaine) sont les applications historiques de premier niveau ayant démocratisé les LLM : elles consistent basiquement à mobiliser le concept d’inférence pour interagir avec l’espace de mots qui sous-tend le modèle.

### Aspects techniques

* En général, les LLM utilisés pour les chatbots sont des variantes conversationnelles des LLM de base : le modèle de langage “primaire” est fine-tuné (sur-entraîné) sur un corpus additionnel de type conversationnel puis soumis à un processus de renforcement humain (RLHF) pour affiner sa pertinence. Ces variantes conversationnelles sont portent la plupart du temps le nom du modèle suivi du suffixe "-chat" (exemple : [https://huggingface.co/meta-llama/Llama-2-7b-chat](https://huggingface.co/meta-llama/Llama-2-7b-chat))
* Lorsque l'utilisateur envoie un prompt au modèle via une interface web ou en ligne de commande, le prompt est lui-même converti en vecteurs puis projeté dans l'espace vectoriel du LLM, afin que les calculs de proximité entre vecteurs soient opérés et que le mot le plus proche du prompt (le plus probable) soit généré par le modèle

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

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
{% endtab %}
{% endtabs %}



