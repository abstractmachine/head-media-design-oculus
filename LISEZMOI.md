Ce tutoriel sur la création d'un projet Unity + Oculus a été crée pour le [Master Media Media](https://www.hesge.ch/head/en/programs-research/master-arts-media-design) de la HEAD – Genève.

- [Introduction](#Game-Engine)
- [Exemples](#Exemples)
- [Installation](00_installation)

Ce didacticiel est disponible à la fois sur les [tutorials](https://abstractmachine.net/tutorials) du site d'[abstractmachine](https://abstractmachine.net/tutorials) et sur le [abstractmachine GitHub repository](https://github.com/abstractmachine/head-media-design-oculus).

### Game Engine

[Unity](https://unity.com/) est un « moteur de jeu », utilisé pour créer des jeux 2D, 3D, de réalité augmentée et de réalité virtuelle, ainsi que des expériences interactives en général. Ses concurrents les plus proches sont [Unreal Engine](https://www.unrealengine.com/en-US/) et le projet open source plus modeste [Godot](https://godotengine.org).

Les moteurs de jeu sont des outils et/ou des collections de code qui ont été conçus pour faciliter la création d'un jeu, plutôt que de le coder vous-même à partir de zéro. Les moteurs de jeu ont déjà résolu toutes les bases techniques nécessaires pour importer et manipuler des images, des modèles 3D, des animations, des rigs, des textures, des matériaux, des sons et d'autres actifs qui composent votre jeu. Les moteurs de jeu résolvent également le problème de savoir comment développer le comportement et la logique du jeu, souvent en mettant en œuvre diverses solutions basées sur le code et la programmation visuelle pour le comportement interactif et les aspects narratifs d'un jeu.

Alors qu'un moteur de jeu vous oblige à apprendre le moteur lui-même, il vous protège d'une grande partie des tracas liés à l'apprentissage du développement sur toutes les myriades de plates-formes sur lesquelles vous souhaitez installer votre jeu. Voici, par exemple, quelques-unes des plates-formes sur lesquelles vous pouvez déployer/distribuer un jeu réalisé avec Unity :

- WebGL
- Windows
- macOS
- Linux
- iOS/iPadOS
- Android
- Playstation
- XBox
- Nintendo Switch
- Steam Deck
- Oculus
- Vive
- (...)

Comme vous pouvez le voir, la liste est longue et même incomplète. L'idée est donc qu'au lieu d'avoir à apprendre les détails techniques de chacune de ces plates-formes, tout ce dont vous avez besoin pour créer votre jeu est d'apprendre Unity et l'outil se chargera du reste.

### Exemples

La liste des jeux réalisés avec Unity est presque infinie. Voici quelques démonstrations Unity de jeux créés avec l'outil, ainsi que les bandes-annonces de quelques-uns des jeux les plus célèbres créés avec cet outil.

- [Unity GDC 2021 Showcase](https://www.youtube.com/watch?v=na7EMenl2lY)
- [Unity AR & VR Games Showreel 2019](https://www.youtube.com/watch?v=zNMlglRyRSo)
- [Unity GDC 2016 Showreel](https://www.youtube.com/watch?v=8lWpnvNxs8k)
- [Beat Saber](https://www.youtube.com/watch?v=vL39Sg2AqWg)
- [Superhot](https://www.youtube.com/watch?v=A1jothqmqHw)
- [Return of the Obra Dinn](https://www.youtube.com/watch?v=ILolesm8kFY)
- [Firewatch](https://www.youtube.com/watch?v=HdUYYnfRdl8)
- [Monument Valley](https://www.youtube.com/watch?v=tW2KUxyq8Vg)
- [Inside](https://www.youtube.com/watch?v=op4G1--kb-g)
- [Cuphead](https://www.youtube.com/watch?v=NN-9SQXoi50)
- [Far: Lone Sails](https://www.youtube.com/watch?v=_QiC8pNfYl4)
- [Sayonara Wild Hearts](https://www.youtube.com/watch?v=F-RyxYcxSQ4)
- [Kids](https://www.youtube.com/watch?v=GAyvZ22AxNw)
- [Night In The Woods](https://www.youtube.com/watch?v=Aj_rrFIWpnI)
- [Donut County](https://www.youtube.com/watch?v=NWt1GPkfzkM)
- [Reigns](https://www.youtube.com/watch?v=lcOYlTbl-as)
- [Untitled Goose Game](https://www.youtube.com/watch?v=9LL2AtHo1gk)

### Réalité Virtuelle
La réalité virtuelle en tant que concept est un vieux rêve, et comme la plupart des autres interfaces informatiques contemporaines que nous utilisons aujourd'hui, Ivan Sutherland en a construit un prototype dans les années 1960, intitulé [L'épée de Damoclès](https://en.wikipedia. org/wiki/The_Sword_of_Damocles_(virtual_reality)).

(youtube: https://www.youtube.com/watch?v=43mA_ypfwKg)

Il y a eu de nombreuses itérations entre l'épée de Damoclès et l'Oculus Quest, avec un arrêt important dans les années 1980 et [VPL Research] (https://en.wikipedia.org/wiki/VPL_Research), comme on le voit ici via le 1992 bizarrerie [Lawnmower Man](https://en.wikipedia.org/wiki/The_Lawnmower_Man_(film)) où vous verrez également leur autre invention célèbre, le "gant de données" :

(youtube: https://www.youtube.com/watch?v=zTrgHXNAs24)

Nous devrions également citer l'installation/expérience [Osmose](http://www.medienkunstnetz.de/works/osmose/) de Char Davis en 1995, qui a été la première expérience immersive qui nous a donné une idée plus complète de ce que la réalité virtuelle pourrait être en tant qu'expérience poétique pleinement intégrée et fonctionnelle :

(youtube: https://www.youtube.com/watch?v=54O4VP3tCoY)

Mais l'artiste qui nous a vraiment montré la voie de la réalité virtuelle (avec et sans casque), ainsi que de la réalité augmentée, et de tout un tas d'autres réalités qui n'ont pas encore été pleinement comprises, c'est [Jeffrey Shaw](https: //en.wikipedia.org/wiki/Jeffrey_Shaw). Si jamais il y avait un successeur au trône d'Ivan Sutherland, ce serait Jeffrey Shaw. Rendez-vous service et apprenez tout ce que vous pouvez sur Jeffrey Shaw et son travail :

(vimeo: https://vimeo.com/442537219)

Depuis ces premières expériences, il y a eu de nombreux casques, de nombreux échecs et de nombreuses itérations de réalité virtuelle totalement immersive. L'échec le plus célèbre, et pourtant le plus brillant, dans la fabrication d'un casque de réalité virtuelle a été le système [Virtual Boy](https://en.wikipedia. org/wiki/Virtual_Boy) de [Gunpei Yokoi](https://fr.wikipedia.org/wiki/Gunpei_Yokoi) :

(youtube: https://www.youtube.com/watch?v=Jjz4bls_gPs)

### Oculus
Vers 2010, [une démo de ruban adhésif](https://arstechnica.com/gaming/2012/09/virtual-realitys-time-to-shine-hands-on-with-the-oculus-rift/) nommée "Oculus Rift" a commencé à faire le tour en intégrant un grand nombre de ces idées antérieures dans un package plus petit et potentiellement commercialisable.

(youtube: https://www.youtube.com/watch?v=uzCwczY1jTM)

Pour faire court, Facebook a rapidement racheté Oculus et leur prototype, le fondateur Palmer Luckey s'est transformé à la fois en [un mème de VR pieds nus](https://knowyourmeme.com/memes/times-virtual-reality-magazine-cover) et en [un financier de trolls pro-Trump](https://www.theverge.com/2016/9/23/13025422/palmer-luckey-oculus-founder-funding-donald-trump-trolls) - oh ouais et n'oublions pas quand [Mark Zuckerberg a tapé dans les mains l'avatar de son collègue Rachel Franklin](https://www.theverge.com/2017/10/9/16450346/zuckerberg-facebook-spaces-puerto-rico-virtual-reality-hurricane) à l'intérieur d'un flux de réalité virtuelle en direct de Porto Rica et du désastre laissé par l'ouragan Maria. Plusieurs milliers de personnes sont mortes dans cette catastrophe, et l'idée était que vous pourriez mieux sympathiser avec elles si d'une manière ou d'une autre vous pouviez simplement insérer votre tête dans leur souffrance. Bon temps.

A l'écriture de ce tutoriel, Facebook a récemment changé le nom de toute leur entreprise en Meta, accompagné d'une vidéo loufoque expliquant leur vision du futur en passant par le "Metaverse".

Pour faire court, Facebook a rapidement racheté Oculus et leur prototype, le fondateur Palmer Luckey s'est transformé à la fois [a barefoot VR dork meme as ainsi qu'un [financeur de l'usine de trolls pro-Trump - oh ouais et [Mark Zuckerberg a fait un high-five à l'avatar de sa collègue Rachel Franklin dans un flux de réalité virtuelle en direct de Porto Rica et du désastre laissé par l'ouragan Maria. Plusieurs milliers de personnes sont mortes dans cette catastrophe, et l'idée était que vous pourriez mieux sympathiser avec elles si d'une manière ou d'une autre vous pouviez simplement insérer votre tête dans leur souffrance.

Au moment de la rédaction de ce tutoriel, `Facebook` a récemment changé le nom de toute leur entreprise en `Meta`, accompagné d'une vidéo loufoque expliquant leur vision du futur passant par le 'Metaverse'.

(youtube: https://www.youtube.com/watch?v=gElfIo6uw4g)

### Oculus Quest
Ce didacticiel utilise les casques [Oculus Quest](https://www.oculus.com/quest-2/) 1 et 2 comme plate-forme pour explorer la réalité virtuelle, et Unity 2021.2 pour créer le monde interactif à l'intérieur de ces casques. Bien que l'Oculus Quest ne soit pas le casque ultime de la réalité virtuelle - nous attendons toujours que quelqu'un résolve la myriade de contraintes de conception et technologiques de la réalité virtuelle - il a l'avantage d'emballer toutes les bases d'environ 2020 réalité virtuelle dans un casque entièrement autonome. Avec l'Oculus Quest, vous mettez simplement l'appareil sur votre tête et cela fonctionne ; ce qui en fait un dispositif idéal pour les expositions publiques de réalité virtuelle.

(youtube: https://www.youtube.com/watch?v=g1bq32kjOKo)

### Haïku virtuel et la ville de demain
Dès le confinement 2020, mes collègues Marion Bareil et Pierre Rossel ont conçu une série de cours ([Virtual Haiku](https://www.hesge.ch/head/projet/master-media-design-virtual-haiku) & [La Ville de Demain](https://www.hesge.ch/head/projet/workshop-vr-imaginer-ville-demain)) autour de casques de réalité virtuelle utilisant le regard des joueurs comme premier mode d'interaction. Voici quelques projets issus de ce cours :

(vimeo: https://vimeo.com/465320477)

(vimeo: https://vimeo.com/465315601)

(vimeo: https://vimeo.com/568886317)

(vimeo: https://vimeo.com/568883212)

(vimeo: https://vimeo.com/568885645)

(vimeo: https://vimeo.com/568885456)

(vimeo: https://vimeo.com/568884516)

(vimeo: https://vimeo.com/465314621)

(vimeo: https://vimeo.com/465320377)

(vimeo: https://vimeo.com/465320217)

(vimeo: https://vimeo.com/465320316)

Et voici quelques autres projets de notre [Master Media Design](https://www.hesge.ch/head/en/programs-research/master-arts-media-design) qui mettent en avant l'utilisation des casques de réalité virtuelle :

(vimeo: https://vimeo.com/210307366)
