# rawgit-privada
Finally, the capabilities of RawGit, plus the ability to serve files from
private repos!  Clearly this should only be used in protected network
environments to avoid the risk of spaffing your private files to anyone who
knows or can guess the path.


## Installing

1.  Install Node.js.

2.  Clone this git repo (fork it first if you plan to make changes).

        git clone git://github.com/rgrove/rawgit.git

3.  Install dependencies.

        cd rawgit && npm install

4.  Start the local server.

        npm start

5.  Browse to <http://localhost:5000/> and you should see RawGit in action.

## Running Tests

```
npm test
```

## Difference Compared to rawgit
rawgit-privada makes a few changes to rawgit.  It accepts an environment variable
`githubtoken` for access to private repos, and it disables the 301 redirect
functionality for non-whitelisted file types.  It also adds a feature when
`NODE_ENV == 'development'` which ensures that there is no caching of github
data; this eliminates the otherwise extant 5 minute cache time which is a tremendous
PITA when developing.  Furthermore, the `WHITELIST` environment variable, which
is the rawgit path to a whitelist json file, allows you to limit rawgit to providing
responses to the master branch of the named repos.  This is intended for situations
where the development server is on a private network, allowing access to all repos
which the github key has access to, yet where you also want to deploy to prod using
the same pattern, but want to restrict access only to the master branch of specified
repos.


## Contributing

Want to fix a bug? If it's something small, just send a pull request. If you
want to add a new feature or make significant changes, please get in touch and
ask if I'm interested before doing the work.

## License

Copyright (c) 2016 Ryan Grove (ryan@wonko.com).
very small portion: Copyright (c) 2016 Brad Smith

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
