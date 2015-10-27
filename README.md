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
  -i, --iterations NUMBERnumber of iterations
  -b, --bandwidth [NUMBER]number of calls to run simultaneously (Default is 10)
  -r, --repeat [NUMBER]  time (ms) between repeating call (Default is 1000)
  -t, --types [STRING]   types of HTTP calls to send, comma-dilineated (Default is post,get,put,patch,delete,head)
  -k, --no-color         Omit color from output
      --debug            Show debug information
  -v, --version          Display the current version
  -h, --help             Display help and usage details
```

### `--repeat`

Repeat is the number of milliseconds it waits **after the last call completed**. This won't stack up calls on top of each other if the requests are taking forever. That means, if you set the `--repeat` param to 1500 ms, and the calls take 2000 ms to complete, there will be 3500 ms between the start of each call. I wanted to make sure the previous calls went through before stacking more on. Ends up being pretty snappy most of the time.

### `sleep()` vs `setInterval`

The original script this was built out of was using `setInterval` and/or `setTimeout`, both of which, for some reason on my system, stopped working after a couple hundred iterations. *I still have no idea why it does that. If you know, please shoot me a message*. The synchronous `sleep()` call checks the milliseconds of the current `Date()` object before continuing. All the tests I've done with this method seem to be working quite nicely for me, tested over 10k iterations with no signs of stopping. If you have another method that works better, please let me know.

## Why?

I needed a way to test a large number of requests into [Kong](https://getkong.org/) for testing of the [Galileo](http://apianalytics.com/) platform (for which I built the frontend). This cli did the ticket.

