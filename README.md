# ghPinnedAPI

Get your pinned respositories api

## To locally execute the project

Clone this respository:

```shell
git clone https://github.com/kremilly/ghPinnedAPI
```

Install the dependencies:

```shell
pip install -r requirements.txt
```

To run the server, use:

```shell
python index.py
```

## Using the api on your project

If you want to add your pinned repositories to your portfolio or website and can't find an API that works for this, then your problems are over. I've created an API that does exactly that, and its usage is extremely easy. Simply pass your GitHub username as a query parameter.

### Example of request

```shell
https://gh-pinned-api.vercel.app/api?user=YOUR_USERNAME
```

> *Replace `YOUR_USERNAME` with your GitHub username*

### A simple example of use in JavaScript

```javascript
// Fetch is a default function of javascript for requests
// Replace kremilly for your GitHub username
fetch('https://gh-pinned-api.vercel.app/api?user=kremilly').then(
   json => json.json()
).then(callback => { 
   console.log(callback) 
})
```

> *The API will return a JSON with all your pinned repositories (if any; otherwise, it will return an empty JSON)*

#### Simple output of request:

```json
{
    "description": "Get your pinned respositories api",
    "forks": 0,
    "home": "https://gh-pinned-api.vercel.app",
    "languages": [
      "Python",
      "HTML"
    ],
    "name": "ghPinnedAPI",
    "stars": 1,
    "tags": [
      "api",
      "github",
      "python",
      "github-pinned-api"
    ],
    "url": "https://github.com/kremilly/ghPinnedAPI"
  }
```

### Queries Parameters

* `user`: Set the username

### Data returned by the API

* `name` Repository name (required)
* `description` Repository description (optional)
* `home` Repository home URL (optional)
* `url` Repository url on GitHub (generated by GitHub)
* `stars` Repository stars amount (default is `0`)
* `forks` Repository forks amount (default is `0`)
* `languages` Repository languages (generated by GitHub)
* `tags` Repository topics on GitHub (optional)

## Dependencies

* Python
* Flask
* GraphQL
* requests
* python-dotenv
