# Sample Grid Editor package project for action buttons

This repository contains a sample project for the Grid Editor Package system capable of adding new action blocks to the action picker. The project can be imported into the currently released Editor version.

The package will show an add and a remove button in the preferences window pane, which will dynamically add or remove an action block from the picker. The package also adds a static action button when it gets loaded, and removes the buttons on unload.

## Overview

Packages for the Grid Editor generally consists of two parts:

- The main JavaScript module containing the logic of the package. The code runs in a NodeJS environment with no special restrictions. The package can communicate with the Editor core through a special interface.
- A preferences panel window shown in the Preferences pane. The code for the preferences **must** be a single HTML page. This is run in the renderer process of the Electron application. The preferences panel can request a MessagePort to communicate with the NodeJS part of the package.

## Installation

Packages are run from the `packages` folder of the Grid Editor user data folder (by default, found inside the 'Document' folder under `grid-userdata`). Each package can be found inside it's separate folder.

The sample project repository can be directly cloned into the packages folder. The package should then be shown inside the packages list in the Preferences window pane.

When developing a package, changes can be seen depending on what is being modified:

- For the NodeJS module, changes are **only** applied after the Editor is restarted.
- Changes in the preferences window can be seen after a package disable-enable cycle.
