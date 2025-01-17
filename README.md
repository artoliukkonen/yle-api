# yle-api

Client for YLE API (<http://developer.yle.fi/>).

**Work in progress. All contributions (pull requests, issues, comments) welcome!**

## Installing

You need NodeJS 0.12 or newer to use this library.

Install the library with:

	npm install yle-api

In order to use YLE API, you must provide it with your developer API keys. Follow the developer site instructions. Note that terms of service apply to any usage of the API, including this client.

## Using as a command-line tool

Authorize the command-line tools with your API keys as follows:

- Copy `.yleapi-EXAMPLE` into your home folder and rename it to `.yleapi`
- Edit the file to add your own API keys

You can now run command-line tools as follows:

	yle-api get-programs
	yle-api get-program 1-820561
	yle-api get-program-stream 1-820561

## Using as a node library

Add yle-api into your package.json:

	npm install --save yle-api

Require the library with your API keys as follows:

	var yleApi = require('yle-api')({appId: '', appKey: '', decryptKey: ''});

Fetch some programs
	yleApi.getPrograms({q: 'Uutiset'}, function(error, response) {
		// Response contains array of programs matching search term "Uutiset"
	});
