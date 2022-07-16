Explorons des animations plus complexes que la rotation de cubes. En fait, nous allons examiner l'un des exemples les plus potentiellement complexes d'associations `Animation` et `Animation Controller`, à savoir le cas de `Humanoid`.

(youtube: qgJs7uluwlU)

Vous avez peut-être remarqué qu'il existe une nouvelle génération de personnages humains en 3D qui apparaissent dans les jeux vidéo et les récits immersifs. Ces personnages ont des types de corps plus réalistes, une peau plus riche et plus dynamique qui réagit mieux à la lumière et aux ombres, et ils ont même des expressions faciales quelque peu décentes. Ce dernier aspect - les expressions faciales - nécessite encore plus d'avancées techniques et de meilleurs outils, mais nous nous rapprochons de plus en plus des expériences pseudo-cinématographiques au sein de moteurs de jeux interactifs programmables en temps réel.

L'une des raisons de l'augmentation soudaine des personnages de qualité est une amélioration des outils utilisés pour construire des humains virtuels. Il est très long de créer des personnes sommet par sommet dans des outils de modélisation 3D (cf. Blender, ci-dessous), puis d'attacher leur modèle 3D `skin` à un `rig` de `bones` afin qu'ils puissent être animés dans Unity ou Irréel. Non seulement nous avons utilisé beaucoup de jargon dans la phrase précédente, mais nous avons également décrit plusieurs processus laborieux. Ainsi, pour accélérer ce flux de travail, de nombreux outils générateurs d'humanoïdes ont été développés.

