# Boxes & Item - Unreal Engine Blueprint Project

## Overview

This project is a solution to the following test task:

**Task:**
Create two Blueprints: `BP_Item` and `BP_Boxes`.

### BP_Item
- A static mesh box.
- Physics is disabled in the `Begin Play` event.
- Contains an integer variable `Index` (set as instance editable and expose on spawn).

### BP_Boxes
- Consists of two hollow "boxes" with open tops and a `BoxCollision` component at the bottom of the boxes.

### Scenario Map
- The map contains one `BP_Boxes` instance and ten `BP_Item` instances with `Index` values ranging from 0 to 9.

### Required Logic (Blueprint Implementation):
1. **Item Movement:** When keys 1-0 are pressed, the `BP_Item` with the corresponding `Index` should move at a uniform speed to one of the two designated positions (`Pos`). The position is chosen randomly. (For example, pressing the "4" key moves the item with `Index = 4`).
2. **Enable Physics:** Upon reaching the target position, physics should be enabled for the item, causing it to drop to the bottom of the box.
3. **Item Removal:** Once the item collides with the `BoxCollision` at the bottom of the box, the item should be removed from the map.

Pressing the same key again will have no effect since the item has already been removed.

## Additional Features

In addition to the requested functionality, the following features were added to enhance the experience:

1. **Handling Multiple Items with the Same Index:** 
   - If there are multiple items with the same `Index` on the level, a single key press will trigger one item. This means you will need to press the key as many times as there are items on the map.
   - If you set the default value of the `bMoveAllItemsAtOnce` variable in the `BP_Player` to `true`, all items with the specified index will move to the boxes simultaneously.

2. **Handling Items that Miss the Box:** 
   - If an item does not touch the bottom of the box and falls to the floor (which can happen if you quickly press all the number keys), the item will remain on the floor for 3 seconds before respawning at its initial location.

## How to Use

1. Place the `BP_Boxes` and `BP_Item` instances on the map as described in the scenario.
2. Press keys 1-0 to trigger the corresponding items.
3. Adjust the `bMoveAllItemsAtOnce` variable in `BP_Player` as needed to enable or disable the simultaneous movement of items with the same index.
4. Observe the item behavior and additional features as they interact with the environment.

 
