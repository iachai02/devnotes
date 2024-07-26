# Flexbox

## What do you need

- start out with a class container that holds children elements

## Properties
- `display: flex`: aligned in row orientation (default orientation)
    - row: default MAIN axis
    - column: default CROSS axis
- `flex-direction:`:
    - `column`: change the elements to be in column orientation
    - `row`: change the elements to be in the row orientation (this is default)
- `justify-content:`: aligns elements on the main axis
    - `flex-end`: aligns all the elements to the end of the main axis
    - `flex-start`: sends them to the start of the main axis
    - `center`: centers the elements
    - `space-around`: spaces the elements evenly and centered
    - `space-between`: even spacing between all the children in the row
- `align-items:`: aligns elements on the cross axis
    - `flex-start`: align them at the start of the cross axis
    - `flex-end`: align them at the end of the cross axis
    - `center`: centers them in the cross axis
    - `stretch`: stretches the elements across the entire cross axis
- `flex-wrap:`:
    - `wrap`: if there are any elements too large that push other elements, this will allow the elements being pushed to go to another row
- `gap:`:
    - `vertical{pixel} horizontal{pixel}`: spreads the element by that amount in the vertical or horizontal direction
- `flex-grow:`:
    - `{number}`: grows the elements based on the other elements
- `flex:`: uses flex-grow, flex-shrink, flex-basis in one go
    - `{number}`
    - `{flex-grow} {flex-shrink} {flex-basis}`
- `flex-self:`: ignores the flex alignment from the parent 
    - `flex-end`: ignores the flex alignment from the parent and moves the element