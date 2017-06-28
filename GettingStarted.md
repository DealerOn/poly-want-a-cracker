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





