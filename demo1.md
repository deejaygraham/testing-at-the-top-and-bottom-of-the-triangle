# End to End testing a website

## Create a node project 

docs for cypress are very good. https://docs.cypress.io/guides/overview/why-cypress
md bbce2e
cd bbce2e

npm init and accept all default

Install Cypress npm install cypress (currently v12)

npx cypress open

Shows the e2e and component (used to only be e2e)
Not configured so we set that up.
Choose browser. Chrome

Can write tests here in testing window. Prefer to write tests in VS code

First we want to do some configuration. We are going to be testing the BBC website.

Add a scripts section to your package.json

"scripts": {
    "debug": "npx cypress open --e2e --browser chrome",
    "test": "npx cypress run --e2e --browser chrome"
  }
  
  e2e folder for end to end
  
  tests normally thing.test.js
  here they are thing.cy.js
  
  Open cypress.config.js and add a baseUrl: 'http://bbc.co.uk/'
  If we were testing a local deployment, we need to start that first. 
  
  Create a new file something.cy.js
  describe and it blocks
  cy. prefix for 
  
  but expect etc. work as you would expect.
  
  Let's just check that we can see a nice welcoming message.
  Welcome to the BBC
  
  We need a sign in page. Perhaps we can find that link and click it.
  
  cy.visit('/my/page/path')
  cy.get('[data-testid="selector-in-question"]')
  cy.get('[data-testid="selector-in-question"]').debug() - shown in dev tools
  
  
  Search BBC
  Type nature, hit return and scroll something into place.
  
  Generating tests.
  
  CBeebies 
  Lets find a schedule link for radio 4, click it and see where it goes
  
  Retries happening
  
  Screenshots and video
  
  Check that the link is there, check that an image is loaded.
  
  Weather map, search for Newcastle weather - a list, pick one
  newcastle upon tyne is more specific.
  Link for today
  Observations section, humidity, visibility, pressure.
  May want to look at markup here? 
  
  Recommendations for search - stolen from cypress
Don't target elements based on CSS attributes such as: id, class, tag
Don't target elements that may change their textContent
Add data-* attributes to make it easier to target elements

<button 
data-cy="submit" >
  
  cy.get('button').click()	 Never	Worst - too generic, no context.
cy.get('.btn.btn-large').click()	 Never	Bad. Coupled to styling. Highly subject to change.
cy.get('#main').click()	 Sparingly	Better. But still coupled to styling or JS event listeners.
cy.get('[name="submission"]').click()	 Sparingly	Coupled to the name attribute which has HTML semantics.
cy.contains('Submit').click()	 Depends	Much better. But still coupled to text content that may change.
cy.get('[data-cy="submit"]').click()	 Always	Best. Isolated from all changes.
  
  Check title, 
  Look for text, 
  Links to iPlayer, Sounds, News, Sport, CBBC, Bitesize
  
