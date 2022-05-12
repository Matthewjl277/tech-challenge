# Seedata.io Tech Challenge

## Introduction
We appreciate no-one likes doing technical challenges so we've tried to make this as simple as possible, we're only expecting you to take an hour out of your time to complete as much as you can, with the mantra quality over quantity in mind!

### **Challenge options/effort**
You have the following options for completing the challenge:
1. Pair programming session (1hr 15min session): You complete the challenge as a pair programming exercise and we discuss your choices and code as you complete the tasks
2. Individual programming session (1hr 45min session): We start an interview session togerher, I will then leave you to complete the challenge on your own for the first hour of the interview and we then reconvene for the final 45 minutes to discuss your solution 
2. In advance (45 minute session): You to complete the challenge in your own time, submit your work as a pull request and then we arrange for a 45 minutes interview to discuss your solution

### **Challenge purpose:**
The challenge is designed to give us an idea of how you approach problems and requirements and the solutions you put in place to fulfil/solve them. IT focusses on the following areas:
* **React - component composition, state and styling**
* **Node - bug fixing, javascript coding and testsing**

We are not looking for polished results but we would like you to be able to talk us through your decisions aroudn code, structure and any tools you've used.

We'd also love to hear how you think any of the code could be improved or the additional steps you might have taken given more time.

## The Challenge

The challenge centers around our code base which deals with events. Events are raised and relate back to a seed that we planted. See the ERD below:


[![](https://mermaid.ink/img/pako:eNp1UMsKg0AM_JUl1-oPSG-th0JvXr0EN9Wluiu7URDx35v6KLXSnDLDMDPJCIXTBAkUNYZwNVh6bHKrZNKeLKtzHKuMSC_crJrxuBBKnYyojP7AjL2xpbLY0C-nXYPGLuz0bThH_XV8wyCRt0MID-0xhELhTcvG2Z0DV56Q79RTfZGTdy22gQga8lJSy0fmPjlwRXIJJLJq9M8ccjuJrms1MqXasPOQPLAOFAF27LLBFpCw72gTrV9dVdMLs25zEw)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNp1UMsKg0AM_JUl1-oPSG-th0JvXr0EN9Wluiu7URDx35v6KLXSnDLDMDPJCIXTBAkUNYZwNVh6bHKrZNKeLKtzHKuMSC_crJrxuBBKnYyojP7AjL2xpbLY0C-nXYPGLuz0bThH_XV8wyCRt0MID-0xhELhTcvG2Z0DV56Q79RTfZGTdy22gQga8lJSy0fmPjlwRXIJJLJq9M8ccjuJrms1MqXasPOQPLAOFAF27LLBFpCw72gTrV9dVdMLs25zEw)


Our application consists of a simple React (create-react-app) front end and an express node.js back end.

The purpose of tis application is to list all the events on the front end app.


### Backend Challenge
The back end consists of an express api, each route communicates with a service, which in turns calls a repository that will return the data required by the service.
We would like you to:
* Fix the current failing tests in the following stages:
  1. An event returned from the repo has a property of threatLevelCode. There is a constant object that holds descriptions for each code in ```~/server/constants/ThreatLevels```, use this file to add an additional property to the event named ```threatLevel``` with the description matching the events threatLevelCode. i.e. event 1 had threatLevelCode 1, the returned event from the EventService should have a property of ```threatLevel``` with a value of 'TPL:Green'
  1. The EventService needs to return an Event object with a ```seed``` property that contains the seed record related to the event.
  3. Implement the sortField functionality. A sortField url parameter is passed to the API, implement the code that will use this value to sort the results returned


### Frontend Challenge
The front end recieves a list of events from the back end via an api call. We would like you to:

#### Basic challenge
* Display these results in a table
* Each row should display:
  * Event type
  * Event description
  * Seed name
  * Seed domain
  * Add an indicator to each row that reflects the events threat level code (0: white, 1: green, 2: amber, 3:red)
  * Make it pretty!

#### Additional tasks (if you want to do more)
* Make Sort By field work correctly and call the back-end passing the value of the sort field selected


## Working on the code
1. Fork this repository
1. Clone your repository
1. Run ```yarn``` to install dependencies

### Working in advance
If you chose to complete the work in your own time, please submit your work as a pull request on this repository along with any comments you feel are relevant.

## Additional Info
* You can use any additional packages you see fit to enhance the output or make the tasks easier, just be ready to explain your choices behind your selections!
* This is a real world task, if you need to google then google - we all do it!!

## Scripts
The following scripts are available to you:

|script|description|
|------|-----------|
|```start```| Starts both front and back end concurrently - FE runs on ```http://localhost:3000```, BE runs on ```http://localhost:3001```|
|```start:client```| Starts the front end only |
|```start:server```| Starts both back end only |
|```test```| Runs all tests for front end and then all tests for back end |
|```test:server```| Runs back end tests only |
