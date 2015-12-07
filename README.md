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

I needed a way to test a large number of requests into [Kong](https://getkong.org/) for testing the [Galileo](http://apianalytics.com/) platform (for which I built the frontend). This cli did the ticket.

## Licenses

This application is released under [ISC](https://tldrlegal.com/license/-isc-license) licencing.

The images included with this application are released under their corresponding license:

- `fixtures/test.jpg` - [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/deed.en) - [https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg](https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg)
- `fixtures/test.gif` - [Public Domain](https://en.wikipedia.org/wiki/Public_domain) - [https://commons.wikimedia.org/wiki/File:Cat_trotting,_changing_to_a_gallop.gif](https://commons.wikimedia.org/wiki/File:Cat_trotting,_changing_to_a_gallop.gif)
- `fixtures/test.ico` - [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/deed.en) - adapted from and released under same license as [https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg](https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg)
- `fixtures/test.png` - [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.en) - [https://commons.wikimedia.org/wiki/File:Fails_edge_parity_test.png](https://commons.wikimedia.org/wiki/File:Fails_edge_parity_test.png)
- `fixtures/test.svg` - [CC BY 2.5](https://creativecommons.org/licenses/by/2.5/deed.en) - [https://commons.wikimedia.org/wiki/File:SVG_logo.svg](https://commons.wikimedia.org/wiki/File:SVG_logo.svg)
