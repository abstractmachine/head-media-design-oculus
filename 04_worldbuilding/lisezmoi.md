### Greyboxing
Construire un jeu peut être un processus complexe. Cela peut également être un processus laborieux, en particulier lorsque vous travaillez en 3D. De ce fait, de nombreuses méthodes ont vu le jour au fil des années pour concevoir des jeux et des environnements virtuels rapidement, mais surtout sous la forme d'un système modulaire pouvant (plus) facilement s'adapter au gameplay tel qu'il émerge.

Les jeux vidéo ne sont pas seulement un média audiovisuel, ce sont des espaces [affordants](https://en.wikipedia.org/wiki/James_J._Gibson) avec lesquels il faut interagir pour les percevoir. Par conséquent, vous souhaitez souvent commencer à concevoir un espace virtuel à l'aide de formes de base simples et facilement modifiables avec lesquelles vous pouvez commencer à interagir, avant d'investir du temps et de l'énergie dans le processus de modélisation long et complexe. En concevant le monde à l'aide de boîtes, de sphères, de cylindres et d'avions simples, vous pouvez rapidement vous faire une idée de votre jeu avant même d'en avoir déterminé l'apparence.

Ce processus est appelé "greyboxing", en raison de toutes les boîtes grises que vous diffusez autour de votre `Scene` au fur et à mesure que vous construisez votre jeu.

Voici une conférence de 2022 de Blake Rebouche, l'un des concepteurs d'un jeu Playstation populaire (wikipedia:Horizon Forbidden West keyword:Horizon_Forbidden_West language:fr). Dans cette conférence, il décompose toutes les différentes étapes que lui et ses collaborateurs ont traversées lors de la conception de l'une des quêtes du jeu. Notez comment il passe rapidement d'un prototype papier (cf. 05:10) à un niveau simplifié en boîte grise avec lequel les joueurs peuvent interagir en utilisant des gestes et des énigmes réduits. Ce n'est qu'après que ces principes de base ont été élaborés que l'équipe a commencé à créer des modèles, des éclairages ou des cinématiques complexes. Notez également comment ils ont largement utilisé les sessions de jeu enregistrées avec des joueurs commentant leurs expériences avec les niveaux (cf. 50:00), et sont revenus sur divers aspects repensés de leur jeu sur la base de ces commentaires.

(youtube: KxcXUYx3eLQ?t=311)

Nous avons déjà vu à quel point il est facile de créer votre scène dans Unity : ouvrez un nouveau projet ou une nouvelle scène, cliquez sur le bouton `+` dans la fenêtre `Heirarchy` et commencez à ajouter des formes de base. Vous n'avez pas besoin de coder quoi que ce soit, ni même de comprendre grand-chose sur les logiciels de modélisation, les textures, les shaders, la photogrammétrie, la retopologie ou tout autre jargon aux sonorités folles que les YouTuber 3d bros vous lancent.

![Unity Basic Shapes](unity-basic-shapes.png)

Voici quelques-unes des formes de base que vous pouvez rapidement utiliser pour créer le monde de votre jeu. Parfois, tout ce dont vous avez besoin pour avoir une idée de la taille de votre forêt est de placer quelques cylindres verts avec des sphères sur le dessus.

![Unity simple forest](unity-simple-forest.png)

Assurez-vous d'utiliser les six outils à l'intérieur de la fenêtre "Scène" pour déplacer, faire pivoter et redimensionner vos formes. Essayez également de faire glisser une forme "à l'intérieur" d'une autre forme à l'intérieur de la `Heirarchy` afin de comprendre ce qui se passe lorsque vous modifiez la `Position`, la `Rotation` et surtout les valeurs `Scale` dans l'inspecteur de ces formes `parent` ou leurs `enfant`. Regardez ce qui arrive à l'objet `enfant` lorsque vous modifiez la taille de l'objet `parent`. Ensuite, essayez de supprimer temporairement l'objet `enfant` de son `parent`, modifiez le `scale` du `parent`, puis remettez l'objet `child` à l'intérieur de l'influence de la propriété `transform` du `parent`. Ce qui se produit? Les valeurs de l'objet de jeu "enfant" restent-elles les mêmes ?

### Objet vide
Une fois que votre `Scene` commence à devenir même légèrement complexe, c'est une bonne idée de créer quelques `Empty Object` et de placer votre collection de personnages, bâtiments, obstacles et autres à l'intérieur de leur `Hierarchy`.

![Objet vide de hiérarchie d'unité](unity-heirarchy-create-empty.png)

Soyez prudent cependant avec les propriétés `Position`, `Rotation` et `Scale` de ces objets vides. Il est souvent plus facile de comprendre comment tous ces objets de jeu s'influencent mutuellement en commençant par un `Empty Object` aux coordonnées `0,0,0` et avec une `scale` de `1,1,1` avant de commencer à ajouter des enfants à cela.

![Forêt de la hiérarchie de l'unité](unity-heirarchy-forest.png)

### ProBuilder
Une fois que vous en avez marre de ces formes simplistes, mais que vous souhaitez tout de même créer rapidement les formes de base de votre monde, vous pouvez activer l'outil `ProBuilder` intégré directement dans l'éditeur Unity. Cet outil est à la fois simple et extrêmement puissant, et surtout rapide. Lorsque les *coûts* de construction de formes 3D sont faibles, vous n'hésitez pas vraiment à essayer des choses nouvelles et étranges, à les détruire toutes, puis à les reconstruire différemment dans une toute autre direction. Pour cette raison, `ProBuilder` est également un excellent outil pour les étudiants qui débutent avec la modélisation 3D et qui ne sont pas encore familiarisés avec la logique de la pensée en 3D.

(youtube: TYAYFfXg6tg)

Voici un tutoriel plus complet de l'équipe Unity sur la façon de démarrer rapidement avec les outils intégrés `ProBuilder`.

(youtube: dYBOBgfcTgY)