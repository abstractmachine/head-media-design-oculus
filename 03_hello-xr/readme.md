### Time To VR
Let's put some triangles into our Oculus headset. Loosely inspired by Mark Cerny's [Time to triangle](https://www.youtube.com/watch?v=ph8LyNIT9sg&t=162s) measurement, let's see how quickly we can get some triangles into an immersive virtual reality world.

We're going to keep this as simple as possible, with the goal of getting a (red) cube on the screen as quickly as possible. For art direction we'll use as our influence the supercool VR game [Superhot](https://superhotgame.com).

(youtube: A1jothqmqHw)

### New Project
Open up the Unity Hub on your macOS, Windows, or Linux machine. Go into the `Projects` tab and press the `New project` button. You will see a series of choices. Make sure you are using `Unity 2021.2.##`. Make sure that you are using the `3D Core` template, which configures your Unity project to the standard 3D rendering system which is a good starting point for any virtual reality project. Inside the `Project Settings` section, you can give your project a name, and determine the location where it will be saved. Finally, when you are happy with these settings, click `Create project` to open your project in the Unity editor.

![Unity New Project window](unity-new-project-window.jpg)

### Sample Scene
Your project should open up with a `SampleScene` in the `Hierarchy`.

![Unity Empty Project](unity-empty-project.png)

If your project doesn't look like my screenshot, it is because I have configured my editor to use the `Tall` layout by default (cf. Unity Editor).

### Inifinity Room
Let's add a floor and a cube to our `Scene`. At the top of the `Hierarchy` tab, you'll find a `+` button; select `+` > `3D Object` > `Plane` to create a flat plane in the middle of the scene.

![Unity Create Plane](unity-create-plane.jpg)

Select that plane, look at it's values inside the `Inspector` tab. You should see the `Transform` values, which describe the `x`, `y`, and `z` position, the rotation, and the scale of the plane.

![Unity ajust plane size](unity-plane-100-1-100.png)

Let's stretch out our plane to give it a larger size in the `x` and `z` directions. In my example, I've given it a scale multiplier of `100` units.

![Unity white scene](unity-white-scene.png)

This should create the impression of an infinite white floor spreading off into the distance, similar to the infinite white room in [THX 1138](https://www.youtube.com/watch?v=nkQAhpLBok8).

### Red Cube
Now let's put a red cube in the middle of this abstract room. Before we create the cube, let's create a new folder to hold all our color materials. In the `Project` tab, select the `+` button and create a new `Folder` in your `Project` named `Materials`. It is good practice to name your folders using simple words, and keep your Uppercase and Lowercase names consistent. In Unity, the tradition is to start folder names with a capital letter and to use plural names where appriopriate.

![Unity Materials folder](unity-materials-folder.png)

Now let's create our `Red` color material in this new folder. Right-click on the folder, or alternatively select the folder name and click on the `+` button to create a new `Material`. Name that material "`Red`". Give it a red color, and drag the `Smoothness` slider down to `0` for a more *flat* look.

![Unity Material Color Red](unity-material-color-red.png)

We now have a red material to paint our 3D scene with.

![Unity 3D Cube](unity-create-cube.png)

Go back to the `Hierarchy` tab and create a `+` > `3D Object` > `Cube`.

This should inject a 3D Cube into your `Scene`, but unfortunately the cube is stuck in the floor. Let's lift the cube into the air and give it a little rotation using the following settings in the `Cube` object's `Inspector`:

![Unity Cube Transform Settings](unity-3d-cube-transform.png)

Here, we've set the Cube's position to `2` units on the `Y` axis, and rotated the cube `45°` *around* the `Y` axis.

![Unity drag material](unity-drag-material.png)

Finally, let's drag out `Red` material from the `Project` tab, directly onto the object in the `Scene` tab in order to give it the color red.

You should now have a `Game` view that shows a red cube hovering in the air.

![Unity Red Cube Game View](unity-red-cube-game-view.png)

### Export to Headset
In order to export to our headset, we need to change several settings in the `Build Settings` window. In your menu bar, go to `File` > `Build Settings` to open this window. Make sure you `Switch Platform` to `Android`, then select your Oculus device in the Android `Run Device` menu, and finally `Build and Run`. If you don't see your device listed, you might need to `Refresh` this list; also, double-check that your headset is plugged in, turned on, and that you have activated `Developer Mode` as explained in the `Installation` tutorial.

![Unity Build Settings](unity-build-settings.png)

When Unity is finished exporting your project, you should see your game inside your Oculus headset. Yipee! Ummm, wait a minute. Look at your headset. What do you see? Is this normal? What the %$@#& is going on. That is totally uncool Unity! There is nothing immersive about this experience.

![Unity Oculus Flat Mode](unity-oculus-flat-mode.png)

The problem is that we have not activated the "virtual reality" mode in our game. Therefore, Oculus considers that Unity sent us a traditional game that needs to be played on a flatscreen TV. So it builds a flatscreen TV for you inside your headset. Maybe watching flatscreen televisions is just training for our ~~future~~ present dystopic hellscape, but it's probably not what you wanted.

### XR Plugin
We need to activate the special "virtual reality mode" inside your Unity project. Open the menu `edit` > `Project Settings`, find the `XR Plugin Management` section and select `Install XR Plugin Management`.

![Unity Settings Install XR Plugin](unity-settings-xr-plugin.png)

Once the plugin has been installed, select the `Android` (cf. little robot icon) tab inside this tool and activate the `Oculus` option.

![Unity Settings Oculus](unity-settings-android-oculus.png)

### Convert To XR Rig
If you re-build and run your application in your headset, you should now be immersed in a 360° world, but the headset won't rotate or move with the movements of your head because it is using a classical 3D camera. This is an odd experience. Try it if you like, just don't move your head. Interresting, but again, not really what you were expecting in a virtual reality headset.

![Unity Convert Camera to XR Rig](unity-convert-to-xr-rig.png)

To *convert* our classical game camera to vr-headset compatible "rig", select the `+` button, choose `XR` > `Convert Main Camera to XR Rig`.

*Now, finally*, you can build your application again and run it on your device. You should now see your lovely Red 3D Cube floating in immersive virtual reality.

![Oculus Virtual Reality](oculus-hello-xr.png)

### Look Behind You!
A good exercise for *thinking* about how to design in virtual reality, is to start by putting a second object *behind* your `XR Rig`. Create a second material (here I've chosen blue), and placed it "behind" the `XR Rig`.

![Unity front and back objects](unity-vr-front-back-objects.png)

Now when I `Build and Run` my application in my headset, I should have two objects to look at.

The next obvious step would be to continue this [greyboxing](https://www.youtube.com/watch?v=dYBOBgfcTgY) method by building an entire blocked-out city directly inside of Unity, and then to start animating elements within this scene. Hey, sounds like a good subject for a tutorial.

(youtube: dYBOBgfcTgY)