# load("@rules_cc//cc:defs.bzl", "cc_import", "cc_library")

cc_import(
    name = "lib_gdal_private",
    hdrs = glob(["include/gdal/*.h"]),
    shared_library = "lib/libgdal.so",
    # static_library = "lib/libgdal.a",
    visibility = ["//visibility:public"],
)

cc_library(
    name = "lib_gdal",
    hdrs = glob(["include/gdal/*.h"]),
    includes = [
        "include",
        "include/gdal",
        "include/ogr",
    ],
    linkopts = [
        "-pthread",
        # "-ld",
        # "-libxerces-c-3.2",
    ],
    visibility = ["//visibility:public"],  # Note that the cc_import is not necessarily public.
    deps = [":lib_gdal_private"],
)
