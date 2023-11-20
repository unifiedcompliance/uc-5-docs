# PlantUML Diagrams as Code



Unified Modeling Language (UML) is a standard notation for the modeling of objects as a first step in developing an object-oriented design methodology. UML is an accepted standard of the Object Management Group (OMG), which is also sponsoring CORBA as the industry standard for distributed object programming.

Diagrams can be as simple as the short sequence diagram below left, or the very involved one below right.

| Simple                                                                                  | Complex                                                                           |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| ![](https://www.complianceascode.net/wp-content/uploads/2021/10/this-that-sequence.png) | ![](https://www.complianceascode.net/wp-content/uploads/2021/12/longsequence.png) |

What gives UML its strength is that it can be used for modeling a system _independent_ of any platform or language. UML diagrams are so standardized that modeling them using plain language - _textual modeling tools_ - evolved shortly after UML became a standard. So much so that UML has become a staple in the compliance as code world, specifically **diagramming as code**. Diagramming as code tools support the use of textual notations and languages to describe software models and automatically render the corresponding graphical diagram from that textual description1.

## PlantUML is a _textual model_ of UML

While UML has been applied to various activities since the second half of the 1990s and has been used with object-oriented development methods since that time2, sites that have converted plain text English into UML diagrams, such as Plantuml.com, yuml.com, and code2flow.com didn’t even _come into existence_ until 2015, and didn’t start becoming popular until 2018. The list of tools that are currently available is here:

| Site                             | Free?        | Interchangeable |
| -------------------------------- | ------------ | --------------- |
| plantuml.com                     | Donation     | Yes             |
| code2flow.com                    | Subscription | No              |
| yuml.me                          | Subscription | No              |
| nomnoml.com                      | Free         | No              |
| www.spinellis.gr/umlgraph/       | Free         | Yes             |
| cruise.umple.org/umpleonline/    | Free         | No              |
| zenuml.com                       | Freemium     | Yes             |
| chartmage.com                    | Free         | No              |
| sourceforge.net/projects/useocl/ | Freemium     | Yes             |
| dotuml.com                       | Freemium     | No              |
| websequencediagrams.com          | Freemium     | Yes             |
| sequencediagram.org              | Donation     | Yes             |
| blockdiag.com                    | Free         | No              |
| swimlanes.io                     | Free         | Yes             |
| umlet.com                        | Freemium     | No              |

We are adding to this list with our latest no-code bubble.io release, the first to allow federated sharing with attribution to the contributors of the diagrams.

## References

1. “Text to UML and Other ‘Diagrams as Code’ Tools - Fastest Way to Create Your Models.” n.d. Accessed December 13, 2021. [https://modeling-languages.com/text-uml-tools-complete-list/](https://modeling-languages.com/text-uml-tools-complete-list/). ↩︎
2. Whitepapers and scholarly articles started appearing around 2010 describing how to construct text-based UML diagrams. This is one of the better articles: Washizaki, Hironori, Masayoshi Akimoto, Atsushi Hasebe, Atsuto Kubo, and Yoshiaki Fukazawa. 2010. “TCD: A Text-Based UML Class Diagram Notation and Its Model Converters.” In Advances in Software Engineering, edited by Tai-hoon Kim, Haeng-Kon Kim, Muhammad Khurram Khan, Akingbehin Kiumi, Wai-chi Fang, and Dominik Ślęzak, 296–302. Communications in Computer and Information Science. Berlin, Heidelberg: Springer. [https://doi.org/10.1007/978-3-642-17578-7\_29](https://doi.org/10.1007/978-3-642-17578-7\_29). ↩︎
