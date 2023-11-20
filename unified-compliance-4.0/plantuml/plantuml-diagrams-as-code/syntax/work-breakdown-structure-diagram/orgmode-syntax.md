# OrgMode Syntax

Work Breakdown Structure Diagrams are created with nodes. Position of those nodes inside the code determines where they are located and how their connecting lines are built.&#x20;

## Node Declaration

The basic node is declared by an asterisk followed by the text you wish to appear in the node.

#### Example: Node Declaration

```
@startwbs
'Example: Node Declaration

'Create a basic node.
* Top

@endwbs
```

![Node](<../../../../.gitbook/assets/01Node\_OM\_Declaration copy.png>)

## Properties

Nodes have six properties. The only required properties are the **depth** and **text**.

* **depth** - how far down the diagram the node appears
* **direction** - which side the node appears with relation to its incoming arrow
* **box** - determines if the node appears inside of a box&#x20;
* **fill\_color** - determines the fill color of the node's box
* **text** - the written content of the node
* **style\_label** - an identifying label used for styling

### Depth

Depth determines how far down the diagram a node appears. It is represented by a number of asterisks equal to the node's depth. The node will appear in a branch beneath the most recent node of one less depth.&#x20;

Empty space before the **depth** asterisk will cause an error. Spaces before the **text** are ignored. This makes code organization a little tricky but can be performed by adding tabs or spaces in front of the text.

#### Example: Node Depth

```
@startwbs
'Example: Node Depth

'Create a top level node.
* Top Depth 0

'Create a node at a depth of one.
**  1st Branch Depth 1

'Create two nodes at a depth of two.
***     A Depth 2
***     B Depth 2

'Repeat the 2nd and 3rd step.
**  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
**  3rd Branch Depth 1
***     E Depth 2
***     F Depth 2

@endwbs
```

![Node Depth](../../../../.gitbook/assets/02Node\_OM\_depth.png)

### Direction

Replacing an asterisk with a dash will cause the node to move to the left of its branch. If this is done to multiple nodes they will be moved in order. We can show this by adding dashes to the previous depth diagram.

#### Example: Node Direction

```
@startwbs
'Example: Node Direction

'Create a top level node.
* Top Depth 0

'Create a node at a depth of one.
**  1st Branch Depth 1

'Create two nodes at a depth of two.
***     A Depth 2
***     B Depth 2

'Repeat the 2nd and 3rd step.
'Replace an asterisk (*) with a dash (-) at Depth 1.
*-  2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
'Replace an asterisk (*) with a dash (-) at Depth 2.
**  3rd Branch Depth 1
***     E Depth 2
**-     F Depth 2

@endwbs
```

![Node Direction](../../../../.gitbook/assets/03Node\_OM\_direction.png)

### Boxes

Every node has a boolean option determining if the node is contained within a **box**. The default is true. In order to remove the **box** you can place an underscore at the end of any depth property. This underscore is in addition to asterisks and dashes. It is not a replacement.

Note: **fill\_color** can not be used in conjunction with a false **box** node.

#### Example: Node Boxes

```
@startwbs
'Example: Node Boxes

'Create a top level node.
* Top Depth 0

'Create a node at a depth of one.
**  1st Branch Depth 1

'Create two nodes at a depth of two.
***     A Depth 2
***     B Depth 2

'Repeat the 2nd and 3rd step.
'Remove the box from the node at depth 1 .
**_ 2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
'Remove the boxes from the nodes at depth 2.
**  3rd Branch Depth 1
***_    E Depth 2
***_    F Depth 2

@endwbs
```

![Node Boxes](../../../../.gitbook/assets/04Node\_OM\_box.png)

### Fill Color

