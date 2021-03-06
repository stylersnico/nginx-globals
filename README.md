# nginx-globals

## Summary
This project contains my current nginx configuration files that were crafted with security in mind, all combined into seperate conf files to simplify and standize configurations. By calling these from include statements in your nginx configs it makes locking down your nginx sites easy. This is a simple project, but will help lock down nginx (likely) more than you have it now. Benefit from my years of tweaking nginx, and fortify your webserver, all feedback welcome!

## Usage
* Install nginx (I know, but someone had to say it)

* Checkout the nginx-globals project

```
git clone https://github.com/philcryer/nginx-globals.git
```

* (as root) copy the globals into place

```
cp -R nginx-globals/globals /etc/nginx/
```

* Edit an nginx site config and activate the globals you want, removing any duplicate lines from current configs

```
server {
  ...
  include       globals/cache.conf;
  include       globals/drop.conf;
  include       globals/php.conf;
  include       globals/secure.conf;
  include       globals/ssl.conf;
  ...
}
```

* Test the config changes

```
nginx -t
```

* Errors? Fix them. No errors? Restart nginx

## Feedback
These are my tried and true nginx configs, some crafted from trial and error, while some were snarfed from various sites online, giving credit given where known (see individual files for details). Having said that, there's no way they're all perfect and I'm sure others could improve on them, so please do! Open an issue, suggest changes or make a pull request - Thanks!

## License
The MIT License (MIT)

Copyright (c) 2015 philcryer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

