# Question ouverte

"Décrivez votre processus et raisonnement pour évaluer la sécurité d'un système embarqué au niveau matériel et logiciel."

En réalité, je suivrais ce que j'ai appris durant mes cours de "pentest". 
D'abord, j'analyse les interfaces, c'est-à-dire les points d'entrée. Sur du hardware : 
- Est-ce qu'il y a un port USB ? 
- Un jtag ?
- Un clavier ?
- Une carte WIFI
- Du bluetooth
- ...

Sur du software :
- Les formulaires
- Les stockages locaux
- Les ports ouverts

J'analyse aussi, spécialement pour le software (mais ça marche pour le hard), les technologies utilisées, et je regarde si une CVE est présente sur ces technologies. Concernant les points d'entrée, j'analyse comment sont échangées les données : est-ce qu'il y a du chiffrement ? De l'authentification ? De la vérification d'intégrité ?
Pour ça, j'essaie d'intercepter des données, de les comprendre, de les modifier, de me faire passer pour quelqu'un.

De manière générale sur les systèmes, je teste ce qui peut mettre en péril les "piliers" de la sécurité informatique, à savoir l'intégrité, la confidentialité, la traçabilité et la disponibilité. Je me renseigne donc sur l'architecture, j'essaie de découper mon système à analyser en "composants" et je les étudie chacun de leur côté, et ensuite chacun ensemble. Je vérifie que les chiffrements se basent sur des protocoles connus ou non, etc.

Ensuite, je fais une analyse de risques, selon le profil de l'entreprise qui me missionne pour évaluer le système. En effet, les risques ne sont pas les mêmes pour un artisan et son site web qu'avec des voitures autonomes par exemple. Et je fournis un rapport détaillé.
