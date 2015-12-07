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

## Licenses

This application is released under [ISC](https://tldrlegal.com/license/-isc-license) licencing.

The images included with this application are released under their corresponding license:

- `fixtures/test.jpg` - [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/deed.en) - [https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg](https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg)
- `fixtures/test.gif` - [Public Domain](https://en.wikipedia.org/wiki/Public_domain) - [https://commons.wikimedia.org/wiki/File:Cat_trotting,_changing_to_a_gallop.gif](https://commons.wikimedia.org/wiki/File:Cat_trotting,_changing_to_a_gallop.gif)
- `fixtures/test.ico` - [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/deed.en) - adapted from and released under same license as [https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg](https://commons.wikimedia.org/wiki/File:So_happy_smiling_cat.jpg)
- `fixtures/test.png` - [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.en) - [https://commons.wikimedia.org/wiki/File:Fails_edge_parity_test.png](https://commons.wikimedia.org/wiki/File:Fails_edge_parity_test.png)
- `fixtures/test.svg` - [CC BY 2.5](https://creativecommons.org/licenses/by/2.5/deed.en) - [https://commons.wikimedia.org/wiki/File:SVG_logo.svg](https://commons.wikimedia.org/wiki/File:SVG_logo.svg)
