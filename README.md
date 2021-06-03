# ServiceStack Intro
https://docs.servicestack.net/create-your-first-webservice#watched-builds

## Setup
- Install the x dotnet tool: `dotnet tool install --global x`  
- Create a web app project template: `x new web WebApp`  
- Run the created app: `dotnet watch run --project WebApp`
  - Need to be running visual studio as administrator
  - If a previous run has been closed you may need to kill the process (search for name of project)

## Project structure
AppProject: Handles startup, web assets. Considered the "orchestrator", references all other (non-test) project but should be free of any business logic.  
ServiceInterface: This is where the business logic should sit. Convention is that logic is grouped under feature folders. Project can be split into multiple if desired.  
ServiceModel: Contains all of the DTOs and the service contracts. 

### Questions
- Is the idea to build a monolith or do you build lots of small projects in a pseudo microservices fashion?  
- Is it possible to scale the project layers independently?  

### Pros
- Server generated dtos are nice, especially typescript  
- Seems really quick to get a prototype up and running, reminds me of rails  

