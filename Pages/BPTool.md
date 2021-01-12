## Introduction

As part of the 5100 module we have to create a tool for the third year. The tool that we have to do with Solange Schmid ([https://sosolamojo.github.io](https://sosolamojo.github.io)) is the Scene Exporter Tool, a tool who have to covert and write unity scene objets in a json format file.

## Tool

To display the tool, click on the "Tool" tab located on the top bar and then click on "Scene Exporter". It is then possible to place it wherever you want in the Unity interface.

![](https://worgaros.github.io/Images/openwin.gif)

The tool interface was created using the Unity GUI functions.
Here is a schema explaining the interface of the tool:

![](https://worgaros.github.io/Images/tool.PNG)

After selecting an object in the hierarchy, click the "Ignore object" button to add it to the list of objects to be ignored.

![](https://worgaros.github.io/Images/ignoreobj.gif)

If you want to remove an object from this list, just click on the button to the right of the corresponding object.

![](https://worgaros.github.io/Images/allowobj.gif)

Once the right objects have been added to the list, the "export to Json" button allows you to choose the location where to save the file. The basic name of the file is the name of the scene followed by the date and time.

![](https://worgaros.github.io/Images/savetojson.gif)

Once the location is chosen, the variables of the SceneData class instantiation get the name of the scene as well as the list of tags and layers. Then the objects of the hierarchy are browsed except those contained in the list of objects to ignore. For each object and child of the objects an instantiation of the type of the Data class will be filled by the name of the object, its instance ID, the instance ID of the parent, the layer of the object, the tag of the object. It will also fill the class of components contained in the Data class. The SceneData class instantiation contains the list of Data filled previously.  Finally, everything contained in the SceneData class is converted to Json format and written to a file at the previously chosen location.
Here is an example of the start of a file created:

![](https://worgaros.github.io/Images/json.PNG)


### [Back to main page](https://worgaros.github.io/)