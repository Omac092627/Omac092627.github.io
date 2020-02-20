THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS
  A native client application is one that is installed on a user's computer or device. Examples of such an application include, but is not limited to, WinForms, WPF, Windows Store, Windows Phone, and iOS applications.

  Cookies are included with every HTTP request, therby slowing down your web application by needlessly transmitting the same data over and over. 

  Cookies are included with every HTTP request, thereby sending data unencrypted over the internet(unless served over an SSL).

  Cookies are limited to about 4kb of data - enough to slow down your application, but not enough to be terribly useful.

  What we really want is:
    A lot of storage space 
    On the client
    that persists beyond a page refresh
    and isn't transmitted to the server

    HTML5 STORAGE:
      It's web storage, or local storage or DOM storage.

      It's a way for web pages to store named key/value pairs locally, within the client web browsers. Like cookies, this data persists even after you navigate away from the website, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server -unless sent manually. It is implemented natively in web browsers, so it is available even when third-party browser plugins are not.

      FROM YOUR JAVASCRIPT CODE:
        You'll acess HTML storage through the localstorage object on the global window object. Before you can use it, you should peep whether the browser supports it. 

        how to check for it?
          Example: function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}


//USING HTML5 STORAGE:
  Calling setItem() with a named key that already exists will silently overwrite the previous value. Calling getItem() with a non-existent key will return null rather than throw an exception.

Like other JavaScript objects, you can treat the localStorage object as an associative array. Instead of using the getItem() and setItem() methods, you can simply use square brackets. For example, this snippet of code:

var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);
…could be rewritten to use square bracket syntax instead:

var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;