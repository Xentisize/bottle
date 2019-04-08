# Reading notes for Bottle's source code

## Import module(s)

- sys: importing stdout and stderr for redirection <line 119>  
   exit signal (exit(1): Exit with errors, exit(0): Exit without errors) <line 4369>
- argparse.ArgumentParser: setting up the cli of the program
- base64
- cgi
- email.utils
- functools
- hmac
- imp
- itertools
- mimetypes
- os
- re
- tempfile
- threading
- time
- warnings
- weakref
- hashlib
- types.FunctionType
- datetime.date as datedate
- datetime.datetime
- datetime.timedelta
- tempfile.TemporaryFile
- traceback.format_exc
- traceback.print_exc
- unicodedata.normalize
- ujson.dumps as json_dumps
- ujson.loads as json_lds
- inspect.signature
- http.client as httplib
- \_thread as thread
- urllib.parse.urljoin
- urllib.parse.SplitResult as UrlSplitResult
- urllib.parse.urlencode
- urllib.parse.quote as urlquote
- urllib.parse.unquote as urlunquote
- http.cookies.SimpleCookie
- http.cookies.Morsel
- http.cookies.CookieError
- collections.MutableMapping as DictMixin
- pickle
- io.BytesIO
- configparser

## Constants

- \_\_author\_\_ = 'Marcel Hellkamp'
- \_\_version\_\_ = '0.13-dev'
- \_\_license\_\_ = 'MIT'

## Pre-defined functions

- \_stdout: alias to stdout
- \_stderr: alias to stderr

## Exceptions

- BottleException(Exception)
- RouteError(BottleException): all routing related exceptions
  - RouterUnknownModeError(RouteError)
  - RouteSyntaxError(RouteError): route parser problem
  - RouteBuildError(RouteError): route can't be built
- RouteReset(BottleException): plugin or request handler

## Classes

- ConfigDict(dict) <line 2330>

## Running Flow

1. \_main(sys.argv: []) -> None <line 4363>  
   1.1 \_cli_parse(args: []) -> (argparse.Namespace, argparse.ArgumentParser) : parse the cli options and return arguments and the parser  
   1.2 add `bottle` or `__main__` into the imported modules dict  
   ? <line 4381> What is purpose of host.rfind(']') < host.rfind(':')
