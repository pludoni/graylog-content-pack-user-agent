# Graylog Content Pack User Agent extractor

- Parses the http user agent via a remote API (http://useragentstring.com) and fills fields, like OS, Language, Browser Version
- the included pipeline rule expects a message attribute called "user_agent" to extract from

## Installation

1. install content pack
2. create/update pipeline:
  - attach rule to stage
  - modify rule if your message parameter is not called user_agent, (e.g. "HTTP_USER_AGENT")



