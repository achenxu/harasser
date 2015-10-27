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

## Why?

I needed a way to test a large number of requests into [Kong](https://getkong.org/) for testing of the [Galileo](http://apianalytics.com/) platform (for which I built the frontend). This cli did the ticket.

### `sleep()`?

The original script this was built out of was using `setInterval` and/or `setTimeout`, both of which, for some reason on my system, stopped working after a couple hundred iterations. This synchronous call checks the milliseconds of the current `Date()` object before continuing. All the tests I've done with this method seem to be working quite nicely for me. If you have another method that works better, please let me know.
