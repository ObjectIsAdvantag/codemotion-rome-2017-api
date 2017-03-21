# Code Motion conference, Milan 2016

**If you're attending the conference, 
check [Cisco DevNet presence](https://github.com/CiscoDevNet/codemotion-milan-2016): 
join the keynote, attend a talk, and take codelabs)**

> To give a try to the CodeMotion Milan Interactive Voice Machine
>
>    call **+39-051-042-1150**


## What's going on here ?

_Well, Cisco APIs at work: a REST API, a Tropo IVR and a [Cisco Spark Bot](https://github.com/CiscoDevNet/node-sparkbot-samples/tree/master/examples/devnet) playing all together_


This code takes a json event file and exposes it as a REST API with 3 ressources :
- [GET /](https://codemotion-api.herokuapp.com/) : returns all events, sorted by begin date
- [GET /next](https://codemotion-api.herokuapp.com/next?limit=10): shows upcoming activities
- [GET /now](https://codemotion-api.herokuapp.com/now) : returns events happening now

This API is consumed by a [Tropo Voice Machine](https://tropo.com) :
- Call +39-051-042-1150 (a Tropo self-service IVR - Interactive Voice Response, featured: a Portuguish phone number) 
- have upcoming activities spoken to you (featured: Tropo Speech To Text),
- get details for an activity (featured: Tropo DTMF - touch tone),
- select an activity and receive details by SMS (featured: Tropo Outbound SMS)

Text your email to the +1 414-999-0205 (featured: Tropo bi-directional SMS support)
- have your [Cisco Spark](https://www.ciscospark.com) account added to the DevNet Support room (featured: Tropo Outbound requests to external Web APIs)
- note that [Tropo.eu](https://blog.tropo.eu/2016/09/20/tropo-in-europe-what-it-means/) has now launched, you can pick an SMS-enabled phone number in Europe,

Launch your favorite CiscoSpark client (Web, iOS, android, windows or mac)
- you're now part of a Cisco Spark Room, (featured: Cisco Spark Memverships API) 
- get real time info what's going on (featured: Cisco Spark Bot accounts & WebHook API)
- check if the session you're attending has begun: /next, /now


## Architecture

If you want to dig into the code:
- this project is leveraging SailsJS for the REST API aspects, the [ActivityController](api/controllers/ActivityController.js) holds main logic,
- the Voice Machine script custom logic starts here for [Voice interactions](tropo-IVR.js#L354) and there for [SMS interactions](tropo-IVR.js#L318).  
app.js

This API is deployed on [Heroku](https://codemotion-api.herokuapp.com/).


## Want to learn more

Check these webinars from Cisco Live Vegas 2016:
- DEVNET2002
- DEVNET3002


## MIT License

Feel free to use, reuse, extend, and contribute