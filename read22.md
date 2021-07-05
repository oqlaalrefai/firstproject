# local store
- ersistent local storage is one of the areas where native client applications have held an advantage over web applications.
- the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state
- values may be stored in the registry, INI files, XML files ## Cookies : used for persistent local storage of small amounts of data
- But they have three potentially dealbreaking downsides:

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)
- Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful
- HTML5 Storage” is a specification named Web Storage:put, it’s a way for web pages to store named key/value pairs locally, within the client web browser.
- this data is never transmitted to the remote web server
- From your JavaScript code, you’ll access HTML5 Storage through the localStorage object on the global window object. Before you can use it
``` function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
} ```
- HTML5 Storage is based on named key/value pairs.
- The named key is a string. The data can be any type supported by JavaScript
- data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.
- Calling `setItem()` with a named key that already exists will silently overwrite the previous value
- Calling `getItem()` with a non-existent key will return null rather than throw an exception.
- Like other JavaScript objects, you can treat the localStorage object as an associative array
- There are also methods for removing the value for a given named key:
  - removeItem()
- If you want to keep track programmatically of when the storage area changes, you can trap the storage event.
- storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and actually changes something
- The handle_storage callback function will be called with a StorageEvent object, except in Internet Explorer where the event object is stored in window.event.
``` function handle_storage(e) {
  if (!e) { e = window.event; }
}
 ```
PROPERTY	TYPE	DESCRIPTION
key		string	the named key that was added, removed, 			or modified

oldValue	any	the previous value (now overwritten), 			or null if a new item was added

newValue	any	the new value, or null if an item was 			removed

url*		string	the page which called a method that 			triggered this change

- The storage event is not cancelable
- “5 megabytes” is how much storage space each origin gets by default
- “QUOTA_EXCEEDED_ERR” is the exception that will get thrown if you exceed your storage quota of 5 megabytes. “No” is the answer to the next obvious question
- Here is a live demonstration. Make a few moves, then close the browser tab, then re-open it. If your browser supports HTML5 Storage, the demonstration page should magically remember your exact position within the game, including the number of moves you’ve made, the position of each of the pieces on the board, and even whether a particular piece is selected.
- the present condition of HTML5 Storage is surprisingly rosy. A new API has been standardized and implemented across all major browsers, platforms, and devices.
- One vision is an acronym that you probably know already: SQL.
- if you’ve used more than one database product in your life, you are aware that “SQL” is more of a marketing term than a hard-and-fast standard.
-  competing vision for advanced, persistent, local storage for web applications: the Indexed Database API, formerly known as “WebSimpleDB,” now affectionately known as “IndexedDB.
- The Indexed Database API exposes what’s called an object store. An object store shares many concepts with a SQL database.
- There are “databases” with “records,” and each record has a set number of “fields.” Each field has a specific datatype, which is defined when the database is created
- The primary difference is that the object store has no structured query language
- use methods provided by the object store to open a cursor on the database named “USERS,” enumerate through the records, filter out records for inactive users, and use accessor methods to get the values of each field in the remaining records.


