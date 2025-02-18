![https://github.com/twitchtv/twirp/blob/main/logo.png](https://github.com/twitchtv/twirp/blob/main/logo.png)

# Twirpd Protoc Plugin
Protoc plugin for generating Twirp clients for Dart.

Meant to be used by [twirpd](https://github.com/cheddar-me/twirpd) package in Dart client apps. Check [twirpd](https://github.com/cheddar-me/twirpd) for more docs.

## Getting started

### Install Protoc
Make sure you have protoc or buf installed.

**Mac:**
```
brew install protobuf
```
**Linux:**
```
apt-get install protobuf
```

### Code Generation
First you need to install `twirpd-protoc-plugin` by running:
```
dart pub global activate twirpd-protoc-plugin
```
Then you can use `protoc` command to generate all needed files:
```
protoc \
  --twirpd_out={PATH_TO_OUTPUT_DIR} \
  -I {PATH_TO_DIR_WITH_PROTOS} {PROTO_FILE_NAMES}
```
For example:
```
protoc \
  --twirpd_out=lib/src/generated \
  -I proto my_service.proto
```

If you are using external Google proto messages, you can include them in the command, for example:
```
protoc \
  --twirpd_out=lib/src/generated \
  -I proto my_service.proto google/protobuf/timestamp.proto
```

This should generate all the code you need.

## Using it

Check [twirpd](https://github.com/cheddar-me/twirpd) for more docs on how to use generated classes.


Made with 💛 at [Cheddar](https://cheddar.me/).
