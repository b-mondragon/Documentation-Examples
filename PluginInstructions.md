# How Does the Text Editor Work

The text editor component is a plugin-based editor that allows you to add different functionalities. This component is based on the X library, which is located in the following folder: `repository/src/components/FormComponents/TextEditor`

The text editor component can have the two following toolbars:

* **Fixed toolbar**: A toolbar that is always present in the text field and includes text-editing options.
* **Mark Balloon toolbar**: A floating toolbar that appears when you type in the text fields of the form UI or when you select the text. You can hover over it to select the styles and apply them to your text.

## Fixed Toolbar

You can modify the fixed toolbar attributes to change its appearance. Take into account the following.

While importing the component `TextEditor`, this receives a prop called `toolbarConfig`.

The `toolbarConfig` receives two attributes:

```jsx
   toolbarConfig={{
     display: true, // If set to false, the fixed toolbar will not be displayed
     btnArr: ['h1', 'bold', 'italic'], // Array of buttons displayed in the fixed toolbar
   }}
```

## How to add new plugins into the Mark Balloon toolbar

First, go to the Mark Balloon toolbar, which is located in the following folder: `repository/src/components/FormComponents/TextEditor/MarkBalloonToolbar.tsx`

Inside the `BalloonToolbar` element are several `MarkToolbarButton` elements. These are the buttons and functionalities of the text editor component. Inside the `type={getPluginType(editor, MARK_BOLD)}` attribute the `MARK_BOLD` value indicates the functionality.

To add a plugin to the Mark Balloon Toolbar:

1. Import the plugin element from the Plate library by adding it to the list under: `import {NEW_ELEMENT} from '@udecode/plate'`
2. Add a `MarkToolbarButton` element under `BalloonToolbar`

```jsx
     <MarkToolbarButton
        type={getPluginType(editor, MARK_BOLD)}
        icon={<FormatBold/>}
        tooltip={boldTooltip}
        actionHandler="onMouseDown"
      />`
```

3. Define the `type` attribute value.

   3.1 Include `{getPluginType(editor, MARK_BOLD)}`

   3.2 Replace the `MARK_BOLD` value with the functionality you imported in step 1.

4. Define the `icon` attribute value. This is the icon that is displayed on the toolbar.
5. Define the `tooltip` attribute value. This is the information that appears when you hover over the icons on the toolbar.
6. Add the `actionHandler="onMouseDown"` attribute.

**Note:** The attributes vary depending on the type of plugin. For more information about the plugins supported by the X library, go to the X documentation [here](https://github.com).
