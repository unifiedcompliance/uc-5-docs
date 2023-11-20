# Styling

## Styling

Styling WBS diagrams is very similar to adding style tags and classes to HTML. The head of the PlantUML file will contain a style section that sets the format and colors for the WBS diagram. You can use style to set defaults for the entire diagram. They can be determined by depth of node or depth of arrow. They can also be determined by specific node and arrow as identified by a **style\_label** attached to the end of a node.

We will start with a basic diagram with a depth of two.

#### Starting Diagram

```
@startwbs
'Example: Starting Diagram

<style>

</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Starting Diagram](../../../../.gitbook/assets/Style01\_start.png)

## Basic Styling Syntax

The style section of and WBS diagram is defined by style tags. It begins with \<style> and ends with \</style>. Inside of those tags you must inform PlantUML that you are styling a WBS diagram with a wbsDiagram{} object. The rest of all styling will be contained inside of this object.

All styling inside of the wbsDiagram{} object contains at least one target and one property. In the following example the **node** is the target and the property of that target is the **BackGroundColor**.

#### Example: Basic Styling Syntax

```
@startwbs
'Example: Basic Styling Syntax

<style>
wbsDiagram{
    node {
        BackGroundColor #CD1E1E
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Basic Styling Syntax](../../../../.gitbook/assets/Style02\_basic\_syntax.png)

## Targets

Targets can be multi-tiered. For example you can target nodes at a specific depth. The following are the seven possible targets.

* **node**
* **arrow**
* **depth**
* **rootNode**
* **leafNode**
* **boxless**
* **style\_label**

### Node

The **node** target allows you to change the styling of nodes.

#### Example: Targeting Nodes

```
@startwbs
'Example: Targeting Nodes

<style>
wbsDiagram{
    //Change the line color of all nodes.
    node {
        LineColor DarkCyan
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Targeting Nodes](../../../../.gitbook/assets/Style03\_node.png)

### Arrow

The **arrow** target allows you to change the color of the connecting lines.

#### Example: Targeting Arrows

```
@startwbs
'Example: Targeting Arrows

<style>
wbsDiagram{
    //Change the line color of all connections.
    arrow {
        LineColor DarkCyan
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Targeting Arrows](../../../../.gitbook/assets/Style04\_arrow.png)

### Depth

The **depth** target allows you to change the style of nodes and connections at specific tiers in the diagram. **Depth** starts at the top tier with a value of 0. The **depth** value refers to the node and the connections immediately below it.

#### Example: Targeting Depth

```
@startwbs
'Example: Targeting Depth

<style>
wbsDiagram{
    //Change the line color of all objects at a depth of 0.
    :depth(0) {
        LineColor #561D5E    
    }
    //Change the line color of nodes with a depth of 1.
    //Change the line color of connections with a depth of 1 to a different color.
    :depth(1) {
        node{
            LineColor DarkCyan    
        }
        arrow{
            LineColor #CD1E1E    
        }
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Targeting Depth](../../../../.gitbook/assets/Style05\_depth.png)

### Root Node

The **rootNode** target allows you to change the style of the top tier node.

#### Example: Targeting Root Node

```
@startwbs
'Example: Targeting Root Node

<style>
wbsDiagram{
    //Change the line color of the top tier node.
    rootNode{
        LineColor #CD1E1E
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Targeting Root Node](../../../../.gitbook/assets/Style06\_rootNode.png)

### Leaf Nodes

The **leafNode** target allows you to change the style of the final node of every branch. This works regardless of symmetry.

#### Example: Target Left Nodes

```
@startwbs
'Example: Targeting Leaf Nodes

<style>
wbsDiagram{
    //Change the line color of all final tier nodes.
    leafNode{
        LineColor #CD1E1E
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2
****        i. Depth 3
****        ii. Depth 3

**  3rd Branch Depth 1

@endwbs
```

![Targeting Leaf Nodes](../../../../.gitbook/assets/Style07\_leafNode.png)

### Boxless

The **boxless** target allows you to change the style of **boxless** nodes.

#### Example: Targeting Boxless Nodes

```
@startwbs
'Example: Targeting Boxless Nodes

<style>
wbsDiagram{
    //Change the font color of all boxless nodes.
    boxless {
        FontColor #CD1E1E
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***_    B Depth 2

**_ 2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***_    F Depth 2

@endwbs
```

![Targeting Boxless Nodes](../../../../.gitbook/assets/Style08\_boxless.png)

### Style Label

Style\_labels can be used to target specific nodes for styling.

#### Example: Targeting Style Labels

```
@startwbs
'Example: Targeting Style Labels

<style>
//Create two style labels.
.label_1{
    BackgroundColor #561D5E
    FontColor #E6E6E7
}
.label_2{
    BackgroundColor #CD1E1E
    FontColor #E6E6E7
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
'Add style labels to two nodes.
***     C Depth 2 <<label_1>>
***     D Depth 2 <<label_2>>

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Targeting Style Labels](../../../../.gitbook/assets/Style09\_style\_label.png)

## Properties

There are 11 properties that can be styled on Work Breakdown Structure diagrams.

* BackGroundColor
* RoundCorner
* LineColor
* LineStyle
* LineThickness
* FontColor
* Padding
* Margin
* HorizontalAlignment
* MaximumWidth
* Shadowing

### BackGroundColor

BackGroundColor changes the fill color of the node. The BackGroundColor is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign.&#x20;

#### Example: Style BackGroundColor

```
@startwbs
'Example: Style BackGroundColor

'Create style to add background colors to multiple nodes.
<style>
wbsDiagram{
    node {
        :depth(0){
            BackGroundColor #CD1E1E\561D5E
        }
        :depth(1){
            BackGroundColor #009EA1
        }
        :depth(2){
            BackGroundColor #561D5E
        }
        
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style BackGroundColor](../../../../.gitbook/assets/Style10\_BackGroundColor.png)

### RoundCorner

RoundCorner adjusts the curve of the corners of the drawn node.

#### Example: Style RoundCorner

```
@startwbs
'Example: Style RoundCorner

'Create style to adjust the roundness of the corners of nodes.
<style>
wbsDiagram{
    node {
        :depth(0){
            RoundCorner 4
        }
        :depth(1){
            RoundCorner 8
        }
        :depth(2){
            RoundCorner 16
        }
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style RoundCorner](../../../../.gitbook/assets/Style11\_RoundCorner.png)

### LineColor

LineColor changes the color of lines on nodes and the connections between them. The LineColor is defined by a standard color name or hex code. Create a gradient by using two colors. This property must come after a hash (**#**) sign and touch the hash sign.

#### Example: Style LineColor

```
@startwbs
'Example: Style LineColor

'Create style to adjust the line colors of the diagram.
<style>
wbsDiagram{
    :depth(0){
        LineColor #CD1E1E|009EA1
    }
    :depth(1){
        LineColor #561D5E
    }
    :depth(2){
        LineColor #009EA1
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style LineColor](../../../../.gitbook/assets/Style12\_LineColor.png)

### LineStyle

LineStyle adjusts breaks breaks in the drawn lines of the diagram. A single number will cause the line to be drawn with an equal length of drawn line and break. If you use two number separated by a semicolon(;) the first number determines the length of the drawn line and the second number determines the length of the break.

#### Example: Style LineStyle

```
@startwbs
'Example: Style LineStyle

'Create style to adjust the line style of the diagram.
<style>
wbsDiagram{
    :depth(0){
        LineStyle 5
    }
    :depth(1){
        LineStyle 5;1
    }
    :depth(2){
        LineStyle 2;2
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style LineStyle](../../../../.gitbook/assets/Style13\_LineStyle.png)

### LineThickness



#### Example: Style LineThickness

```
@startwbs
'Example: Style LineThickness

'Create style to adjust the line thickness of the diagram.
<style>
wbsDiagram{
    :depth(0){
        LineThickness 2
    }
    :depth(1){
        LineThickness 4
    }
    :depth(2){
        LineThickness 8
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style LineThickness](../../../../.gitbook/assets/Style14\_LineThickness.png)

### FontColor

#### Example: StyleFontColor

```
@startwbs
'Example: Style FontColor

'Create style to adjust the font color of the diagram.
<style>
wbsDiagram{
    :depth(0){
        FontColor #CD1E1E
    }
    :depth(1){
        FontColor #561D5E
    }
    :depth(2){
        FontColor #009EA1
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style FontColor](../../../../.gitbook/assets/Style15\_FontColor.png)

### Padding

Padding adjusts the space between the node text and the line that draws the exterior of the node.

#### Example: Style Padding

```
@startwbs
'Example: Style Padding

'Create style to adjust the padding of the diagram.
<style>
wbsDiagram{
    :depth(0){
        Padding 4
    }
    :depth(1){
        Padding 8
    }
    :depth(2){
        Padding 16
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Style Padding](../../../../.gitbook/assets/Style16\_Padding.png)

### Margin

Margin adjusts the space between nodes. Margin must exist inside of a node target. It affects the entire diagram and cannot be further targeted. If more than one margin exists inside the style the first margin will supercede all others.

#### Example: Style Margin

```
@startwbs
'Example: Style Margin

'Create style to adjust the margins of the diagram.
<style>
    node {
        Margin 3
    }
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2 
***     F Depth 2 

@endwbs
```

![Style Margin](../../../../.gitbook/assets/Style17\_Margin.png)

### HorizontalAlignment

HorizontalAlignment is used to align the node text when it has multiple lines. The options are "left," "right," and "center."

```
@startwbs
'Example: Style HorizontalAlignment

'Create style to adjust the horizontal alignment of node text in the diagram.ima
<style>
wbsDiagram{
    :depth(0){
        HorizontalAlignment left
    }
    :depth(1){
        HorizontalAlignment center
    }
    :depth(2){
        HorizontalAlignment right
    }
}
</style>

*:Top 
Depth 0;

**  1st\nBranch\nDepth 1
***     A\nDepth 2
***     B\nDepth 2

**  2nd\nBranch\nDepth 1
***     C\nDepth 2
***     D\nDepth 2

**  3rd\nBranch\nDepth 1
***     E\nDepth 2
***     F\nDepth 2

@endwbs
```

![Style HorizontalAlignment](<../../../../.gitbook/assets/Style18\_Margin copy.png>)

### MaximumWidth

MaximumWidth adjusts how wide the text node is allowed to be. It will automatically wrap node text without manually formatting multiline text.

#### Example: Style MaximumWidth

```
@startwbs
'Example: Style MaximumWidth

'Create style to adjust the MaximumWidth of node text in the diagram.
<style>
wbsDiagram{
    :depth(0){
        MaximumWidth 100
    }
    :depth(1){
        MaximumWidth 75
    }
    :depth(2){
        MaximumWidth 10
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2 
***     F Depth 2 

@endwbs
```

![Style MaximumWidth](../../../../.gitbook/assets/Style19\_MaxWidth.png)

### Shadowing

Shadowing determines how far a node's shadow appears from the node producing the shadow.

#### Example: Style Shadowing

```
@startwbs
'Example: Style Shadowing

'Create style to adjust the shadowing of nodes in the diagram.
<style>
wbsDiagram{
    :depth(0){
        Shadowing 5
    }
    :depth(1){
        Shadowing 10
    }
    :depth(2){
        Shadowing 20
    }
}
</style>

* Top Depth 0

**  1st Branch Depth 1
***     A Depth 2
***     B Depth 2

**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

**  3rd Branch Depth 1
***     E Depth 2 
***     F Depth 2 

@endwbs
```

![Style Shadowing](../../../../.gitbook/assets/Style20\_Shadowing.png)
