# Organization

PlantUML provides many organizational options for sequence diagrams. There are tools for visually grouping and separating information. It even has a nice page break option in case you need to print, make a pdf, or a presentation.

## Title

Titles are created with the **title** command followed by the **text** for the diagram title. Title supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.&#x20;

Titles can be single line or multiline. Use **\n** for manual line breaks. For automatic line breaks use the **end title** command. You will need to define color and emphasis for every line break.

Titles can also contain images. Use the **\<img>** markup tag to insert images in the title text. You can adjust the size of the image with the **{scale}** property.

#### Example: Title With Manual Line Breaks and Creole

```
@startuml
'Example: Title With Manual Line Breaks and Creole

'Create a multiline title with manual line breaks.
'Use creole to emphasize the text.
title **Title** \n__Text__

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Title With Manual Line Breaks and Creole](../../../../.gitbook/assets/Organization01\_title\_manual\_lines.png)

#### Example: Title With Automatic Line Breaks and Markup

```
@startuml
'Example: Title With Automatic Line Breaks and Markup

'Create a multiline title with automatic line breaks.
'Use markup to emphasize and color the text.
title 
<u:red><font color=cyan>Title</font></u>
<font color=561D5E><b> Text </b></font>
end title

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Title With Automatic Line Breaks and Markup](../../../../.gitbook/assets/Organization02\_title\_auto\_lines.png)

#### Example: Title Image

```
@startuml
'Example: Title With Images

'Create a multiline title with automatic line breaks.
'Add text and an image with different sizes.
title 
An Image
<img:https://www.unifiedcompliance.com/wp-content/themes/tardigrade//images/cch_logo_icon.png>

A Resized Image
<img:https://www.unifiedcompliance.com/wp-content/themes/tardigrade//images/cch_logo_icon.png{scale=0.5}>
end title

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Title With Images](../../../../.gitbook/assets/Organization03\_title\_images.png)

## Header & Footer with Page Numbers

You can add a header and footer with the words **header** and **footer**. Follow each with the desired **text**. You can use creole for emphasis in the header. &#x20;

This is a great place to use the values of **%page%** and **%lastpage%**. We will use a page break here to show that the page values are working. For more on this, see [Page Break](organization.md#page-break) below.

#### Example: Header & Footer with Page Numbers

```
@startuml
'Example: Header and Footer with Page Numbers 

'Add a header.
'Use creole for emphasis.
header **Header** __Text__

'Add a footer with page number variables.
footer Page %page% of %lastpage%

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text

newpage

Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Header and Footer with Page Numbers](../../../../.gitbook/assets/Organization04\_header.png)

![Header and Footer with Page Numbers](../../../../.gitbook/assets/Organization04\_header\_001.png)

## Page Break

You can add a page break with the **newpage** command. This command has an optional **text** field. The **text** field will change the **title** of the new page. This **text** field is not as robust as an actual **title**. To create a multiline **title** here you must use manual **\n** line breaks. It does support creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. You will need to define color and emphasis for every line break.

#### Example: Page Break

```
@startuml
'Example: Page Break

'Add a title.
title
Original
Title
Text
end title

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text

'Make a page break with a new multiline title.
'Emphasize and color the title.
newpage <font color=561D5E><b>New</b></font>\nTitle\nText

'Send some messages and replies.
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Page Break 1 of 2](../../../../.gitbook/assets/Organization05\_page\_break.png)

![Page Break 2 of 2](../../../../.gitbook/assets/Organization05\_page\_break\_001.png)

## Dividers

You can add dividers to a sequence diagram with four equal signs. The divider has an optional text field. To utilize **text** place it in the middle of the equal signs. To create a multiline **divider** use manual **\n** line breaks. The **divider** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The default font for **dividers** is bold so adding code for bold emphasis will do nothing.

#### Example: Dividers

```
@startuml
'Example: Organization

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Make a divider with no text.
====

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Make a divider with multiline text.
'Add emphasis and color.
== //Divider//\n<font color=561D5E>Text</font> ==

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Dividers](../../../../.gitbook/assets/Organization06\_Divider.png)

## Vertical Spacing

You can add vertical space between messages with the pipe character. Three consecutive pipe characters will add a default amount of 25 pixels between messages. To customize the added amount use four pipes with a whole number in the middle.

#### Example: Vertical Spacing

```
@startuml
'Example: Vertical Spacing

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Add 25 pixels of vertical spacing.
|||

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Add 50 pixels of vertical spacing
||50||

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Vertical Spacing](../../../../.gitbook/assets/Organization07\_spacing.png)

## Delays

You can show a **delay** on your diagram with three consecutive periods. You can add **text** to the **delay** by using six periods with your chosen **text** in the middle. To create a multiline **delay** use manual **\n** line breaks. **Delays** support creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.

Notice that when you use delays, the **lifeline** changes from the default dashed line into a solid line.

#### Example: Delays

```
@startuml
'Example: Delays

