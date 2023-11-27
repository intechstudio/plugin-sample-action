
# Sample Grid Editor plugin project for action buttons

This repository contains a sample project for the Grid Editor Plugin system capable of adding new action blocks to the action picker. The project can be imported into the currently released Editor version. 

The plugin will show an add and a remove button in the preferences window pane, which will dynamically add or remove an action block from the picker. The plugin also adds a static action button when it gets loaded, and removes the buttons on unload.

## Overview

Plugins for the Grid Editor generally consists of two parts:

 - The main JavaScript module containing the logic of the plugin. The code runs in a NodeJS environment with no special restrictions. The plugin can communicate with the Editor core through a special interface.
 - A preferences panel window shown in the Preferences pane. The code for the preferences **must** be a single HTML page. This is run in the renderer process of the Electron application. The preferences panel can request a MessagePort to communicate with the NodeJS part of the plugin.

## Installation

Plugins are run from the `plugins` folder of the Grid Editor user data folder (by default, found inside the 'Document' folder under `grid-userdata`). Each plugin can be found inside it's separate folder.

The sample project repository can be directly cloned into the plugins folder. The plugin should then be shown inside the plugins list in the Preferences window pane.

When developing a plugin, changes can be seen depending on what is being modified:

 - For the NodeJS module, changes are **only** applied after the Editor is restarted.
 - Changes in the preferences window can be seen after a plugin disable-enable cycle.

 

