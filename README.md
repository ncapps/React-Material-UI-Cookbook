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

### Grids - Placing components on the page
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

### App Bars - the top level of every page
- Create a fixed position `AppBar` using the `fixed` value of the `position` property
- Use the `toolbar mix-in` styles to add a top margin so that content isn't hidden behind the `AppBar` component
- Hide the `AppBar` component while the user is scrolling down by creating a listener on the `scroll` event on the `window` object. 
- Create a Toolbar HOC to improve code reuse
- The `MenuItem` component accepts a `component` property that is used to render the `Link` component. Pass properties to the `Link` component using the `to` property

### Drawers - a place for navigation controls
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

### Tabs - Grouping content into tab sections
- `AppBar` components can be used with the `Tabs` component. The App Bar provids a container for your tab buttons
- The `Tabs` component has two properties to help you align your tab buttons. `centered` to center the tabs and `fullWidth` to spread out the tabs
- You can use the `compose()` function from `recompose`. This functions makes your code more readable when you're applying several higher order functions that decorate your component
- Rendering tabs based on state
- Create abstactions for tab content to simplify markup
- Tab navigation with routes
