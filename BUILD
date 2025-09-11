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
    gazelle = "@multitool//tools/gazelle",
)
