---
tags: [javascript, Notebooks, rust]
title: firefox
created: '2019-07-30T06:19:49.054Z'
modified: '2023-05-24T12:36:45.313Z'
---

# firefox

> free and open-source web browser developed by mozilla

```
The Beast continued its studies with renewed Focus, building great Reference works and contemplating new Realities.
The Beast brought forth its followers and acolytes to create a renewed smaller form of itself and,
through Mischievous means, sent it out across the world.

from The Book of Mozilla, 6:27
```

[en.wikipedia.org/wiki/The_Book_of_Mozilla](https://en.wikipedia.org/wiki/The_Book_of_Mozilla)

## about

> type into addr bar

```
about:about                 // get all about pages
about:mozilla               // get a easteregg / funny quote

about:preferences#search    // jump to seach in preferences

about:telemetry

about:performance           // starts taskmanager

about:config
  dom.webnotifications.enabled = false !

about:logins                // lockwise password etc
```


## awesome bar

> changing results on the fly

looking for a specific type of result, like a bookmark or tag, speed up the process of finding it by typing in special characters after each search term in the address bar separated by spaces:

```sh
^   # search matches in browsing history
*   # search matches in bookmarks
+   # search matches in tagged pages
~   # search matches in typed pages
%   # search matches in currently open tabs
#   # search matches in page titles
@   # search matches in web addresses
$   # search matches in suggestions
```

## see also

- [[javascript]], [[rust]]
- [[duckduckgo]]
- [[macos keyboard shortcuts]]
- [Awesome Bar - Search your Firefox bookmarks, history and tabs from the address bar](https://support.mozilla.org/en-US/kb/awesome-bar-search-firefox-bookmarks-history-tabs#w_changing-results-on-the-fly)
