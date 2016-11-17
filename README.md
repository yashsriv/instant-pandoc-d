!nstant-pandoc-d
================

instant-pandoc-d is a Node.js server based on @suan's
[instant-markdown-d]("https://github.com/suan/instant-markdown-d").

Full credit goes to @suan for the original server. This is merely
a ripoff made to work with pandoc as well.

This enables instant previewing of pandoc Markup files. A plugin
can easily be written for any text editor to interface with it. There is
one in planning for vim and which will hopefully be available at:
[https://github.com/yashsriv/vim-instant-pandoc](https://github.com/yashsriv/vim-instant-pandoc)

Prerequisites
-------------
- A html5 compatible browser set as your default browser
- `pandoc` cli installed (duh!!)

Installation
------------
- `[sudo] npm -g install instant-pandoc-d`

REST API
--------
|          Action          | HTTP Method |        Request URL        |         Request Body         |
| :----------------------: | :---------: | :-----------------------: | :--------------------------: |
| Refresh Markdown on page |     PUT     | http://localhost:\<port\> | \<New Pandoc File Contents\> |
|       Close Webpage      |    DELETE   | http://localhost:\<port\> |                              |

By default, \<port\> is `8090`, but it can be specified while starting server like:

```shell
$ instant-pandoc-d -p 80
```

_Copied_ exactly from @suan's repo:
Environment variables
---------------------

* `INSTANT_MARKDOWN_OPEN_TO_THE_WORLD=1` - by default, the server only listens
  on localhost. To make the server available to others in your network, set this
  environment variable to a non-empty value. Only use this setting on trusted
  networks!

* `INSTANT_MARKDOWN_ALLOW_UNSAFE_CONTENT=1` - by default, scripts are blocked.
  Use this preference to allow scripts.

* `INSTANT_MARKDOWN_BLOCK_EXTERNAL=1` - by default, external resources such as
  images, stylesheets, frames and plugins are *allowed*. Use this setting to
  *block* such external content.
