Use Python directly on Eos with absolutely no setup
=============================================================

Sorcerer now features an API targeted at the end user. It's called spy, short for SorcererPython. With absolutely zero setup, nontechnical users can commandeer the lighting console from Blender's text editor. 

**Accessing spy:**
--------------------------------------------------------------------
Users shall access spy through the following 2 lines of code:

*import bpy*

*from bpy import spy*

After those two lines, the user has full access to the spy functions below:

**OSC Functions**
------------------------------------------------------------------------
The *send_osc_lighting(address, argument)* function sends an OSC message to control the lighting console. You pass it an address and an argument, and it doesn’t return anything. The *lighting_command(command_as_string)* function sends a command string to the lighting console. You pass it a command line string, and it doesn’t return anything.

The *press_lighting_key(key_as_string)* function simulates pressing a key on the lighting console. You pass it the key name as a string, and it doesn’t return anything. The *lighting_key_down(key_as_string)* function presses a key down on the lighting console without releasing it. You pass it the key name as a string, and it doesn’t return anything. The *lighting_key_up(key_as_string)* function releases a key on the lighting console. You pass it the key name as a string, and it doesn’t return anything.

**Example Implementations:**

::

    import bpy
    from bpy import spy
    import time

    # Just for fun:
    spy.osc.lighting_command("3")
    time.sleep(1)
    spy.osc.lighting_command("2")
    time.sleep(1)
    spy.osc.lighting_command("1")
    time.sleep(1)
    spy.osc.lighting_command("Boom!") # Just a fun little demo

**Edit a macro**

::

    spy.osc.lighting_key_down("Macro")
    spy.osc.lighting_key_down("Macro")
    spy.osc.lighting_key_up("Macro")
    time.sleep(.3)
    spy.osc.press_lighting_key("softkey_6") # Start editing the top macro


The *send_osc_video(address, argument)* function sends an OSC message to control the video switcher. You pass it an address and an argument, and it doesn’t return anything. The *send_osc_audio(address, argument)* function sends an OSC message to control the audio mixer. You pass it an address and an argument, and it doesn’t return anything. The *send_osc_string(osc_address, destination_ip_address, destination_udp_port, string_to_send)* function sends a OSC message to a custom destination, or to a place not defined within Sorcerer's settings. You pass it an OSC address, an address, a port, and a string, and it doesn’t return anything.

**Utility Functions**
----------------------------------------------------------------------
The *get_frame_rate(scene)* function gets the true frame rate of the scene by calculating considering the scene's fps and the scene's fps_base. It also rounds the result to 2 decimal places. If you instead use *bpy.context.render.fps*, you will just get the integer fps, which is not necessarily the complete picture that you need if the fps_base is something other than 1. For most Sorcerer operations, we use this function to get the true frame rate. This spy function returns a float rounded to 2 decimal points.

The *parse_channels(input_string)* function parses an input string and returns a list of channel numbers based on what it sees in the string. For ecample, if you pass the function "1 - 5, 6 - 10", it will return [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].

The *parse_mixer_channels(input_string)* function converts a string of mixer channel numbers into a list of tuples. You pass it the input string, and it returns a list of tuples. This is typically used when you want concurrent groups when user uses () (). So for example, if you were to pass this function "(1 - 5) (6 - 10)", the function would return [(1, 2, 3, 4, 5), (6, 7, 8, 9, 10)]. Whereas the normal *parse_channels(input_string)* function would just return a list if integers regardless of () in the input string.

The get_light_rotation_degrees function gets the true rotation degrees of a light object after applying modifiers and constraints. You need this, not the built-in x_rotation/y_rotation accessible in Blender's UI because that number is not impacted by modifiers and/or constraints. You pass this spy function the light object’s name as a string, and it returns the rotation as x_rotation_degrees, y_rotation_degrees.

The try_parse_int function safely converts a value to an integer, avoiding runtime errors. You pass it the value, and it returns the integer or None. The swap_preview_and_program function swaps the preview and program for the ALVA M/E Switcher. You pass it a list of cues, and it doesn’t return anything.

The frame_to_timecode function converts the current frame number to a timecode string format (00:00:00:00). You pass it the frame number and optionally the frames per second (fps), and it returns the timecode string. The time_to_frame function converts a given time of a song to a frame number. You pass it the time, frame rate, and the start frame of the song strip, and it returns the frame number.

The add_color_strip function adds a color strip to the timeline. You pass it the name, length, channel, color, strip type, and start frame of the strip, and it doesn’t return anything. The analyze_song function uses AI to analyze a song for beats and sections. You pass it the context and the file path of the song, and it returns the analysis result.

The find_available_channel function finds an available channel to avoid overlapping strips in the sequence editor. You pass it the sequence editor, start frame, end frame, and optionally the starting channel (default is 1), and it returns the available channel. The duplicate_active_strip_to_selected function duplicates the active strip to selected strips. You pass it the context, and it doesn’t return anything.

The find_relevant_clock_strip function finds the most relevant sound strip with a timecode clock assignment. You pass it the scene object, and it returns the relevant strip object. The calculate_bias_offseter function calculates bias for flash strip background timing. You pass it the bias, frame rate, and the length of the strip in frames, and it returns the calculated bias as a float.

The render_volume function calculates the volume for a 3D audio object and a speaker pair. You pass it the speaker, empty object, sensitivity, object size, and the integer mixer channel, and it returns the calculated volume. The color_object_to_tuple_and_scale_up function formats Blender color objects for lighting console use. You pass it the Blender color object, and it returns a tuple of integers scaled to 0-100.

The update_alva_controller function updates the ALVA controller. You pass it the controller object, and it doesn’t return anything. The home_alva_controller function resets the ALVA controller to its home position. You pass it the controller object, and it doesn’t return anything.

Find Functions
For more advanced usage and detailed information on spy.find functions, please refer to the source code and developer documentation.

The is_inside_mesh function checks if an object is inside a mesh object. You pass it the object and the mesh object, and it returns true if the object is inside the mesh. The invert_color function inverts a color value, used for influencer calculations. You pass it the color value, and it returns the inverted color.

The find_int function finds and returns an integer within a string. You pass it the string, and it returns the integer or 1 if no integer is found. The mix_my_values function mixes values for the cpvia_generator in mixer nodes. You pass it the parent object and the parameter to mix, and it returns the mixed values.

The split_color function converts Blender's RGB space to the correct color space for fixtures. You pass it the parent object, red, green, and blue components, and the type of conversion, and it returns the converted color. The find_my_patch function finds the best patch for a given channel. You pass it the parent object, channel number, type of patch, and the desired property, and it returns the best patch.

The find_parent function corrects cases where self is a collection property instead of a node or object. You pass it the object, and it returns the parent object. The find_controllers function finds relevant strips, objects, and nodes in the scene for Sorcerer. You pass it the scene object, and it returns the relevant controllers.

The find_strips function finds relevant strips in the scene for Sorcerer. You pass it the scene object, and it returns the relevant strips. The find_objects function finds relevant objects in the scene for Sorcerer. You pass it the scene object, and it returns the relevant objects. The find_nodes function finds relevant nodes in the scene for Sorcerer. You pass it the scene object, and it returns the relevant nodes.
