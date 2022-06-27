### Gaze
In the previous chapter, we learned to create visual scripts that react to our mouse. But this is a virtual reality headset tutorial. Desktop mice do not exist in VR. I am not suggesting that VR suffers from *musophobia*: [the mouse is an amazing invention](https://www.youtube.com/watch?v=yJDv-zdhzMY), just not in a 3D VR context; mice are designed for moving on 2D surfaces. Instead we should be interacting with something more 3D-virtual-reality-ish.

One of the most obvious forms of interaction we can design in VR is the gaze: we are wearing a headset, meaning that there is already an implicit gaze. The problem with this approach is that there is a wide field of view and our players can be looking at many different things inside of this field of view. So you need to be smart when you are designing interactions around your gaze: think big targets for the player's gaze. Despite this fundamental problem, it is nevertheless a simple concept to understand and often a good starting point for designing simple interactions in virtual reality without getting bogged down by complicated controller setups.

At the [Media Design Master](https://www.hesge.ch/head/en/programs-research/master-arts-media-design) program at the [HEAD – Genève](https://www.hesge.ch/head/en) we have built a lot of projects with VR, AR, XR, and [whatever realities](https://www.youtube.com/watch?v=FVJqeu_HfSA) you want to add to that list. In 2021, my colleagues [Marion Bareil](https://tourmaline-studio.com/fr#about) and [Pierre Rossel](https://github.com/prossel/) developped a series of projects with our students exploring how you could interact solely with your gaze inside of a VR world: cf. [Imagining the City of Tomorrow](https://www.hesge.ch/head/en/project/vr-workshop-imagining-city-tomorrow). The following project by Alejandra Oros shows one such interaction using this modality:

(vimeo: 568883212)

For a recent class we taught together, Pierre Rossel adapted his gaze-detection approach to a simple series of scripts built with visual scripting: [VS Gaze Detector](https://github.com/prossel/VS-gaze-detector). We will now use these scripts to add gaze interactions to Unity.

### New Project
In my Unity Hub, I've created a new 3D project named (highlight:orange text:`Gaze`) but you can call yours whatever you want. I'm using (highlight:cyan text:`Unity 2021.3`); if you are using another version of Unity, these instructions should still work fine as long as you are using at least `Unity 2021.1` or later.

![Unity Hub - New Project](hub-new-project-gaze.png)

### New Materials
Similar to the last tutorial, I've created a new (highlight:purple text:`Materials`) folder, and added ((highlight:red text:` + `)) three new (highlight:yellow text:`Materials`) to this folder. I have given my materials three distinct (highlight:green text:`colors`) and named them (highlight:yellow text:`Hot`), (highlight:yellow text:`Cold`), and (highlight:yellow text:`Default`). I have also created an empty (highlight:fuchsia text:`Scripts`) folder.

![New Materials](new-materials-hot-cold-default.jpg)

Let's create a new ((highlight:red text:` + `)) (highlight:sky text:`Cube`) and (highlight:blue text:`apply`) the (highlight:yellow text:`Default`) material to it.

![Default Cube](new-cube-default-material.png)

Make sure to add a (highlight:brown text:`Script Machine`) to your (highlight:sky text:`Cube`) set to `Graph`. In the future, this `Script Machine` will detect whenever the player is looking at it — but now its contents will remain empty. Once this (highlight:sky text:`Cube`) is ready with an empty (highlight:brown text:`Script Machine`) graph, we can import the `Gaze Detection` package to animate the object.

### Import Unity Package
Go to Pierre Rossel's [VS Gaze Detector](https://github.com/prossel/VS-gaze-detector) page on Github, and click on the [Latest Release](https://github.com/prossel/VS-gaze-detector/releases/tag/v1.3.0) button. On this page, find the (highlight:mud text:`VSGazeDetector.unitypackage`) and download the file onto your computer.

![VSGazeDetector Latest Release](vs-gaze-detector-release-latest.png)

Once you have downloaded this file, you should see a (highlight:mud text:`VSGazeDetector.unitypackage`) file ready for installation. First, make sure your Unity project is already open, then double-click on this package to begin the installation process. You should see a window open up inside of Unity, with a list of all the files that will be installed into your project. You can (highlight:green text:`import`) all of these files, including a handy tutorial scene that Pierre has prepared for you to demonstrate his tool. If you want a more minimal installation, you can select just the (highlight:pink text:`required scripts`), as I have done in the illustration below. Either method will work for the following steps.

![Install VSGazeDetector](import-vs-gaze-detector.png)

When Unity has finished importing these scripts, you should see them inside your project folder.

