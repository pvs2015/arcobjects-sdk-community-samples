##Using HookActions in custom commands

###Purpose  
This sample demonstrates how to use the IHookActions interface in custom commands to zoom, pan, flash and create graphics, labels, and callouts of selected features. The sample uses the MapControl, GlobeControl, and ToolbarControl in conjunction with the control commands.  


###Usage
1. Add data to map, globe or both. For instance, add wsiearth/wsiearth.tif as the globe backdrop to allow black graphics and callouts to be seen. You could add line features from UsaMajorHighways/usa_major_highways.shp.  
1. Select some features. Note: on globe, you must select multiple features using Shift+Ctrl; there is no extent selection.  
1. Right-click the display to zoom, pan, flash or create graphics, labels, or callouts of selected features.  
1. Note: on globe, graphics cannot be selected.  





####Additional information  
<div xmlns="http://www.w3.org/1999/xhtml">Each custom command uses the HookHelper and GlobeHookHelper object to manage the hook passed to the ICommand.OnCreate event. In the ICommand.OnClick event, the IBasicMap.FeatureSelection method is used to return the feature selection of the IHookHelper.FocusMap or the IGlobeHookHelper.Globe. The geometry of each feature in the feature selection is added to an IArray.</div>  
<div xmlns="http://www.w3.org/1999/xhtml"> </div>  
<div xmlns="http://www.w3.org/1999/xhtml">The IHookActions.ActionSupportedOnMultiple property is used to determine whether the specified action (zoom, pan, flash, graphic, label, or callout) is supported with the geometries in the array. If the action is supported, the IHookActions.DoActionOnMultiple or IHookActions.DoActionWithNameOnMultiple method is called to perform the specific action. The DoActionWithNameOnMultiple method is used when performing a label or callout action. In addition to passing an array of geometries, an array of strings for labeling is also passed. In this case, that string array contains the value from the first field of each feature.</div>  
<div xmlns="http://www.w3.org/1999/xhtml"> </div>  
<div xmlns="http://www.w3.org/1999/xhtml">The custom commands are added to a ToolbarMenu using the IToolbarMenu.AddItem method and the ToolbarMenu's hook property is set to the ToolbarControl. In the MapControl and GlobeControl OnMouseDown event, the IToolbarMenu.PopupMenu method is used to display the menu when the right mouse button is clicked.</div>  


####See Also  
[HookHelper](http://desktop.arcgis.com/search/?q=HookHelper&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  
[GlobeHookHelper](http://desktop.arcgis.com/search/?q=GlobeHookHelper&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  
[IHookActions](http://desktop.arcgis.com/search/?q=IHookActions&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  


---------------------------------

####Licensing  
| Development licensing | Deployment licensing | 
| :------------- | :------------- | 
| Engine Developer Kit | Engine: 3D Analyst |  
|  | ArcGIS for Desktop Basic: 3D Analyst |  
|  | ArcGIS for Desktop Standard: 3D Analyst |  
|  | ArcGIS for Desktop Advanced: 3D Analyst |  


