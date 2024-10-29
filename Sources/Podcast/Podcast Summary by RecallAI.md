https://app.getrecall.ai/share/4047190d-f786-518c-a51f-ad0f892385f6

## Introduction and Background

- The discussion focuses on Uber's Domain-Oriented Microservices Architecture (DOMA) and its significance in addressing complex system challenges. 00:00

- The decision to discuss this topic was influenced by a conversation with Uwe, highlighting the importance of understanding and evaluating such architectural approaches seriously. 00:22

- There is an emphasis on the need for more open discussions about what works and what doesn't in software architecture, using Uber's approach as a reference point. 01:36

- Uber's architecture is considered successful because it has resulted in functional software that addresses specific problems, despite not following certain traditional methodologies like Domain-Driven Design (DDD). 01:53

- The text briefly touches on controversies surrounding Uber, including issues related to driver exploitation, environmental impact, and past allegations of sexual harassment within the company. 02:23

- The content is based on a blog post, which aims to present a positive image by discussing problem-solving strategies, though it suggests a cautious approach to such narratives. 03:11

- The discussion focuses on understanding the challenges that Uber's Domain-Oriented Microservices Architecture(DOMA) aims to solve, emphasizing the importance of problem-solving over design methodologies like domain-driven design. 03:30

- The approach involves identifying the problems first, then outlining the measures taken to address these issues, and evaluating whether the proposed solutions are effective. 03:39

## Uber's Transition to Microservices and Initial Challenges

- The text highlights that Uber's transition to microservices was driven by issues such as system availability, where the entire system could fail, and the need for more autonomous teams. 05:55

- Uber faced challenges with their monolithic architecture, including high risk during deployments and poor modular boundaries, which led to limited team autonomy. 06:14

- To address these challenges, Uber chose to implement microservices instead of other modularization techniques, such as using packages or other mechanisms available in programming languages like Java. 06:28

- The implementation of microservices was intended to improve system resilience, allowing individual microservices to fail without affecting the entire system, thus enhancing overall availability. 06:50

- The system is designed to continue functioning even if a microservice fails, indicating a well-considered decision to address potential issues with service separation. 07:08

- There is a discussion about the difficulty of justifying the existence of a microservice, which is seen as independent of microservices and more related to general software architecture. 07:20

- Microservices are noted for having clearer boundaries and stronger separation compared to monolithic architectures, which can make restructuring easier. 07:46

- The use of architecture management tools and clear responsibilities is emphasized, suggesting that these should be present regardless of whether microservices are used. 08:26

- Independent deployment of microservices allows for autonomous teams that can deliver at their own pace, which is a classic success story of microservices. 08:51

- The transition from monolithic to microservices architecture is seen as a way to achieve greater independence and scalability in development organizations, especially as the number of engineers increases. 09:13

- There is a recognition that while microservices can support autonomy, organizational changes are also necessary to fully realize this autonomy. 09:48

- The discussion highlights the importance of organizational responsibility and suggests that technical solutions alone are insufficient for achieving full autonomy. 10:00

## DOMA: Domain-Oriented Microservices Architecture at Uber

- Uber has developed a Domain-Oriented Microservices Architecture (DOMA) to manage its complex system of microservices. 10:37

- The company operates approximately 2,200 critical microservices, which are essential for its production environment. 10:52

- There is limited information about the size of Uber's development organization, but it is estimated to involve thousands of developers. 12:21

- Uber's goal with DOMA is to reduce complexity while maintaining flexibility, particularly for large organizations and distributed systems. 12:56

- A significant challenge identified is the need to debug issues that require navigating through around 50 services and coordinating with about 12 teams, highlighting the complexity of their system. 13:50

- The discussion highlights the challenge of identifying domain-specific functionality within Uber's services, noting that many service names do not clearly indicate their business purpose, which is considered unusual. 14:31

- There is a mention of complex dependencies within the system, which are illustrated in a diagram. These dependencies make the system difficult to understand, and addressing this complexity is identified as a necessary task. 16:46

- The complexity of dependencies is compared to a common issue in microservices architecture, where intricate interconnections can complicate system management. 17:57

- It is noted that such complex dependency diagrams could also be found in monolithic systems, indicating that the issue is not exclusive to microservices. 18:18

