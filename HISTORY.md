# HISTORY

## v1.0.0 (May 2x, 2012)

  - removed router DSL for 1.0 release
  - removed restriction on environments
  - refactored validation handler logic
  - refactored params coercion logic
  - users can customize log formats
  - cleanup of spec helpers
  - many small bugfixes

## v0.9.3 (Oct 16, 2011)

  - new router DSL - much improved, see examples
  - refactored async_aroundware
  - make jruby friendlier (removed 1.9 req in gemspec)
  - enable epoll
  - SSL support
  - unix socket support
  - reload config on HUP
  - and a number of small bugfixes + other improvements..
  - See full list @ https://github.com/postrank-labs/goliath/compare/v0.9.2...v0.9.3

## v0.9.2 (July 21, 2011)

  - See full list @ https://github.com/postrank-labs/goliath/compare/v0.9.1...v0.9.2

## v0.9.1 (Apr 12, 2011)

  - Added extra messaging around the class not matching the file name (Carlos Brando)

  - Fix issue with POST parameters not being parsed by Goliath::Rack::Params
  - Added support for multipart encoded POST bodies
  - Added support for parsing nested query string parameters (Nolan Evans)
  - Added support for parsing application/json POST bodies
  - Content-Types outside of multipart, urlencoded and application/json will not be parsed automatically.

  - added 'run as user' option
  - SERVER_NAME and SERVER_PORT are set to values in HOST header

  - Cleaned up spec examples (Justin Ko)

  - moved logger into 'rack.logger' key to be more Rack compliant (Env#logger added to
    keep original API consistent)
  - add command line option for specifying config file
  - HTTP_CONTENT_LENGTH and HTTP_CONTENT_TYPE were changed to CONTENT_TYPE and CONTENT_LENGTH
    to be more Rack compliant
  - fix issue with loading config file in development mode

  - Rack::Reloader will be loaded automatically by the framework in development mode.


## v0.9.0 (Mar 9, 2011)

(Initial Public Release)

Goliath is an open source version of the non-blocking (asynchronous) Ruby web server framework
powering PostRank. It is a lightweight framework designed to meet the following goals: bare
metal performance, Rack API and middleware support, simple configuration, fully asynchronous
processing, and readable and maintainable code (read: no callbacks).

The framework is powered by an EventMachine reactor, a high-performance HTTP parser and Ruby 1.9
runtime. One major advantage Goliath has over other asynchronous frameworks is the fact that by
leveraging Ruby fibers, it can untangle the complicated callback-based code into a format we are
all familiar and comfortable with: linear execution, which leads to more maintainable and readable code.

While MRI is the recommend platform, Goliath has been tested to run on JRuby and Rubinius.

Goliath has been in production at PostRank for over a year, serving a sustained 500 requests/s for
internal and external applications. Many of the Goliath processes have been running for months at
a time (read: no memory leaks) and have served hundreds of gigabytes of data without restarts. To
scale up and provide failover and redundancy, our individual Goliath servers at PostRank are usually
deployed behind a reverse proxy (such as HAProxy).
