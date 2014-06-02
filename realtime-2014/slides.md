# Realtime Web Apps
## In 2014 & Beyond

#### Phil [@leggetter](http://www.leggetter.co.uk)
#### &nbsp;
#### [BladeRunnerJS](http://bladerunnerjs.org)

--

## Realtime Web Apps
## &#8595;
## **s/Web/Internet**
## &#8595;
## Realtime Internet Apps

--

## Internet Usage (per day)

* [200 billion emails][email-stat]
* [7 million blog posts written][wordpress-stat]<sup>†</sup>
* [500 million tweets][twitter-stat]
* [55 million Facebook status updates][facebook-stat]
* [5 billion Google+ +1's][googleplus-stat]
* [60 million Instagram photos posted][instagram-stat]
* [33 million hours of Netflix watched][netflix-stat]
* [200 million hours of YouTube watched](youtube-stat)
* [2 billion minutes spent on Skype][skype-stat]

[email-stat]:http://www.radicati.com/wp/wp-content/uploads/2013/04/Email-Statistics-Report-2013-2017-Executive-Summary.pdf
[twitter-stat]:http://abcnews.go.com/Business/twitter-ipo-filing-reveals-500-million-tweets-day/story?id=20460493
[facebook-stat]:http://blog.kissmetrics.com/facebook-statistics/
[googleplus-stat]:http://www.mediabistro.com/alltwitter/social-media-stats-2012_b30651
[wordpress-stat]:http://wordpress.com/stats/posting/
[instagram-stat]:http://instagram.com/press/
[youtube-stat]:http://www.youtube.com/yt/press/statistics.html
[netflix-stat]:http://blog.netflix.com/2014/01/new-isp-performance-data-for-december.html
[skype-stat]:http://blogs.skype.com/2013/04/03/thanks-for-making-skype-a-part-of-your-daily-lives-2-billion-minutes-a-day/

Note:

What are the main (work safe) uses for the Internet each day?

<small>† 41.5 million posts in April = 1.38 million per day. Assuming WordPress.com have 20% of the market; 1.38 * 5 = 6.9 million posts on all blogging platforms.</small>

--

## The Internet...

1. **is *the* communications platform**
2. **is becoming *the* entertainment platform**

--

![](img/internet.png)

Note:

The following images provides the most basic overview of what we have to work with; the Internet with a foundation of TCP/UDP.

As we progress we'll update the diagram with the building block we now have to work with in order for us to try to innovate and build amazing Internet apps.

--

# When do we need Realtime?

Note:
- We're here to talk about realtime. Where does it fit in?
- Realtime plays a part in all of the previous examples. But where depends on...

--

## Data

Is there a timely nature to the data?

Note:
- Is there value in getting that data quickly?
- Does it need to maintain in-context?
- Hashtags can indicate context after the event.

--

## User Experience

Is there a timely nature to the experience?

Note:
- Anything with human-to-human interaction
- Some interactions with systems

--

## Realtime is required when there's a *Need* or *Demand* for:

* Up to date information
* Interaction to maintain engagement

--

# These aren't new *Needs* or *Demands*

--

# HTTP, Browsers & Servers made it Difficult

--

## What made it difficult?

* HTTP - request/response paradigm
* Keeping persistent HTTP connections alive
* No cross-browser `XMLHttpRequest`
* 2 connection limit
* No browser cross origin support
* General cross browser incompatibilities

--

![](img/internet-http.png)

--

## Hacks & Tricks

* Java Applets
* Flash
* HTTP Hacks

--

# Driving Forces behind the Hacks?

--

<!-- .slide: data-background="img/plato-talkomatic.png" data-background-size="60%" -->

Note:

Talkomatic realtime Chat - created back in 1973

--

<!-- .slide: data-background="img/yahoo-chat.png" data-background-size="50%" -->

Note:

Web Chat

--

<!-- .slide: data-background="img/reuters-kobra.png" data-background-size="90%" -->

Note:

Financial Data

--

<!-- .slide: data-background="img/legacy-finance-web.gif" data-background-size="90%" -->

--

# Realtime Going Mainstream

Note:

So how has "the Realtime Web" and realtime web technology all of a sudden gone mainstream?

--

<!-- .slide: data-background="img/follow-magnified.png" data-background-size="100%" class="dark" -->

# A Realisation & Demonstration of Value

Note:
- outside of finance and chat - okay, still plenty of chat

- Twitter
- Facebook
- Skype
- Other chat solutions

- Demand and Need for update to date info
- Demand and Need for interaction

- The FOLLOW & FRIEND buttons - we know who's interested.

--

# Accessible Realtime Technology

--

## Improved Server Power

* Processors and Memory are cheaper & faster
* More data can be processes
* Connections can be dealt with
* Scaling is easier

--

## Web Browser Capabilities and Consistency

* Cross browser `XMLHTTPRequest` support
* CORS
* Server Sent Events / EventSource
* WebSocket
* WebRTC

Note:
Cross browser "Hacks"

--

## Software Choice

* Lots of language & runtime options
* More open source solutions
* Hosted services

--

## A Note on Connectivity

* Fallbacks
* Upgrades

Note:

Two diagrams would be nice here

--

# Any Client Technology

--

![](img/internet-http-es-ws.png)

--

# Realtime Apps in 2014

Note:
In a great place to be able to innovate.
So what's being built and with what?
This is software - these are my opinions. You can achieve similar things in different ways.

--

# Notifications & Signalling

--

<!-- .slide: data-background="img/itv-news-may-2014.png" data-background-size="75%" -->

--

<!-- .slide: data-background="img/internet-high-5.png" class="dark" -->

## Internet ^5 Machine
<!-- .element: class="fragment fade-out" data-fragment-index="1" -->

<video class="stretch" poster="video/internet-high-5-machine.webmhd.png" width="100%" preload="auto" controls>
  <!-- .element: class="fragment fade-in" data-fragment-index="1" -->
  <source src="video/internet-high-5-machine.mp4" type="video/mp4">
  <source src="video/internet-high-5-machine.webmhd.webm" type="video/webm">
  <p>Please download and watch our <a href="video/internet-high-5-machine.mp4">promotional video clip</a></p>
</video>

--

<!-- .slide: data-background="img/talkyio-laptop.png" data-background-size="100%" class="dark" -->

## talky.io

--

**Receive message**

```js
var sock = new SockJS( 'http://localhost:9999/sockjs' );

sock.onmessage = function( e ) {
  console.log( 'message', e.data );
};
```
<!-- .element: class="hljs javascript" -->

**Send Message**

```js
var http = require('http');
    sockjs = require('sockjs');

var hello = sockjs.createServer();
hello.on( 'connection' , function( conn ) {
  conn.write( 'hello SockJS' );
} );

var server = http.createServer();
hello.installHandlers( server, { prefix:'/sockjs' } );
server.listen( 9999, '0.0.0.0' );
```

--

![](img/internet-http-es-ws-msg.png)

--

## Notifications & Signalling Solutions

* Client/Server
  * WebSocket-only or HTTP-only solutions
  * [SockJS](https://github.com/sockjs)
  * [Engine.IO](https://github.com/automattic/engine.io)
  * [Primus](https://github.com/primus/primus)
  * You generally need an abstraction.
* Peer-to-Peer
  * [simpleWebRTC](http://simplewebrtc.com/)
  * [PeerJS](http://peerjs.com/)

--

# Lots of Data

--

<!-- .slide: data-background="img/mancity-match-day-centre.png" data-background-size="100%" -->

Note:

- Manchester City Match Day Centre
- Identify and get the specific pieces of information that it needs

--

<!-- .slide: data-background="img/mancity-match-day-centre-pubsub.png" data-background-size="100%" -->

Note:

- Overview data about the score, scorers, location and time played
- Timeline information about key events
- Activity Stream: commentary
- Textual key moments
- A social stream
- Photos
- An overview of the status of the starting 11 players

--

<video class="stretch" poster="video/trader2.png" width="100%" preload="auto" controls>
  <source src="video/trader2.mp4" type="video/mp4">
  <source src="video/trader2.webm" type="video/webm">
  <p>Please download and watch our <a href="video/internet-high-5-machine.mp4">promotional video clip</a></p>
</video>

--

**Subscribe**

```js
var pusher = new Pusher( APP_KEY );
var channel = pusher.subscribe( 'game-overview' );

channel.bind( 'goal_scored', function( data ) {
  // Handle Update
} );

channel.bind( 'time_updated', function( data ) {
} );
```

**Publish**

```js
var pusher = new Pusher( APP_KEY );
var channel = pusher.subscribe( 'game-overview' );

var data = { team_id = 'manchester_city',
             goals_scored: 2,
             goal_scorer: 'Sergio Agüero'
           };
channel.trigger( 'goal_scored', data );
```

--

![](img/internet-http-es-ws-msg-pubsub.png)

--

## PubSub Solutions

* Self Hosted
  * [Socket.IO](http://socket.io)
  * [Faye](http://faye.jcoglan.com)
  * [XSockets](http://xsockets.net)

* Hosted
  * [GoInstant](http://goinstant.com)
  * [Hydna](http://hydna.com)
  * [PubNub](http://pubnub.com)
  * [Pusher](http://pusher.com)
  * [Realtime.co](http://realtime.co)

--

# Complex Client/Server Interactions

Note:

- You can use PubSub for this
- CT - initially just displaying data - now interactive.

--

<!-- .slide: data-background="img/fx-motif.png" data-background-size="100%" -->

Note:
Why does RMI suit this?

--

<!-- .slide: data-background="img/shooter.png" data-background-size="100%" -->

--

**Server**

```js
public class GameHub : Hub {
    public void Move(Player p, int x, int y) {
      // Check if move is allowed
      // Call the broadcastMessage method to update clients.
      Clients.All.playerMoved(p, x, y);
    }
}
```
<!-- .element: class="hljs javascript" -->

**Client**

```
$.connection.hub.start(); // async

var game = $.connection.gameHub;

game.client.playerMoved = function (player, x, y) {
  // update game
};

chat.server.move( me, x, y );
```
<!-- .element: class="hljs javascript" -->

--

![](img/internet-http-es-ws-msg-pubsub-rmi.png)

--

## RMI Solutions

* [dNode](https://github.com/substack/dnode)
* [SignalR](http://www.asp.net/signalr)
* [Java.rmi](http://docs.oracle.com/javase/7/docs/api/java/rmi/package-summary.html)

--

# Collaborating on Data

--

<!-- .slide: data-background="img/gdocs-collaboration.png" data-background-size="100%" -->

--

**TODO: GIS**

--

**DataSync**

```
var myDataRef = new Firebase('https://my-app.firebaseio.com/');

myDataRef.push( {name: '@leggetter', text: 'Yo from FOWA!'} );

myDataRef.on( 'child_added', function(snapshot) {
  // Add the data
});

myDataRef.on( 'child_changed', function(snapshot) {
  // Update the data
});

myDataRef.on( 'child_removed', function(snapshot) {
  // Remove the data
});
```

--

![](img/internet-http-es-ws-msg-pubsub-rmi-ds.png)

Note:
It's now so much easier to innovate!

--

# It's not just Apps. It's Things!

--

<!-- .slide: data-background="img/iot-2020.png" data-background-size="70%" -->

Note:

- IDC report
- Same report: 7.7 Billion people

--

<video class="stretch" poster="video/gangnam-thumb.png" width="100%" preload="auto" controls>
  <source src="video/gangnam-node.mp4" type="video/mp4">
  <source src="video/gangnam-node.webm" type="video/webm">
  <p>Please download and watch our <a href="video/internet-high-5-machine.mp4">promotional video clip</a></p>
</video>

Note:
- AR Drones controlled via UDP packets
- Generally accessed via a library abstraction

--

## IoT Platforms

* [SmartThings](http://www.smartthings.com/index.php)
* [NinjaBlocks](http://ninjablocks.com/)
* [EvryThing](https://www.evrythng.com/)
* [SKYNET.im](http://skynet.im)

--

# And APIs...

--

<!-- .slide: data-background="img/nest-thermostat.jpg" data-background-size="100%" -->

Note:

- Nest acquired by Google for $3.2B

--

# Beyond

--

## Network Infrastructure

* Reliablity
* Speed
* Beyond HTTP

--

## Thanks

#### Phil [@leggetter](http://www.leggetter.co.uk)
#### &nbsp;
#### [BladeRunnerJS](http://bladerunnerjs.org)
