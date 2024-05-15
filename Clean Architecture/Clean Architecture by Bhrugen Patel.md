- Most user Architecture Pattern
- Separation of Concern, with circular layering
- Inward Dependency
## DOMAIN

- Inner most layer
- Contains
	- Core entities & their specifications
	- Models, Database Tables
	- Also known as Domain Entities
	- So our database entities or models will reside in the domain layer.


## APPLICATION

- Place to host all of your business logic
- Contains
	- All the interfaces separate from implementation to support separation of concern. 
		- Interfaces means - not always the interface


## INFRASTRUCTURE

- Handles external concerns like database.
- If you have email service and other services that we use in the application.
- We keeps our database migrations and dbcontext in this layer along with repositories.


## PRESENTATION

- Outer most layer
- Responsible for handling user interaction and user input.
- This layer must be designed in a way that it is easily replaceable.




---
####                                                           ALWAYS BE AN INWARD DEPENDENCY
---


## Dependency flow between all the layers

- Presentation layer and infrastructure layer will have a dependency.
- Presentation & Infrastructure layer will include Application layer, because that is the business logic and application layer will include domain layer.

#### You may wonder why the Presentation layer references the Infrastructure layer. Let's clarify with an example.

Consider this scenario: Your application interfaces with a Payment Gateway or a third-party service (such as Azure or AWS). Database entries are created only upon receiving a webhook callback from services like Stripe. To ensure service replaceability, these services must implement an interface within the application layer. However, the frontend is responsible for initiating interactions with the payment gateway. Therefore, the Presentation layer must establish a dependency (project reference) to the Infrastructure layer.

However, the specific implementation details may vary depending on the architecture and design choices of the application.


