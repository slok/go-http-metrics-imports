# go-http-metrics-imports

This repository shows how [go-http-metrics] doesn't import all the compatible frameworks when is used.

## How

[go-http-metrics] library uses independent packages for each of the compatible frameworks. This way, importing the library
doesn't mean importing all the supported libraries, just the ones that you want and imported explicitly.

## Examples

In this package you have 3 go apps.

- [`std`](std/) uses [go-http-metrics] with standard library (no frameworks).
- [`gin`](gin/) uses [go-http-metrics] with gin framework.
- [`echo`](echo/) uses [go-http-metrics] with echo framework.

Check `go.mod` files to see the explicit imports.

Now Lets use `go list -json` so Go tell us what are the subimports on each of the apps so we can see the imported libraries by [go-http-metrics].

- [`std`](std/golist.json)
- [`gin`](gin/golist.json)
- [`echo`](echo/golist.json)

As it can be seen in `Deps` field, the imports of `std`, `gin` and `echo` are different and match with the dependencies of the framework
that they are using.

[go-http-metrics]: https://github.com/slok/go-http-metrics
