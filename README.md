# react-interview-questions-India
React JS Interview Questions mainly asked by Indian Interviewers

# React JS Interview Questions and Answers

## Table of Contents

| No. | Questions                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------ |
| 1   | [What are the different storage mechanism in browsers?](#1)      |
ToTheNew: (15-jan)
optional chaining
seo in react
 localStorage, sessionStorage, cookies limitations
event.stopPropagation vs event.preventDefault()
flatten a nested object 

EY: (18-jan)
Promises vs Callback
write promise code
Write code to fetch data from server.

Unifytech: (19-jan)
lifecycle of react-native navigation
getSnapshotBeforeUpdate() use cases
oops concept in android development
storage in react native
weakmap use cases
design patterns in React Native development.
write code for:
closure
longest increasing sequence

Iris Software:(26-Jan)
javascript datatypes of NaN, null, array
css div vs span
box model


Publicis Sapient: (27-jan)
Software development steps
microservices architecture
React JS
TDD approach
huskey, prettier, linting
Github checks

Infinite Computer Solutions: (29-jan)
why redux loose data on page refresh
react reconciltion
what is the output of below codes in react component
1.
const [abc, setAbc] = useState(0)
useEffect(()=>{
setAbc(10)
console.log(abc)
},[])

2.
const [abc, setAbc] = useState(0)
useEffect(()=>{
setAbc(10)
console.log(abc)
},[abc])

3.
const [abc, setAbc] = useState(0)
useEffect(()=>{
setAbc(10)
console.log(abc)
})

4.
const [abc, setAbc] = useState(0)
useEffect(()=>{
console.log(abc)
},[abc])
 
for (let i=0; i<1000;i++){
setAbc(i)
}

Iris Software[2nd Round(Manager)]: (30-Jan) 
Professional journey

Pratham:
3 api calls one after another. correct approach.
what should we do while waiting for the data if it's around 10 sec.
how to use variables in CSS
scss
webpack configuration
publish npm packages
semantic elements
react vs angular
how unidirectional data flow helps
how using virtual dom is faster
can we use multiple redux stores in react app.

Pratham2: (02-Feb)
[CDN] (#cdn)
architectural diagram
appliaction takes time to load. fix it
how to debug performance issue
performance bottle necks you faced
security in react appliaction
Web components
pointers to check in code reviews
pointers to check while driving sprint planning, giving story points.
pixel perfect design.
reusable UI components
design pattern in your project.

<a name="1"></a>
**1. What are the different storage mechanism in browsers**

  Three different storage mechanisms exist for the web browser:
  
  a) localStorage
  
  b) sessionStorage
  
  c) cookies.

  ### localStorage
  
  localStorage is storage data that is only stored in the browser where:
    Stored data is persistent. This means this data remains in the browser’s memory even if the user refreshes the web page or closes and reopens the browser window.
    Stored data is only accessible through client-side JavaScript and cannot be accessed by the server.
    Stored data is not automatically sent to the server with every HTTP request. This means that the server will not have access to the data unless it is specifically requested.
  
      localStorage.setItem("greeting", "Hello World!");
  
  If we were to refresh the web page, close and reopen the tab, close and reopen the browser, or even restart our computer, the data remains! The only way to delete this data is to either clear our browser’s memory or explicitly delete the localStorage data with the removeItem() or clear() function.

### sessionStorage

  sessionStorage behaves similarly to localStorage in that the data stored with it is only accessible through client-side JavaScript and is not automatically sent to the server with every HTTP request. However, sessionStorage has one key difference: the data stored with it is automatically deleted when the user closes the browser tab or window where the data was stored.
  
      sessionStorage.setItem("greeting", "Hello World!");
  
  When we refresh the web-page, the data will not be deleted (just like localStorage ). However, by closing and reopening the browser tab or closing and reopening the browser window, the data will be deleted!
  
  Alternatively, like localStorage, data can also be deleted by clearing out the browser’s memory or with the removeItem() and clear() functions:

### Cookies

  Cookies are another form of data that can be stored in the browser. Some key properties of cookies include:
  
  Persistence. The data stored in cookies is persistent, which means it will remain in the browser even if the user refreshes the web page or closes and reopens the browser window.
  Accessibility/Security. Cookies can be marked as HttpOnly which means that they can only be accessed by the server and not by JavaScript running in the browser. This helps to protect the security of the data stored in the cookie.
  Automatic transmission. Unlike localStorage or sessionStorage, the data stored in cookies is automatically sent to the server with every HTTP request.
  Cookies, like localStorage, are persistent in memory. If we were to refresh the web-page or close and re-launch the browser window (or tab), the data stored in cookies will not be deleted. However, cookie data can be deleted if we were to explicitly clear browser memory or the cookie happens to reach its expiration date.

### localStorage & sessionStorage Security
  Both localStorage and sessionStorage are accessible through JavaScript running in the browser. This means that any data stored in these types of storage, such as authentication data, is vulnerable to cross-site scripting (XSS) attacks. In a XSS attack, an attacker can inject client-side scripts, such as JavaScript, into a web app in order to gain access to sensitive information.
  
  There are some steps we can take to prevent XSS attacks.
  
  We can ensure all links on our website are from a trusted source. This includes not only the URLs of <a/> tags, but also the URLs of <img/> elements, as attackers can use these to inject malicious code into the web app.
  We can escape untrusted data. This is often done automatically when using a modern front-end framework like React.
  However, when it comes to storing sensitive data in the browser, cookies are better suited for storing sensitive data than localStorage or sessionStorage.

### Cookie Security
  Cookies can be marked as HttpOnly and thus can only be accessed by the server and not by JavaScript running in the browser. This make cookies immune to XSS attacks. We can also set a Secure flag to a cookie to guarantee the cookie is only sent over HTTPS. These are some of the reasons why cookies are often used to store sensitive tokens or session data.
  
  However, cookies are vulnerable to a type of attack known as cross-site request forgery (CSRF). In a CSRF attack, an attacker lures a victim to a malicious website or email, which causes the victim’s web browser to perform an unwanted HTTP request to another website where the victim is currently authenticated. This exploit of how the browser handles cookies can allow the attacker to gain access to sensitive information.
  
  To help prevent CSRF attacks, the SameSite flag was introduced for cookies. When this flag is set, cookies are not sent with cross-site requests, which makes it much more difficult for attackers to perform a CSRF attack.
  
  Some older browsers still don’t support the SameSite flag. For an additional step to countering CSRF, we can include a token (e.g. X-CSRF-TOKEN) with every HTTP request. This helps to ensure that the request is being made by the intended user and not an attacker. By using both the SameSite flag and a token, you can help to protect your web app from CSRF attacks and keep your users’ data safe.

<a name="cdn"></a>
## What Is a CDN ?
A content delivery network (CDN) is a group of geographically distributed servers that speed up the delivery of web content by bringing it closer to where users are.

CDNs rely on a process called “caching” that temporarily stores copies of files in data centers across the globe, allowing you to access internet content from a server near you. Content delivered from a server closest to you reduces page load times and results in a faster, high-performance web experience. By caching content like web pages, images, and video in servers near your physical location, CDNs allow you to do things like watch a movie, download software, check your bank balance, post on social media, or make purchases without having to wait for content to load.




