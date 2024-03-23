Patch Eos visually using cones
===============================

.. figure:: ../source/_static/node_patch.png
   :align: center
   :alt: Node patch
   :width: 300px

Usually, the patching process for DMX software starts at the patch page. In Sorcerer, it starts at 3D view. That is because Sorcerer is designed for the artist, not the stage technician. Art is not to be restricted by petty technicals. With Sorcerer, go to 3D view and place fixtures wherever you want without patching. Fixtures are represented by simple cones. Label, rotate, color, and duplicate the cones as desired. Use array modifiers to rapidly create large groups. Constrain the array modifier to curves/splines/shapes if they aren’t supposed to be in a straight line. Duplicate groups to maintain consistent locations. Then, once your art is finished, go into the node editor to create them on the lighting console. Instead of using multiple lines of syntax, write out all the details for one group at once, review all at once, and hit the Patch button. The Sorcerer orb will create the channel, patch the DMX, position and orient the light in Augment3D, create a group, label the group, and leave the new lights selected so they are highlighted in Augment3D. Finally, the orb will create a group controller node for the new group with the group’s view toggles set for the group’s capabilities.

If the patch page is knowhere to be found on the N tab of the Shader Editor or Sorcerer Nodes view, that is most likely because "Eos console mode" is toggled off in the node settings. This is there to make it clear that this is essentially the only nodes feature that will not work on universal consoles.

If you don't want to or need to ever think about the universe and addressing, just leave universe and address at 1 and 1. It will take care of the rest for you, being careful not to patch anything past address 512. It will automatically increment everything appropriately (assuming you don't need to work around other existing fixtures and assuming you don't have more patching needs than you have the physical universes for. In that case, you should pay attention between groups). 

Note: There is a known issue where addressing information is occasionally missing on the console once every 5-100 lights or so. It is easiest to remedy this on the console itself. We're not sure yet if this is a Sorcerer issue, an Eos issue or a network issue. By EOD, Sorcerer will switch to using TCP for these systems instead of UDP. That will make these administrative tasks much more reliable.


USITT ASCII import (import Eos's existing patch using flash drive)
-------------------------------------------------------------------
If you already have everything patched and built out in your console show file, you can instead load a USITT ASCII file created by your console into the text editor to automatically create group controller nodes and a 3D representation of your 3D rig (if it exists in your show file, if not, that's okay) inside Blender/Sorcerer. Simply select that text block in the menu depicted above and press the wand button. Sorcerer should then build out the Sorcerer show file based on the USITT ASCII data. It will do its best to try to interpret which fixture types have which abilities, and it will toggle those parameter view check boxes accordingly. It's does its best, but it doesn't always get it right. The quickest way to make corrections to numerous groups is in Properties. If your lighting fixture type uses a color profile that is not in the color profile drop down, please contact Alva Theaters through your customer work order portal (make a work order) and we will try to support you in that as soon as we can.
