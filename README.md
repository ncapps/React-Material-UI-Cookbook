Welcome to the repository for Material UI Cookbook. Here're you'll find all the
code samples that accompany the book and instructions on
how to run the samples using Storybook.

## Installation

The first step is cloning this repository:

```
git clone https://github.com/PacktPublishing/Material-UI-Cookbook.git
```

Then, change into the `Material-UI-Cookbook` directory. From there, you can run
the install command:

```
npm install
```

## Running the examples

To run the examples, make sure that you're in the `Material-UI-Cookbook` directory
and run Storybook:

```
npm run storybook
```

This will open Storybook in a new browser tab. The navigation is separated into
chapters and chapters are separated into recipes. The recipe names follow the
those found in the book and follow the same chronological order.

## Notes

### Chapter 1. Grids - Placing components on the page
- Apply breakpoints with `Grid` components
- Change the `justify` property value to tell the `Grid` container how to fill empty spaces
- Create higher-order Container and Item components from Grid components for improved readability
```
const Container = props => <Grid container {...props} />;
const Item = props => <Grid item {...props} />;
```
- Breakpoints can be added to HOC as well
- HOC are a great tool for removing excess syntac from JSX
- Only the specify the `xs` breakpoint property if you want a fixed number of columns. You can combine different widths in a fixed way (i.e. full-width header and footer with smaller content)
- Use the `direction` property of a `Grid` container to change the direction flow for items
- Use the `Hidden` component to hide elements at a given breakpoint

### Chapter 2. App Bars - the top level of every page
- Create a fixed position `AppBar` using the `fixed` value of the `position` property
- Use the `toolbar mix-in` styles to add a top margin so that content isn't hidden behind the `AppBar` component
- Hide the `AppBar` component while the user is scrolling down by creating a listener on the `scroll` event on the `window` object. 
- Create a Toolbar HOC to improve code reuse
- The `MenuItem` component accepts a `component` property that is used to render the `Link` component. Pass properties to the `Link` component using the `to` property

### Chapter 3. Drawers - a place for navigation controls
There are three types of `Drawer` components
  1. **Temporary**: a transient drawer that closes when an action is taken
  2. **Persistent**: a drawer that can be opened and stays open until explicitly closed
  3. **Permanent**: a drawer that is always visible
- Control the `Drawer` component type using the `variant` property
- The `Drawer` component takes an `open` property, which displays the drawer when true
- Render Drawer items based on the state of your component
- Navigate between pages using links for `Drawer` items. Check the current path to highlight the respective link
- Divide your drawer into sections if you have lots of items
- Add a `Button` component to the `ListSubheader` component so that it's clickable
- Use the `Collapse` component to hide children `ListItems`
- A common plaace to put a button that toggles the visibility of `Drawer` components is the `AppBar` component at the top of every page in your app

### Chapter 4. Tabs - Grouping content into tab sections
- `AppBar` components can be used with the `Tabs` component. The App Bar provids a container for your tab buttons
- The `Tabs` component has two properties to help you align your tab buttons. `centered` to center the tabs and `fullWidth` to spread out the tabs
- You can use the `compose()` function from `recompose`. This functions makes your code more readable when you're applying several higher order functions that decorate your component
- Rendering tabs based on state
- Create abstactions for tab content to simplify markup
- Tab navigation with routes

### Chapter 5. Expansion Panels - Group content into panel sections
- Applications are divided into sections so that users can mentally organize the information they're looking at. The `ExpansionPanel` component is one way that you can create these sections
- Headers in `ExpansionPanel` components can be formatted. Typically, the Typography component is used to render text within an expansion panel header
- Change the `variant` property of the `Typography` component to update the style
- Scrollable panel content by setting a fixed height, updating the flexDirection to column, and setting overflow to 'auto'
- Lazy loading panel content. You can wait for the user to expand the panel before making an API call to render the content in the `ExpansionPanelDetails` component

### Chapter 6. Lists - Display simple collection data
- The `List` component is used to render data collections. Lists are like simple tables. 
- A collection, usually an array of objects, is mapped to `ListItem` components.
- `ListItem` components support icons. 
- Use an avatar for list items that have `primary` and `seconday` text
- The circle that surrounds the icon is the `Avatar` component and it helps the icon stand out
- Passing `undefined` as a property value is equivalent to not setting the property at all
- You can organize lists into sections containing smaller lists
- You can use `List` components to group your items into sections, and use a `Divider` component to visually indicate the section boundary
- Lists can be nested. This is useful when you have a large number of items to render.
- List items can be clickable, resulting in a change in state or a link. You can also have secondary actions on lists called controls.
- The `ListItemSecondaryAction` component is used as a container for any controls in your list item.
- Large lists can cause performance issues. The solution is to virtualize lists using `react-virtualized`
- In order to provide predictable performance characteristics, you only want to render itms that are actually visible to the user as they scroll through the list

### Chapter 7. Tables - Display Complex Collection Data
- Use the `Table` component to display tabular data
- You can implement sortable columns in a `Table` component
- Add a search feature to your tables when you need the ability to search for relevant information
- Select rows using a `TableRow` property
- Table rows often represent an object that you can perform actions on. You can include common actions directly in each table row

### Chapter 8. Cards - Display Detailed Information
- Use multiple cards to organize information in a way that helps the user understand what they're looking at
- The main content of a `Card` component is where information concerning the subject is placed. The `CardContent` component is a child of `Card`
- Use the a `CardHeader` component to let it handle the layout styles of the header and to keep the markup within your `Card` semantic
- `CardActions` components can be used by `Card` components to display actions that users can take on the subject
- Cards have built-in capabilities for displaying media like images and videos
- You can make your cards expandable and reveal additional content when a use clicks on an `expand` button
- If you're trying to fit too much content into a `Card`, making the card expandable may be masking a problem. Instead, consider a different approach like creating a new page for the subject

