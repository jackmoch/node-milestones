# Find Words

There are several advanced libraries for using Node.js streams. We will explore
the event-stream module.

## Requirements

The purpose of this program is to list English words that begin with a search
term.

Create a JavaScript file to act as a Node.js program named `10.js`. This program
should read a file `/usr/share/dict/words`. This file is used by the operating
system for spell checking. If this file does not exist on your system, you can
use one from GitHub such as: https://github.com/atebits/Words

An argument to this program should be used as a search term. The case of the
search term should not matter. If no argument is passed, respond only with a
simple [usage message](https://en.wikipedia.org/wiki/Usage_message).

Limit the results to only ten words and case should not matter.

Start with a `createReadStream` and use event-stream's `split` and `map`
methods. You will also create your own `Transform` stream stored as `limitTen`.
This `Transform` should be a limiter before sending the results to stdout.

```js
createReadStream(path)
    .pipe(?)
    .pipe(?)
    .pipe(limitTen)
    .pipe(process.stdout)
```

Expected:

```bash
$ ./10.js
Usage: 10.js [searchterm]
$ ./10.js app
Usage: 10.js [searchterm]
Appalachia
Appalachian
appall
appalling
appallingly
appallment
appalment
appanage
appanagist
apparatus
$ ./10.js JAVA
Java
Javahai
javali
Javan
Javanee
Javanese
```

## Bonus

-   Optionally accept the wordlist as stdin with no argument given
    `cat file | ./10.js`
-   Write another `Transform` stored as `hackerType` to stream each letter to
    the terminal every 50 ms
-   Try another popular stream library: Highland.js
-   If you search for something at the beginning of the alphabet, like 'a' or
    'aal', there is a slight delay before the program exits while the stream
    continues through the wordlist even though the app has printed the 10
    results or will not find any more results. End the stream as soon as
    possible to remove this delay.

[Words (Unix)](https://en.wikipedia.org/wiki/Words_(Unix))
[event-stream](https://github.com/dominictarr/event-stream)
[Highland.js](http://highlandjs.org/)
