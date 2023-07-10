# BoardgameDevTool

This project is meant to serve as a spring board for any game that has a boardgame-like gamespace. For example: Mario Party. 
It includes the following features:
  - Game Map creation
  - Customization of each node in the map
  - Some extra map features

You have full access to source code when you buy the assset on [insert asset store link] and are encouraged to modify the code to fit your exact needs. If you have any issues contact me at <fatherboard28@gmail.com>

# Documentation

This is the documentation of what the project supports and is capable of doing.
All of the functionality is in the Editor window found by selecting the "BoardGameDevTool" tab at the top of the screen then selecting "Board Builder" from that menu.

## Game Map Creation

There are a couple components that go into creating a working map. It is not complicated if you already know what you want to implement, so I would suggest having an idea of what to make before trying to make it in Unity.
Once you know what you want to make these are the steps required to have a working Game Map:
  - Make Node Types using the _NodeTypeMaker_ tool
  - Plan out roughly what the map will look like
  - Make the map in Unity using the _NodeMakerWindow_ tool

---

### Making Node Types (Node Type Maker)

A Node Type has two parts an extended class and a Scriptable Object. The class is an extension of the _Node_ class and implements the _OnLand()_ method. The Scriptable Object part stores data for the Node. This tool automatically creates both of these for you. 

All you need to do is the following: <br>
  - Give it a Name (System.string)<br>
  - Give it a Mesh (UnityEngine.Mesh)<br>
  - Give it a list of _Materials_ (UnityEngine.Material).<br> 

Note: All of this information is editable later on in the Scriptable Object. 

Once you hit the _Make Node Type_ button it will create two files in the folder "Assets/NodeTypes":
  - "\<Name\>Node.cs" | Extended _Node_ script
  - "\<Name\>NodeData.asset" | Scriptable Object 

Note: you do not need to make this folder the tool will do that for you.

The Extended _Node_ Script will look something like this:
```CS
public class <Name>Node : Node
{
  public override void OnLand(Player player)
  {
  }
}
```

If you have a desired effect or feature to happen when a player lands on this node then put that code inside of the _OnLand()_ method for the respective NodeType. 

`Player player` is the player object that landed on the node so if you need to access any information in that then use `player` inside of _OnLand()_.

---

### Making The Board (Node Maker)

This tool creates a Node Game Object with a couple components attached. It loads the mesh, materials, and NodeType script from the NodeType you selected. It will place this Game Object as a child of a Map Game Object that the script will create. 

It will open a window that looks like this:
![Node Maker Window!](/NodeMaker.png "Node Maker Window")

All you need to do is:
  - Select a NodeType
  - Set the nodes ID
  - Set the adjacent Nodes

The Node's ID and Type cannot be changed once the node is created but the Adjacent Nodes are changeable after creation. This can be done by using the _NodeEditor_ Window or in the Nodes Game Object in the scene.

