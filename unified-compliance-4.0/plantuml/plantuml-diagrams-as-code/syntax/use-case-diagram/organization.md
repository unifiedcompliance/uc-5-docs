# Organization

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

'Create two associations.
:Zarek: -- (Stock)
:Ivy: -- (Bag)

@enduml
```

![Title With Manual Line Breaks and Creole](../../../../.gitbook/assets/Organization04.1\_title.png)

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

'Create two associations.
:Zarek: -- (Stock)
:Ivy: -- (Bag)

@enduml
```

![Title With Automatic Line Breaks and Markup](../../../../.gitbook/assets/Organization04.2\_title.png)

#### Example: Title With Images

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

'Create two associations.
:Zarek: -- (Stock)
:Ivy: -- (Bag)

@enduml
```

![Title With Images](../../../../.gitbook/assets/Organization04.3\_title.png)

## Packages

The package method is an organizational tool used to show ownership of **actors** and **use\_cases**. Packages consist of four parts. The only requirement for a package is to have at least one **actor** or **use\_case** in the **body**.

* **style** - determines the shape of the package, there are two options
  * **package** - makes a folder shaped border for the package
  * **rectangle** - makes a rectangle shaped border for the package
* **subject** - a text field for the subject of the package
* **boundary** - a text field for the boundary of the package
* **body** - contains the **actors** and **use\_cases** that belong to the **subject**

#### Example: Package

```
@startuml
'Example: Organization Package

'Create a package with a subject and boundary.
'Add two entities in the body.
package Store <<Business>>{
    :Zarek:
    (Stock)
}

@enduml
```

![Standard Package](../../../../.gitbook/assets/Organization01\_package.png)

#### Example: Rectangle

```
@startuml
'Example: Organization Rectangle

'Create a rectangle package with a subject and boundary.
'Add at least one entity in the body.
rectangle Store <<Business>>{
    :Ivy:
    (Bag)
}

@enduml
```

![Rectangle Package](../../../../.gitbook/assets/Organization02\_rectangle.png)

## Page Break

You can add a page break with the **newpage** command.

#### Example: Page Break

```
@startuml
'Example: Page Break

'Create two associations.
:Zarek: -- (Stock)
:Ivy: -- (Bag)

'Create a page break.
newpage

'Create two more associations.
:Sean: -- (Mop)
:Maria: -- (Greet)

@enduml
```

![Page Break 1 of 2](../../../../.gitbook/assets/Organization03\_page\_break.png)

![Page Break 2 of 2](../../../../.gitbook/assets/Organization03\_page\_break\_001.png)
