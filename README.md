# Sherlock [![Build Status](https://travis-ci.com/TheYahya/sherlock.svg?branch=master)](https://travis-ci.com/TheYahya/sherlock)
> Find usernames across [social networks](https://github.com/theyahya/sherlock/blob/master/sites.md)

<p align="center">
<a href="https://asciinema.org/a/223115">
<img src="https://asciinema.org/a/223115.svg">
</a>
</p>

## Installation

**NOTE**: Python 3.6 or higher is required.

```bash
# clone the repo
$ git clone https://github.com/TheYahya/sherlock.git

# change the working directory to sherlock
$ cd sherlock

# install python3 and python3-pip if not exist

# install the requirements
$ pip3 install -r requirements.txt
```

## Usage

```bash
$ python3 sherlock.py --help
usage: sherlock.py [-h] [--version] [--verbose] [--quiet] [--tor]
                   [--unique-tor] [--csv] [--site SITE_NAME]
                   [--proxy PROXY_URL]
                   USERNAMES [USERNAMES ...]

Sherlock: Find Usernames Across Social Networks (Version 0.4.0)

positional arguments:
  USERNAMES             One or more usernames to check with social networks.

optional arguments:
  -h, --help            show this help message and exit
  --version             Display version information and dependencies.
  --verbose, -v, -d, --debug
                        Display extra debugging information and metrics.
  --quiet, -q           Disable debugging information (Default Option).
  --tor, -t             Make requests over TOR; increases runtime; requires
                        TOR to be installed and in system path.
  --unique-tor, -u      Make requests over TOR with new TOR circuit after each
                        request; increases runtime; requires TOR to be
                        installed and in system path.
  --csv                 Create Comma-Separated Values (CSV) File.
  --site SITE_NAME      Limit analysis to just the listed sites. Add multiple
                        options to specify more than one site.
  --proxy PROXY_URL, -p PROXY_URL
                        Make requests over a proxy. e.g.
                        socks5://127.0.0.1:1080
```

For example, run ```python3 sherlock.py user123```, and all of the accounts
found will be stored in a text file with the username (e.g ```user123.txt```).

## Docker Notes
If you have docker installed you can build an image and run this as a container.

```
docker build -t mysherlock-image .
```

Once the image is built sherlock can be invoked by running the following:

```
docker run --rm mysherlock-image user123
```

The optional ```--rm``` flag removes the container filesystem on completion to prevent cruft build-up.  See https://docs.docker.com/engine/reference/run/#clean-up---rm

One caveat is the text file that is created will only exist in the container so you will not be able to get at that.


Or you can simply use "Docker Hub" to run `sherlock`:
```
docker run theyahya/sherlock user123
```

## Tests
If you are contributing to Sherlock, then Thank You!

Before creating a pull request with new development, please run the tests
to ensure that all is well.  It would also be a good idea to run the tests
before starting development to distinguish problems between your
environment and the Sherlock software.

The following is an example of the command line to run all the tests for
Sherlock.  This invocation hides the progress text that Sherlock normally
outputs, and instead shows the verbose output of the tests.

```
$ python3 -m unittest tests.all --buffer --verbose
```

Note that the tests are very much a work in progress.  Significant work is
required to get full test coverage.  But, the current tests are working
properly, and will be expanded as time goes by.

## Original creator of Sherlock
Siddharth Dushantha ([sdushantha](https://github.com/sdushantha))

## License

MIT © [Yahya SayadArbabi](https://theyahya.com)
