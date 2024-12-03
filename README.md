# BubasBobaShoppe-TreeGeneration
<p>An alternative repo of Drew's <a href="https://github.com/Drewayou/BubasBobaShoppe">"BubasBobaShoppe"</a> for a parallel programming class,</p>
<p>to attempt and implement tree generation via CPU multithreading in unity. </p>

<p align="center">
  <img src="Assets/Art/ForReadMeFile/25kTreesin1min.png?raw=true" width="1200" height="550"/>
</p>

## Table of contents
- [Methodology](#methodology)
<br></br>
- [How to run](#how-to-install)
<br></br>
- [More Info](#more-info)
-------------------
<a name="methodology"></a>

### Methodology
<p>Similar to how we applied DAXPY for homework 2 in our class, we utilize vector calculations in this project. </p>
<p>However, instead of multiplication, it's simply equating each vector index to the next index of objects </p>
<p>inside the object transform array. This "gets rid" of a double for loop necessary in the sequential case! </p>
<br></br>
<p>There are cons for this methodology though. Due to Unity's Core API being unsafe for multithreading, </p>
<p>only limited Native Arrays are allowed to be utilized and all data needed to be </p>
<p>processed *MUST* be fed in and expected as output. </p>
<p>This also means any Unity API's like Random.Range() or methods relying on the main thread itself cannot be accessed!</p>
<br></br>
<p>More info about Documentation used for this project can be found <a href="https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Jobs.IJobParallelForTransform.html">HERE</a> & <a href="https://docs.unity3d.com/6000.0/Documentation/Manual/job-system-parallel-for-jobs.html">HERE</a>.</p> 
<sub>(*Note: The links above leads to Unity documentation for "IJobParallelForTransform" a built-in Unity interface used for this project, and Unity's "Parallel jobs" documentation.*)</sub>
<br></br>
<br></br>
<p>In addition to this, a loop is still utilized to "load" each object into the "treeNewPositionArrayInJob". </p>
<p>There may be ways to decrease this inefficiency and moreover, there is more memory overhead needed to save both </p>
<p>"TransformAccessArray", and the Native Array "treeNewPositionArrayInJob" for the parallel processes to run. </p>

<p align="left">
  <img src="Assets/Art/ForReadMeFile/UnityParInfo.png?raw=true" width="720" height="950"/>
</p>
<sub>(*Above is an image from Unity's documentation on how parallel jobs are in Unity*)</sub>

-------------------

<a name="how-to-install"></a>

### How to run
<h4>1) Install Unity.</h4>
<sub>(*Note: This was made in Unity version 6000.0.23f1, but any version above that should work as well.</sub> 
<sub>(*Moreover, you need to install Unity Hub to get the Unity Engine and open projects. Link can be found <a href="https://unity.com/download"</a> HERE</sub> 
<sub>If upgrading the project is needed, do so and it "shouldn't" glitch the code.*)</sub>
  <img src="Assets/Art/ForReadMeFile/UnityInstall.png?raw=true" width="720" height="150"/>
<h4>2) Download and Open the project by selecting the "Asset" Folder.</h4>
<sub>(*Some help can be found via Unity forums : Link can be found :
  <a href="https://discussions.unity.com/t/how-to-open-unity-project-from-project-folder-where-file-is/641138"> HERE)</a>*
</sub>
  <img src="Assets/Art/ForReadMeFile/Projects.png?raw=true" width="720" height="250"/>
<h4>3) Find and open the "GenerateTreesScene".</h4>
  <img src="Assets/Art/ForReadMeFile/GenerateTreesScene.png?raw=true" width="720" height="450"/>
<h4>4) Locate the "World Generator" to open it's inspect.</h4>
  <img src="Assets/Art/ForReadMeFile/WorldGenerator.png?raw=true" width="720" height="200"/>
<h4>5) In the Inspector, locate the "GenerateTrees" script and edit the amount of trees you want to add to the scene. Also check "on", or "off" the "Use Parallelism To Generate bool.</h4>
  <img src="Assets/Art/ForReadMeFile/Inspector.png?raw=true" width="400" height="300"/>
<h4>6) Hit "Play" and wait for the scene to generate.</h4>
<sub>*(If you have an 8 core CPU or less, a suggestion of <25k trees would be advisable.*</sub>
<sub>*Unity's "realtimeSinceStartup" documentation code was used and can be found : <a href="https://docs.unity3d.com/ScriptReference/Time-realtimeSinceStartup.html">HERE</a>*)</sub>
  <img src="Assets/Art/ForReadMeFile/Play.png?raw=true" width="750" height="100"/>
<h4>7) When done, check the console for the time it took to generate the trees!</h4>
  <img src="Assets/Art/ForReadMeFile/Console.png?raw=true" width="650" height="200"/>

-------------------

<a name="more-info"></a>

### More Info
<p>This project was meant for a university class.</p>
<p>However, this is only part of a full repo for an indie game Andrew Aguilar </p>
<p>is developing. More info of the Indie game can be found here <a href="https://sites.google.com/view/andrewaguilar/current-passion-project"> Andrew's Portfolio</a>.</p>
<p>You can also play the Game's Alpha <a href="https://revisedwords.itch.io/bubas-boba-shoppe">HERE</a>.</p>
<p align="left">
  <img src="https://github.com/Drewayou/BubasBobaShoppe-TreeGeneration/blob/main/Assets/Art/UIElements/MainMenu.png?raw=true" width="720"/>
</p>

