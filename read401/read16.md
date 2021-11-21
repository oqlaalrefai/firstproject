## Web Scrape
- is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort

- Inspecting the Website :
  - The first thing that we need to do is to figure out where we can locate the links to the files we want to download inside the multiple levels of HTML tags
  - On the website, right click and click on “Inspect”. This allows you to see the raw code behind the site.
  - Notice that on the top left of the console, there is an arrow symbol.If you click on this arrow and then click on an area of the site itself, the code for that particular item will be highlighted in the console

### python code :
 once we’ve identified the location of the links, let’s get started on coding!
```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url) #access the site with our requests library.
```
if its return the `<Response [200]>` the access was successful
- we parse the html with BeautifulSoup so that we can work with a nicer `soup = BeautifulSoup(response.text, “html.parser”)`
- `soup.findAll('a') ` We use the method .findAll to locate all of our <a> tags.
- extract the actual link that we want
```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’] 
```

- We can use our urllib.request library to download this file path to our computer
```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```

- we should include this line of code so that we can pause our code for a second so that we are not spamming the website with requests. This helps us avoid getting flagged as a spammer.
`time.sleep(1)`

- Web Crawlers can retrieve data much quicker, in greater depth than humans, so bad scraping practices can have some impact on the performance of the site

- web scraping best practices you can follow to avoid getting web scraping blocked:

### Respect Robots.txt :It has specific rules for good behavior, such as how frequently you can scrape, which pages allow scraping, and which ones you can’t. 
- Google to scrape their websites, by not allowing any other websites to scrape.
- If it contains lines like the ones shown below, it means the site doesn’t like and does not want to be scraped.
    - User-agent: *
    - Disallow:/ 
- Here are a few easy giveaways that you are bot/scraper/crawler :
  1. Scraping too fast and too many pages, faster than a human ever can  
  2. Following the same pattern while crawling
  3. Too many requests from the same IP address in a very short time
  4. Not identifying as a popular browser
  5. using a user agent string of a very old browser

### Make the crawling slower, do not slam the server, treat websites nicely
- Web scraping bots fetch data very fast, but it is easy for a site to detect your scraper, as humans cannot browse that fast
- Use **auto throttling mechanisms** which will automatically throttle the crawling speed based on the load on both the spider and the website that you are crawling. Adjust the spider to an optimum crawling speed after a few trial runs. Do this periodically because the environment does change over time.

### Do not follow the same crawling pattern
- Humans generally will not perform repetitive tasks as they browse through a site with random actions
- Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.

### Make requests through Proxies and rotate them as needed 
- There are several methods that can change your outgoing IP.

1. TOR
2. VPNs
3. Free Proxies
4. Shared Proxies – the least expensive proxies shared by many users. The chances of getting blocked are high.
5. Private Proxies – usually used only by you, and lower chances of getting blocked if you keep the frequency low.
6. Data Center Proxies, if you need a large number of IP Addresses and faster proxies, larger pools of IPs. They are cheaper than residential proxies and could be detected easily.
7. Residential Proxies, if you are making a huge number of requests to websites that block to actively. These are very expensive (and could be slower, as they are real devices). Try everything else before getting a residential proxy.

### Rotate User Agents and corresponding HTTP Request Headers between requests
- A user agent is a tool that tells the server which web browser is being used. If the user agent is not set, websites won’t let you view content
- The only way to make your User-Agent appear more real and bypass detection is to fake the user agent. Most web scrapers do not have a User Agent by default, and you need to add that yourself.
-  If you find your bots getting blocked even after putting in a recent User-Agent string, you should add some more request headers. 
- The most basic ones are:
 - User-Agent
 - Accept
 - Accept-Language
 - Referer
 - DNT
 - Updgrade-Insecure-Requests
 - Cache-Control
- Do not send cookies unless your scraper depends on Cookies for functionality.


### Use a headless browser like Puppeteer, Selenium or Playwright
- If none of the methods above works, the website must be checking if you are a REAL browser.
- The simplest check is if the client (web browser) can render a block of JavaScript. If it doesn’t, then it pretty much flags the visitor to be a bot
-  There are libraries to automatically control browsers such as
  - Selenium
  - Puppeteer and Pyppeteer
  - Playwright
- Bot detection tools look for any flags that can tell them that the browser is being controlled through an automation library.
  - Presence of bot specific signatures
  - Support for nonstandard browser features
  - Presence of common automation tools such as Selenium, Puppeteer, Playwright, etc.
  - Human-generated events such as randomized Mouse Movement, Clicks, Scrolls, Tab Changes etc.
-  tools which could help your headless browser-based scrapers from getting banned.
  - Puppeteer Extra  – Puppeteer Stealth Plugin
  - Patching Selenium/ Phantom JS – Stack OverFlow Answer on Patching Selenium with Chrome Driver
  - Fingerprint Rotation – Microsoft Paper on Fingerprint Rotation

### Honeypots
- are systems set up to lure hackers and detect any hacking attempts that try to gain information
- When following links always take care that the link has proper visibility with no nofollow tag. Some honeypot links to detect spiders will have the CSS style display:none or will be color disguised to blend in with the page’s background color.

### Check if Website is Changing Layouts
- Some websites make it tricky for scrapers, serving slightly different layouts.
- To prevent this, check if you are getting data scraped using XPaths or CSS selectors. If not, check how the layout is different and add a condition in your code to scrape those pages differently.

### Avoid scraping data behind a login
- Login is basically permission to get access to web pages. Some websites like Indeed do not allow permission

### Use Captcha Solving Services
- If you need to scrape websites that use Captcha, it is better to resort to captcha services. Captcha services are relatively cheap, which is useful when performing large scale scrap

### How can websites detect and block web scraping?
- mechanisms to detect a scraper/spider from a normal user :
1. Unusual traffic/high download rate especially from a single client/or IP address within a short time span.
2. Repetitive tasks performed on the website in the same browsing pattern
3. Checking if you are real browser – A simple check is to try and execute javascript. Smarter tools can go a lot more and check your Graphic cards and CPUs 😉 to make sure you are coming from real browser.
4. Detection through honeypots – these honeypots are usually links which aren’t visible to a normal user but only to a spider. When a scraper/spider tries to access the link, the alarms are tripped.

### How do you find out if a website has blocked or banned you?
- sign of being blocked or banned:
  - CAPTCHA pages
  - Unusual content delivery delays
  - Frequent response with HTTP 404, 301 or 50x errors
- Frequent appearance of these HTTP status codes is also indication of blocking
  - 301 Moved Temporarily
  - 401 Unauthorized
  - 403 Forbidden
  - 404 Not Found
  - 408 Request Timeout
  - 429 Too Many Requests
  - 503 Service Unavailable




















