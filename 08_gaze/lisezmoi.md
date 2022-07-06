### Gaze
L'une des formes d'interaction les plus évidentes avec lesquelles nous pouvons concevoir nos expériences VR est le regard : nous portons déjà un casque, ce qui signifie qu'il y a par défaut un regard implicite. Compte tenu de l'offre actuelle d'expériences VR, je dirais que le regard est un mode d'interaction sous-développé. Ce didacticiel explorera donc la détection de l'endroit où nous regardons - au moins dans un sens général - dans notre champ visuel immersif à 360°.

*Attention* : concevoir des interactions autour du regard du joueur peut être problématique. D'une part, il y a un large champ de vision et nos joueurs regardent potentiellement beaucoup de choses différentes à l'intérieur de ce champ de vision. Vous devez être intelligent lorsque vous concevez des interactions autour du regard. Pensez *grandes cibles*. Mais surtout, on ne regarde pas les choses de la même façon qu'on les touche, et fixer un objet des yeux pour l'activer est un geste inélégant, souvent physiquement inconfortable. Lorsque je dois fixer un objet pour l'activer, j'ai rapidement l'impression d'incarner Cameron Vale dans (wikipedia:Scanners language:fr) avec ma tête sur le point d'[exploser](https://www.youtube.com/watch?v=YI3NoBeNwfk).

(youtube: 7zKJQeYhhK0)

