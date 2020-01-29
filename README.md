# Graylog Content Pack User Agent extractor

- Parses the http user agent via a remote API (http://useragentstring.com) and fills fields, like OS, Language, Browser Version
- the included pipeline rule expects a message attribute called "user_agent" to extract from

## Installation

1. install content pack
2. create/update pipeline:
  - attach rule to stage
  - modify rule if your message parameter is not called user_agent, (e.g. "HTTP_USER_AGENT")


## How it works

- Pipeline rule will trigger the data extractor/lookup table
- That will make an API call to, e.g. http://useragentstring.com/?uas=Opera/9.70%20(Linux%20i686%20;%20U;%20en-us)%20Presto/2.2.0&getJSON=all
- the returned json will be extracted into fields:

```
user_agent (Source field)
    Mozilla/5.0(Linux;Android 5.1.1;OPPO A33 Build/LMY47V;wv) AppleWebKit/537.36(KHTML,link Gecko) Version/4.0 Chrome/42.0.2311.138 Mobile Safari/537.36 Mb2345Browser/9.0
user_agent__agent_name
    Android Webkit Browser
user_agent__agent_type
    Browser
user_agent__agent_version
    --
user_agent__os_linux
    Null
user_agent__os_name
    Android
user_agent__os_type
    Android
user_agent__os_versionNumber
    5.1.1
user_agent_name
    Android Webkit Browser --
user_agent_os
    Android 5.1.1
```
