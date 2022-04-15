Let's start animating our game objects in Unity.

### Physics | Scripts | Animation
There are many ways to get our game objects to move about. We can add physics to a game object. Or we can move an object via scripts using either `C#` code or via `visual scripting`. And finally, we can get our object to move using keyframe-based animations. Most Unity projects use some combination of these three means of moving things around. The first two subjects (physics & scripting) will be covered in future tutorials; meaning that this tutorial is dedicated to keyframe-based animations.

### Keyframes
The concept of keyframes emergerd during the industrialisation phase of animated film production in the early 20th century. As groups of animation teams became larger and larger, allowing for more complex narratives to be produced, different roles were assigned to different types of animators. Higher-level animation jobs were created (story, character design) with lower-level jobs taking care of the more tedious aspects, hence derogatory terminology such as the "dope sheet". From this taylorist mindset emerged the concept of "keyframes".

As the following documentary of Max Fleicher's studio from the 1930s explains, there are two important early stages in animated film production: (a) the creation of what they here call « key pictures », and (b) the creation of « in-between drawings » which the documentary also calls « in-betweeners » or « in-betweens »:

(youtube: RxJOw5O0h8o)

In this type of animation, the « key » frames are the important frames at the beginning and the end of the animation sequence, as well as the key visual points that mark the peaks of various movement changes of each character and the objects in the scene. These « key » images do not represent every frame of movement, just the *key* points of the movement. If you have these key points, you can more easily fill in the gaps of images *in-between* by completing the intermediary positions of the character as they move their body from key frame A to key frame B and then on to key frame C, and so on and on. The keys do not contains all animated images, the actual image-by-image changes *in-between* these key frames are drawn by the "in-betweeners" who make sure that each step of the movement is correctly drawn so that it arrives precisely at the desired "key" frame at the end of the movement.

If you want a more detailed breakdown of how this system works, here is a YouTube video that opens with a handy chart:

(youtube: d418iMMxfl8)

