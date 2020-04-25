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

### Chapter 6. List - Display simple collection data
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
