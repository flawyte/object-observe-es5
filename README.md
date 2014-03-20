# ES5 Object.observe polyfill
[After taking inspiration from eligrey](https://gist.github.com/eligrey/384583), I've decided to implement an Object.observe polyfill that matches spec almost 100% (see below for differences). If you're not familiar with the API, [HTML5 Rocks](http://updates.html5rocks.com/2012/11/Respond-to-change-with-Object-observe) has a good writeup on it.

## Differences
Though this polyfill has the majority of functionality that I anticipate people to use, there are a few differences.

### Missing Features:
- Doesn't work with Arrays. This might be addressed in the future.
- Only supports the `add`, `delete`, and `update` events on an object. The Spec implements other low-level events, such as `preventExtensions` and `frozen`. These may be addressed at a later date.

### API Differences
- Deleted properties don't have the `oldValue` parameter in the change payload.
- Currently, the changes payload is only a single-element array. This will be updated in the future.

## Intended Uses
The most obvious use is for data-binding. When a user, or another 3rd party, makes changes to an object there can now be handlers in place for how to respond. This brings an incredible amount of automation and power to applications.

## Support
This will work in any browser that has implemented ES5. To summarize: IE9+, Chrome 6+, FireFox 4+, Safari 5+, and Node.

## License
The MIT License (MIT)

Copyright (c) 2014 Joel Griffith

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.