Many software tools use this concept of keyframes for animating an object, a character, or a graphical object. [AfterEffects](https://en.wikipedia.org/wiki/Adobe_After_Effects), [Blender](https://www.blender.org), [Cinema4D](https://www.maxon.net/en/cinema-4d), [DaVinci Resolve](https://www.blackmagicdesign.com/products/davinciresolve/) — to name just a few programs you might already have heard of — make heavy use of keyframes in their workflow.

Today we still call them keyframes, but instead of "in-betweeners" we use the term "interpolation" to describe the intermediary positions created *in between* each keyframe.

While it might not seem obvious at first, even motion capture systems integrate this concept of keyframes but expand the concept to defining each individual point that the system tracks in 3D space over time. So the system is breaking down both the *key physical joints* and attributes (arms, legs, feet, hands, fingers, but also jaw, eyes, mouth, cheeks, etc) into their separate parts, as well as tracking their *key 3D positions over time*. Software such as Unity then interpolate automatically all the *intermediary* or *in-between* positions of each joint taken from the motion capture recording. This approach is more modular and means that different parts can be modified in real-time via interactivity. I.e. by breaking down they various parts, the characters can evolve and transition from one motion captured set of keyframes to another, based on interactive input from the player. Keyframes are essential to this modularity. It might seem like an overly complicated process, but it is all built up atop this very simple concept of "keyframes" and "in-between frames".

(youtube: djvDGel7nf0?t=54)

### Animating A Cube
Ok, enough animation history. Let's animate a cube.

![Unity Red Cube](unity-cube.png)

Place a cube in your scene and give it a color to make it easily identifiable. Now let's create an `animation clip` and attach it to this cube. But before we do so, let's create a new `Animations` folder (capital `A`, plural `s` at the end) inside our `Assets` folder in the `Project` window. We will save all our files related to animation in here.

![Unity Animations Folder](unity-project-animations-folder.png)

Let's now open two new windows and attach them to our Unity editor. Open up both the `Window` > `Animation` > `Animation` and the `Window` > `Animation` > `Animator` windows and attach them to our editor.

![Unity Animation Windows](unity-animation-windows.png)

This is how I have configured my setup but you can set it up however you like.

![Unity Docked Animation Windows](unity-docked-animation-windows.png)

As you can see, I have docked my `Animator` window next to the `Scene` window tab, and `Animation` next to my `Game` window tab. This configuration allows me to look at the `Scene` while ajusting `Animation` values below it while editing the game, and then observe which `Animator` sequence is playing when my `Game` is active in that window. Again, these are just preferences, and you can configure it however you like.

As you can see in the above illustration, by selecting the `Cube` game object in our `Hierarchy`, the Unity editor will explain that it can create an `Animation Clip` and an `Animator` of that clip for you by clicking on one single `Create` button. This is very handy, so go ahead and do that, making sure to save your files in the `Animations` folder in your `Project`. I have decided to call the name of my animation "`Spin.anim`".

![Unity Animation Files](unity-animation-files.png)

When you click that button, the Unity editor does a lot of complex things for you to make your life easier. Take a look at all the things it just connected up. Inside your `Assets` folder you should now see two files: one with the name you gave your new `Animation Clip` and the other the name of the game object you had selected when you pushed the `Create` button. This second file is the `Animation Controller` which will control which animation is currently playing (or not playing). This clip has also automatically been added to a new game object component that you should now see on your `Cube` game object, entitled `Animator`. Look inside the `Inspector` window and you should see that this new relationship. If you keep your `Cube` selected and open the `Animator` window, you will also see that Unity has automatically added your new `Spin.anim` clip to the `Cube.controller` file and has been setup as your default animation that will automatically start playing upon `Entry` into the game. And finally, with your `Cube` still selected you should see that the `Animation` is waiting for you to begin animating the various properties of your `Spin` animation.

That's a whole lot of connections and relations all simplified into one single button. Since you are probably beginning, this means that there are a lot of things that you probably don't understand with all of these windows, files, components and objects.

### Animate Property
Before we explain the relationships of all these various components, let's just animate one of the properties of our cube. Make sure your Cube is selected in the hierarchy, and that the "Spin" animation clip is selected in the `Animation` window's top left corner, just underneath the `Preview` button. Now select which `Property`, or properties, you wish to animate. Here I have decided to animate the cube's `Transform` > `Rotation`.

![Unity Animation Property selector](unity-animation-property-selector.png)

Note that all of the various components inside of your game object can be animated using this `Animation` window.

### Modify Keyframes
As soon as we have added a property to animate, the `Animation` window automatically adds a `begin` and an `end` keyframe for each of the possible values we can animate. By clicking the arrows in this window we can the white `Timeline` cursor to the exact moment in time of each of these keyframes. We can then enter the exact values we wish into this window, modify the game object directly in the `Scene` or through its values in the `Inspector`. 

![Unity Animation Clip Keyframes](unity-animation-keyframe-end.png)

In the above example you can see that I have moved the time cursor to the final keyframe of my `Animation Clip`, and modified the `Y` axis rotation to the value of `360`°. If you rewind the time cursor to the beginning of my clip, the `Y` rotation value began at `0`°, meaning that all of the intermediary frames will be *interpolations* between these two values, depending on where the time cursor is inside of the animation clip. Also note that the lozange-shaped keyframe values (and parent values) that I have *changed* at that specific point in time have been colored blue.

![Unity Animation Spin](unity-animation-spin.gif)

You can temporarily preview the animation by pressing the triangle `Play` button inside the `Animation` window. This will play your animation in a loop. As you may notice, the animation speeds up and slows down, at each of the keyframe extremities. This is because the `curves` of your keyframes are configured to smooth out the changes at each keyframe point.

![Unity Animation Curves](unity-animation-curves-tangent-linear.png)

If you want a more robotic, linear rotation movement, select the specific `Property` you want to fix (here I am adjusting the `Rotation.y` value), select the `Curves` button at the bottom of the `Animation` window, and set each of your keyframe sides (`left` side, `right` side or `both`, depending on the keyframe position) to `Linear`.