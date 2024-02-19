
# Update so that it actually builds.

At the moment (2024/02/19) the hpack-convert won't build with the latest GHC (such as 9.8.1, ghc-9.4.8), and the [official repository](https://github.com/yamadapc/hpack-convert) doesn't provide a windows binary release. This prevents you from using hpack-convert on windows.

For ease of use, a windows binary is provided here.

It built on windows (lts-15.5) successfully and it works well, using @kindaro 's fork: https://github.com/kindaro/hpack-convert/commit/fa98909f18992713fba82d2033e04fdedb58592a

Related links:

https://github.com/yamadapc/hpack-convert/issues/18

https://github.com/yamadapc/hpack-convert/pull/16

---

# hpack-convert
[![Build Status](https://travis-ci.org/yamadapc/hpack-convert.svg?branch=hpack-convert)](https://travis-ci.org/yamadapc/hpack-convert)
- - -
Convert Cabal manifests into [hpack's package.yamls](https://github.com/sol/hpack).

## Installing from source
```
git clone https://github.com/yamadapc/hpack-convert
cd hpack-convert
stack install
```

## Download a pre-built binary
- [OSX](https://github.com/yamadapc/hpack-convert/releases/download/v0.14.4/hpack-convert_x86_64-osx.tar.gz)
- [Linux 64-bits (_Requires **libgmp**_)](https://github.com/yamadapc/hpack-convert/releases/download/v0.14.4/hpack-convert_x86_64-linux.tar.gz)

## Usage
```bash
# Inside a directory with a .cabal file, run:
hpack-convert
# This will convert your .cabal file into a `package.yaml`
```

## Using the web-service without installing anything
There's a simple web-service running `hpack-convert` on a free Heroku dyno, if
it's awake, this command should convert your cabal file:
```bash
curl -F "cabalfile=@./`echo *.cabal`" https://hpack-convert.herokuapp.com
```
_Source-code at https://github.com/yamadapc/hpack-convert-api_

## License
MIT
