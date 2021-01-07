# Chambers
The following repository shows some of the code I've written for the Chambers Collaborative project. 

The project is written in Unity C# and is still in a development phase.

In this repository you'll find code written by me but may contain snippets of other students. 

As the semesters continue and I will work on this project I will update this repository as soon as semesters finish.

## The AI and AI Tools

The AI for the game is a Utility Theory based solution.

The reasoning behind this was that Behaviour Tree's and State Machines would create a too predictable AI and feel rigid.

I also had already created an architecture in my AI class from _David "Rez" Graham_ that would be reusable for this project. The inspiration of this system came from the GDC Talk _["Building a Better Centaur AI"](https://www.gdcvault.com/play/1021848/Building-a-Better-Centaur-AI)_

With little refactoring and a revamp of the Editor Tools it was easily reused.

__How it works__

Every `Action` in the game is an asset modifyable by designers through the editor.
Each `Action` must have a `Score Evaluator` the evaluator determines how to score the action for the AI. In order for an `Action` to actually execute code it can add `Sub Actions` which execute specific code to make the characters do something such as Moving or Shooting at the target. A `Target` could be anything, for example an `Entity`, `Tile` or `Interactable`.

During each turn of the game a squad `Controller` (AI or Player) creates a list of `ActionTargetPair`'s which for the AI means to determine the score for all of its members until no more actions remain. For the player this will create a list of where the player can move or shoot caching this data so that when the user switches between its members it is pulled from this cache giving a responsive swap mechanic.

For images and documentation on the AI please see the following documents.
* [Design Documentation](https://docs.google.com/document/d/1s1DyVbrEd67uqciO3BuTavZj7oeaOwB3R2-Yg4nLGPA)
* [Programming Documentation](https://docs.google.com/document/d/1FqUmumLTBxoZ_04HPmiofVdTwiW7RfIvOuyWCH9AymY/edit?usp=sharing)

## Weapon System

Much like the AI Tool the designers can create a new weapon asset which is modifyable through a custom editor view. This allows designers an easy flow to create new weaponry for the game. The system still needs a lot of work as we do not yet know from a design perspective how weapons will work. 

__How it works__

Each weapon has a default `Action` which is the action used to shoot at a target. But weapons can also bring special abilities which is added to the "Special Ability" slots.

__Other Tools__

Even though weapons can easily be tested out during the game I knew we would need more than just quick and easy editing at run time. We might also want to test the statistics for a weapon of how good it actually is. For this I created a custom window to test a particular weapon.

For images and documentation on the AI please see the following documents.
* [Design Documentation](https://docs.google.com/document/d/1rwcMRdbi3FC9kJFvhvV3_8PcSUzGupK5M9c_vDIG05w)
* [Programming Documentation](https://docs.google.com/document/d/1VU2SC7Cm7tL1NWSGTyOPsJ6MHJGS7RIeVtdD4T8IZcY)

## Misc.

### Project Guidelines

Before the project began we didn't have a set guideline for Unity and C# naming conventions and guidelines. I already started creating one before the semester started and eventually continued working from it. I will likely be continuing to update these guidelines as there are many things yet to be discovered.

* [Unity Project Guidelines](https://docs.google.com/document/d/1_sCy7x2zJ5GcQwL2tpib4Zzp9HUOS10mMsEfMnH2lMs)

### Grid/Pathfinding Generation Research

At the start of the project I was interested in how XCOM achieved their grid generation so I set out to research on how to achieve something similar. By looking at online footage I noticed that they are quite possibly using a custom solution which made a lot of sense to me. For our simple needs we turned out not to create it until we absolutely need it and used Unity's standard Navigation Mesh Generation locked to a defined grid.

At the end of the semester we talked about the short comings of the project in its current state and pathfinding seems to have been quite buggy and is in dire need for a better solution to allow designers to freely design levels without restrictions. So for the next semester this will likely be back on the table.

* [Research Grid Generation](https://docs.google.com/document/d/1sp6Ds0t4rw2X-lGZleYvP3roX-4-zwps8heoojcVS_M)
