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

### Pros
- Server generated dtos are nice, especially typescript  
- Seems really quick to get a prototype up and running, reminds me of rails  
- Built in multi-tenancy is interesting
  - Is this something you use?
	- Do you have products used on a per location basis or sold externally?
- Built in messaging support - the "Reply to URL" feature sounds pretty neat  

### Questions
- Idea appears to be that instead of building a monolith you build lots of small projects in a pseudo microservices fashion?  
  - How granular does this go? Break each feature out into it's own service to be individually scaled, keep similar logic in the same project or whatever fits the job?
- A single host can contain one to many service assemblies (modularized): https://docs.servicestack.net/modularizing-services
  - Is there a gateway layer that allows for these instances to be scaled horizontally or is it expected that there's only a single instance of each service running at a time?
- Is the message bus something that is being used atm? 
  - Is there any built in support for things like sagas, distributed transactions, fault compensation etc? Kind of like mass transit.