The **fill\_color** property determines the fill color of the drawn object. The **fill\_color** is defined by a standard color name or hex code. This property must come after a hash (**#**) sign and touch the hash sign. At the time of this writing **fill\_color** does not support gradients.

Note: **fill\_color** can not be used in conjunction with a false **box** node.

#### Example: Node Fill Color

```
@startwbs
'Example: Node Fill Color

'Create a top level node.
* Top Depth 0

'Create a node at a depth of one.
**  1st Branch Depth 1
'Create two nodes at a depth of two.
***     A Depth 2
***     B Depth 2

'Repeat the 2nd and 3rd step.
'Add color to the node at depth 1 .
**[#DarkCyan] 2nd Branch Depth 1
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
'Add color to the nodes at depth 2.
**  3rd Branch Depth 1
***[#CD1E1E]    E Depth 2
***[#561D5E]    F Depth 2

@endwbs
```

![Node Fill Color](../../../../.gitbook/assets/05Node\_OM\_fill\_color.png)

### Text

**Text** supports emphasis with creole and markup language. It also supports colors with markup language. You can define colors with a standard color name or hex code. See [Text Formatting](../text-formatting.md) for a list of creole and markup options.

You can create multiline text contained by a colon (:) and semicolon (;). All empty space between the colon and semicolon will be displayed in the **text**.

Node **text** also support icons from OpenIconic.

#### Example: Node Text

```
@startwbs
'Example: Node Text

'Create a top level node.
'Put and Icon in the text.
* Top Depth 0 <&person>

'Create a node at a depth of one.
**  1st Branch Depth 1
'Create two nodes at a depth of two.
'Use multiline text in one node.
***:A 

    Depth 
2;
***     B Depth 2

'Repeat the 2nd and 3rd step.
'Add emphasis to the text at depth 1 using creole.
**  **2nd Branch** //Depth 1//
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
'Add color and emphasis to the text at depth 2.
**  3rd Branch Depth 1
***    <color:#CD1E1E><b>E Depth 2</b></color>
***    F Depth 2

@endwbs
```

![Node Text](<../../../../.gitbook/assets/06Node\_OM\_text (3).png>)

### Style Label

Style\_labels are tags that can be added to nodes in order to format specific nodes. It works similar to CSS or \<style> tags in HTML. Style will be covered in its own section later in this chapter.

Note: **fill\_color** and inline **text** formatting will override **style\_label** formatting.

#### Example: Node Style Label

```
@startwbs
'Example: Node Style Label

<style>
wbsDiagram {
    .style_label {
        BackgroundColor #CD1E1E
    }
}
</style>

'Create a top level node.
* Top Depth 0 

'Create a node at a depth of one.
**  1st Branch Depth 1
'Create two nodes at a depth of two.
***     A Depth 2
***     B Depth 2

'Repeat the 2nd and 3rd step.
'Add a style label to the node at depth 1.
**  2nd Branch Depth 1 <<style_label>>
***     C Depth 2
***     D Depth 2

'Repeat the 2nd and 3rd step.
'Add style labels to the node at depth 2.
**  3rd Branch Depth 1
***     E Depth 2 <<style_label>>
***     F Depth 2 <<style_label>>

@endwbs
```

![Node Style Label](../../../../.gitbook/assets/07Node\_OM\_style\_label.png)

### With All Properties

#### Example: Nodes With All Properties

```
@startwbs
'Example: Nodes With All Properties

<style>
wbsDiagram {
    .style_label {
        BackgroundColor #CD1E1E
    }
}
</style>

* Top Depth 0 

**  1st Branch Depth 1
**-_            A Depth 2
***:B 

    **Depth** 
2; <<style_label>>

**  2nd Branch Depth 1 
**-_            C Depth 2
***[#561D5E]    <color:#E6E6E7><b>D Depth 2</b></color>

**  3rd Branch Depth 1
**-_            E Depth 2
***[#DarkCyan]  <color:#E6E6E7><b>F Depth 2</b></color>

@endwbs
```

![Nodes With All Properties](../../../../.gitbook/assets/08Node\_OM\_all\_properties.png)
