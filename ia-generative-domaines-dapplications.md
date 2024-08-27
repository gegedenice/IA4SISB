# IA générative : domaines d'applications

{% tabs %}
{% tab title="Chatbot" %}
Applications de 1er niveau : chatbots basés sur de l'inférence basique

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



{% endtab %}
{% endtabs %}

