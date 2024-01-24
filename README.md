<!--
<h1 align="center"> 
Yunasawa の Library <br></br>
Realtime Debug Command - Documentation 
</h1>

<h4 align="center"> Documentation contains everything about REALTIME DEBUG COMMAND.</h4>

<p align="center">
 <img src="https://img.shields.io/badge/Script-DOCUMENTATION-blue.svg" alt="Unity Download Link">
 <img src="https://img.shields.io/badge/Contact-yunasawa200@gmail.com-purple.svg" alt="License MIT">
</p>

<h2> ★ About </h2>

<b><i>Realtime Debug Command</i></b> provides you an input field used to handle and debug your logics, events or you can use it as a feature of you game. 

<h2> ★ Table On Contents </h2>

- <a href="#how-to-create-debug-command-panel"> ★ How to create Debug Command Panel </a><br>
- <a href="#how-to-create-new-debug-command"> ★ How to create new Debug Command </a><br>

<h2><div id="how-to-create-debug-command-panel"> ★ How to create Debug Command Panel </div></h2>

<h3><i> From Menu Item / Hierarchy </i></h3>

- First, you can select an object in hierarchy to be parent of RDC.
- Right-click in hierarchy, select <kbd>YのL</kbd> > <kbd>2D</kbd> > <kbd>Realtime Debug Command</kbd> or select <kbd>Tools</kbd> > <kbd>YのL</kbd> > <kbd>Create Object</kbd> > <kbd>2D</kbd> > <kbd>Realtime Debug Command</kbd> on window bar.
- In case you don't select a canvas to be the parent, a new Canvas and Event System will be created automatically.

<h3><i> From Prefab / Asset </i></h3>

- Find RDC in <kbd>Assets</kbd> > <kbd>Yunasawa の Library</kbd> > <kbd>Realtime Debug Command</kbd> > <kbd>Prefabs</kbd> > <kbd>Debug Command Panel</kbd>.
- Drag it into an object that you want it to be the parent of RDC.

<h2><div id="how-to-create-new-debug-command"> ★ How to create new Debug Command </div></h2>

- I recommend you to create a new Debug Command right inside <kbd>Assets > Yunasawa の Library > Realtime Debug Command > Scripts > Debug Commands</kbd>, otherwise you will have some small troubles.
- Here is a sample code for a Debug Command, I call it DC_Debug. It is used to display a message inside log window with a general command of /debug selection message

![Screenshot 2024-01-23 023140](https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/25c62a7c-0f90-41df-9de0-9c654f4ee8be)
-->

<ul>
<li> As you can see on the sample picture, now I will show you how to make one step by step: </li>
  <ul>
  <li> First, create a new class/object (name it whatever you want, I recommend to put DC_ in the beginning), inherited from <b>DebugCommand</b>. </li>
  <li> Make a constructor for it, now you have to concentrate on this step. <b>CommandNodes</b> is a <b>List</b> of <b>CommandNode</b>. Here is <b>CommandNode</b> class: </li>
<img align="center" width="90%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/6f2146ba-77cb-4a9b-bce9-f9bda03e47c7"><br>
  As you can see, <b>CommandNode</b> has 3 properties, Nodes, Suggestions and StartWith. 
   
  - <b>Nodes</b> is the general name of node in a command. For example, in the command <img align="center" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/1288567b-6599-4c4c-8be6-65fc37375adb">, <b>Nodes</b> are "debug", "selection", "message".
  - <b>Suggestions</b> will show up when you typing the commands so you can Tab to finish it automatically, when you typing the "selection" node of <img align="center" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/1288567b-6599-4c4c-8be6-65fc37375adb">, a list of <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/d8f93816-51b1-4f4a-ba94-164b0ec15fcd"> will show up.
  - And for "StartWith", if you enable this only the suggestions which start with the word you're typing will appear; like you are in 
  <li> Back to sample DebugCommand, you can see inside the constructor, I assign <b>CommandNodes</b> with a new list, inside I make new CommandNode object with inputing params are Nodes, Suggestions and StartWith.</li>
  </ul>
</ul>
 


