# Tools and utilities that aid in XLA development and usage.

licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//tensorflow/compiler/xla:internal"])

# Filegroup used to collect source files for dependency checking.
filegroup(
    name = "c_srcs",
    data = glob([
        "**/*.cc",
        "**/*.h",
    ]),
    visibility = ["//tensorflow/compiler/xla:internal"],
)

cc_binary(
    name = "hex_floats_to_packed_literal",
    srcs = ["hex_floats_to_packed_literal.cc"],
    deps = [
        "//tensorflow/compiler/xla:types",
        "//tensorflow/core:framework_internal",
        "//tensorflow/core:lib",
        "//tensorflow/core:lib_internal",
    ],
)

cc_library(
    name = "dumped_computation_to_graphviz_library",
    srcs = ["dumped_computation_to_graphviz.cc"],
    deps = [
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/legacy_flags:debug_options_flags",
        "//tensorflow/compiler/xla/service",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "dumped_computation_to_graphviz",
    deps = [
        ":dumped_computation_to_graphviz_library",
    ],
)

cc_binary(
    name = "show_signature",
    srcs = ["show_signature.cc"],
    deps = [
        "//tensorflow/compiler/xla:shape_util",
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

cc_library(
    name = "replay_computation_library",
    srcs = ["replay_computation.cc"],
    deps = [
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla:shape_util",
        "//tensorflow/compiler/xla:status_macros",
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:global_data",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/client/lib:testing",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:framework_internal",
        "//tensorflow/core:lib",
    ],
    alwayslink = True,
)

cc_binary(
    name = "replay_computation_cpu",
    deps = [
        ":replay_computation_library",
        "//tensorflow/compiler/xla/service:cpu_plugin",
    ],
)

cc_binary(
    name = "replay_computation_gpu",
    deps = [
        ":replay_computation_library",
        "//tensorflow/compiler/xla/service:gpu_plugin",
    ],
)

cc_binary(
    name = "replay_computation_interpreter",
    deps = [
        ":replay_computation_library",
        "//tensorflow/compiler/xla/service:interpreter_plugin",
    ],
)

cc_binary(
    name = "show_literal",
    srcs = ["show_literal.cc"],
    deps = [
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "convert_computation",
    srcs = ["convert_computation.cc"],
    deps = [
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "show_text_literal",
    srcs = ["show_text_literal.cc"],
    deps = [
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:text_literal_reader",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "dumped_computation_to_text",
    srcs = ["dumped_computation_to_text.cc"],
    deps = [
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/service",
        "//tensorflow/compiler/xla/service:computation_tracker",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "dumped_computation_to_operation_list",
    srcs = ["dumped_computation_to_operation_list.cc"],
    deps = [
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/service",
        "//tensorflow/compiler/xla/service:hlo",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

cc_binary(
    name = "dumped_computation_to_tf_graphdef",
    srcs = ["dumped_computation_to_tf_graphdef.cc"],
    deps = [
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla:types",
        "//tensorflow/compiler/xla/client",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:computation",
        "//tensorflow/compiler/xla/client:local_client",
        "//tensorflow/compiler/xla/legacy_flags:debug_options_flags",
        "//tensorflow/compiler/xla/service",
        "//tensorflow/compiler/xla/service:hlo_graph_dumper",
        "//tensorflow/compiler/xla/service:session_proto",
        "//tensorflow/core:lib",
    ],
)

# -----------------------------------------------------------------------------

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
