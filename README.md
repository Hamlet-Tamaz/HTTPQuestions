## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
- protocol
- domain
- port
- path
- query string
- anchor tag
``` 			
* Name the pieces of the following urls:
	* `https://www.google.com/`
	
	```
	protocol://domain/
	```
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	
	```
	protocol://domain/path
	```
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
	
	```
	protocol://domain:port/path?querystring
	```
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
	
	```
	protocol://domain/path/anchortag
	```
	
* Can a server use more than 1 port?
	- yes; this is used when the server is communicating with more than one client 
* Why is https different than http?
	- https offers security features that http doesn't; for example, https provides secrecy when it comes to hiding the information entered into the website (ie. entering your password)
* How does a server interpret the following url's query paramter.  What data structure does it create on the server?
	- it creates an array (puppies) with the names fido, max, and moxie inside.

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

__HTTP Request/Response__

* Name at least 4 http verbs
* What is each verb useful for in your own words

```
- Get: a verb which requests information from the server
- Post: a verb which tells the server that new information is going to be given
- Put: tells the server that existing info on the server will be adjusted
- Delete: information on the server will be deleted

```


* What does idempotent mean?

```
It means that the (HTTP) method can be called many times over and always have the same outcome.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
- 100s: You're in the process of getting what you want 
- 200s: You got what you want in some form 
- 300s: You have to go somewhere else to get what you want 
- 400s: I couldn't give you what you want, but there wasn't an error on my end 
- 500s: Some kind of error has happened on the server's side; it’s the server fault 
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
The browser will likely redirect to that new location since that is where it needs to go in order to retrieve whatever it was we asked for.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept: Request
	* Content-type: both
	* User-agent: request
	* Set-cookies: response
	* Cache-control: both
	* Cookie:request
* Is the following a http request or response?  How do you know for each?

```
- The first one is a response; there are certain headers which only responses have including vary and ETag. Plus, it is returning to us the html code we likely requested.
- The next is a request; it starts with a DELETE verb. It also has a host header which is exclusive to requests. 
```


```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON files are human readable strings of data with syntax similar to Javascript, except they are always stings set in quotes. JSON is used for asynchronous communication between servers and clients.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
console.log(JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}').age)
```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
```
JSON.parse('{"Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}').Companies.forEach(function(el) {console.log(el.company)})
```


* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
console.log(JSON.stringify(myObj))
```

__MISC__

* Describe what DNS is.
	- Domain Name System: gives human readable names to IP addresses.
* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).
	- "-v" stands for verbose: it is a flag we've previously used; it asks sends a command to (when possible) give more detailed information on whatever was originally being requested.
	- "-X" specifies a custom request method for the HTTP communication with the server.
* What is TCP/IP?  How does it interact with HTTP?
	- It is a protocol system which provided unification and standardizatin to the web. Being credited for the modern web, it allowed for smooth communication accross platforms and even just clients/servers in terms of what set rules/procedures to follow when reading HTTP. It is also responsible for making sure that no information that is sent gets lost along the way and is delivered in a timely manner. Finally, it is also responsible for not only sending/resending any info over the web, but it also can break up the info to smaller pieces and send them that way. 
* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?
	- see answer above.
