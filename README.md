# harasser

Send repeated http requests, even indefinitely, if you like. I hereby wash my hands of what you do with this.

## Install

```bash
npm install -g harasser
```

## Usage

```cli
harass url_to_harass [options]

Options:
  -i, --iterations NUMBER number of iterations
  -b, --bandwidth [NUMBER] number of calls to run simultaneously (Default is 10)
  -r, --repeat [NUMBER]  time (ms) between repeating call (Default is 1000)
  -m, --methods [STRING] methods of HTTP calls to send, comma-delineated  (Default is post,get,put,patch,delete)
  -a, --append BOOLEAN   append method to url to call
  -h, --headers [STRING] headers, comma delineated (Default is Host:httpbin.org)
  -t, --filetypes [STRING] which filetypes to send in calls, randomly assigned  
          (Default is css,csv,gif,html,ico,jpg,js,json,md,png,svg,txt,xml,yml)
  -f, --includeform BOOLEAN include calls with application/x-form-urlencoded bodies
  -k, --no-color         Omit color from output
      --debug            Show debug information
  -v, --version          Display the current version
```

### `--repeat`

Repeat is the number of milliseconds it waits **after the last call completed**. This won't stack up calls on top of each other if the requests are taking forever. That means, if you set the `--repeat` param to 1500 ms, and the calls take 2000 ms to complete, there will be 3500 ms between the start of each call. I wanted to make sure the previous calls went through before stacking more on. Ends up being pretty snappy most of the time.

### `sleep()` vs `setInterval`

The original script this was built out of was using `setInterval` and/or `setTimeout`, both of which, for some reason on my system, stopped working after a couple hundred iterations. *I still have no idea why it does that. If you know, please shoot me a message*. The synchronous `sleep()` call checks the milliseconds of the current `Date()` object before continuing. All the tests I've done with this method seem to be working quite nicely for me, tested over 10k iterations with no signs of stopping. If you have another method that works better, please let me know.

## Why?

I needed a way to test a large number of requests into [Kong](https://getkong.org/) for testing the [Galileo](http://apianalytics.com/) platform (for which I built the frontend). This cli did the ticket.

## Licenses

This application is released under [ISC](https://tldrlegal.com/license/-isc-license) licensing.
