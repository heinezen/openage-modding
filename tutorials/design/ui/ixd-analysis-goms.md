# Introduction

GOMS (which stands for **G***oals*, **O***perators*, **M***ethods*, **S***election Rules*) is a technique to break down a user task into its individual steps. In the GOMS model, goals are achieved by completing a set of operations (method). There can be multiple methods available to they user of which they choose one based on the selection rules. For more complex tasks, goals are allowed to be divided into several subgoals.

![GOMS elements](Elements_of_a_GOMS_model.svg)
(*[The concepts behind a GOMS model and their relationships](https://en.wikipedia.org/wiki/GOMS#/media/File:Elements_of_a_GOMS_model.svg)*, Olli Savolainen, licensed [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0))

GOMS are very useful for analyzing the complexity of a task and the potential hurdles users have to face. However, GOMS does not account for errors and inexperience, making it only applicable to the average user. Another drawback of "standard" GOMS (called CMN-GOMS) is that multitasking is not considered because operation are sequential. This is especially a problem in games as experienced players often automate motor operations (pointing, clicking, etc.) while simultaneously executing perceptual operations. A way to mitigate this is using more advanced GOMS models like CPM-GOMS.

# GOMS Example

We will now create a GOMS notation for a user task from AoE2. A common task involving the interface is the construction of a building using a villager. In our example, the player wants to build a house. For simplification purposes, we assume that all necessary resources are available and an idle villager is visible on screen.

- **Goal:** Build a house
- **Methods:** Mouse control; Hotkeys
- **Operations:** see below
- **Selection rules**: Mouse control is easy, but requires focus; Hotkeys must have been learned at some point before; ...

We will first have a look at the mouse control method. The notation must include *all* perceptive, cognitive and motor tasks necessary.

```
GOAL: BUILD-HOUSE
   GOAL: SELECT-VILLAGER
      LOCATE-IDLE-VILLAGER-ON-SCREEN
      MOVE-MOUSE-OVER-VILLAGER
      PRESS-MOUSE-BUTTON
   GOAL: CONSTRUCT-HOUSE
      GOAL: OPEN-BUILD-MENU
         LOCATE-BUILD-MENU-BUTTON
         MOVE-MOUSE-OVER-BUILD-MENU-BUTTON
         PRESS-MOUSE-BUTTON
      GOAL: FIND-HOUSE
         LOCATE-HOUSE-BUTTON
         MOVE-MOUSE-OVER-HOUSE-BUTTON
         PRESS-MOUSE-BUTTON
      GOAL: PLACE-HOUSE
         LOCATE-OPEN-SPACE-FOR-BUILDING
         MOVE-MOUSE-TO-OPEN-SPACE
         PRESS-MOUSE-BUTTON
```

The same example with the hotkey method looks like this:

```
GOAL: BUILD-HOUSE
   GOAL: SELECT-VILLAGER
      PRESS-IDLE-VILLAGER-HOTKEY
   GOAL: CONSTRUCT-HOUSE
      GOAL: OPEN-BUILD-MENU
         PRESS-BUILD-MENU-HOTKEY
      GOAL: FIND-HOUSE
         PRESS-HOUSE-HOTKEY
      GOAL: PLACE-HOUSE
         LOCATE-OPEN-SPACE-FOR-BUILDING
         MOVE-MOUSE-TO-OPEN-SPACE
         PRESS-MOUSE-BUTTON
```

As you can see, the hotkey method does not require as many operations as the mouse control method because it does not need as many `LOCATE` operations. Less operations neither indicates that the method is faster nor does is necessarily mean that the method is less complicated. For example, remembering the hotkeys would be a selection requirement of this method and therefore requires a certain amount of knowledge on the player's side.

The methods and selection rules can be combined into a unified notation, shown below.

```
GOAL: BUILD-HOUSE
   GOAL: SELECT-VILLAGER
      [select*:  GOAL: SELECT-VILLAGER-MOUSE-METHOD
                    LOCATE-IDLE-VILLAGER-ON-SCREEN
                    MOVE-MOUSE-OVER-VILLAGER
                    PRESS-MOUSE-BUTTON
                 GOAL: SELECT-VILLAGER-HOTKEY-METHOD
                    PRESS-IDLE-VILLAGER-HOTKEY]
   GOAL: CONSTRUCT-HOUSE
      [select*:  GOAL: CONSTRUCT-HOUSE-MOUSE-METHOD
                    GOAL: OPEN-BUILD-MENU
                       LOCATE-BUILD-MENU-BUTTON
                       MOVE-MOUSE-OVER-BUILD-MENU-BUTTON
                       PRESS-MOUSE-BUTTON
                    GOAL: FIND-HOUSE
                       LOCATE-HOUSE-BUTTON
                       MOVE-MOUSE-OVER-HOUSE-BUTTON
                       PRESS-MOUSE-BUTTON
                    GOAL: PLACE-HOUSE
                       LOCATE-OPEN-SPACE-FOR-BUILDING
                       MOVE-MOUSE-TO-OPEN-SPACE
                       PRESS-MOUSE-BUTTON
                 GOAL: CONSTRUCT-HOUSE-HOTKEY-METHOD
                    GOAL: OPEN-BUILD-MENU
                       PRESS-BUILD-MENU-HOTKEY
                    GOAL: FIND-HOUSE
                       PRESS-HOUSE-HOTKEY
                    GOAL: PLACE-HOUSE
                       LOCATE-OPEN-SPACE-FOR-BUILDING
                       MOVE-MOUSE-TO-OPEN-SPACE
                       PRESS-MOUSE-BUTTON]

* Selection Rule for GOAL: SELECT-VILLAGER
   If hotkeys can be remembered, use SELECT-VILLAGER-HOTKEY-METHOD
      else use SELECT-VILLAGER-MOUSE-METHOD
* Selection Rule for GOAL: CONSTRUCT-HOUSE
   If hotkeys can be remembered, use CONSTRUCT-HOUSE-HOTKEY-METHOD
      else use CONSTRUCT-HOUSE-MOUSE-METHOD
```

# Keystroke-Level Model

The Keystroke-Level Model GOMS (KLM-GOMS) provides a simple technique to estimate the time a user needs for a specific method. To achieve this, every operation is categorized into interaction types. Each interaction type is assumed to be completed in a certain time by the user. The following list contains the most prominent interaction times and their suggested completion times:

- **K**eystroke: Pressing a key on the keyboard. Keystroke combinations are handled as if the keys were pressed in sequence. A sequence of keystrokes can also be written as **T(n)**. *Time: 0.28s*
- **P**ointer: Pointing with the mouse courser on a target on the screen. *Time: 1.1s*
- **B**utton Press: Mouse button press **or** release. *Time: 0.1s*
- **BB**: Mouse button press **and** release *Time: 0.2s*
- **H**oming: Moving the hand(s) from mouse to keyboard. *Time: 0.4s*
- **M**ental preparation: Time necessary for perception or thinking (e.g. searching for a button in the interface). This type is the most fuzzy one and is prone to errors. *Time: 1.2s*
- **R**esponse: Response time of the application if not immediate (e.g. a loading screen). The time has to be measured independently for the operations.

KLM-GOMS can easily be visualized by taking GOMS notation and adding the interaction types to the right of the operations. With this method we can categorize the previous examples.

```
GOAL: BUILD-HOUSE
   GOAL: SELECT-VILLAGER
      LOCATE-IDLE-VILLAGER-ON-SCREEN       M
      MOVE-MOUSE-OVER-VILLAGER             P
      PRESS-MOUSE-BUTTON                   BB
   GOAL: CONSTRUCT-HOUSE
      GOAL: OPEN-BUILD-MENU
         LOCATE-BUILD-MENU-BUTTON          M
         MOVE-MOUSE-OVER-BUILD-MENU-BUTTON P
         PRESS-MOUSE-BUTTON                BB
      GOAL: FIND-HOUSE
         LOCATE-HOUSE-BUTTON               M
         MOVE-MOUSE-OVER-HOUSE-BUTTON      P
         PRESS-MOUSE-BUTTON                BB
      GOAL: PLACE-HOUSE
         LOCATE-OPEN-SPACE-FOR-BUILDING    M
         MOVE-MOUSE-TO-OPEN-SPACE          P
         PRESS-MOUSE-BUTTON                BB
```

After doing this, we can calculate the estimated time the average user needs to complete the task.

```
4M + 4P + 4BB = 4.8 + 4.4 + 0.8 = 10s
```

10 seconds is probably a very conservative estimate and does not represent the average user well. Therefore, it is important to adjust the values to the context by observing users or to use different time estimations for other experience levels. You can also add custom interaction types to KLM-GOMS that are based on the interaction in your application.

```
GOAL: BUILD-HOUSE
   GOAL: SELECT-VILLAGER
      PRESS-IDLE-VILLAGER-HOTKEY        K
   GOAL: CONSTRUCT-HOUSE
      GOAL: OPEN-BUILD-MENU
         PRESS-BUILD-MENU-HOTKEY        K
      GOAL: FIND-HOUSE
         PRESS-HOUSE-HOTKEY             K
      GOAL: PLACE-HOUSE
         LOCATE-OPEN-SPACE-FOR-BUILDING M
         MOVE-MOUSE-TO-OPEN-SPACE       P
         PRESS-MOUSE-BUTTON             BB
```

The hotkey method is less time consuming than the mouse select method when calculating with our estimated completion times.


```
3K + M + P + BB = 0.84 + 1.2 + 1.1 + 0.2 = 3.34s
```

Similar to the previous result, the estimate of 3.34 seconds is presumably not accurate. However, it shows that using hotkeys is more efficient for our example.

Analyzing an ingame interface with KLM-GOMS like in our example is usually not the best idea because users tend to utilize multitasking in games more than in other applications. Therefore, it is better suited for analyzing non-ingame parts of the interface, e.g. the settings menu. KLM-GOMS shares the same disadvantages as standard GOMS which means it does not factor in chances for errors.

# Further Reading

* [Cogulator](http://cogulator.io/) is a free software to create CPM-GOMS to judge multitasking applications
