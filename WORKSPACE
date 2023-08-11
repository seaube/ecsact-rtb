workspace(name = "ecsact_rtb")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "com_grail_bazel_toolchain",
    sha256 = "51f4baa3bad0fd7ad3a20a12462549b6a2dc329db32226a513d4c648724bb24c",
    strip_prefix = "bazel-toolchain-ceeedcc4464322e05fe5b8df3749cc02273ee083",
    url = "https://github.com/grailbio/bazel-toolchain/archive/ceeedcc4464322e05fe5b8df3749cc02273ee083.zip",
)

load("@com_grail_bazel_toolchain//toolchain:deps.bzl", "bazel_toolchain_dependencies")

bazel_toolchain_dependencies()

load("@com_grail_bazel_toolchain//toolchain:rules.bzl", "llvm_toolchain")

llvm_toolchain(
    name = "llvm_toolchain",
    cxx_standard = {"linux": "c++20"},
    distribution = "clang+llvm-15.0.6-x86_64-linux-gnu-ubuntu-18.04.tar.xz",
    llvm_version = "15.0.6",
)

load("@llvm_toolchain//:toolchains.bzl", "llvm_register_toolchains")

llvm_register_toolchains()

load("//:repositories.bzl", "ecsact_rtb_repositories")

ecsact_rtb_repositories()

load("//:workspace.bzl", "ecsact_rtb_workspace")

ecsact_rtb_workspace()

http_archive(
    name = "rules_ecsact",
    sha256 = "3db6d498a681e036dabdcc1bb7e5ee254acadae4ab2ecf19d253f824db88d5e4",
    strip_prefix = "rules_ecsact-0.3.0",
    urls = ["https://github.com/ecsact-dev/rules_ecsact/archive/refs/tags/0.3.0.tar.gz"],
)

load("@rules_ecsact//ecsact:repositories.bzl", "rules_ecsact_dependencies")

rules_ecsact_dependencies()

http_archive(
    name = "hedron_compile_commands",
    sha256 = "3cd0e49f0f4a6d406c1d74b53b7616f5e24f5fd319eafc1bf8eee6e14124d115",
    strip_prefix = "bazel-compile-commands-extractor-3dddf205a1f5cde20faf2444c1757abe0564ff4c",
    url = "https://github.com/hedronvision/bazel-compile-commands-extractor/archive/3dddf205a1f5cde20faf2444c1757abe0564ff4c.tar.gz",
)

load("@hedron_compile_commands//:workspace_setup.bzl", "hedron_compile_commands_setup")

hedron_compile_commands_setup()
