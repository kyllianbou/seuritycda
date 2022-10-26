# Security CDA 

## HTTPS && ! HTTP

La mise en place de HTTPS sur un site ou une application web est une garantie de sécurité qui repose sur TLS pour assurer la confidentialité et l’intégrité des informations échangées, ainsi que l’authenticité du serveur contacté.

La mise en place de HTTPS a pour objectif :
 de garantir, autant que possible, l’authenticité du site consulté ;
 de garantir également l’intégrité et la confidentialité des données échangées en bloquant les attaques de type Man-In-The-Middle



 ## CORS (Cross-Origin Resource Sharing),SOP (Same-Origin Policy),CSP (Content Security Policy)

### CORS

Il est parfois nécessaire de contourner la SOP (stratégie de sécurité par défaut du navigateur) afin de permettre l’appel de ressources en dehors de l’Origin telles que peuvent en fournir des services web tiers de météo ou d’actualités par exemple. La méthode utilisée dans ce cas est nommée Cross- Origin Resource Sharing. 

### SOP

L’objectif de Same-Origin Policy (SOP) est de fournir un cadre de contrôle des interactions possiblement effectuées par les éléments embarqués dans une page web. SOP est une contrainte implémentée par tous les navigateurs du marché. Cette contrainte ne signifie pas que toutes les res- sources doivent provenir d’une même Origin, mais impose des restrictions dans la communication entre composants lorsque ceux-ci ont des Origins différentes.

### CSP

Content Security Policy (CSP) permet de définir une stratégie de contrôle des accès aux res- sources atteignables d’un site web donné par l’application de restrictions sous forme de liste d’autorisations.

La maîtrise de l’ensemble des ressources récupérées par un site web permet de réduire le risque d’apparition et l’exploitabilité de vulnérabilités XSS, abordées plus en détails en section.

