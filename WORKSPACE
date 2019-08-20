load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")

# Lateset version
maybe(
    http_archive,
    name = "bazel_skylib",
    url = "https://github.com/bazelbuild/bazel-skylib/releases/download/0.9.0/bazel_skylib-0.9.0.tar.gz",
    sha256 = "1dde365491125a3db70731e25658dfdd3bc5dbdfd11b840b3e987ecf043c7ca0",
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")
bazel_skylib_workspace()

# Lateset version
http_archive(
    name = "com_google_protobuf",
    sha256 = "c90d9e13564c0af85fd2912545ee47b57deded6e5a97de80395b6d2d9be64854",
    strip_prefix = "protobuf-3.9.1",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/v3.9.1.zip"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

maven_jar(
    name = "error_prone_annotations_maven",
    artifact = "com.google.errorprone:error_prone_annotations:2.3.3",
    sha1 = "42aa5155a54a87d70af32d4b0d06bf43779de0e2",
)

bind(
    name = "error_prone_annotations",
    actual = "@error_prone_annotations_maven//jar",
)

# Latest version
http_archive(
    name = "com_google_googleapis",
    sha256 = "5a9106cdb5ebecae4a7e0c2f5b38f6c57a47cc3ab1a45e427df0b0b44e612e09",
    strip_prefix = "googleapis-4bb50a3e4c8d49d1cec1a98434cccaeaec55a886",
    urls = ["https://github.com/googleapis/googleapis/archive/4bb50a3e4c8d49d1cec1a98434cccaeaec55a886.zip"],
)

load("@com_google_googleapis//:repository_rules.bzl", "switched_rules_by_language")

switched_rules_by_language(
    name = "com_google_googleapis_imports",
    grpc = True,
    java = True,
)

# Latest version
http_archive(
    name = "build_stack_rules_proto",
    sha256 = "85ccc69a964a9fe3859b1190a7c8246af2a4ead037ee82247378464276d4262a",
    strip_prefix = "rules_proto-d9a123032f8436dbc34069cfc3207f2810a494ee",
    urls = ["https://github.com/stackb/rules_proto/archive/d9a123032f8436dbc34069cfc3207f2810a494ee.tar.gz"],
)

load("@build_stack_rules_proto//:deps.bzl", "io_grpc_grpc_java")

io_grpc_grpc_java()

load("@io_grpc_grpc_java//:repositories.bzl", "grpc_java_repositories")

grpc_java_repositories(omit_com_google_protobuf = True)
