package(default_visibility = ["//visibility:public"])

proto_library(
    name = "service_proto",
    srcs = [
        "service.proto",
    ],
    deps = [
        "@com_google_protobuf//:timestamp_proto",
    ],
)

load("@com_google_googleapis_imports//:imports.bzl", "java_grpc_library")

java_proto_library(
    name = "service_java_proto",
    deps = [
        ":service_proto",
    ],
)

java_grpc_library(
    name = "service_java_grpc",
    srcs = [":service_proto"],
    deps = [":service_java_proto"],
)
