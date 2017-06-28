# poly-want-a-cracker
A chat application tutorial utilizing Polymer, socket.io, and you.

If you would like to code along, it'd be best to: 
  * Install Node https://nodejs.org/en/download/
  * Install the Polymer cli: `npm install -g polymer-cli`
  * Scaffold out the boiler plate: `polymer init polymer-2-starter-kit`
  * Start the web server with `polymer serve`

To run the server:
* open a console in the server directory
* `npm install`
* `npm start`


Step 1: 
* (Optional) Update "My-App" to something better
  * Update App details in the manifest.json
    * Set the name and short name to better values.
  * Update app name and titles in index.html. 
* Create a new HTML file to hold out chat log element and name it poly-chatlog.html
  * If you're using the Polymer 2 Snippets, create a new p-webcomponent in the poly-chatlog.html file and provide the element name 'PolyChatLog'
  * If you're not using the snippets, follow the polymer guide for structuring out a new component, or grab the basic file from the Step 1 commit.
* Register the new element in the polymer.json file 
* Install the Socket IO client (we'll upgrade to using a component later)
  * npm install --save socket.io-client
* Install Fetch library (we'll upgrade to using a component later)
  * npm install --save fetch

Step 2:
* Update poly-chatlog dom module ID
* Add poly-chatlog page to the main application (my-app.html) element imports
* Add poly-chatlog page to the my-app.html iron-selector for the page list
* (Optional) Update My App names/titles to something better
* Update iron selector names and iron page names to reflect full element names
  * We need to update this so the changes we make to the page selector logic will continue to work. 
* Modify the '_pageChanged' method to remove the 'my-' portion of the URL concatenation, since we added it directly to the page names a moment ago.
  * 'poly-chatlog' does not follow the 'my-*' format, so we need to be able to account for that too. 
* Update existing areas to add the 'my-' so they continue to work. 
  * Update the default page to include the 'my-' so the default page continues to work.
  * Update the '_showPage404' logic to include the 'my-' so the 404 page continues to work. 
  * Update the fallback-selection of the iron-pages element to include the 'my-' so the 404 fallback continues to work. 
  * Update the iron-selector href values to include the 'my-' so they continue to work. 

Step 3:
* Import paper-input
  * bower install --save paper-input
  * Select the 2.0 preview versions of the dependencies if prompted. 
* Import paper-button
  * bower install --save paper-button
  * Select the 2.0 preview versions of the dependencies if prompted. 
* Add import reference to paper-input and paper-button. 
* Add script reference to socket.io client
* Update Template to include a dom-repeat for the messages property (we'll add that in a moment.)
* Add a paper-input element to accept the text we'll be typing in. 
* Add a paper-button to the input in the suffix slot to allow submitting the content. 
* Add a Messages property of type Array, a currentMessage property of type String, and a socket property of type Object to the poly-chatlog element. 
* Add the logic to the ready() method to connect to the chat server and push the messages to the room. 
* create an addMessage(message) function and a sendMessage function for pushing messages onto the message property and emitting messages to the socket.io server respectively. 

Step 4:
* Create a new component and name it PolyChatBubble and set the dom module id to poly-chatbubble. 
* Add a userId property of type String and create a div in the template with ID set to the userId property and class of message-bubble. 
* Create a few slots in the poly-chatbubble for a prefix, suffix, and the catch-all slot. 
* Update the poly-chatlog template to replace the contents of the list item with a poly-chatbubble, setting the user-id (because camel cased property names become hyphenated externally) property of the bubble to the item.from property of the repeated item.
* Set the contents of the poly-chatbubble to be the item.message property. 
* Import paper-item
  * bower install --save paper-item
  * Select the 2.0 preview versions of the dependencies if prompted. 
* Import paper-listbox
  * bower install --save paper-listbox
  * Select the 2.0 preview versions of the dependencies if prompted. 
* Update the poly-chatlog to utilize the paper-listbox and paper-item for the messages. 

