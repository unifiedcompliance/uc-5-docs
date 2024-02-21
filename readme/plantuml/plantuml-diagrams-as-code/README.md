# Diagrams as Code

I’m not telling you something you don’t know; compliance with industry regulations and standards is paramount. From data protection laws to quality management frameworks, our organizations across every sector we’ve researched need to demonstrate adherence to these requirements. Our organizations invest significant time and resources to ensure operations adhere to these increasingly stringent regulations. Various Authority Documents mention a host of diagrams to be maintained for compliance purposes:

* access path diagram,
* application topology diagram,
* data flow diagram,
* network diagram,
* procedure diagram,
* site plan diagram or floor plan diagram,
* software logic diagram,
* system topology diagram,

…and over fifty other diagrams have been mapped within the Unified Compliance Framework\[^ For a simple list of diagrams called for by Authority Documents, see the hyponym/hypernym list at https://compliancedictionary.com/term/21937.]. Compliance diagrams can be placed roughly into two camps. The first camp is those diagrams that _should_ be created by the computer systems they apply to. The second camp is those diagrams that _can_ be made by Generative Artificial Intelligence (GAI) applications like those from OpenAI, Amazon, etc., with ChatGPT being the most heard of GAI. Both sets of diagrams either _should_ or _can_ begin as Diagrams as Code. Why? With the advent of PlantUML, a powerful language for diagramming in plain text language, compliance efficiency comes into play.

## Why UML?

Unified Modeling Language (UML) is a standard notation for the modeling of objects as a first step in developing an object-oriented design methodology. UML is an accepted standard of the Object Management Group (OMG), which is also sponsoring CORBA as the industry standard for distributed object programming.

Diagrams can be as simple as the short sequence diagram below left, or the very involved one below right.

| Simple                                                                                                                  | Complex                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| ![](https://www.dropbox.com/scl/fi/g36e12ajc1b2834ech4da/this-that-sequence.png?rlkey=8b2ippt9s0070sgn9w122cqy4\&raw=1) | ![](https://www.dropbox.com/scl/fi/i9fem81pymr5y731offkj/longsequence.png?rlkey=jebpt6wcw8q05jipwls5k1p5h\&raw=1) |

What gives UML its strength is that it can be used for modeling a system _independent_ of any platform or language. UML diagrams are so standardized that modeling them using plain language - _textual modeling tools_ - evolved shortly after UML became a standard. So much so that UML has become a staple in the compliance as code world, specifically **Diagrams as Code**. Diagrams as Code tools support the use of textual notations and languages to describe software models and automatically render the corresponding graphical diagram from that textual description\[^ “Text to UML and Other ‘Diagrams as Code’ Tools - Fastest Way to Create Your Models.” n.d. Accessed December 13, 2021. [https://modeling-languages.com/text-uml-tools-complete-list/](https://modeling-languages.com/text-uml-tools-complete-list/).].

_How_ do diagrams created using text create compliance efficiency? Easy. Diagrams as Code enable organizations to quickly generate different types of diagrams from a single source – plain text language. Instead of an organization using LucidChart, Miro, FigJam, Visio, Gliffy, SmartDraw, Draw.io, Sketch, blah blah blah blah blah, your team can create the diagrams using **text** and then let the software turn that text into art. If you natively draw a diagram using any of the software mentioned above tools, you are locked into _that_ application. If you start with PlantUML, then any of the tools above that support PlantUML can be used to edit the diagram (and return it as text as well). This reduces complexity. This reduces the cost of software, training, and the overhead of working with multiple incompatible formats—compliance Efficiency.

## What are Diagrams as Code?

Originally, Diagrams as Code was an approach to creating visual diagrams, such as network or architecture diagrams, using code rather than a graphical user interface. Diagrams as Code have become a paradigm shift for visual communication. They are intended to allow developers, engineers, and other technical professionals to represent visual models using familiar code syntax. Diagrams as Code generates the diagram from the code produced by software rather than being created manually using a visual editor\[^ “Diagrams as Code: A Paradigm Shift for Visual Communication.”].

With the advent of GAI, diagrams can be created from simple prompts. For instance, the ChatGPT-4 prompts below…

```
Generate a short description of the following procedure [procedure] by the [R] where the [A] is accountable and the [C] is informed for [company name].

[procedure] = create media policy

[R] = Media Relations Manager

[A] = Human Resources Manager

[C] = Legal Team

[company name] = Unified Compliance

Outline the procedure steps for the above.

Generate a sequence diagram in PlantUML format for the procedure above.
```

… generate the following text (including a PlantUML diagram as code)…

```
The Media Relations Manager will create a media policy for Unified Compliance in collaboration with the Human Resources Manager, who will ensure that the policy follows company standards and regulations. The Legal Team will also be informed of the creation of the policy to provide legal oversight.

Procedure Steps:

The Media Relations Manager will research and draft the media policy.

The Human Resources Manager will review the policy for compliance with company standards and regulations.

The Legal Team will be informed of the policy and provide legal oversight.

The policy will be revised and finalized as needed.

The policy will be distributed to all relevant employees and stakeholders.

Sequence Diagram:

@startuml
actor “Media Relations Manager” as MR
participant “Human Resources Manager” as HR
participant “Legal Team” as LT
MR -> HR: Draft media policy
HR -> HR: Review policy for compliance
HR -> LT: Inform of policy creation
LT -> LT: Provide legal oversight
HR -> MR: Provide feedback on policy
MR -> HR: Revise policy as needed
MR -> HR: Finalize policy
MR -> HR: Distribute the policy to relevant parties
@enduml
```

… for which the visual diagram looks like this:

<figure><img src="https://www.dropbox.com/scl/fi/yurxx6v9uj5vtrufabbjl/Visual-diagram-of-PlantUML-Diagram-as-Code.png?rlkey=bj7he3gq2wwb7gz9f1y9emm2q&#x26;raw=1" alt=""><figcaption><p><em>Visual diagram of PlantUML Diagram as Code</em></p></figcaption></figure>

## Can Diagrams as Code be used for regulatory diagramming requirements?

One of the significant advantages of using Diagrams as Code for compliance is the ability to capture detailed information about the system concisely and standardized. Traditional visual diagrams often lack the level of detail required for compliance purposes. With Diagrams as Code, organizations can document their systems to minor components, providing auditors and regulatory bodies with a comprehensive view of the organization’s processes and data disclosures.

Moreover, Diagrams as Code enable organizations to generate different types of diagrams from a single source quickly. With a well-defined codebase, organizations can automatically create class diagrams, activity diagrams, entity-relationship diagrams, and other visual representations of their systems. This flexibility allows project managers and compliance teams to extract the information they need in various forms, depending on the specific compliance requirements.

The use of Diagrams as Code also provides a great help in maintaining consistency across different projects and teams. When compliance regulations change or new projects are initiated, organizations can quickly leverage existing code templates and frameworks to generate compliant diagrams. This consistency ensures compliance standards are upheld throughout the organization and reduces the risk of non-compliance due to human error or oversight.

Given this discussion on using Diagrams as Code for regulatory diagramming requirements, I’d sprinkle a bit of wisdom on top to amplify the message. Here’s how we can jazz it up:

### Adding a Dash of Realism with “The Devil’s in the Details”

Ladies and gents, while we’ve been singing praises about Diagrams as Code, let’s not forget the devil’s in the details. It’s fantastic that these diagrams offer a high level of detail and standardization, but not all regulatory bodies have caught up with the times. Some still expect to see traditional visual diagrams with glossy finishes. So, while you’re coding away those diagrams, remember that you might need to translate them into a more... let’s say, “classic” format for specific audiences.

### “Flexibility is Key” - A Reminder

Also, let’s hammer home the flexibility of Diagrams as Code. Imagine you’ve got a complex system that makes the Gordian Knot look like child’s play. With Diagrams as Code, you’re not just creating one type of diagram but setting up a Swiss Army knife of diagramming capabilities. Need a class diagram? Done. An activity diagram? You got it. An entity-relationship diagram? Please, that’s child’s play. This adaptability isn’t just remarkable; it’s crucial for ensuring that whatever the regulatory requirement, you’re prepared. Think of it as your diagramming superhero cape - one size fits all.

### Consistency: The Holy Grail of Compliance

And let’s not skip on consistency. In the ever-changing landscape of compliance regulations, consistency is your North Star. It keeps your diagrams from turning into a Picasso painting when they should look more like a Mondrian. When regulations update (because they will, as sure as taxes), having a solid foundation of Diagrams as Code means you’re just a few tweaks away from compliance, not a complete overhaul. This isn’t just efficient; it’s sanity-saving.

## What do the regulators say about Diagrams as Code?

Right now, nothing specific. However, the National Institute of Standards and Technology (NIST) provides guidelines for creating diagrams that meet regulatory requirements. While the guidelines do not specifically address Diagrams as Code, they provide helpful information on creating clear, accurate diagrams that comply with applicable standards\[^ § PL-2: System Security Plan of Force, “Security and Privacy Controls for Information Systems and Organizations.”]. In addition, the International Organization for Standardization (ISO) provides standards for creating diagrams that meet regulatory requirements. ISO 5807:1985, for example, provides guidelines for creating flowcharts that comply with international standards. While this standard predates Diagrams as Code, the principles it outlines may still be relevant\[^ ISO Working Group, “ISO 5807.”].

### Text-based regulatory diagramming has many benefits

Because text-based diagrams are created using text, they can be easily updated and modified as needed. This is without requiring the user to drag and drop symbols or connectors. This can save time and reduce errors, particularly when diagrams need to be updated frequently.

In addition, because text-based uses a simple syntax, diagrams can be created quickly and easily, even by users not experienced with traditional diagramming tools. This can be particularly useful when diagrams, such as during an audit or regulatory inspection, need to be rapidly created.

Finally, these text-based tools can be easily integrated with other tools and systems, such as version control systems or issue-tracking systems. In this way, it will be easier to collaborate on diagrams over time and ensure that they remain accurate and up-to-date in the long run.

## What tools can be used to create Diagrams as Code?

While UML has been applied to various activities since the second half of the 1990s and has been used with object-oriented development methods since that time\[^ Whitepapers and scholarly articles started appearing around 2010 describing how to construct text-based UML diagrams. This is one of the better articles: Washizaki, Hironori, Masayoshi Akimoto, Atsushi Hasebe, Atsuto Kubo, and Yoshiaki Fukazawa. 2010. “TCD: A Text-Based UML Class Diagram Notation and Its Model Converters.” In Advances in Software Engineering, edited by Tai-hoon Kim, Haeng-Kon Kim, Muhammad Khurram Khan, Akingbehin Kiumi, Wai-chi Fang, and Dominik Ślęzak, 296–302. Communications in Computer and Information Science. Berlin, Heidelberg: Springer. [https://doi.org/10.1007/978-3-642-17578-7\_29](https://doi.org/10.1007/978-3-642-17578-7\_29).], sites that have converted plain text English into UML diagrams, such as Plantuml.com, yuml.com, and code2flow.com didn’t even _come into existence_ until 2015, and didn’t start becoming popular until 2018. As of this writing, there are several tools are available for creating Diagrams as Code, each with its own features and capabilities. Here are a few popular options:

* **PlantUML**: PlantUML\[^ “Open-Source Tool That Uses Simple Textual Descriptions to Draw Beautiful UML Diagrams.”] is a tool that allows you to create UML diagrams using a simple and intuitive language. The diagrams are created as code and can be easily integrated into various documents and presentations. It supports multiple types of diagrams, including sequence, class, use case, and more. It is available online as a website under the same name, implemented in various other websites, within most of the Generative AI tools, and into the Unified Compliance Framework. PlantUML is now a part of the [CommonControlsHub.com](https://cch.commoncontrolshub.com) experience.
* **Graphviz**: Graphviz\[^ “Graphviz.”] is a tool for creating diagrams using a plain text language. It can produce various diagrams, including directed and undirected graphs, flowcharts, and more. Graphviz can also be integrated with other software tools and programming languages.
* **Mermaid**: Mermaid\[^ “Mermaid | Diagramming and Charting Tool.”] is a tool that allows you to create various types of diagrams, including flowcharts, sequence diagrams, class diagrams, and more, using simple and intuitive language. It also supports real-time collaboration and can be integrated with various software tools and platforms.
* **Draw.io**: Draw.io\[^ “Draw.Io- Diagrams.Net.”] is a web-based diagramming tool that allows you to create diagrams using a drag-and-drop interface. It supports various diagram types, including flowcharts, UML diagrams, and network diagrams. Draw.io allows real-time collaboration and integration with multiple software tools and platforms.
* **C4 Model with Structurizr**\[^ “Structurizr.”]: While not a tool in the traditional sense, the C4 Model for visualizing software architecture, combined with Structurizr, allows you to write your architecture Diagrams as Code. This could be a noteworthy addition for those looking to document software architecture comprehensively. Structurizr builds upon Diagrams as Code, allowing you to create multiple software architecture diagrams from a single model.

These tools offer a range of features and capabilities for creating Diagrams as Code, and the best option will depend on your specific needs and preferences. For our purposes here, we will focus on PlantUML.

## References

“Diagrams as Code: A Paradigm Shift for Visual Communication.” Accessed April 18, 2023. https://www.lucidchart.com/blog/diagrams-as-code.

“Draw.Io- Diagrams.Net.” Accessed April 18, 2023. https://app.diagrams.net/.

Force, Joint Task. “Security and Privacy Controls for Information Systems and Organizations.” National Institute of Standards and Technology, December 10, 2020. https://doi.org/10.6028/NIST.SP.800-53r5.

Graphviz. “Graphviz.” Accessed April 18, 2023. https://graphviz.org/.

ISO Working Group. “ISO 5807:1985.” ISO. Accessed April 18, 2023. https://www.iso.org/standard/11955.html.

“Mermaid | Diagramming and Charting Tool.” Accessed April 18, 2023. https://mermaid.js.org/.

PlantUML.com. “Open-Source Tool That Uses Simple Textual Descriptions to Draw Beautiful UML Diagrams.” Accessed April 18, 2023. https://plantuml.com/.

“Structurizr.” Accessed February 15, 2024. https://structurizr.com/.
