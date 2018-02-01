# Creating new custom nodes in Houdini using te Python Source Editor in Houdini.

# Name variable, call houdini using (hou.node), tell it where, and to create_the camera node.

rendercam = hou.node("obj").createNode("cam") 
rendercam.setName("RenderCam")
rendercam.parm("resx").set(1920)
rendercam.parm("resy").set(1080)

render_ifd = hou.node("/out").createNode("ifd")
render_ifd.setName("Mantra_Render_HD")
render_ifd.parm("camera").set("/obj/rendercam")
render_ifd.parm("vm_renderengine").set("pbrraytrace")

