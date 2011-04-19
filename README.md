gosh: Security theater for piped shell scripts
==============================================

Concerned about theoretical man-in-the-middle attacks when piping
scripts from `curl` to your shell?

Enter `gosh`. It's like a TSA backscatter machine for your computer.
Install it with RubyGems:

    $ gem install gosh

Then pipe it a shell script:

    $ curl https://github.com/sstephenson/gosh/raw/master/hello.sh | gosh

`gosh` will open the script in your `$EDITOR` where you can review it
for any liquids, metals, explosives, or unattended baggage. If you
accept the contents of the script, enter `YES` at the top of the file,
save it, close it, and `gosh` will run it. Otherwise, just close the
file and it won't be run.

### Extra-secure digest mode

In addition to the interactive mode described above, `gosh` can also
accept a hex digest (MD5, SHA1, SHA256, or SHA512) from the command line with the `-d` flag:

    $ curl https://github.com/sstephenson/gosh/raw/master/hello.sh | gosh -d c131b1a23b0279072cfe59bca7a69fe4a41e9ad2c825ac0deacc2e836e817193b4a4f587ee4d287e960ef416718b4d2c3531716b3f343b1d129f241f79ea2c3b

If the specified digest does not match the digest of the piped script,
`gosh` will refuse to execute it.

Hashing algorithm used is automatically determined from given digest length, and defaults to SHA512 (meaning it will fail on any length not matching 32, 40, 64, 128 characters).

### License

(The MIT License)

Copyright (c) 2011 Sam Stephenson

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
