load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

########################################
### rules_dotnet
########################################

http_archive(
    name = "rules_dotnet",
    sha256 = "b422380a8842ad68eca92f9f91d65d9199a5366b257a7820c5624b67611c0f4d",
    strip_prefix = "rules_dotnet-0.9.0",
    url = "https://github.com/bazelbuild/rules_dotnet/releases/download/v0.9.0/rules_dotnet-v0.9.0.tar.gz",
)

load(
    "@rules_dotnet//dotnet:repositories.bzl",
    "dotnet_register_toolchains",
    "rules_dotnet_dependencies",
)

rules_dotnet_dependencies()

dotnet_register_toolchains("dotnet", "7.0.101")

load("@rules_dotnet//dotnet:rules_dotnet_nuget_packages.bzl", "rules_dotnet_nuget_packages")

rules_dotnet_nuget_packages()

########################################
### paket2bazel
########################################

load("@rules_dotnet//dotnet:paket2bazel_dependencies.bzl", "paket2bazel_dependencies")

paket2bazel_dependencies()

load("//:main.bzl", "Main")

Main()