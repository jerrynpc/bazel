licenses(["restricted"])  # GNU GPL v2

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
    visibility = [
        "//third_party:__pkg__",
        "//src:__pkg__"
    ],
)

filegroup(
    name = "embedded_tools",
    srcs = [
        "BUILD.tools",
        "proguard5.3.3/docs/GPL.html",
        "proguard5.3.3/lib/proguard.jar",
    ],
    visibility = ["//src:__pkg__"],
)

genrule(
    name = "proguard_zip",
    srcs = [
        "proguard5.3.3/docs/GPL.html",
        "proguard5.3.3/lib/proguard.jar",
    ],
    outs = ["proguard.zip"],
    cmd = "$(location //src:zip_files) third_party/java/proguard $@ $(SRCS)",
    tools = ["//src:zip_files"],
    visibility = ["//src:__pkg__"],
)

# TODO(iirina): Remove this target after #8311 is completley merged.
genrule(
    name = "proguard_srcs_zip",
    srcs = [":srcs"],
    outs = ["proguard_srcs.zip"],
    cmd = "$(location //src:zip_files) third_party/java/proguard $@ $(SRCS)",
    tools = ["//src:zip_files"],
    visibility = ["//src:__pkg__"],
)