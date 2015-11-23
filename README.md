Hacker Mainframe!
===================

**Warning** *This software and its documentation is pre-release and may not behave as intended nor documented herein*
This program is an advanced  **Hacker** Client server Interface for the hacker on the go! 

----------


MainFrame
-------------
The **MainFrame** is designed to make your life as easy and care free as possible. Doing everything from installing code on objects for you to making a slurp network that is easy to use.

> **Functions:**

> - **Slurp DB** Save a Slurp to a location in the central database.
> - **Shared Slurps** Your Slurp list is shared between different clients
> - **Simple Install** Install with a `simple command`.
> - **Bank Access** make transactions with the Financial Servers
> - **Create Hacker Items**
>  - **Room Logger** A drink that logs to the MainFrame information about where you are.
>  - **Better Hacker** An Upgrade for your hacking tool
>  - **Positional Tool** Does some stuff

#### <i class="icon-file"></i> Create a new Client

To connect a new Slurp node paste in
```
Connect("{ServerName}").Install(Name())
```
Replacing ServerName with the server you installed the hosting software on.

#####Permanent Install
If you want a permanent client select:
```
Install Local AutoHack
```
This will automatically add the client code as a check to the beginning of the code on the client you connected from.

#### <i class="icon-folder-open"></i> Navigation

All your stored Slurp Nodes are listed under Slurp>List.

* You can select one by pressing <kbd>Up</kbd> and <kbd>Down</kbd>or <kbd>W</kbd> and <kbd>S</kbd>.
* To Connect and Slurp to the Node press <kbd>G</kbd>.
* To Rename the Node press <kbd>R</kbd>.
* To display the Nodes Info press <kbd>I</kbd>.
* To Connect with a remote terminal if available press <kbd>C</kbd>.

#### <i class="icon-pencil"></i> Rename a Client Node

You can rename the current client from its main menu by selecting.
```
Rename
```

#### <i class="icon-trash"></i> Uninstall the client

* **The Simple Way** Hit the reset button on your Hacking Device 
 * This will not how ever delete it from the central database
* **Select Uninstall** If you select `Uninstall` from the menu on a client you will be asked to confirm you want to uninstall this node and if you want to remove it from the central database.
 
#### <i class="icon-hdd"></i> Database storage

By default the mainframe will store its data on a HardDrive <i class="icon-hdd"></i>

**Warning:** I have not tried it but I believe if the HardDrive is deleted for example in a trash can then your data is gone. Consider using a raid setup if you can find 2 HardDrives or setup a <i class="icon-upload"></i> backup site.


----------


Cook Sites
-------------------
Basically this is a networked oven that is used by the server for cooking out code into items

### Possible Workflow
The Stoves do not have the ability to directly connect to the server but they may beable to use the objects they connect to for that.


```sequence
Note Right of Cooker: New object present
Cooker->Object: Do you have cookOS running?
Object-Cooker: No
Cooker-Object: Well then do you have the method connect?
Object-Cooker: Yes
Cooker-Object: Then here is your new code wrapper
Note Right of Cooker: Connect("MainFrame").cookerPing(ObjType)
Note Right of Cooker: if(false) then
Note Right of Cooker: Old Code Here
Note Right of Cooker: End
Object-MainFrame: Cooker said I am a <type> and wants to install
MainFrame-Object: Your code should be ...
Object-Cooker: My code should be ...
Cooker-Object: Your code is now ...
Cooker-Object: Tell the server your now installed
Object-MainFrame: I am now installed with the code.
```

> **Not yet implemented**
> 
> - This feature has not been coded yet why not fork the repo and try to make one your self?

----------


Backup Sites
-------------------

> **Not yet implemented**
> 
> - This feature has not been coded yet why not fork the repo and try to make one your self?
> 
> **Planned Features**
> 
> * All database info is transmitted to this server as a backup.
> * Possibly also a location to connect to if something happens to your main server *(not sure though if something can happen to it other then your self messing it up)*.


Contribute
-------------

The more the merrier you're welcome to use this code how ever you see fit to do so. If you add and cool features please share them back with a pull request.

### <i class="icon-fork"></i> Get the fork outa here

When you get more familiar and comfortable with the code of the mainframe you may want to make your own version of the mainframe maybe even make a <i class="icon-upload"></i> **Pull Request** So that your code or features get integrated directly into the main repo for everyone to use.

When making pull requests please fallow these guidelines.


**Do's**

 - Submit cool new features 
 - Submit AWESOME new features
 - Other features are cool too
 - Fix a bug if you find one
 - Maybe make the mainframe multilingual like the game is

**Don'ts**

- Submit profanities or mean spirited text

> **Note:** Your pull requests will be read so please do not try to submit code that is malicious to the player. 

>Also just to make my life easier please **try to put features in separate commits**

----------

Program Structure
--------------------
###Server
New Client
```sequence
Note Right of Client: Hey Server I wana be installed 
Client->MainFrame: server.install(Name())
MainFrame->CodeWrangler: coder.setup(name)
CodeWrangler->Client: var clientBase = client.GetCode()
CodeWrangler->Client: client.ClearCode()
CodeWrangler->Client: client.AppendCode(ClientSoftwareWrapperOpen)
CodeWrangler->Client: client.AppendCode(clientBase)
CodeWrangler->Client: client.AppendCode(ClientSoftwareWrapperClose)
CodeWrangler->Client: client.Reboot()
```


### Menu Lists

#### Server

#### Client Menu
 - Install
 - Slurp
  - Add this Node (If not in DB)
  - Remove this Node (If in DB)
  - List Nodes
  - Go to Server Room
  - Go Home
  - Go Back (If last jump was to here from another node)
  - Set this as
  - Set as Home  
 - Uninstall
  - Are you sure? (Yes / No)
