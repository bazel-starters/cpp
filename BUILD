"""Targets in the repository root"""

# We prefer BUILD instead of BUILD.bazel
# gazelle:build_file_name BUILD

load("@gazelle//:def.bzl", "gazelle")

exports_files(
    [
        ".clang-tidy",
    ],
    visibility = ["//:__subpackages__"],
)

gazelle(
    name = "gazelle",
    env = {
        "ENABLE_LANGUAGES": ",".join([
            "starlark",
            "proto",
            "cc",
        ]),
    },
    gazelle = "@multitool//tools/gazelle",
)
