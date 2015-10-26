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