'Send a message from Sean to Maria and a reply.
Sean  ->  Maria : Text
Sean  <-- Maria : Text

'Add a delay to the diagram.
...

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Add a delay with text to the diagram.
... 3 years later ...

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

'Add a delay with multiline text.
'Add emphasis and color.
... <font color=561D5E><b>5 years</b></font> \n__later__ ...

@enduml
```

![Delays](../../../../.gitbook/assets/Organization08\_delays.png)



## DurationConstraint

**DurationConstraints** consist of four parts. First you must change the **!pragma teoz** setting to **true**. Second, place an anchor at the start point. Anchors are created with a {string} inside of curly braces. Anchors are placed at the beginning of a message line. Third, place an anchor at the at the end point of the **durationConstraint**. Finally you will define which anchors are the beginning and end of each **durationConstraint** and place the **text**.

To create a multiline **durationConstraint** use manual **\n** line breaks. The **durationConstraint** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The default font for **durationConstraint** is bold so adding code for bold emphasis will do nothing.

#### Example: DurationConstraint

```
@startuml
'Example: DurationConstraint

'Change the setting to allow for durationConstraints.
!pragma teoz true

'Send four messages/replies with start and end point anchors.
{start1} Sean  ->  Maria : Go do this thing please
{start2} Maria ->  Zarek : You do the thing
{end2}   Maria <-- Zarek : Done
{end1}   Sean  <-- Maria : Finished

'Define the start and end anchors of the durationConstraints.
'Use multiline text. 
'Add emphasis and color.
{start1} <-> {end1} : __Duration__ \nText
{start2} <-> {end2} : <font color=561D5E><b>Shorter</b></font> Duration Text

@enduml
```

![DurationConstraint](../../../../.gitbook/assets/Organization09\_duration\_constraint.png)

## Boxes

Boxes are useful for visual organization. They simply draw a box around participant lifelines that you want to group together.

### Defining Boxes

**Boxes** are defined with the **box** and **end box** commands. Place the respective commands above and below the declared **lifelines** you want the **box** to encompass.

#### Example: Defining Boxes

```
@startuml
'Example: Defining Boxes

'Place a box around Sean and Maria.
box
participant Sean
participant Maria
end box

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Defining Boxes](../../../../.gitbook/assets/Organization10\_box\_declaration.png)

### Box Title

**Boxes** have an optional **title** field that will appear at the top of the **box**. If used, this field comes immediately after the **box** command. To create a multiline **title** use manual **\n** line breaks. The **title** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The default font for **title** is bold so adding code for bold emphasis will do nothing.

#### Example: Box Title

```
@startuml
'Example: Box Text

'Place a box around Sean and Maria.
'Add text.
box Box Text
participant Sean
participant Maria
end box

'Place a box around Zarek and Ivy.
'Add multline text.
'Add emphasis and color.
box <font color=561D5E>Box</font>\n__Text__
participant Zarek
participant Ivy
end box

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Zarek ->  Ivy : Text
Zarek <-- Ivy : Text

@enduml
```

![Box Title](../../../../.gitbook/assets/Organization11\_box\_text.png)

### Box Color

**Boxes** have an optional **color** property. You can change the **color** by adding a standard color name or hex code after a hash mark. The **color** property is always the last property on the box line. You can use two colors separated by a forward slash to make a gradient.

#### Example: Box Color

```
@startuml
'Example: Box Color

'Place a box around Sean and Maria.
'Add text and a background color.
box Box Text #00FFFF
participant Sean
participant Maria
end box

'Place a box around Zarek and Ivy.
'Add multline text.
'Add a gradient background color.
box Box\nText #Red/00FF00
participant Zarek
participant Ivy
end box

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Zarek ->  Ivy : Text
Zarek <-- Ivy : Text

@enduml
```

![Box Color](../../../../.gitbook/assets/Organization12\_box\_color.png)

## Mainframe

Mainframe draws a box around the entire diagram. It has a mandatory **title** field. To create a multiline **title** use manual **\n** line breaks. The **title** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.&#x20;

#### Example: Mainframe

```
@startuml
'Example: Organization Mainframe

'Declare a mainframe with a multiline title.
'Use creole and markup to emphasize and color the title.
mainframe **Mainframe** \n<font color=561D5E><i>Text</i></font>

'Send some messages and replies.
Sean  ->  Maria : Text
Sean  <-- Maria : Text
Maria ->  Zarek : Text
Maria <-- Zarek : Text
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Mainframe](../../../../.gitbook/assets/Organization13\_mainframe.png)

