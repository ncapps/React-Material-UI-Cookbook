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

### Grids
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
- Column direction
- Use the `direction` property of a `Grid` container to change the direction flow for items
- Use the `Hidden` component to hide elements at a given breakpoint
