"""BUILD definition for the formatter binary

This is in its own package because it has so many loading-time symbols,
we don't want to trigger eager fetches of these for builds that don't want to run format.
"""

load("@aspect_rules_lint//format:defs.bzl", "format_multirun")

package(default_visibility = ["//:__subpackages__"])

format_multirun(
    name = "format",
    cc = "@llvm_toolchain_llvm//:bin/clang-format",
    starlark = "@buildifier_prebuilt//:buildifier",
)
