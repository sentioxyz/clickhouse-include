workspace(
    name = "clickhouse-lib",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

HERMETIC_CC_TOOLCHAIN_VERSION = "v3.1.0"

http_archive(
    name = "hermetic_cc_toolchain",
    sha256 = "df091afc25d73b0948ed371d3d61beef29447f690508e02bc24e7001ccc12d38",
    urls = [
        "https://mirror.bazel.build/github.com/uber/hermetic_cc_toolchain/releases/download/{0}/hermetic_cc_toolchain-{0}.tar.gz".format(HERMETIC_CC_TOOLCHAIN_VERSION),
        "https://github.com/uber/hermetic_cc_toolchain/releases/download/{0}/hermetic_cc_toolchain-{0}.tar.gz".format(HERMETIC_CC_TOOLCHAIN_VERSION),
    ],
)

load("@hermetic_cc_toolchain//toolchain:defs.bzl", zig_toolchains = "toolchains")


# Plain zig_toolchains() will pick reasonable defaults. See
# toolchain/defs.bzl:toolchains on how to change the Zig SDK version and
# download URL.
zig_toolchains(
    host_platform_sha256 = {
        "linux-aarch64": "12be476ed53c219507e77737dbb7f2a77b280760b8acbc6ba2eaaeb42b7d145e",
        "linux-x86_64": "fdc3adf212d3ed790ea8b44293256324a90ebb5ba9647c01f4d435e2cf49dbd7",
        "macos-aarch64": "203162501abd62ec940e8785d019220d1af0a593bfa705b88675ed29ad20cdef",
        "macos-x86_64": "0c89e5d934ecbf9f4d2dea6e3b8dfcc548a3d4184a856178b3db74e361031a2b",
        "windows-x86_64": "c17df4db67ca328e77d2ff9a790a5e013d885de0667dbf25d9a1206103662d30",
    },
    url_formats = [
        "https://storage.googleapis.com/sentio-dev/zig-{host_platform}-0.11.0-dev.3312%2Bab37ab33c.tar.xz",
        "https://ziglang.org/builds/zig-{host_platform}-{version}.{_ext}",
        "https://mirror.bazel.build/ziglang.org/builds/zig-{host_platform}-{version}.{_ext}",
    ],
    version = "0.11.0-dev.3312+ab37ab33c",
)

# zig_register_all_toolchains
# use: bazel query @zig_sdk//toolchain/...
register_toolchains(
    # "@zig_sdk//toolchain:linux_amd64_gnu.2.28",
    #    "@zig_sdk//toolchain:linux_arm64_gnu.2.28",
    #    "@zig_sdk//toolchain:darwin_amd64",
       "@zig_sdk//toolchain:darwin_arm64",
)

