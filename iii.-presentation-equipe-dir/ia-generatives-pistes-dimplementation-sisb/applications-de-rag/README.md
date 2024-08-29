# Applications de RAG

## RAG sur PV équipe de direction

Démo en local (avec anythingLLM) : [http://localhost:3001/workspace/pv\_dir](http://localhost:3001/workspace/pv\_dir)

## Autres pistes d'implémentation

* Chatbot de RAG sur procédures guichet
* Assistant RAG de rédaction de mails pour équipe Data Research

Démo en local (avec anythingLLM) : [http://localhost:3001/workspace/rdm](http://localhost:3001/workspace/rdm)

* Infoscience

\-> RAG sur abstracts/fulltext de thèses

\-> Ajout d’un format d’export du fulltext en embeddings

## Points de vigilance

* RAG en production : pas si simple

Si le principe du RAG est relativement simple et la réalisation d’un POC très abordable, le réglage optimal du système peut être assez chronophage (test de plusieurs LLM, test de plusieurs modèles d’embeddings, réglages des paramètres des deux modèles, test des librairies/outils d’extraction des contenus des documents…).

D’autre part, l’optimisation des applications de RAG est un champ de R\&D en soi afin d’éliminer au maximum la possibilité des hallucinations, effectuer les calculs de similarités dans les embeddings des documents les plus performants…

* condition de sécurisation de la confidentialité des données : hébergement en local du LLM et de la base de données vectorielles

