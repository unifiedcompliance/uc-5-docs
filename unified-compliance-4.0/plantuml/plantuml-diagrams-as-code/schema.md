# Schema



The schema for PlantUML diagrams is very simple. In essence, outside of the _core_ schema elements diagramming as code has these _specific_ elements”

* **name** the name of the file in question.
* **diagram** the textual content of the diagram.
* **description** the textual content of the diagram.
* **diagram\_type** the type of the diagram, such as _Deployment, Class, Activity_, etc.

The whole schema is below (not much to it). We’ve explained the main parts above, the rest can be found at [GRCSchema.org/PlantUML](https://grcschema.org/PlantUML)

## The content and the license

As you can see in the diagram below, the structure for the content is very simple. In addition to the fields defined above, the **CoreMetaData** allows tracking for updates to the diagrams, while the **license** fields provide the necessary content for the share-alike licenses that the diagrams will be assigned (meaning you’ll be able to use them as you see fit).

![PlantUML Content](https://www.complianceascode.net/wp-content/uploads/2021/12/PlantUMLJSONpt1.png)

**Diagram Type** is drawn from a list of the available diagram types supported by PlantUML. The list, as of this publishing, is

* Activity
* Archimate
* AsciiMath
* Class
* Component
* Deployment
* Gantt
* JSON
* MindMap
* Object
* Use Case
* State
* Timing
* YAML
* WBS
* ERD

![Contributors](https://www.complianceascode.net/wp-content/uploads/2021/12/PlantUMLJSONpt2.png)

Beyond that, the **Contributors** portion of the schema tracks _who_ created and updated each of the diagrams.

When sharing these documents within a federated system, the schemas for an _Account1, Organization2,_ and _Person3_ must also be taken into consideration.

#### ERD

The ERD for connecting the PlantUML table to the various account tables is shown below4.

![PlantUML ERD](https://www.complianceascode.net/wp-content/uploads/2021/10/PlantUML-ERD.png)

### Footnotes

1. [https://grcschema.org/account](https://grcschema.org/account) ↩︎
2. [https://grcschema.org/organization](https://grcschema.org/organization) ↩︎
3. [https://grcschema.org/person](https://grcschema.org/person) ↩︎
4. In the ERD Users and Persons are one in the same as a Person is a published User. ↩︎