- The complexity of the system necessitates frequent meetings and coordination among teams, and it is mentioned that there are also very complex workflows involved. 18:42

- The discussion highlights a problem where the boundaries between services in Uber's Domain-Oriented Microservices Architecture (DOMA) are becoming blurred, leading to dependencies where teams modify code, data models, and even make decisions on behalf of other teams. This situation dilutes the responsibility of a team for its microservice. 19:10

- There are different approaches to handling team responsibilities, such as allowing other teams to write code with the responsible team conducting reviews, or restricting code writing to the responsible team only. The current situation suggests that teams are performing tasks that should be under the purview of the responsible team. 20:09

- The organizational issues are evident, and there is a theoretical risk of ending up with a distributed monolith due to these blurred boundaries and dependencies. 20:50

- Understanding these dependencies is challenging, and latency spikes in one service can affect many others, leading to poor performance and limited visibility into the dependencies and problems. 21:05

- Although there is some autonomy in the system, the teams cannot develop independently to the extent needed to resolve these issues. 21:33

- Building a monolith from the existing 2,200 microservices is not considered feasible, especially with thousands of developers involved. The speaker dismisses this option as unrealistic. 21:51

- There is a problem with modularization, particularly in functional modularization, where understanding 50 services across 12 teams indicates a likely issue with the current modularization approach. 22:15

- There are issues with team responsibilities and modularization, which can be disrupted if a module's data model or code is altered without proper encapsulation, violating the principle of information hiding. 22:33

- The concept of domain-oriented microservices architecture (DOMA) is introduced as a relatively new approach, drawing on principles from domain-driven design and service-oriented architecture, aimed at large distributed systems in big organizations. 23:23

- The explanation of how these design principles are applied is not detailed, and there is no clear reference to specific concepts borrowed from clean architecture or domain-driven design. 24:00

## Domains and Layers within DOMA

- The focus is on customer satisfaction rather than strictly adhering to domain-driven design principles, and there is no strong connection to domain-driven design concepts. 24:26

- In a domain-oriented microservices architecture, domains are collections of interrelated microservices. Examples include the map search engine, ride service, and matching platform. 24:49

- Uber Maps, for instance, consists of 80 microservices across three gateways, suggesting a two-digit number of microservices within each domain. 25:32

- There is no specific statement about the organization of teams around domains, and domains are defined as a bottom-up collection of related microservices. 25:49

- The definition of a domain as a collection of related microservices is considered weak, as it lacks clear criteria for determining whether a set of microservices constitutes a domain. 26:01

- The discussion addresses the challenge of modularization in software architecture, noting that simply introducing new modules does not significantly help unless dependencies are more strictly controlled, which can lead to a cleaner architecture. 26:40

- A domain-oriented approach is discussed, where layers are introduced as collections within a domain. These layers follow a classic layered architecture where upper layers can use lower layers but not vice versa. 27:07

- Lower layers in this architecture have a broad impact radius, meaning failures in these layers can have significant consequences as they affect many microservices above them. Lower layers are more generic, while upper layers are more specific. 27:37

- The architecture uses synchronous microservices, which can lead to availability issues if a service is unavailable. The suggestion is made to consider asynchronous microservices to mitigate this problem, although it is not identified as a major issue in the current setup. 28:02

- The layers in the architecture are listed as follows: the lowest layer is the infrastructure layer, which includes functionalities that any organization can use, such as storage or network. 28:54

- Above the infrastructure layer is the business layer, which includes functionalities that the organization can use but are not specific to a particular product category or line of business. 29:11

- The top layer includes functionalities specific to a particular product category, such as rides or fraud detection, but these do not have knowledge of the mobile application that calls them. 29:34

- The architecture includes a presentation layer that offers functionality for various applications, such as mobile or web, and an edge layer that exposes these functionalities externally, potentially for mobile applications. 30:09

- The architecture aims to reduce dependencies, providing more clarity and ensuring that changes in the code by other teams are not affected. However, it is uncertain if this approach fully resolves issues related to dependencies among services and teams. 30:33

- Examples of domain services mentioned include map search service, service, and matching platform, which are part of layers 2 and 3, focusing on domain-specific functionality. 31:07