Malgré ces problèmes fondamentaux, la détection du regard d'un utilisateur est néanmoins un concept simple à comprendre et souvent un bon point de départ pour concevoir des interactions simples en réalité virtuelle sans s'enliser dans des configurations de contrôleur compliquées. Faites juste attention à ne pas [faire fondre](https://www.youtube.com/watch?v=Np10WlC9iDk) le cerveau de votre joueuse.

Au programme [Media Design Master](https://www.hesge.ch/head/en/programs-research/master-arts-media-design) à la [HEAD – Genève](https://www.hesge.ch/head/en) nous avons construit beaucoup de projets avec VR, AR, XR, et [quelques réalités qui restent encore à déterminer](https://www.youtube.com/watch?v=FVJqeu_HfSA). En 2021, mes collègues [Marion Bareil](https://tourmaline-studio.com/fr#about) et [Pierre Rossel](https://github.com/prossel/) ont développé une série de projets avec nos étudiant•e•s explorant comment vous pourriez interagir uniquement avec votre regard à l'intérieur d'un monde VR : cf. [Imaginer la ville de demain](https://www.hesge.ch/head/en/project/vr-workshop-imagining-city-tomorrow). Le projet suivant d'Alejandra Oros montre une telle interaction utilisant cette modalité.

(vimeo: 568883212 width:500vw height:500vw)

Pour un cours récent que nous avons enseigné ensemble, Pierre Rossel a adapté cette approche de détection du regard en une série de scripts relativement simples et construits avec des scripts visuels : [VS Gaze Detector](https://github.com/prossel/VS-gaze-detector). Nous allons maintenant utiliser ces scripts pour ajouter des interactions de regard à Unity.

### New Project
Dans mon Unity Hub, j'ai créé un nouveau projet 3D nommé (highlight:orange text:`Gaze`) mais vous pouvez appeler le vôtre comme vous voulez. J'utilise (highlight:cyan text:`Unity 2021.3`); si vous utilisez une autre version de Unity, ces instructions devraient toujours fonctionner correctement tant que vous utilisez au moins `Unity 2021.1` ou une version ultérieure.

![Unity Hub - New Project](hub-new-project-gaze.png)

### Nouveaux matériaux
Tout comme pour le tutoriel précédent, j'ai créé un nouveau dossier (highlight: purple text:`Materials`) et ajouté ((highlight:red text:` + `)) trois nouveaux (highlight:yellow text:`Materials`) à ce dossier. J'ai donné à mes matériaux trois éléments distincts (highlight:green text:`colors`) et les ai nommés (highlight:yellow text:`Hot`), (highlight:yellow text:`Cold`) et (highlight:yellow text:` Par défaut`). J'ai également créé un dossier vide (highlight:fuchsia text:`Scripts`).

![Nouveaux matériaux](new-materials-hot-cold-default.jpg)

Créons un nouveau ((highlight:red text:` + `)) (highlight:sky text:`Cube`) et (highlight:blue text:`appliquer`) le matériau (highlight:yellow text:`Default`).

![Cube Default Material](new-cube-default-material.png)

Ajoutez un (highlight:brown text:`Script Machine`) vide à votre (highlight:sky text:`Cube`) défini sur `Graph`. À l'avenir, cette `Script Machine` détectera chaque fois que le joueur la regardera - mais pour l'instant, son contenu restera vide. Une fois que ce (highlight:sky text:`Cube`) est prêt avec un graphique vide (highlight:brown text:`Script Machine`), nous pouvons importer le package `Gaze Detection` pour animer l'objet.

### Import Unity Package
Rendez-vous sur la page [VS Gaze Detector](https://github.com/prossel/VS-gaze-detector) de Pierre Rossel sur Github, et cliquez sur [Latest Release](https://github.com/prossel/VS-gaze-detector/releases/tag/v1.3.0). Sur cette page, trouvez le (highlight:mud text:`VSGazeDetector.unitypackage`) et téléchargez le fichier sur votre ordinateur.

![VSGazeDetector Latest Release](vs-gaze-detector-release-latest.png)

Une fois que vous avez téléchargé ce fichier, vous devriez voir un fichier (highlight:mud text:`VSGazeDetector.unitypackage`) prêt à être installé. Tout d'abord, assurez-vous que votre projet Unity est déjà ouvert, puis double-cliquez sur ce package pour lancer le processus d'installation. Vous devriez voir une fenêtre s'ouvrir dans Unity, avec une liste de tous les fichiers qui seront installés dans votre projet. Vous pouvez (highlight:green text:`Importer`) tous ces fichiers, y compris une scène de didacticiel pratique que Pierre a préparée pour vous afin de démontrer son outil. Si vous souhaitez une installation plus minimale, vous pouvez sélectionner uniquement les (highlight:pink text:`scripts requis`), comme je l'ai fait dans l'illustration ci-dessous. L'une ou l'autre méthode fonctionnera pour les étapes suivantes.

![Install VSGazeDetector](import-vs-gaze-detector.png)

Lorsque Unity a fini d'importer ces scripts, vous devriez maintenant les voir dans votre dossier (highlight:orange text:`Project`).

![Project folder](project-vs-gaze-detector-scripts.png)

Nous sommes maintenant prêts à commencer à utiliser ces scripts dans notre projet.

### Caméra Raycast
Dans un moteur de jeu 3D comme Unity, un (highlight:fuchsia text:`Ray`) est une ligne droite invisible qui jaillit dans l'espace 3D. La principale raison pour laquelle cette ligne existe est de détecter s'il y a des objets qui entrent en collision avec elle. Les collisions peuvent avoir lieu n'importe où le long de ce chemin (highlight:fuchsia text:`Ray`). Les raycasts peuvent donc être utilisés pour détecter si un monstre repère notre joueur : par exemple, chaque fois que nous franchissons cette ligne invisible, le dragon géant se lèvera et commencera à tirer dans notre direction. Nous pouvons également attacher l'un de ces rayons invisibles au centre de notre (highlight:red text:`Appareil photo`) et détecter si un objet entre dans notre « regard ».

Dans l'illustration ci-dessous, vous pouvez voir plusieurs lignes blanches s'étendre à partir de la caméra. Ce cône pyramidal carré décrit ce qu'on appelle le (wikipedia:frustrum language:fr keyword:Tronc_(géométrie)): il s'agit d'une représentation géométrique du champ de vision de la caméra et s'étend vers l'extérieur à partir de la perspective du (highlight:red text:`Camera`). Au centre de ce frustrum, nous pouvons voir un seul blanc plus brillant (highlight:fuchsia text:`Ray`) s'étendant sur plusieurs unités, et dans l'illustration ci-dessous croise actuellement le cube devant lui.

![Gaze Raycaster Camera](gaze-raycaster-mouse-camera.png)

Le [VS Gaze Detector](https://github.com/prossel/VS-gaze-detector) de Pierre Rossel contient un tel objet Raycast que vous pouvez connecter à votre (highlight:red text:`Camera`). Ouvrez le dossier `VisualScripts` de (highlight:orange text:`VSGazeDetector`) et recherchez les scripts (highlight:purple text: `GazeRaycaster`) et (highlight:blue text:`MouseLookAround`). Faites glisser ces deux éléments sur votre (highlight:red text:`Caméra`) principale. Le script (highlight:blue text:`MouseLookAround`) est facultatif, mais nous aidera à tester notre script en vous permettant de simuler des mouvements de caméra en utilisant uniquement votre souris.

Appuyez sur (highlight:green text:`Play`) et vous devriez maintenant voir un aperçu dans la vue de la scène d'un (highlight:fuchsia text:`Ray`) qui sort de votre appareil photo lorsque vous déplacez votre souris :

![Gaze Raycast](gaze-raycast.gif)

Jusqu'à présent, cela ne fait rien de significatif. Il n'y a actuellement aucune instruction dans notre cube pour décrire comment il doit se comporter chaque fois que ce (highlight:fuchsia text:`Ray`) se croise. Ajoutons ce comportement maintenant.

### Script Graph
Voici une capture d'écran d'un nouveau (highlight:blueish text:`Script Graph`) que j'ai ajouté au (highlight:pink text:`Cube`). Notez que nous plaçons ce comportement sur le *cube* qui *reçoit* le regard, et non sur la `Camera` qui envoie la sonde (highlight:fuchsia text:`Ray`). Cela nous permettra potentiellement d'ajouter de multiples comportements sur des objets d'acabit différents, chacun pouvant interpréter à sa manière ce que signifie recevoir le regard du joueur.

![Cube New Script Graph](gaze-cube-script-graph.png)

Nous avons créé quatre nœuds dans ce graphique, en utilisant nos nouveaux événements que nous avons importés avec le package `VsGazeDetector` ci-dessus.
- L'événement (highlight:mud text:`OnGazeEnter`) est déclenché chaque fois que le `Ray` entre en collision avec notre (highlight:pink text:`Cube`). Chaque fois que cette interaction se produit, le (highlight:blueish text:`Script Graph`) définit le `Material` du Cube sur le matériau `Cold` que nous avons créé plus tôt dans ce didacticiel. Comme vous pouvez le voir dans l'illustration ci-dessous, cette interaction rend le cube bleu.
- L'événement (highlight:brown text:`OnGazeExit`) est déclenché chaque fois que ce `Ray` sort en collision avec notre (highlight:pink text:`Cube`). Cela change le `Material` de l'objet à `Default`.
- L'événement (highlight:yellow text:`OnGazeStay`) est déclenché de manière répétitive tant que nous continuons à interagir avec notre (highlight:pink text:`Cube`). Ce concept de `Stay` (*rester*) signifie "tant que ce rayon reste en interaction avec cet objet". Cette action `Stay` déclenche l'action `Rotation` et se répète constamment, pour chaque image, environ soixante fois par seconde tant que nous continuons à regarder l'objet.
- L'événement (highlight:sky text:`OnGazeTimer`) est très pratique et se déclenche chaque fois que nous restons à regarder cet objet plus longtemps qu'un nombre défini de secondes. Ici, nous avons défini cette valeur (highlight:sky text:`Delay`) sur (highlight:sky text:`2`) secondes. Lorsque cette action se déclenche, nous remplaçons le `Material` du (highlight:pink text:`Cube`) par la couleur `Hot` créée plus tôt dans ce didacticiel. Dans l'illustration ci-dessous, le cube devient rouge chaque fois que le joueur le regarde pendant plus de `2` secondes. Comme nous n'avons pas besoin de changer constamment cette couleur, nous avons laissé son option `Repeat` décochée.

![Gaze Raycast interactions with Cube](gaze-raycast-change-material.gif)