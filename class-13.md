
# Notes on The Past, Present & Future of Local Storage for Web Applications

Cookies allow for persistent local storage but they have downsides of slowing down web application by needlessly transmitting same data over and over, sending data unencrypted over the internet (unless otherwise secured), and are limited to aboiut 4 KB of data which is enought to slow down web application but not enough to be much useful.

What we want is a lot of storage space on the client that persists beyond a page refresh and isn't transmitted to the server.

## A brief history of local storage hacks before HTML5

Internet Explorer. `userData` allowing webpages to store up to 64 KB of data per domain.

Flash 6 introduced by Adobe in 2002 with Local Shared Objects of up to 100 KB storage per domain. Evolved to AMASS, then integrated into Dojo Toolkit.

Google launched Gears in 2007 as open source browser plugin.

All pre-HTML5 solutions are either specific to single browser, or reliant on third-party plugin. HTML5 set out to provide a standardized API implemented natively and consistently in multiple browsers without having to rely on third party plugins.

## Introducing HTML5 storage

it's a specific named Web Storage, also referred to as Local Storage or DOM Storage. It's a way for web pages to store named key/value pairs locally, within the client web browser. The data persists after navigating away form page, closing browser tab, exiting browswer, etc. But data is never transmitted to the remote web server (unless you mean to send it manually). It is implemently natively in web browsers, so available when third-party plugins are not.

Access HTML5 storage through `localStorage` objected on the global `window` object using JS code:
```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```
or use Modernizr to detect support for HTML5 Storage:
```
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

## Using HTML5 Storage

It's based on named key/value pairs.'

Calling `setItem()` with a named key that already exists will silently overwrite the previous value. Calling `getItem()` with a non-existent key will return null rather than throw an exception.

Calling `removeItem()` with a non-existent key will do nothing.