- There is a concern about how the architecture is enforced in practice, as the paper does not address this. Ensuring the architecture is maintained in reality is a challenge. 31:22

- The architecture is described as a top-level structure that should ideally be domain-focused, applicable to any company with products, not just Uber. This raises doubts about its effectiveness in solving specific problems like managing multiple services and teams. 32:03

## Gateways and Hierarchical Structuring in DOMA

- Domains are organized into countries, and gateways serve as interfaces for these domains. 32:58

- The architecture discussed involves a gateway that encapsulates services, allowing specific access methods to these services, which helps in reducing system complexity and facilitates future migrations and service discovery. 33:17

- The concept is similar to using modules with interfaces, where only the interface needs to be known, making it easier to use the module. This approach is akin to using a facade to hide complex system details. 34:22

- The architecture introduces a hierarchical structuring mechanism where microservices are grouped into domains, and domains are grouped into layers, providing a coarser granularity than microservices alone. This is analogous to classes and packages in programming. 34:50

- The structuring mechanism aims to create a clearer and more manageable system, even with a large number of microservices, by organizing them into packages with dependencies and facades, leading to a well-structured system. 35:23

## Extensions in DOMA and Their Implications

- The architecture includes domain layers and gateways as mechanisms to introduce more structure, along with extensions that allow logic extensions at the microservice level. An example given is services that determine if a driver can go online, which may involve various criteria such as ratings or permissions. 36:21

- The discussion involves the concept of extensions in Uber's Domain-Oriented Microservices Architecture (DOMA), specifically focusing on logic extensions that determine if a driver can go online. This involves multiple interfaces that need to confirm the driver's eligibility. 37:03

- There is a mention of data extensions, which allow the system to be expanded with additional data, reminiscent of discussions around Eric Evans' domain-driven design and legacy systems. This involves interpreting data within a context rather than simply passing it through. 38:22

- The approach of storing additional data in a microservice is seen as contradictory to encapsulation principles, where a module should expose functionalities but not its internal data. The data structure is made extendable, allowing one module to manage data for another, which is considered unusual. 39:20

- The concept of a core data model is introduced, which includes redundant or additional elements in the platform's data model. This is seen as conflicting with the idea that data should only make sense within specific contexts, as learned in bounded contexts. 40:11

- The discussion raises questions about the responsibilities and data management in Uber's Domain-Oriented Microservices Architecture (DOMA), suggesting that there might be a lack of clear boundaries and potential issues with data handling and logic separation. 40:48

- There is a concern that the architecture might lead to a chaotic data model and difficulties in managing responsibilities, as different entities might manage data and logic separately, leading to coordination challenges. 42:05

- The architecture's design might not satisfy aesthetic or traditional architectural principles, as its primary goal is to solve Uber's specific problems rather than adhere to conventional design standards. 41:34

- There are technical concerns about the inability to guarantee data correctness at the type system level, which could lead to potential issues in data integrity. 42:33

- The architecture includes logic extensions and data extensions, as well as custom extensions, which involve using directed acyclic graphs (DAGs) for task execution, a powerful feature that might complicate the layering and responsibility distribution. 42:44

- The use of DAG-based task execution logic in the presentation architecture raises questions about whether it should be allowed to span across layers, potentially leading to unclear responsibilities and control over presentation aspects. 43:00

- The proposed solutions and extensions in the architecture need further examination to understand how they address the identified problems and whether they effectively solve them. 43:51

## Addressing Complexity and Dependencies with Gateways

- The implementation of gateways has been used to address the complexity of understanding multiple services across different teams, although it requires understanding the functionality behind these gateways. 44:08

- Gateways help reduce dependencies by focusing on domain interfaces rather than microservices within the domain, which is seen as a good approach for modularization. 45:01

- There is a challenge when teams modify code and data models in other services, which can lead to issues if not properly managed. 45:40

- The use of data and logic extensions allows for modifications without directly altering the microservice, but this can lead to technical workarounds due to insufficient modularization and encapsulation. 46:01

- Allowing modifications through extensions might solve immediate issues but can create further complications, as understanding these extensions becomes necessary when problems arise. 46:34

- The introduction of gateways in distributed communication can increase latency, as it adds additional network layers, potentially exacerbating existing latency issues. 47:25

