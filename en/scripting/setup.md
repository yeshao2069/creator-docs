# Creating scripts

## Creating component scripts

In __Cocos Creator__, scripts are also part of resources. You can create a component script by selecting the folder in the **Assets** panel where you want to place the script file, then right-clicking and selecting **TypeScript**, or just click the Create button (**+**) in the upper left corner.

![create-script](setup/create-script.png)

Next, name it as `say-hello`, and notice a script file named `say-hello` has been generated in the **Assets** panel.

![ts](setup/ts.png)

A simple component script may look like this example:

```typescript
import { _decorator, Component, Node } from 'cc';
const { ccclass, property } = _decorator;

@ccclass('NewScript')
export class NewScript extends Component {
    /* class member could be defined like this */
    // dummy = '';

    /* use `property` decorator if your want the member to be serializable */
    // @property
    // serializableDummy = 0;

    start () {
        // Your initialization goes here.
    }

    // update (deltaTime: number) {
    //     // Your update function goes here.
    // }
}
```

> **Note**: it is recommended that users use **TypeScript** to write scripts. If you wish to use **JavaScript** to write scripts, they can be created directly in the operating system file manager, or created in a code editor.

## Editing scripts

Choose a favorite text-editing tool (such as: **Vim**, **Sublime Text**, **Web Storm**, **VSCode**...) for script editing, please setup in the **Preferences -> External Program -> Default Script Editor** option of the editor menu bar.

By double-clicking the script resource, the script editor directly opens to allow for editing. When the script is edited and saved, then returned to the editor, Cocos Creator will automatically detect the changes to the script and compile it quickly.

Before writing code, please read [Basics of Scripting](basic.md) documentation to learn more about scripts.

## Add a script to a scene node

Adding a script to a scene node is actually adding a script component to that node. Select the scene node to which you wish to add a script in the **Hierarchy** panel, at which point the properties of that node will be displayed in the **Inspector** panel. Adding a script component includes the following two ways:

1. Drag and drop the script from **Assets** panel directly into the **Inspector** panel.

    ![add scriptcomponent](setup/add-script-component.png)

2. Click the **Add Component** button at the bottom of the **Inspector** panel and select **Custom script -> SayHello** to add the script component just created. It is also possible to add it by searching for **SayHello** in the **Add Component** search box, provided that the **Add components using popups** feature in **Preferences -> Laboratory** is enabled.

    ![add scriptcomponent](setup/add-script-component2.png)

> **Note**: the component name of a script component is the name of the class defined in the script, not the script file name. The class name of the script will be the same as the script file name when the script is created, but if there are changes to the script file name/class name afterward, the two are not automatically synchronized, and can be manually synchronized, if needed.

Using `say-hello.ts` as an example, if it is renamed to `hello` in the **Assets** panel, notice that the script component name in the **Inspector** panel is still the original name, **SayHello**, only the script name has changed to `hello`:

![change-scriptname](setup/change-scriptname.png)

Double click to open `say-hello.ts`, and change the class name to **Hello**:

```TypeScript
import { _decorator, Component, Node } from 'cc';
const { ccclass, property } = _decorator;

@ccclass('Hello')
export class Hello extends Component {}
```

After saving the script and returning to the editor, notice that the script component name in the **Inspector** panel has changed to **Hello**, but the script file name is still the original name, `say-hello`:

![change-classname](setup/change-classname.png)
