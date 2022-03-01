# Problems with navigating in audio files

I've experienced issues when trying to skip around in longer audio files using the `<audio>` element.

It doesn't matter whether skipping is done via the `controls` or via setting `currentTime` via JavaScript, after all both of these likely do the same.

The problem here is that the browser requests parts of files using the `Range` headers.
Chrome does this even when it has part of the file buffered, Firefox behaves slightly better as it loads the file.

- https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Ranges
- https://medium.com/@vishal1909/how-to-handle-partial-content-in-node-js-8b0a5aea216
- https://stackoverflow.com/a/9565178/1262751

And the simple `python -m http.server` I've been using for serving the content files does not support Ranges.

The nice node based `http-server` does support these however, so everything works fine when using that.
It's just strange that it was so hard to find out which server supports that, I almost ended up rolling something from scratch.
Thankfully, it was linked from this [README](https://github.com/danvk/RangeHTTPServer/commit/c5d19c8118bb495f52414906fc1064624f890fe8)

So...

# Solution

Use `npx http-server`, this supports Range requests and will therefore allow skipping through audio at will.