- It is noted that 50% of all microservices are rewritten within one and a half years, which is seen as a significant measure that can lead to clearer designs and responsible decision-making by developers. This approach is not perceived as a problem by the organization, as they argue that having a gateway allows for the replacement of implementations behind it, which is considered an advantage. 47:53

- The number of microservices, totaling 2,200, is initially perceived as high, but a hierarchical division makes it more understandable. However, the distribution across five countries is not very helpful, as it implies a large number of microservices per layer, which still seems excessive. 49:09

## Relating DOMA to Domain-Driven Design (DDD)

- There is a mention of 80 microservices within a single domain, which is seen as manageable. The system's composition and the relationship to domain-driven design (DDD) are discussed, with a reference to Eric Evans' book on DDD. However, the terms and concepts from DDD are not recognizable in the paper being discussed. 49:30

- The text highlights that the domain concepts such as generic subdomain or core domain are defined differently in the context of the discussion, focusing on business logic rather than infrastructure domains like network or storage, which are not typically divided by domain-driven design. 50:31

- It is suggested that the existing problems at the business level could be solved with domain-driven design, and the naming of services and layers is also addressed. 51:20

- The discussion highlights a lack of strong domain orientation in Uber's architecture, suggesting that the division of responsibilities within the system may need reevaluation. 51:35

- There is a critique of the approach to storing interpreted data, which is not aligned with the principles of domain-driven design. 52:07

- Entities are defined within a specific context and should not be exposed indiscriminately, which is seen as problematic and requires further investigation. 52:13

## Organizational Challenges and Scaling

- Organizational issues are identified, such as excessive coordination and scaling challenges, which have not been resolved by the current system. 52:29

- The responsibility of teams for specific components is an organizational problem that remains unsolved, even with the use of domain gateways. 52:42

- Uber has around 5,000 people in product and engineering, with plans to integrate 2,200 microservices into their structure, rewriting 50% of them within 18 months. This scenario may be suitable for their solution, but it is not common. 53:15

- The approach is deemed more applicable to large systems and less relevant for small organizations or startups. 53:55

- Uber's implementation of microservices is considered successful in achieving the desired benefits, but it may not be widely adaptable or beneficial for others. 54:13

- There is a strong technical focus in Uber's approach, with uncertainty about their focus on domain-specific aspects, partly due to limited data available. 54:49

## Concluding Remarks and Q&A

- The discussion emphasizes the importance of topics such as organizational structure and domain-oriented microservices architecture, which are considered equally important as the architecture and structuring of microservices. 55:06

- There is a mention of a lack of questions from the audience, with possible reasons being that everything is clear, no one is listening, or the audience is disengaged. 55:44

- There is a call for more reports on what has been done in architecture and what has been learned, to help the software development community progress. 56:09

- A question is raised about how extensions can be problematic and how such issues could be resolved using domain-driven design (DDD). 57:04

- The concept of logic extensions versus interfaces is discussed, with an example involving a driver wanting to go online and needing approval from various services. 57:14

- Data extensions are described as a situation where data is managed by another service without being accessed, which is seen as problematic. The proposed solution is to keep data within its domain context, where it can be interpreted and managed appropriately. 57:35

- The explanation includes an example of different domains, such as payment and driver management, each having relevant information stored within their respective bounded contexts. 58:10

- There is a discussion about the authority to store driver data and the separation of responsibilities, which seems unclear and contradictory to encapsulation and modularization principles. 59:00

- The concept of modules having interfaces is emphasized, with a concern that allowing extensions might undermine encapsulation and modularization. 01:00:01

- There is a mention of challenges in identifying domains and services within microservices architecture, with a suggestion to keep services independent. 01:00:34

- It is suggested that there might be a lack of proper encapsulation, leading to poor structural design, which is being legitimized as a workaround. 01:01:07

- A sketch by Lisa is referenced, which highlights both problems and solutions within the discussed architecture. 01:01:41

- There is a critical view of the concept of independent systems architecture, with a mention that it was intentionally excluded from a microservices book. 01:02:12

- The speaker expresses a desire to delve deeper into a topic. 01:02:34

- Gratitude is extended to the audience for attending the session, especially given the unusual timing. 01:02:41

- There is a hope expressed for a potential follow-up meeting on Friday. 01:02:49