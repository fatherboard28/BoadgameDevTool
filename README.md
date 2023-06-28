# BoardgameDevTool

This project is meant to serve as a spring board for any game that has a boardgame-like gamespace. For example: Mario Party. 
It includes the following features:
  - Game Map creation
  - Customization of each node in the map
  - Extendable Player class that works with the Game Map out-of-box
  - Customizable turn system
  - Movement on Game Map

You have full access to source code when you buy the assset on [insert asset store link] and are encouraged to modify the code to fit your exact needs. If you have any issues contact me at <fatherboard28@gmail.com>

# WIKI

This is the documentation of what the project supports and is capable of doing.

## Game Map Creation

There are a couple components that go into creating a working map. It is not complicated if you already know what you want to implement, so I would suggest having an idea of what to make before trying to make it in Unity.
Once you know what you want to make these are the steps required to have a working Game Map:
  - Make Node Types using the _NodeTypeMaker_ tool
  - Plan out roughly what the map will look like
  - Make the map in Unity using the _NodeMakerWindow_ tool

### Making Node Types

In order to do this open the _NodeTypeMaker_ tool. On the top of the Unity Editor go to the _BoardGameUtils_ tab and select _NodeTypeMaker_ from the list of windows.
It should bring up the following window:
![Node Type Maker Window!](/NodeTypeMakerWindow.png "Node Type Maker Window")

A Node Type has two parts an extended class and a Scriptable Object. The class is an extension of the _Node_ class and implements the _OnLand()_ method. The Scriptable Object part stores data for the Node. This tool automatically creates both of these for you. 

All you need to do is the following: 
(1) Give it a Name (System.string)
(2) Give it a Mesh (UnityEngine.Mesh)
(3) Give it a list of _Materials_ (UnityEngine.Material). 

Note: All of this information is editable later on in the Scriptable Object. 

Once you hit the _Make Node Type_ button it will create two files in the folder "Assets/NodeTypes":
  - "<Name>Node.cs" | Extended _Node_ script
  - "<Name>NodeData.asset" | Scriptable Object 

Note: you do not need to make this folder the tool will do that for you.

The Extended _Node_ Script will look something like this:
![Extended Node Script!](/NodeScript.png "Extended Node Script")

If you have a desired effect or feature to happen when a player lands on this node then put that code inside of the _OnLand()_ method for the respective NodeType. 
```C#
Player player
```
is the player object that landed on the node so if you need to access any information in that then you can.

