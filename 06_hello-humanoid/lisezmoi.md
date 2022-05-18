Let's explore animations more complex than rotating cubes. In fact, we'll be looking at one of the most potentially complex examples of `Animation` and `Animation Controller` pairings, namely the case of the `Humanoid`.

(youtube: qgJs7uluwlU)

You might have noticed that there is a new generation of 3D human characters that are appearing in video games and immersive narratives. These characters have more realistic body types, richer and more dynamic skin that reacts better to light and shadows, and they even have somewhat decent facial expressions. This last aspect — facial expressions — still needs more technical advances and better tools, but we are inching closer and closer to pseudo-cinematic experiences within real-time programmable interactive game engines.

One of the reasons for the sudden rise in quality characters, is an improvement in the tools used to build virtual humans. It is very time consuming to create people vertex by vertex in 3D modelling tools (cf. Blender, below), and then attach their 3D model `skin` to a `rig` of `bones` so that they can be animated in Unity or Unreal. Not only did we just use a lot of jargon in the previous phrase, but we also described several laborious processes. So to quicken this workflow, many humanoid generator tools have been developed.

### Character Creator & iClone
The most popular tool, and also the most expensive, is [Character Creator](https://www.reallusion.com/character-creator/) which, as it's name implies, allows you to create a fully rigged character just by moving around sliders (taller, shorter, older, younger, eye color, arm length, etc, ad nauseum). The same company also has an animation tool (that also does other stuff) called [iClone](https://www.reallusion.com/iclone/), and that too costs a lot — even with student discounts. So be careful.

(youtube:FDyvM4ciTSQ)

### MetaHuman
Another impressive tool, but that can only be used (legally) with Unreal Engine is [Meta Human](https://www.unrealengine.com/en-US/metahuman-creator). Epic has spent a lot of time, money, and communications on this tool. It is one of the many reasons people are very excited about the Unreal game engine.

(youtube:6mAF5dWZXcI)

### Ziva + Meta = Unity
Unity has also made a lot of acquisitions recently, notably [purchasing Weta Digital](https://blog.unity.com/news/welcome-weta-digital) last year, as well as [Ziva Dynamics](https://venturebeat.com/2022/01/24/unity-acquires-ziva-dynamics-and-its-character-tech/). At first glance it might appear that this is just a reactive move to Epic's advances, but many of these purchases signal that Unity is also looking bigger picture at the overall landscape of how characters, materials, and environments should interact with their tools:

(youtube: sFibYevZ-Fo)

Long story short, Unreal and Unity are in a massive battle right now, and this translates into a lot of development tools focused on sophisticated humanoids with more expressive animations than we had in the previous 30 years or so of human faces and bodies in videogames.

(youtube: eXYUNrgqWUU)

The above video is a trailer from the 2022 Game Developers Conference where Unity showed off their latest advances on these fronts. The face you are looking at is a fully digital real-time character running in Unity.

### Make Human
[Make Human](http://www.makehumancommunity.org) is not pretty like the above character tools. It even has some more-than-dubious notions ideas about race, gender, and body-types. All that said, it is open-source, so maybe-kinda-sorta the community can make it less cringey `¯\_(ツ)_/¯`? Anyway it works with the same principle of moving sliders as Character Creator, in order to adjust the body shape and height of your characters. These characters come fully rigged, and can be imported with little fanfare directly into Unity to be animated with whatever means you want.

### Blender
The most difficult solution, but also the most powerful, is to learn how to make a human from scratch using more traditional 3D modelling software such as Maya, C4D, or Blender. There are many many many tutorials out there for modelling characters, "rigging" them into controllable marionettes, and then importing them into Unity. We will not go through these solutions for this tutorial.

For example, here is a free, 9-part tutorial on creating a humanoid character in Blender, rigging it with a Blender tool called [Rigify](https://docs.blender.org/manual/en/2.81/addons/rigging/rigify.html) and then importing it into Unity: 

(youtube: U-eeKwuqN34)

One of the advantages of learning the entire modelling > rigging > animating > game engine workflow is that you can design non-standard characters without falling into the clichés of most cookie-cutter-make-me-a-human tools. Once you have learned the basics of Blender's [Rigify](https://docs.blender.org/manual/en/2.81/addons/rigging/rigify.html) system, you can even apply it to various quadriped or flying creatures, which are by the way included by default in the basic Rigify installation.

### Open Source Afro Hair Library
While you are designing your own 3D character, might I interest you in rethinking your baseline assumptions on what makes for a standard playable character? How about checking out the [OSAHL](https://afrohairlibrary.org) by [pretty darke](https://prettydarke.cool/portfolio/open-source-afro-hair-library/):

> "The Open Source Afro Hair Library is a queer, feminist, pro-black resource for 3D models of Black hair textures and styles."

(vimeo: 411452990)

### Mixamo
For this tutorial, we are going to use an older humanoid rigging and animation tool named Mixamo. It is a very easy to use tool and allows us to quickly have a humanoid character moving inside of our game or virtual reality experience.

Unfortunately this tool has suffered the opposite trajectory as Ziva Dynamics and MetaHuman. [Mixamo](https://www.mixamo.com) is [yet another](https://en.wikipedia.org/wiki/Category:Discontinued_Adobe_software) (*sigh*) one of those amazing tools that was eventually bought by Adobe, who subsequently abandoned it in development limbo where it just sits there, withering away. For now, it is still (somewhat) usable — albeit only via the Chrome browser. Since it has not evolved in years, it is probably just a matter of time before Adobe pulls the plug. Adobe just doesn't seem to get (or care about) 3D.

But since we are still waiting for a complete humanoid solution from Unity, post-Ziva/Weta acquisition, we will have to use Mixamo nevertheless.

Mixamo is actually two things: an auto-rigging tool and a library of animated movements (idle, walking, jumping, dancing, etc). The original idea of Mixamo was to use AI in order to "auto-rig" 3D characters, thereby removing one of the most tedious steps in transforming a humanoid shape into a character that we can animate in a game or interactive story. Most people use the library aspect, as will we in this tutorial. But the auto-rigging tool is the magic part, and merits mention. This auto-rigging feature allows you to:

1. Create a 3D shape in whatever tool you want. This 3D shape (or `mesh`) has to vaguely ressemble a humanoid with arms, legs, a torso, a head, and be positioned in a "T-Pose" with their arms spread out on each side, away from the torso
2. Upload this character to Mixamo
3. After about a minute it will have generated a fully animated 3D rigged marionnette that you can download
4. You can import and control this character in Unity or Unreal

Today, most people just use Mixamo as a free downloadable library of characters and animations, without realizing that it can also be used to "auto-rig" your own hand-made characters. There is even a Mixamo Blender plug-in tool that allows you to auto-rig your Blender models using the Mixamo system directly from within the software, but this is outside the scope of our tutorial (cf. [Mixamo addon for Blender](https://www.youtube.com/watch?v=wYqJ7AyEuhc)).

### Login
We will use Mixamo entirely through their website. For now, the only browser that seems to work is [Google Chrome](https://www.google.com/chrome/). If you already have an Adobe account, begin by `logging in` in to the Mixamo website with your account; or `sign up` for a new account. Use of the Mixamo website is (for now) free.

### Character
There are two main sections in the Mixamo website: `Characters`, where you chose a character or upload your own, and `Animations` where you apply animations to your currently selected character. We will begin by selecting a character.

![]()

Here I have selected the most middle-of-the-road, un-sexualized, non-white-male-dude-bro character I could find that wasn't a nymphette manic pixie girl or other overwrought videogame cliché. Again, if you want to move into more interesting humanoid territory, you'll need to either design your own (cf. Blender, above) or use software like [Character Creator](https://www.reallusion.com/character-creator/) (cf. above).