### Chapter 9. Snackbars - Temporary Messages
- A `Snackbar` component is used to display messages for users. The messages are brief and don't interfere with the main application components
- Text is the most common form of a `Snackbar` message content. The `message` property accepts a string value. The snackbar is visible when the `open` property is set to `true`
- `Snackbar` is an HOC. You can pass properties to the `SnackbarContent`, `Paper`, and `Typography` components via the `ContentProps` property
- Snackbars are typically displayed in response to something. You can use state to control the visibility of the snackbar.
- The typical pattern with snackbar messages is to have them appear briefly and are hidden automatically after a short duration
- You can control the transitions used by the `Snackbar` components when it is displayed and hidden. The `Snackbar` component directly supports transition customization through properties.
- Snackbar components have an `anchorOrigin` property that allows you to change the position of the snackbar when it's displayed.
- You can use `Snackbar` components to display captured errors and style them so that errors are visually distinctive from normal messages
- Use error boundaries to selectively display components that have not thrown an error and not render components that have thrown an error
- You can embed the next course of action for the user in a snackbar. It could be useful to add a button to close the snackbar or require the user to explicitly acknowledge the message by having to close it manually
- To deal with more than one snackbar message created in a short period of time, you can create queue for all snackbar messages, so that only the most recent notification is displayed, and so that the transitions are handled properly

### Chapter 10. Buttons - Initiating Actions
- Buttons are used to initiate actions
- The `Button` component exists as three variants `Text, Outlined, Contained`
- Contol the emphasis of a `Button` with the `color` and `disabled` properties
- `Button` components can be used as links to other locations in your app
- A `Fab` component (floating action button) displays the primary screen action in a prominent way
- The common case for floating action buttons is to show the user a round button with an icon, positioned in the bottom right of the screen. The position of the `Fab` is `fixed`
- You can create a button that's just an icon using the `IconButton` component. Icon buttons are useful when you have restricted screen real estate or when you want to visually show the toggled state of something
- Butons support tee shirt-style sizing. You can use one of the predefined sizes.

### Chapter 11. Text - Collecting Text Input
- The `TextField` component can be controlled by the React component, `state`
- You need to provide the `TextField` component with aan `onChange` event handler that updates the state for the input
- The `TextField` component is a convenient abstraction that builds on other Material-UI components such as `FormControl` and `Input`
- To help the user understand what to type, you can utilize `label`, `placeholder` and `helperText` properties of the `TextField` component
- When user input mistakes are made, text input fields need to be marked as being in an error state
- The `TextField` support password fields by changing the `type` property
- The `multiline` property provides the ability to enter text values that span multiple lines
- `Input` components have properties that allow you to customize the way that they look and behave. You can adorn inputs with other components to extend the functionality of basic text inputs in a way that helps the user
- You can add masking capabilities that help guide the user toward providing the correct format

### Chapter 12. Autocomplete and Chips - Text Input Suggestions for Multiple Items
- Web applications typically provide autocomplete input fields when there are too many choices to select from
- `Chips` are used when the user needs to be able to make multiple selections
- Building an Autocomplete component
- Selecting Autocomplete suggestions
- API-driven Autocomplete
- Highlighting search results
- Standalone chip input

### Chapter 13. Selection - Make Selections from Choices
- Checkboxes often provide the user with a group of related options that can be check or uncheck. The `Checkbox` component provides basic functionality.
- It's helpful to create a HOC for creating checkbox groups
- You can change the icon that's used for both the check and unchecked state of the `Checkbox` component
- Radios are used when only one value should be selected. 
- There are a number of radio button aspects that can be customized to make unique radio button groups
- A `Switch` is very similar to a checkbox. A switch has more emphasis on toggling on/off action. User's might feel more accustomed to a switch in a mobile environment
- Controlling selects with state
- Selecting multiple items

### Chapter 14. Pickers - Select Dates and Times
- Users need an intuitive way to select date and time values
- Leverage the `TextField` component to use a date picker. Set the `type` property to `date`
- Time pickers are also derived from the `TextField` component
- It's common to set the initial date and time values to the current date and time
- You can combine date and time in a single `TextField` component
- Integrating other date and time packages for a consistent material-ui experience when using date and time pickers

### Chapter 15. Dialogs - Modal Screens for User Interactions
- Material-UI has a dialog component that provides a modal display that doesn't disrupt the current screen content
- Collecting form input
- Confirming actions
- Displaying alerts
- API integration
- Creating fullscreen dialogs
- Scrolling dialog content

### Chapter 16. Menus - Display Actions that Pop Out
- The `Menu` component enables you to organize commands for a given screen
- Think of menus as a combination of lists and buttons
- Composing menus with state
- Menu scrolling options. You can place a maximum height on the menu and have it scroll vertically
- Using menu transitions. By default, `Menu` used the `Grow` transition component
- Customizing menu items. You can change regular menu items that have `onClick` handlers into something more elaborate. For example, you can create a menu with links to other routes in the app

### Chapter 17. Typograhpy - Control Font Look and Feel
- The `Typography` component is used to render text on the screen.
- `Typography` can be used as a standalone component, but it's also used internally by other Material-UI components that render text
- The value passed to the `variant` property determines the styles that are applied to the text
- The styles for each of these variants are defined by the theme
- Use the `inherit` variant value if you want the `Typography` component to inherit the variant styles from its parent
- The `Typography` component has a `color` property
- Use the `align` property of the `Typography` component to align text horizontally
- Wrapping text with the `noWrap` property and breakpoints