# Create a FREE 🎉 Fake REST API with JSON Server Running On The Internet

In this article, I will show you how to create a fake REST API using JSON Server FOR FREE… 🙌

I was working on a simple CRUD application that retrieves some JSON data(using GET request) & displays in the UI. The issue is that: REST URL endpoint was not responding because the URL expired. Then I found that creating a fully-fledged REST API has lots of things involved. From registering a domain to setting up a server, connecting to a database. Creating a REST API using ExpressJS/NodeJS/DjangoREST framework takes time. 

But don't worry, we will learn how to create a fully-fledged REST API from scratch later.

For now, we just want to interact with a simple JSON data (eg: like this).

Here comes JSON Server Typicode (GitHub.com) to rescue and save our energy/time. 🕒
With just simple steps you can host an URL Endpoint for JSON data on the internet. 

You can use GET, POST, PUT, PATCH and DELETE requests.
Here is what I created: 

https://my-json-server.typicode.com/tujeff/tu-json-server

## Step 1:

Create a folder with any name you want. I named it tu-json-server. I suggest you follow along with me. Then open your favorite code editor (I use VS Code) and open the folder in Editor you just created. The folder is empty now. If you are using VS Code open terminal (View > Integrated Terminal). If you are using another code editor open Terminal/Command Prompt and cd into the folder.

Make sure that you have Node.JS installed in your machine. If it isn’t there, just download it.

## Step 2:

Write command in terminal/command prompt:

```s
npm init -y
```

## Step 3:

Now we have a package.json file inside the folder.

Time to Install the JSON server now. Write to the terminal:

```s
npm install json-server
```

It will take some time to install. Once it installed you can see some other files/code added to your folder.

## Step 4:

Create a new file & name it `db.json` (must name it db.json to make it work!)

Put the JSON data you want to retrieve in your apps. I am pasting this data in db.json

```json
{
	"users": [
		{
			"id": 1,
			"name": "Robert Schwartz",
			"email": "rob23@gmail.com"
		},
		{
			"id": 2,
			"name": "Lucy Ballmer",
			"email": "lucyb56@gmail.com"
		},
		{
			"id": 3,
			"name": "Anna Smith",
			"email": "annasmith23@gmail.com"
		},
		{
			"id": 4,
			"name": "Robert Brown",
			"email": "bobbrown432@yahoo.com"
		},
		{
			"id": 5,
			"name": "Roger Bacon",
			"email": "rogerbacon12@yahoo.com"
		},
		{
			"id": 6,
			"name": "Jeff Tu",
			"email": "jefftu@gmail.com"
		},
		{
			"id": 7,
			"name": "Sharon Tu",
			"email": "sharontu@yahoo.com"
		},
		{
			"id": 8,
			"name": "Sammy Shark",
			"email": "sammyshark@yahoo.com"
		},
		{
			"id": 9,
			"name": "Jesse Octopus",
			"email": "JesseOctopus@abc.com"
		},
		{
			"id": 10,
			"name": "DrewSquid",
			"email": "DrewSquid@abc.com"
		},
		{
			"id": 11,
			"name": "Jamie Mantis",
			"email": "JamieMantis@abc.com"
		},
		{
			"id": 12,
			"name": "Molecule Man",
			"email": "MoleculeMan@abc.com"
		},
		{
			"id": 13,
			"name": "Madame Uppercut",
			"email": "MadameUppercut@abc.com"
		},
		{
			"id": 14,
			"name": "Morty Smith",
			"email": "MortySmith@abc.com"
		},
		{
			"id": 15,
			"name": "Alexis Bull",
			"email": "AlexisBull@abc.com"
		},
		{
			"id": 16,
			"name": "Rack Jackson",
			"email": "rackjackson2@abc.com"
		},
		{
			"id": 17,
			"name": "Shyam Jaiswal",
			"email": "shyamjaiswal@gmail.com"
		},
		{
			"id": 18,
			"name": "Bidhan Chatterjee",
			"email": "bidhan@example.com"
		},
		{
			"id": 19,
			"name": "Amit Goenka",
			"email": "AmitGoenka@xyz.com"
		},
		{
			"id": 20,
			"name": "Smita Pallod",
			"email": "SmitaPallod@xyz.com"
		},
		{
			"id": 21,
			"name": "Rajeev Sen",
			"email": "RajeevSen@xyz.com"
		},
		{
			"id": 22,
			"name": "Tom Price",
			"email": "tomprice@xyz.com"
		},
		{
			"id": 23,
			"name": "Nick Thameson",
			"email": "nickThameson@xyz.com"
		},
		{
			"id": 24,
			"name": "Gonzalo Turner",
			"email": "gonzaloturner@xyz.com"
		},
		{
			"id": 25,
			"name": "Dillon Kim",
			"email": "dillonkim@example.com"
		},
		{
			"id": 26,
			"name": "Jonny Liu",
			"email": "liu999@example.com"
		},
		{
			"id": 27,
			"name": "Elliot Don",
			"email": "elliotdon@example.com"
		},
		{
			"id": 28,
			"name": "Ethan Hong",
			"email": "ethonhong@example.com"
		},
		{
			"id": 29,
			"name": "Andy Yang",
			"email": "andyyang7@example.com"
		},
		{
			"id": 30,
			"name": "Audrey Zhao",
			"email": "audrey@gmail.com"
		}
	],
	"tutorials": [
		{
			"id": 1,
			"title": "Javascript 1",
			"description": "Javascript 1 description",
			"published": 1
		},
		{
			"id": 2,
			"title": "Javascript 2",
			"description": "Javascript 2 description",
			"published": 0
		},
		{
			"id": 3,
			"title": "Python 101",
			"description": "Python 101 description",
			"published": 0
		},
		{
			"id": 4,
			"title": "Python 202",
			"description": "Python 202 description",
			"published": 1
		},
		{
			"id": 5,
			"title": "HTML one",
			"description": "HTML one description",
			"published": 1
		}
	]
}
```

## Step 5:

In package.json replace the existing value of key name: “scripts” to:

```json
...
"scripts": {
    "json:server": "json-server --watch db.json"
},
...
```

## Step 6:

Time to run the server. Write the command:

```s
npm run json:server
```

The server should start on http://localhost:3000

Quit the server with `Control+c`

Error: That port is already in use.
```s
$ fuser -k 4001/tcp
```

SO FAR SO GOOD 😇

## Step 7

Now time to host the server on the internet for FREE. For that, you need to create a new repository in GitHub named it `tu-json-server` and Pushed the local repo to remote GitHub.

NOTE: The repo `tu-json-server` MUST be in 'Public'

We already have repo `tu-json-server` in GitHub.com.

Open the URL:

https://my-json-server.typicode.com/<your-github-username>/<your-repo-name>

Our URL: https://my-json-server.typicode.com/tujeff/tu-json-server

👊 AWESOME WORK. YOU JUST CREATED A SIMPLE FAKE REST API WITH FEW STEPS. NOW USE THE ENDPOINT URL AS BACKEND TO YOUR SAMPLE APPS TO RETRIEVE THEM.