- title : Faster APIs with Suave
- description : Introduction to Suave
- author : Shane Charles
- theme : night
- transition : default

***

### Faster APIs with

![Suave](images/suave1.png)

*** 

### Who am I?

- Shane Charles
- Co-owner of Burning Ice Solutions Inc.
- Developer since 2004
- Bachelor of Computer Science from U of M
- Diggin' [F#](http://fsharp.org) and [Erlang](https://erlang.org)


    type ContactType = | Email | Twitter | Blog | GitHub

    let getContactInfo = function
	    | Twitter -> "@dead_stroke"
	    | Blog    -> "http://geekeh.com"
        | GitHub  -> "shanecharles"
	    | Email   -> "shanecharles@burningicesolutions.com"

***

### Our Path

- What is Suave
- How to get Suave
- Routing
- Build an API
- Deploy to Azure?
- Summary
- Questions

***

### Suave

- Lightweight, non-blocking, RESTful web server for .net
- Written in [F#](http://fsharp.org/)
- Self hosted, Azure, Heroku
- But why?
 - Asp.net WebApi
 - Asp.net Core 1.0
 - NancyFx

***

### Becoming Suave

- Get Suave via Nuget or Paket
- Reference library from project/script
- Create a route and start server


    open Suave
    startWebServer defaultConfig (Successful.OK "Hello Suave")

*** 
### Routing in Suave

![Composability](images/composability.gif)

***

### Let's make an API for tracking bugs

What routes do we need?

***

### Get all the bugs

    api/bugs -> 
      get all the bugs from database
      serialize to json
      return json


***

### Get a single bug

    api/bugs/{id} ->
      get bug from database
      if bug exists
        serialze to json
        return json
      else
        return error not found

***

### Create a new bug

    api/bugs/create ->
      if request has valid data
        add bug to database
        serialize to json
        return json
      else
        return error bad request

***

### Rest of API

    api/bugs/{id}/close
    api/bugs/{id}/update
    api/bugs?filter={status}

***

### Deploy to Azure

- .deployment
- web.config
 - app.azure.fsx

---

### It wasn't me

- Scott Hanselman blogged
 - [Suave on Azure with FAKE](http://www.hanselman.com/blog/RunningSuaveioAndFWithFAKEInAzureWebAppsWithGitAndTheDeployButton.aspx)
- Tomas Petricek refined the deployment process
 - [Suave-FsHome on GitHub](https://github.com/tpetricek/suave-fshome)

***

### Summary

- Suave can start from executable or a script
- Routing is functions composed by `>=>`
- `warbler ()` for dynamic content
- Gain access to Agents, Type Providers, and other F# features
- Built a functioning API in around 50 lines of readable code

***

### Upcoming fun

- [fsharpConf - fsharpconf.com](http://fsharpconf.com/)
 - March 4, 2016
 - Free virtual conference!

- [Prairie Dev Con Wpg - prairiedevcon.com](http://prairiedevcon.com/)
 - April 11 - 12, 2016
 - 3 F# talks (Rachel Reese and Adam Krieger)

- [Winnipeg Coffee and Code - www.meetup.com/wpgcoffeecode](http://www.meetup.com/wpgcoffeecode/)
 - March 3, 2016

***

### Questions

- Shane Charles
- Twitter: [@dead_stroke](https://twitter.com/dead_stroke)
- Blog: [http://geekeh.com](http://geekeh.com)
- GitHub: [shanecharles](https://github.com/shanecharles)
 - Code: [faster-apis-suave](https://github.com/shanecharles/faster-apis-suave)
 - Slides: [faster-apis-suave-slides](https://github.com/shanecharles/faster-apis-suave-slides)
- Email: shanecharles@burningicesolutions.com

***
