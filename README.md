# Hackernews Web Scrapper

This application scrape the website Hacker News, display and summarize the top posts in the terminal, 
based on the user request (up to 100 posts). The command line application outputs the data in JSON format. 

The application is executed with the command:

> hackernews N [num of posts]

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for testing purposes. 

### Prerequisites

First, let’s make sure you have the tools required. To install the application, you will need the following:
- A recent version of Node.js downloaded and installed;
- A good text editor, such as Visual Studio Code;

### Installing

Open your computer’s command prompt (Windows) or terminal (macOS/Linux). Change the current directory 
to the folder where you save your documents or projects. Enter the following commands to create a new project 
folder and initialize the project:

>mkdir hackernews-cli<br/>
>cd hackernews-cli<br/>
>npm init

Next, open the hackernews-cli folder in your favorite text editor. Create a folder named bin, extract the file
hackernews-cli.zip and add the file index.js.

The first line that begins with #! is usually called a “shebang.” This is normally only used on Linux or UNIX 
operating systems to inform the system what type of script is included in the rest of the text file. However, 
this first line is also required for Node.js scripts to be installed and run properly on macOS and Windows.

Next, replace the file package.json by the one available in hackernews-cli.zip.

Now, let's install this script “globally”. You can do that with the npm install command. Any commands listed 
in the bin section of the package.json file will be made available as command line applications.

> npm install -g .

Now we'll install the HackerNews-API, a Node.js wrapper for accessing v0 of the official Hacker News API. The 
current production release of HackerNews-API is available through npm below. Go to the hackernews-cli folder
and execute:

> npm install hackernews-api

And last, but not least, install JSON by entering the following command:

> npm install -g json

## Running the tests

The application scrape the website Hacker News and output selected number of top posts in the console. The application
can be executed globally, which means it should run as a command anywhere in the terminal.

The application takes this argument:

> hackernews N
> N = How many posts to print, that must be a positive integer & <= 100.

For example, the application is executed with parameter N = 2:

> hackernews 2

This will be the STDOUT:

```
Hackernews is running!
{
	"title": "Learning Haskell is no harder than learning any other programming language",
	"uri": "https://williamyaoh.com/posts/2019-10-05-you-are-already-smart-enough.html",
	"author": "nuriaion",
	"points": 96,
	"comments": 125,
	"rank": 1
}
{
	"title": "VPN⁰: A Privacy-Preserving Distributed VPN",
	"uri": "https://brave.com/vpn0-a-privacy-preserving-distributed-virtual-private-network/",
	"author": "jlborxes",
	"points": 143,
	"comments": 43,
	"rank": 2
}
```

Some input/output validations you will find in this application:
1. The title and the author are non empty strings not longer than 256 characters;
2. The uri must be a valid URI;
3. The points, comments and ranks are integers >= 0;
4. Valid argument N will be accepted as: 0 =< N <= 100. Hence, results will be capped up to 100, 
non-numeric and sub-zero values won't be returning any results;

## Built With

* [Node.JS](https://nodejs.org) - JavaScript run-time environment.
* [HackerNews-API](https://github.com/HackerNews/API) - Public Hacker News data in near real time, in partnership with Firebase.
* [Visual Studio Code](https://code.visualstudio.com) - Used to implement the source code.

## Author

* **Mateus Silva** - [mateuscience](https://github.com/mateuscience)
