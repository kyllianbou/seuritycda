# Security CDA 

## HTTPS && ! HTTP

![](img/https.png)

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

## systeme de hachage et de salage

Le stockage des mots de passe des utilisateurs par le vérifieur doit être réalisé de manière sécurisée. En effet, en cas de compromission de cette base (cette base a été récupérée ou rendue publique par un attaquant), les mots de passe seront directement révélés s’ils sont stockés en clair. Ainsi, ce sont les empreintes des mots de passe qu’il faut conserver plutôt que les mots de passe eux- mêmes. Le stockage des mots de passe en clair doit être absolument proscrit. Ces empreintes, aussi appelées hachés, sont le résultat d’une fonction de hachage cryptographique 

## Cookies

![](img/cookies.jpeg)

Les cookies ont de multiples usages : ils peuvent servir à mémoriser votre identifiant client auprès d'un site marchand, le contenu courant de votre panier d'achat, la langue d'affichage de la page web, un identifiant permettant de tracer votre navigation à des fins statistiques ou publicitaires, etc.

## API

![](img/API.png)

Une API, ou interface de programmation d’application, permettent à votre produit ou service de communiquer avec d'autres produits et services sans connaître les détails de leur mise en œuvre.

Envoyer json 80% DU TEMPS

## API STATELESS

Un processus ou une application sans état est indépendant. Il ne stocke pas de données et ne fait référence à aucune transaction passée. Chaque transaction est effectuée à partir de rien, comme si c'était la première fois. 

Par exemple, une recherche en ligne pour répondre à une question quelconque est une transaction sans état. Vous tapez votre question dans le moteur de recherche et appuyez sur Entrée. Si votre transaction est accidentellement interrompue ou fermée, vous devez en démarrer une nouvelle. Les transactions sans état sont comparables à des distributeurs automatiques : une seule requête et une seule réponse. 

![](img/state.png)

## API STATEfull

Les applications et processus avec état, quant à eux, peuvent être réutilisés indéfiniment. Les plateformes bancaires en ligne et les messageries en sont deux exemples. Les transactions précédentes sont prises en compte et peuvent affecter la transaction actuelle. C'est pour cela que les applications avec état utilisent les mêmes serveurs chaque fois qu'elles traitent une requête d'un utilisateur. 

La majorité des applications que nous utilisons au quotidien sont des applications avec état. Toutefois, les technologies évoluent et les microservices ainsi que les conteneurs facilitent le développement et le déploiement d'applications dans le cloud. 

## Tokens

![](img/tok.jpeg)

Les jetons d'identification sont utilisés dans l'authentification basée sur les jetons pour mettre en cache les informations de profil utilisateur et les fournir à une application cliente, offrant ainsi de meilleures performances et une meilleure expérience. L'application reçoit un jeton d'identification après qu'un utilisateur s'est authentifié avec succès, puis consomme le jeton d'identification et en extrait les informations de l'utilisateur, qu'elle peut ensuite utiliser pour personnaliser l'expérience de l'utilisateur. 

## injection SQLi

![](img/SQL.jpeg)

SQL (Structured Query Language) est un langage qui nous permet d’interagir avec des bases de données. Les applications Web modernes utilisent des bases de données pour gérer les données et afficher un contenu dynamique aux lecteurs.

L’injection SQL, ou SQLi, est une attaque sur une application web en compromettant sa base de données par des déclarations SQL malveillantes.

## Protection contre les vulnérabilités XSS

Il existe de nombreux scénarios d’attaques mettant en jeu une vulnérabilité XSS. Par exemple, s’il est possible d’injecter du contenu dans une page au travers d’une variableGET12, un attaquant peut inciter (par exemple au moyen d’un courrier électronique trompeur) une victime à cliquer sur un lien fabriqué dans l’objectif d’appeler une page au contenu vulnérable et insérer dans celle- ci un script malveillant. L’attaquant pourra alors contrôler le navigateur de la victime qui pense pourtant visiter un site de confiance. Il est ainsi en mesure, par exemple, de voler la session de la victime et d’usurper son identité sur le site.
On distingue trois causes principales à l’origine des vulnérabilités XSS. Pour chacune d’entre elles, il existe des bonnes pratiques de développement qui permettent de réduire le risque d’une attaque XSS en diminuant la probabilité d’apparition de telles vulnérabilités.

## Maîtrise de l'évaluation de code

La génération de code JavaScript à la volée est parfois utilisée afin d’intégrer des données en entrée transmises sous forme de chaînes de caractères. Cette mauvaise pratique est une opportunité pour un attaquant d’exploiter la vulnérabilité XSS introduite par l’usage de la fonction JavaScript eval(). En effet, l’utilisation de la fonction de désérialisation eval() avec une chaîne de caractères forgée permet à un attaquant de modifier le contenu et le comportement du site.
L’usage de la fonction eval est donc à proscrire au profit, pour l’intégration de données struc- turées, de l’utilisation du format JSON et de la méthode associée JSON.parse.

## Défense en profondeur

protection indépendantes en face de chaque menace envisagée.
Il est plus facile d’appliquer ce principe si le système à sécuriser est composé d’unités distinctes, aux interactions bien définies et possédant leurs propres mécanismes de sécurité. La défense en profondeur demande à ce que soient mises en œuvre les mesures de protection nécessaires et disponibles au niveau de chaque unité. Une mauvaise approche est, par exemple, de concentrer toutes les mesures de sécurité au niveau du point d’entrée du système et de constater que les fonctions internes sont complètement exposées en cas de vulnérabilité en amont, ou encore de ne considérer que le risque sur l’infrastructure en ne plaçant comme élément de sécurité qu’un simple pare-feu périmétrique.

Dans l’idéal, chaque brique logicielle de l’application web participe à la protection de l’ensemble du système. L’architecture logicielle du site web ainsi que l’infrastructure d’hébergement doivent participer à la défense en profondeur.

## Précaution d'usage des bases de données de type Web Storage

Les bases de stockage de données hors-ligne localStorage et sessionStorage sont des bases de données de type clé / valeur permettant l’enregistrement de données côté client par Origin respectivement persistantes et non persistantes. Elles font partie du standard HTML.

Les bases de données locales respectent la contrainte de Same-Origin Policy. Les données manipu- lées au sein d’une Origin ne sont visibles et accessibles que par cette Origin. Il s’agit cependant de la seule mesure implémentée permettant le contrôle d’accès à ces données. Au sein d’une même Origin, tous les scripts JavaScript accèdent aux mêmes bases localStorage et sessionStorage.

## Menaces et objectifs des attaquants

- La compromission des ressources applicatives est une violation de l’intégrité du contenu, dont une conséquence peut être la défiguration 2 du site. Une telle attaque a pour objectif de modifier le site pour remplacer le contenu légitime par un contenu choisi par l’attaquant. Il s’agit, par exemple, de relayer un message politique, de dénigrer le propriétaire du site ou simplement de revendiquer l’attaque comme preuve d’un savoir-faire. Une perte d’intégrité peut aussi résulter en la conduite d’une attaque par point d’eau (watering hole), qui tend un piège aux visiteurs.
- Le vol de données est une attaque qui provoque la perte de la confidentialité de certaines don- nées (authentifiants, informations personnelles, informations bancaires, etc.). Elle est réalisée dans un but souvent lucratif et aboutit la plupart du temps à des usurpations d’identité ou à des paiements frauduleux.
- Le déni de service 3 a pour objet de rendre indisponible le site attaqué pour ses utilisateurs légitimes que ce soit par l’arrêt ou par un ralentissement considérable du service.

![](img/hack.jpeg)