### Character Creator & iClone
L'outil le plus populaire, et aussi le plus cher, est [Character Creator](https://www.reallusion.com/character-creator/) qui, comme son nom l'indique, vous permet de créer un personnage entièrement truqué simplement en déplaçant autour des curseurs (plus grand, plus court, plus âgé, plus jeune, couleur des yeux, longueur de bras, etc., jusqu'à la nausée). La même société dispose également d'un outil d'animation (qui fait également d'autres choses) appelé [iClone](https://www.reallusion.com/iclone/), et cela coûte trop cher, même avec des réductions pour les étudiants. Donc soyez prudents.

(youtube:FDyvM4ciTSQ)

### MetaHuman
Un autre outil impressionnant, mais qui ne peut être utilisé (légalement) qu'avec Unreal Engine est [Meta Human](https://www.unrealengine.com/en-US/metahuman-creator). Epic a consacré beaucoup de temps, d'argent et de communication à cet outil. C'est l'une des nombreuses raisons pour lesquelles les gens sont très enthousiasmés par le moteur de jeu Unreal.

(youtube:6mAF5dWZXcI)

### Ziva + Meta = Unity
Unity a également fait de nombreuses acquisitions récemment, notamment [l'achat de Weta Digital](https://blog.unity.com/news/welcome-weta-digital) l'année dernière, ainsi que [Ziva Dynamics](https://venturebeat.com/2022/01/24/unity-acquires-ziva-dynamics-and-its-character-tech/). À première vue, il peut sembler qu'il ne s'agit que d'un mouvement réactif aux avancées d'Epic, mais bon nombre de ces achats indiquent que Unity a également une vue d'ensemble du paysage global de la manière dont les personnages, les matériaux et les environnements doivent interagir avec leurs outils. Weta et Ziva vont bien au-delà des humanoïdes fantaisistes et nous entraînent dans le monde de la simulation :

(youtube: sFibYevZ-Fo)

Pour faire court, Unreal et Unity sont dans une bataille massive en ce moment, et cela se traduit par de nombreux outils de développement axés sur des humanoïdes sophistiqués avec des animations plus expressives que celles que nous avions au cours des 30 années précédentes de visages et de corps humains dans les jeux vidéo. La vidéo suivante, par exemple, est une bande-annonce de la Game Developers Conference 2022 où Unity a présenté ses dernières et plus grandes avancées sur ces fronts. Le visage que vous regardez est un personnage en temps réel entièrement numérique fonctionnant dans Unity :

(youtube: eXYUNrgqWUU)

### Make Human
[Make Human](http://www.makehumancommunity.org) n'est pas du tout joli comme les outils de personnage ci-dessus. Il a même des notions plus que douteuses sur la race, le sexe et les types de corps. Cela dit, c'est open-source, donc peut-être que la communauté peut le rendre moins grincheux `¯\_(ツ)_/¯` ? Quoi qu'il en soit, cela fonctionne avec le même principe de déplacement des curseurs que Character Creator afin d'ajuster la forme du corps et la hauteur de vos personnages. Ces personnages sont entièrement truqués et peuvent être importés en petite pompe directement dans Unity et animés par tous les moyens que vous souhaitez.

### Blender
La solution la plus difficile, mais aussi la plus puissante, est d'apprendre à fabriquer un humain à partir de zéro en utilisant des logiciels de modélisation 3D plus traditionnels tels que Maya, C4D ou Blender. Il existe de nombreux tutoriels pour modéliser des personnages, les "truquer" en marionnettes contrôlables, puis les importer dans Unity. Nous n'allons pas passer par ces solutions pour ce tutoriel.

Par exemple, voici un tutoriel gratuit en 9 parties sur la création d'un personnage humanoïde dans Blender, en le truquant avec un outil Blender appelé [Rigify](https://docs.blender.org/manual/en/2.81/addons/rigging/rigify.html) puis en l'important dans Unity :

(youtube: U-eeKwuqN34)

L'un des avantages de l'apprentissage de l'ensemble du flux de travail de modélisation > rigging > animation > moteur de jeu est que vous pouvez concevoir des personnages non standard sans tomber dans les clichés de la plupart des outils d'emporte-pièce-faites-moi un humain. Une fois que vous avez appris les bases du système [Rigify](https://docs.blender.org/manual/en/2.81/addons/rigging/rigify.html) de Blender, vous pouvez même l'appliquer à diverses créatures quadripèdes ou volantes, qui sont d'ailleurs inclus par défaut dans l'installation de base de Rigify.

### Open Source Afro Hair Library
Pendant que vous concevez votre propre personnage 3D, puis-je vous intéresser à repenser vos hypothèses de base sur ce qui fait un personnage jouable standard ? Que diriez-vous de consulter le [OSAHL](https://afrohairlibrary.org) de [pretty darke](https://prettydarke.cool/portfolio/open-source-afro-hair-library/) & Cie. :

> "La bibliothèque Open Source Afro Hair Library est une ressource queer, féministe et pro-noire pour les modèles 3D de textures et de styles de cheveux noirs."

(youtube: MqcgDnXSTSk)

### Mixamo
Pour ce didacticiel, nous allons utiliser un ancien outil de rigging et d'animation humanoïde nommé Mixamo. C'est un outil très facile à utiliser et nous permet d'avoir rapidement un personnage humanoïde se déplaçant à l'intérieur de notre jeu ou de notre expérience de réalité virtuelle.

Malheureusement, cet outil a subi la trajectoire inverse de Ziva Dynamics et MetaHuman. [Mixamo](https://www.mixamo.com) est [encore un autre](https://en.wikipedia.org/wiki/Category:Discontinued_Adobe_software) de ces incroyables outils qui ont été achetés par Adobe, qui a par la suite abandonné dans les limbes du développement où il reste juste là, dépérissant éternellement. Pour l'instant, il est encore (quelque peu) utilisable, mais uniquement via le navigateur Chrome. Comme il n'a pas évolué depuis des années, ce n'est probablement qu'une question de temps avant qu'Adobe débranche la prise. Adobe ne semble tout simplement pas obtenir (ou se soucier de) la 3D, malgré le fait qu'il continue d'acheter des outils 3D importants, tels que Substance. Bref, Adobe. *Soupir*. *Double soupir*.

Malgré tout cela, et comme nous attendons toujours une solution humanoïde complète de Unity (post-acquisition de Ziva/Weta), nous devrons utiliser Mixamo pour l'instant.

Mixamo est en fait deux choses : un outil d'auto-rigging et une bibliothèque de mouvements animés (idle, marche, saut, danse, etc.). L'idée originale de Mixamo était d'utiliser l'IA pour automatiquement faire des "rig" de personnages 3D, supprimant ainsi l'une des étapes les plus fastidieuses de la transformation d'une forme humanoïde en un personnage pour les jeu ou récits interactives. La plupart des gens utilisent la bibliothèque, comme nous le ferons dans ce tutoriel. Mais l'outil de "rigging" automatique est la partie magique et mérite d'être mentionné. Cette fonction de rig automatique vous permet de :

1. Créez une forme 3D dans l'outil de votre choix. Cette forme 3D (ou `mesh`) doit vaguement ressembler à un humanoïde avec des bras, des jambes, un torse, une tête, et être positionnée en "T-Pose" avec les bras écartés de chaque côté, loin du torse
2. Téléchargez ce personnage sur Mixamo
3. Après environ une minute, il aura généré une marionnette "rigged" en 3D entièrement animée que vous pouvez télécharger
4. Vous pouvez importer et contrôler ce personnage dans Unity ou Unreal

Aujourd'hui, la plupart des gens utilisent Mixamo comme une bibliothèque de personnages et d'animations téléchargeable gratuitement, sans se rendre compte qu'il peut également être utilisé pour "auto-rigging" vos propres personnages faits à la main. Il existe même un outil de plug-in Mixamo Blender qui vous permet d'auto-riger vos modèles Blender en utilisant le système Mixamo directement depuis le logiciel, mais cela sort du cadre de notre tutoriel (cf. [Mixamo Addon for Blender](https://www.youtube.com/watch?v=wYqJ7AyEuhc)).

### Navigateur Chrome
Nous utiliserons Mixamo entièrement via leur site Web. Pour l'instant, le seul navigateur qui semble fonctionner avec est [Google Chrome](https://www.google.com/chrome/). Oui oui, nous le savons : Chrome est une bête qui aspirera votre batterie à sec. Néanmoins, vous devrez probablement utiliser Chrome.

### Login
Si vous avez déjà un compte Adobe, commencez par (yellow: Login) sur le site Web de Mixamo avec votre compte, ou (highlight:fuchsia text:`Sign Up`) pour un nouveau compte. L'utilisation du site Mixamo est (pour l'instant) gratuite.

(image:mixamo-sign-in.jpg)

### Character
Il existe deux sections principales sur le site Web de Mixamo : (highlight:orange text:`Characters`), où vous (highlight:purple text:`choisir`) un personnage ou (highlight:blue text:`téléchargez`) le vôtre, et (highlight:red text:`Animations`) où vous appliquez des animations à votre personnage actuellement sélectionné. Nous allons commencer par sélectionner un personnage.

(image:mixamo-select-character.png)

Voici (highlight:purple text:`Louise`). Louise porte un costume. Avec Louise, j'ai volontairement sélectionné une femme d'affaires assez discrète. Louise porte des talons et sait marcher avec. Louise fait le travail. En dehors de Louise et de quelques-uns de ses collègues, vous trouverez toutes les variantes de filles Manic Pixie nymphette girls sexualisées, des dérivations de mecs blancs et de tout autre [tropes de jeux vidéo surmenés](https://feministfrequency.com/video-series/) que vous attendez probablement dans une collection de personnages. Bonne chance. Encore une fois, si vous voulez passer à des tropes obsolètes, vous devrez soit concevoir le vôtre (cf. Blender, ci-dessus) ou utiliser un logiciel comme [Character Creator](https://www.reallusion.com/character-creator/) (cf. ci-dessus) et travaillez toutes sortes de magie de curseur inclusive.

Pour l'instant, Louise n'est pas animée. Comme vous pouvez le voir au bas de cette fenêtre, il y a actuellement (highlight:green text:`0/0`) `frames` pour que Louise fasse son truc. Elle est coincée dans la `T-Pose`, qui est une position par défaut d'animation 3D qui montre clairement (surtout à l'ordinateur) quelles parties du corps sont attachées à quoi. En éloignant les bras du torse, on risque moins dans l'ordinateur de confondre les parties du maillage 3D appartenant aux bras et les parties appartenant au corps.

### Animation
Maintenant que vous avez choisi votre personnage, appuyez sur l'onglet (highlight:red text:`Animations`) pour sélectionner une animation en boucle pour elle. Je commence toujours par rechercher une bonne animation (highlight:purple text:`idle`) et je sélectionne généralement un mouvement inactif subtil afin d'avoir une idée des nuances du personnage. Une animation « inactive » est une animation en boucle du personnage au repos : vivant, animé, respirant, prêt à l'action, mais pas encore engagé. Une fois que vous avez (highlight:blue text:`sélectionné votre animation`), vous devriez maintenant voir un certain nombre de (highlight:green text:`frames`) pour cette séquence d'animation, et l'animation devrait jouer en boucle.

(image:mixamo-select-animation.png)

### ♫ The Knee bone is connected to the thigh bone ♫
Si vous voulez mieux comprendre le fonctionnement de ces animations humanoïdes 3D, sélectionnez l'icône (highlight:fuchsia text:`skeleton view`) qui vous montrera le squelette normalement invisible `rig` qui déforme le maillage 3D, à peu près de la même manière les os (et les muscles) contrôlent la forme de notre corps. Cette image rudimentaire vous aidera également à comprendre comment les animations fonctionneront plus tard dans le système d'animation Unity « Mecanim »: ce système de `rig` avec des « os » est ce qui permet à un personnage animé de passer de manière transparente d'une pose ou d'un mouvement à un autre, ainsi que de s'adapter (dans certaines limites) à différentes longueurs et hauteurs de corps. Vous devriez maintenant voir vos os animés sans peau, ce qui signifie techniquement sans « maillages 3D », « textures » ou « matériaux ».

(image:mixamo-skeleton-view.jpg)

Ces « os » sont les positions réelles d'un véritable humain se déplaçant dans l'espace physique, enregistrées par un système de capture de mouvement au fil du temps, image par image, et maintenant lues dans Mixamo. Cet enregistrement à partir d'un système de capture de mouvement n'est rien d'autre qu'un enregistrement des positions et des rotations `x`/`y`/`z` de ces os au fil du temps. Ces animations n'ont même pas besoin d'enregistrer d'attributs physiques autres que ces positions et rotations `x`/`y`/`z`. L'animation 3D finale nécessitera d'injecter ces os invisibles dans le « maillage » 3D d'un personnage et de permettre à ces os de déplacer les sommets du modèle comme s'il s'agissait d'une peau souple sur un corps humain.

### Télécharger
Une fois que nous avons appliqué un (highlight:red text:`animation`) à notre (highlight:orange text:`character`), nous sommes maintenant prêts à (yellow: download) les deux et à les importer comme une seule entité dans l'Unité. Dans la fenêtre des paramètres de téléchargement, vous devrez sélectionner (yellow: FBX for Unity) comme format. Vous pouvez laisser les autres paramètres seuls (`avec habillage`, `30 images par seconde`, `pas de réduction d'images clés`), puis (highlight:brown text:`télécharger`) le fichier.

(image:mixamo-download-settings.png)

Ce fichier au format `FBX` téléchargé aura généralement un nom assez illisible. Dans mon cas, elle a été nommée (highlight:sky text:`Ch07_nonPBR@Idle.fbx`). Mais comme elle s'appelle Louise, j'ai décidé de lui donner le nom de fichier le plus approprié (highlight:sky text:`Louise-Idle.fbx`).

(image:mixamo-file-renamed.jpg)

### Importer
Il existe plusieurs façons d'importer un fichier dans Unity. Le plus simple est probablement de simplement faire glisser le fichier `.fbx` dans le dossier `Assets` de votre fenêtre (highlight:green text:`Project`).

(image:unity-drag-drop.jpg)

Assurez-vous que votre dossier `Assets` est bien organisé, avec des noms clairs : les projets dans Unity peuvent rapidement devenir incontrôlables - gardez vos noms simples. Ici, j'ai créé un dossier nommé `Models` (majuscule `M`, pluriel `s`), et à l'intérieur de ce dossier se trouve un sous-dossier nommé `Louise` qui contiendra toutes les informations du modèle la concernant : matériaux, textures, animations , etc.

Si vous sélectionnez votre modèle importé et regardez son `Inspector`, vous verrez que (highlight:orange text:`télécharger`) n'a été importée avec aucun matériau qui lui a été appliqué. Louise, malheureusement, est toute grise. Rien de mal avec le gris, mais nous nous attendions à un costume bleu foncé. Nous corrigerons cela dans un instant. Nous donnerons également à notre animation `Idle` un meilleur nom que son nom par défaut actuel (highlight:red text:`mixamo.com`). Si vous ne voyez pas votre personnage `Aperçu`, essayez de cliquer sur (highlight:orange text:`lignes grises horizontales`) en bas de l'inspecteur, ou cliquez sur (highlight:orange text:`trois points`) dans le coin inférieur droit de l'`Inspecteur` et choisissez `Convert to Floating Window`.

(image:unity-model-import-missing-materials.png)

### Paramètres du modèle
Comme vous pouvez le voir ci-dessous, il y a * beaucoup * de paramètres possibles pour un modèle, ce qui peut sembler effrayant au premier abord. Notez qu'il y a quatre onglets : (highlight:fuchsia text:`Model`), (highlight:green text:`Rig`), (highlight:red text:`Animation`) et (highlight:purple text:`Materials`).

- `Modèle` traite du maillage 3D (c'est sa forme) et de divers paramètres liés au maillage (qualité, compression, échelle, etc.)
- `Rig` vous permet d'importer ou de créer un rig squelette qui déplacera le maillage 3D
- `Animation` est l'animation du point clé de la plate-forme squelette. Vous pouvez renommer, affiner et sélectionner les codes temporels des différentes animations du personnage
- Les `Materials` sont l'apparence du personnage : les couleurs, les textures et les shaders qui définissent l'apparence de la peau/des vêtements du personnage

Au fil du temps, vous verrez éventuellement que chaque section se décompose parfaitement en aspects spécifiques de ces quatre concepts. Tous les quatre sont essentiels au fonctionnement des personnages 3D dans Unity. Vu le nombre de paramètres, nous ne sélectionnerons ici que l'essentiel, afin de limiter au maximum les soucis effrayants des boutons *("à quoi servent tous ces boutons !?")*.

(image:unity-model-import-settings.png)

Dans l'onglet (highlight:fuchsia text:`Model`), nous allons désactiver les options (highlight:fuchsia text:`Cameras`) et (highlight:fuchsia text:`Lights`). Nous ne créons pas un packshot de produit : nous créons un environnement interactif en temps réel à l'intérieur d'Unity qui utilisera sa propre caméra et son propre système d'éclairage. Il y a beaucoup d'autres options utiles dans cet onglet, mais pour l'instant gardons les choses simples et ignorons toutes les autres. Pour appliquer les modifications que vous apportez, n'oubliez pas de cliquer sur le bouton `Apply` en bas de cette fenêtre.

Dans l'onglet (highlight:green text:`Rig`), sélectionnez le type (highlight:green text:`Humanoid`), ce qui signifie que nous allons animer les os d'une créature à deux pattes (Louise est un humanoïde) avec deux bras et une tête, ressemblant plus ou moins à une créature de forme humaine. Nous devons également indiquer à Unity (highlight:green text:`Create from this model`) pour construire notre avatar humanoïde à partir de la forme décrite dans ce fichier. Un `avatar` est comme une marionnette que vous pouvez contrôler avec diverses animations et peut même se diviser en différentes sous-sections d'animations avec une animation contrôlant la tête, tandis que l'autre contrôle les jambes. En transformant votre modèle 3D en un `avatar` semblable à une marionnette, vous pouvez passer plus élégamment d'une animation à une autre grâce à l'interactivité. N'oubliez pas d'appliquer vos modifications lorsque vous avez terminé.

Dans l'onglet (highlight:red text:`Animation`), nous nous assurons que l'option (highlight:red text:`Import Animation`) est sélectionnée. Plus bas, donnons-lui un meilleur nom : ici, j'ai nommé l'animation « (highlight:red text:`Idle`) ». Je me suis également assuré d'activer l'option (highlight:red text:`Loop Time`). Vous ne pouvez pas le voir dans la capture d'écran ci-dessus, mais il y a encore un autre bouton `Apply` sur lequel vous devez appuyer pour valider tous ces changements.

Enfin, rendons à Louise ses couleurs et ses matières. Sélectionnez l'onglet (highlight:purple text:`Materials`), puis sélectionnez l'onglet (highlight:purple text:`Extract Textures`). Cela nous demandera de sélectionner un dossier dans notre Unity pour projeter d'extraire les vêtements et les textures de peau de Louise. Comme vous pouvez le voir dans le dossier `Assets` de mon `Project`, j'ai sélectionné le dossier (highlight:purple text:`Louise`) pour ces fichiers extraits. Nous ferons ensuite de même pour le bouton (highlight:purple text:`Extract Materials`) : assurez-vous d'enregistrer ces matériaux dans le même dossier que votre modèle. Unity préfère avoir importé des matériaux dans le même dossier que le fichier `.fbx` de votre modèle. Vous pouvez également les extraire dans un dossier spécial "Materials", mais nous n'aborderons pas cela pour le moment. Pour faire simple, extrayez simplement vos textures et matériaux dans le même dossier que votre modèle. Assurez-vous d'appliquer ces modifications et vous devriez maintenant voir Louise avec sa couleur de peau et sa couleur de vêtements retrouver leur apparence normale.

### Configuration de l'avatar
Si vous voulez jouer avec le système des (highlight:orange text:`avatar`), sélectionnez l'onglet (highlight:green text:`Rig`) ci-dessus et cliquez sur le bouton (highlight:orange text:`Configurer`). Cela ouvrira la fenêtre (highlight:blue text:`Configuration de l'avatar`) et placera votre avatar dans la `T-Pose`. Essayez de jouer avec les options "Muscles et paramètres" pour voir dans quelle mesure votre avatar réagit à son équipement. Une fois que vous avez fini de configurer votre avatar, vous pouvez revenir à l'onglet précédent (highlight:green text:`Rig`) avec le bouton (highlight:brown text:`Terminé`) en bas à droite de l'« Inspecteur ».

(image:unity-avatar-configuration.png)

### Textures opaques
Un problème avec les matériaux Mixamo est qu'ils sont mal configurés dans Unity avec des normales inversées, ce qui signifie que nos personnages ressemblent à d'étranges monstres à peau inversée. Pour mon modèle importé Louise, ses vêtements étaient bien, mais ses cheveux étaient bizarrement configurés. Une solution simple à ce problème consiste à sélectionner notre matériau extrait (highlight:purple text:`Ch07_hair`) et de changer son `Rendering Mode` en (highlight:orange text:`Opaque`). Louise devrait maintenant avoir des cheveux normaux.

(image:unity-model-fix-opacity-bug.png)

### Game Object
Maintenant que nous avons correctement configuré notre modèle et corrigé l'étrange bogue du matériau, nous pouvons faire glisser Louise dans notre (highlight:brown text:`Heirarchy`) afin qu'elle apparaisse dans la scène. Je l'ai placée au centre de la scène et je l'ai tournée (highlight:pink text:`180°`) autour de l'axe `Y` afin qu'elle soit face à la caméra. J'ai aussi rapproché la caméra d'elle pour mieux la voir.

(image:unity-add-animation-to-animator.png)

### Animator
Si vous jouez à votre jeu maintenant, vous ne verrez pas encore l'animation que nous avons importée avec Louise. Nous devons faire glisser l'animation (highlight:green text:`Idle`) du dossier `Assets` de notre fenêtre `Project`, directement sur notre (highlight:brown text:`Game Object`) qui se trouve maintenant dans notre `Scene` et Vues `Heirarchy`. Cela ajoutera l'animation (highlight:green text:`Idle`) à Louise (highlight:sky text:`Animation Controller`) où elle devrait être automatiquement sélectionnée comme animation par défaut sur (highlight:red text:`Entry`) dans le jeu.

Si vous appuyez maintenant sur le bouton `Play`, vous devriez voir Louise respirer via sa séquence d'animation "Idle" en boucle.

(unity:louise width:640 height:400)