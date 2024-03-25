Read an Interesting Glossary (learn some of the engineering concepts used to make Sorcerer)
==============================================================================================
**EMAR:** External Multi-disciplinary Animation Renderer. This is the software category that best describes Alva Sorcerer. It is External because unlike nearly all other comparable softwares, it cannot output DMX and instead remote-controls ETC Eos and other consoles. This is a category most occupied by TouchOSC and Depence. It is Multi-disciplinary because it provides access to robust tools for and seamless integration of lighting control and sound control. This is a category dominated by Qlab in the tech theatre context. It is Animation because its primary time-keeping tool is keyframes, not cues. This is a space somewhat occupied by Depence and somewhat by some other DMX software-only programs. It is a Renderer because it does not itself operate during a final performance; rather, it produces deliverables that dedicated FOH hardware executes. Alva Theaters hopes that the introduction of Sorcerer will lead to the development of other EMARs, and thereby, much better art all around.

**Qmeo:** It’s basically a video, but each frame is a lighting cue. The Sorcerer orb creates these on the console through OSC by creating a cue for each frame of an animation sequence and then setting up an event list to fire all of them at the right time. The orb then allows the user to set up start cues/macros and end/cue macro when the qmeo is being built from the sequencer. The qmeo builder in the node editor is compatible with many types of lighting consoles while the version inside the sequencer is only compatible with Eos.

**DDC:** Design Drag Coefficient. This is an engineering/physics coefficient used to mathematically quantify exactly how much drag is introduced in the artistic design process by dumb software decisions. A software with very low DDC will not inhibit an artist’s creative impulses. An artist using software with high DDC will not have creative impulses to begin with. Not a single design decision during the Alva Sorcerer project was made without asking the question, “Does this increase DDC or decrease DDC?”

**LPCI:** Lazy Pixel Count Index. This is engineering trigonometry used to mathematically quantify exactly how many pixels in a UI are unused, are doing nothing, and cannot be put to work by the user because they are too lazy. Note: reasonable use of white space does not contribute to LPCI since white space, when used correctly, does serve a valid purpose and does decrease DDC. Not a single design decision during Sorcerer UI development was made without asking the question, “Does this increase LPCI or decrease LPCI?”

**Lighting Choreographer/Lighting Sculptor/Lighting Animator:** These are all terms used to describe simultaneous disciplines within the new theatrical light design field made possible by Blender and Sorcerer. A *lighting choreographer* uses the tools to make lights dance the same way groups of humans dance. With posing, rhythm, cadence, expression, and inertia, often with the aid of flash strips and flash nodes. A *lighting sculptor* is more of a slow-motion painter, working slightly less with time and more with the intricate details of specific cues with the aid of the node editor. The *lighting animator* instead focuses on imbuing specific lighting fixtures with humanlike movement that exudes emotions. They may work extensively with performance capture, the NLA editor, and the graph editor to force the audience to care about the feelings of specific fixtures. To the lighting animator, every lighting fixture can be made an actor with nearly the same emotive responsibilities as the human ones. 

Noticeably absent from this list is the term “lighting pro***mer”. Pro***ming is what *we* do here at Alva Theaters. Leave that to *us*, the software developers. Stage lighting should be thought of as *art*, **NEVER** as "pro***ming".

**“Performance Capture” vs “Mo***n Capture”:** Technically, what Blender/Sorcerer does is called “mo***n capture” since it barely captures a single armature, if that. However, the term “performance capture” reflects the broader artistic intent of capturing emotive expression far more accurately, so here it is called performance capture. 

**Motor Node:** A feature not yet introduced to Sorcerer. This node will serve as a sort of oscillator for a node-based effects engine that should be released by EOD.

**EOD:** At Alva Theaters, “EOD” means End of December.

**Experimental-rated software:** “*It should work. But... if you try to rely on it for something super important and it doesn't work, don't yell at us, please. Trust us. We're telling you it might not work. But it should work.*” Any software distributed by Alva Theaters labeled as "Beta" is Experimental-rated.

**Design-rated software:** “*We know it works under normal circumstances. If it doesn't and you're our customer, we will treat it like your home is broken. We use a work order management system, not a bug reporting system. It's broken and it shouldn't be. You're our customer, so you have every right to make a work order, not some bug report.*” All publicly available Alva software is Design-rated according to Alva Theaters unless it is marked as "Beta".

**Performance-rated software:** “*If you rely on this software during a live show and it fails you, it’s our fault. You have permission from the universe to yell at us.*” No Alva Theaters software is Performance-rated or is intended to be Performance-rated.

**Safety-rated software:** “*The software is reliable and safe enough to directly control systems that can physically hurt humans under predictable circumstances that are not otherwise regulated by the government.*” No Alva Theaters software is Safety-rated or is intended to be Safety-rated.

**Developerism:** A western religion whose followers worship software developers. The religion's creed states that all decisions made by software UI developers are pure and holy and that anyone that disagrees with them simply is not smart enough to understand the software developer's genius.

**DSD's**: Dumb Software Decisions. Any single fullscreen UI layout has at least half a dozen DSD's at any given time, in roughly any given configuration. UI's that are constantly and thoroughly interated tend to have far fewer apparent DSD's. That is not necessarily because the software is better; rather, it is because users have not yet had enough time to find all the DSD's. If a software has been on the market for years without significant UI redesign, the users will know about dozens, possibly even hundreds of glaring DSD's. The longer a software interface exists unchanged, the more its DSD's become apparent to users.

**"If X: X":** A concept used in the Alva Sorcerer documentation that states that if a part of the documentation means xyz, then it should just say xyz. If it's trying to say [explain the concept more clearly here], then it should simply say [explain the concept more clearly here]. The simplest possible way to explain the concept should be in the documentation. No one should need to explain what the documenation means. If it means this, then it should just say that.

**Anti-Reduction Policy:** If we make a version of Sorcerer that is not behind a pay wall, we might build it by simply adding scripts to a new project. If Sorcerer contains 10 scripts, we might choose to add 4 of those scripts to the version not behind a pay wall. That's okay according to this policy. Once we're inside the scripts, we might want to remove certain features inside the scripts because we think this feature or that feature "is too good to put in the free version". That's not okay according to this policy. This policy states that we will not—for financial reasons—remove features from scripts that are otherwise operational, not being dependent on not-included scripts. For example, this is why Alva Sequencer has 3D audio capability. We thought about removing it since it seems like a pretty advanced feature for the free version, but instead, we created this policy to prohibit that type of reasoning. The 3D audio code happened to be in the sequencer scripts, so it has to stay unless it's dependent on an entire not-included script. We do not intentionally reduce the usefulness of our software.

**Alva Theaters core mission:** "*To build magical machines to make people happy.*"

.. figure:: ../source/_static/alva_theaters_transparent.png
   :align: center
   :alt: Mission
   :width: 200px


