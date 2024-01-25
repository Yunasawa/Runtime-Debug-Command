<!--    -->
<h1 align="center"> 
Yunasawa の Library <br></br>
Realtime Debug Command - Documentation 
</h1>

<h4 align="center"> Documentation contains everything about REALTIME DEBUG COMMAND.</h4>

<p align="center">
 <img src="https://img.shields.io/badge/Script-DOCUMENTATION-blue.svg" alt="script">
 <img src="https://img.shields.io/badge/Contact-yunasawa200@gmail.com-purple.svg" alt="email">
 <img src="https://img.shields.io/fbadge/Debug%20Command-008F64">
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

<ul>
<li> I recommend you to create a new <img width="12%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/829b30b5-10ac-4ade-8d2b-1dab8ce6af3a"> right inside <kbd>Assets > Yunasawa の Library > Realtime Debug Command > Scripts > Debug Commands</kbd>, otherwise you will have some small troubles. </li>
<li> Here is a sample code for a <img width="12%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/829b30b5-10ac-4ade-8d2b-1dab8ce6af3a">, I call it DC_Debug. It is used to display a message inside log window with a general command of <img align="center" width="22.5%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/1288567b-6599-4c4c-8be6-65fc37375adb">. </li>

<br><img align="center" width="95%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/d88bff67-1df0-4f82-b548-b7239a411c65"></br>

<li> As you can see on the sample picture, now I will show you how to make one step by step: </li>
   <ul>
   <li> First, create a new class/object (name it whatever you want, I recommend to put DC_ in the beginning), inherited from <b>DebugCommand</b>. </li>
   <li> Make a constructor for it, now you have to concentrate on this step. <b>CommandNodes</b> is a <b>List</b> of <b>CommandNode</b>. Here is <b>CommandNode</b> class: </li>
<img align="center" width="90%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/6f2146ba-77cb-4a9b-bce9-f9bda03e47c7"><br>
   As you can see, <b>CommandNode</b> has 3 properties, Nodes, Suggestions and StartWith. 
   
   - <b>Nodes</b> is the general name of node in a command. For example, in the command <img align="center" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/1288567b-6599-4c4c-8be6-65fc37375adb">, <b>Nodes</b> are <i>"debug", "selection", "message"</i>.
   - <b>Suggestions</b> will show up when you typing the commands so you can Tab to finish it automatically, when you typing the <i>"selection"</i> node of <img align="center" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/1288567b-6599-4c4c-8be6-65fc37375adb">, a list of <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/d8f93816-51b1-4f4a-ba94-164b0ec15fcd"> will show up.
   - And for <b>StartWith</b>, if you enable this only the suggestions which start with the word you're typing will appear. You are in <i>"selection"</i> node, then you type "n" then only "notify" appears, but if it's disabled, "warning", "caution" and "notify" will show up (Those 3 contain "n").
   <li> Back to sample DebugCommand, you can see inside the constructor, I assign <b>CommandNodes</b> with a new list, inside I make new <b>CommandNode</b> objects with inputing params are <b>Nodes, Suggestions and StartWith</b>.</li>

   - This is node 0: <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/78392b09-fad0-4134-84b8-dd65d9c15881">, it have <i>"debug"</i> as <b>Nodes</b>, <i>"debug"</i> as <b>Suggestions</b> and <b>StartWith</b> is <i>true</i>.
   - Node 1: <img align="center" height="16" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/e3f42f3b-74c4-44f6-923b-05c89ffd50e1"> is similar.
   - Node 2: <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/2926c2a6-b92b-499d-a39f-79afe045c986">, because I don't need <b>Suggestions</b> for this so I don't put anything inside, and <b>StartWith</b> is defaulted by <i>false</i>.

  <li> After finish the constructor, call an override void named <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/6fde6893-8b8d-4c79-87a2-3dc6bae6c448">, <b>value</b> is an array of words separated by <i>space</i>. For example, in command <img align="center" height="17.5" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/77c7f55e-a044-45ad-bfbe-aeb4b7eb2e8a">, <b>value</b> is <i>{ "debug", "log", "Hello", "world" }</i>. Inside this method, you can do your own code to handle the command just like above sample code.</li>
  </ul>
    
 <li> Here is another sample for <img width="12%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/829b30b5-10ac-4ade-8d2b-1dab8ce6af3a"> called DC_Time, used to manage time in game. </li>
<br><div align="center"><img width="60%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/fa980f35-8821-4600-8fcb-bd47299e8b0d"></div><br>

 <li> After you created a new <img width="12%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/829b30b5-10ac-4ade-8d2b-1dab8ce6af3a">, there're 2 things you have to notice: </li><br>
 <table>
   <tr> 
     <td>
      <ul>
      <li>Find this <b>CreateCommand()</b> method in <b>DebugCommandList</b> class.</li>
      <li>Inside this <b>switch</b>, add the first node of commands as <b>case</b> and return the <b>commmand</b> like this.</li>
      </ul>
     </td>
     <td><div align="right"><img width="100%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/2c34de3c-b1c1-4460-b5e4-72c9e026d8c8"></div></td>
   </tr>
   <tr> 
     <td>
      <ul>
      <li>Then find this <b>UpdateCommandLibrary()</b> method in <b>DebugCommandManager</b> class.</li>
      <li>Add the first node of the command inside the list of string like this.</li></li>
      </ul>
     </td>
     <td><div align="right"><img width="100%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/fa700afb-80c2-47fc-bb10-31d6a18ad1b6"></div></td>
   </tr>
 </table>
 <li> Finish those thing and you now can use <img width="12%" src="https://github.com/Yunasawa/Realtime-Debug-Command/assets/113672166/829b30b5-10ac-4ade-8d2b-1dab8ce6af3a"> right inside your project. </li>
</ul>

