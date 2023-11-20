# Interactions

PlantUML gives us seven common interactions as well as a customizable interaction. Five of these interactions behave the same. The other three will require separate explanations.



## Basic Declaration

Interactions are declared with a keyword similar to notes. They are closed with the command word **end**.

#### Example: Interactions Declaration

```
@startuml
'Example: Interactions Declaration

'Declare the opt interaction.
opt

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

'Close the opt interaction
end

'Send a message from Maria to Zarek and a reply.
Maria ->  Zarek : Text
Maria <-- Zarek : Text

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Declaration](../../../../.gitbook/assets/Interactions01\_declaration.png)

## Basic Properties

The five similar interactions have four properties. Only the **operator** is required.

* operator - determines the type of interaction
* operator\_color - defines the color of the pentagon containing the interaction type
* body\_color - defines the color of the main body of the interaction
* header - allows for a message at the top of the body of the interaction

### Operator

The **operator** determines the type of interaction. The **operator** or interaction type is displayed in the upper left corner of the interaction in the sequence diagram. The following five **operators** are also the five similar interactions in PlantUML.&#x20;

* opt
* loop
* par
* break
* critical

You can place interactions within interactions by using more than one **operator** before closing with the **end** command.

#### Example: Interaction Operator

```
@startuml
'Example: Interaction Operator

'Declare the opt interaction.
opt

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare the loop interaction.
    loop

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the loop interaction.
    end

'Close the opt interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Operator](../../../../.gitbook/assets/Interactions02\_operator.png)

### Operator Color

**Operator\_color** is defined by a hash mark followed by a standard color name or hex code. The hash mark _must_ touch the last character of the operator. If there is a space between the **operator** and hash mark you will change the **body\_color**.

#### Example: Operator Color

```
@startuml
'Example: Interaction Operator Color

'Declare the opt interaction.
'Make the operator_color Cyan.
opt#cyan

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare the loop interaction.
    'Make the operator_color purple.
    loop#561D5E

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the loop interaction.
    end

'Close the opt interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Operator Color](../../../../.gitbook/assets/Interactions02.1\_operator\_color.png)

### Body Color

**Body\_color** is defined by a hash mark followed by a standard color name or hex code. Ensure that there is a space to the left of the hash mark.

#### Example: Body Color

```
@startuml
'Example: Interaction Body Color

'Declare the opt interaction.
'Make the body_color Cyan.
opt #cyan

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare the loop interaction.
    'Make the operator_color purple and the body_color red.
    loop#561D5E #red

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the loop interaction.
    end

'Close the opt interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Body Color](../../../../.gitbook/assets/Interactions02.2\_body\_color.png)

### Header

The **header** property defines optional text at the top of the interaction body. The **header** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code. The default font for **headers** is bold so adding code for bold emphasis will do nothing.

#### Example: Interaction Header

```
@startuml
'Example: Interaction Header

'Declare the opt interaction.
'Add a header with creole emphasized text.
opt __Opt Header__

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare the loop interaction.
    'Make the operator_color purple and the body_color red.
    'Add a header with markup text for color and emphasis.
    loop#561D5E #red <font color=FFFFFF><i>Loop Header</i></font>

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the loop interaction.
    end

'Close the opt interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Header](<../../../../.gitbook/assets/Interactions03\_header (1).png>)

## Customizable Interaction

The **group** command allows us to create our own **operator**. It also has optional **operator\_color**, **body\_color**, and **header** properties. The **header** must be enclosed by square brackets.

#### Example: Customizable Interaction

```
@startuml
'Example: Customizable Interaction

'Declare an interaction with a custom operator.
'Add a header.
group search [Search Header]

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare an interaction with a custom operator.
    'Add a header.
    'Make the operator_color purple and the body_color red.
    group#561D5E #red find [Find Header]

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the second interaction.
    end

'Close the first interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Customizable Interaction](../../../../.gitbook/assets/Interactions04\_custom.png)

## Alt/Else

The **alt** interaction behaves like the previous interactions but also has the **else** command word. **Else** can also be followed by an optional **header**. You can color alt/else like the other interactions, as well as picking a different colors for alt and else.

#### Example: Interaction Alt/Else

```
@startuml
'Example: Interaction Alt/Else

'Send a message from Sean to Maria
Sean  ->  Maria : Text

'Declare an alt interaction.
'Add a header.
'Make operator yellow the body_color cyan.
alt#FFFF00 #cyan Success Text

    'Send a reply from Maria to Sean.
    Sean  <-- Maria : Text

'Add an else command with a header.
'Make the body color purple. 
'Emphasize and color the text using markup.
else #561D5E <font color=FFFFFF><i>Failure Text</i></font>

    'Send a reply from Maria to Sean.
    Sean  <-- Maria : Text

    'Declare the loop interaction.
    'Add a header.
    loop Loop Header

        'Send a message from Maria to Zarek and a reply.
        Maria ->  Zarek : Text
        Maria <-- Zarek : Text

    'Close the loop interaction.
    end

'Close the alt interaction.
end

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Alt/Else](<../../../../.gitbook/assets/Interactions05\_alt\_else (2).png>)

## Reference

The reference interaction behaves similar to notes. It consists of the command word **ref**, **position**, and **text**. The position will always be **over** one or more lifelines. You can make the text single line with a **:** or multiline by using the **end ref** command. The reference interaction can exist inside of other interactions but it cannot contain messages or other interactions.

You can change the **operator\_color** of a reference interaction but not the **body\_color**. The **text** supports creole syntax for emphasis and markup language for color and emphasis. You can define colors with a standard color name or hex code.

#### Example: Interaction Reference

```
@startuml
'Example: Interaction Reference

'Declare the opt interaction.
'Add a header.
opt Opt Header

    'Send a message from Sean to Maria and a reply.
    Sean  ->  Maria : Text
    Sean  <-- Maria : Text

    'Declare a reference interaction.
    'Cover Sean.
    'Add single line text.
    'Make the operator_color cyan.
    ref#cyan over Sean : Reference Text

    'Send a message from Maria to Zarek and a reply.
    Maria ->  Zarek : Text
    Maria <-- Zarek : Text

'Close the opt interaction.
end

'Declare a reference interaction.
'Cover all three lifelines.
'Add multiline text that is emphasized and colored with markup.
ref over Sean, Zarek
Reference

<font color=561D5E><i>Text</i></font>
end ref

'Send a message from Zarek to Sean and a reply.
Zarek ->  Sean : Text
Zarek <-- Sean : Text

@enduml
```

![Interaction Reference](../../../../.gitbook/assets/Interactions06\_ref.png)

