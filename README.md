This repository builds with Bazel 0.28.1, but not with Bazel 0.29.0rc6

```
$ bazel build //...
INFO: Analyzed 3 targets (45 packages loaded, 1235 targets configured).
INFO: Found 3 targets...
ERROR: /Users/gustav/src/bazel-0-29-incompat-repro/src/BUILD:22:1: Action src/service_java_grpc-proto-gensrc.jar failed (Exit 1) protoc failed: error executing command bazel-out/host/bin/external/com_google_protobuf/protoc '--plugin=protoc-gen-grpc-java=bazel-out/host/bin/external/io_grpc_grpc_java/compiler/grpc_java_plugin' ... (remaining 4 argument(s) skipped)

Use --sandbox_debug to see verbose messages from the sandbox
google/protobuf/timestamp.proto: File not found.
src/service.proto:3:1: Import "google/protobuf/timestamp.proto" was not found or had errors.
src/service.proto:6:3: "google.protobuf.Timestamp" is not defined.
INFO: Elapsed time: 4.587s, Critical Path: 0.12s
INFO: 2 processes: 2 darwin-sandbox.
FAILED: Build did NOT complete successfully
```
