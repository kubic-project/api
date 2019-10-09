# Copyright 2018 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################
#

proto_library(
    name = "mixer_api_protos_lib",
    srcs = glob(
        [
            "mixer/v1/*.proto",
        ],
    ),
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_gogo_protobuf//:gogo_proto",
        "@googleapis//:rpc_status_protos_lib",
        "@com_google_protobuf//:duration_proto",
        "@com_google_protobuf//:timestamp_proto",
    ],
)

cc_proto_library(
    name = "mixer_api_cc_proto",
    deps = [
        ":mixer_api_protos_lib",
    ],
    visibility = ["//visibility:public"],
)

proto_library(
    name = "mixer_client_config_proto_lib",
    srcs = glob(
        [
        "mixer/v1/config/client/*.proto",
        ],
    ),
    visibility = ["//visibility:public"],
    deps = [
        ":mixer_api_protos_lib",
        "@com_github_gogo_protobuf//:gogo_proto",
        "@com_google_protobuf//:duration_proto",
    ],
)

cc_proto_library(
    name = "mixer_client_config_cc_proto",
    visibility = ["//visibility:public"],
    deps = [
        ":mixer_client_config_proto_lib",
    ],
)

proto_library(
    name = "authentication_policy_config_proto_lib",
    srcs = glob(
        ["envoy/config/filter/http/authn/v2alpha1/*.proto",
         "authentication/v1alpha1/*.proto",
         "common/v1alpha1/*.proto",
        ],
    ),
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_gogo_protobuf//:gogo_proto",
    ],
)

cc_proto_library(
    name = "authentication_policy_config_cc_proto",
    visibility = ["//visibility:public"],
    deps = [
        ":authentication_policy_config_proto_lib",
    ],
)

proto_library(
    name = "jwt_auth_config_proto_lib",
    srcs = glob(
        ["envoy/config/filter/http/jwt_auth/v2alpha1/*.proto", ],
    ),
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_gogo_protobuf//:gogo_proto",
        "@com_google_protobuf//:duration_proto",
    ],
)

cc_proto_library(
    name = "jwt_auth_config_cc_proto",
    visibility = ["//visibility:public"],
    deps = [
        ":jwt_auth_config_proto_lib",
    ],
)

proto_library(
    name = "tcp_cluster_rewrite_config_proto_lib",
    srcs = glob(
        ["envoy/config/filter/network/tcp_cluster_rewrite/v2alpha1/*.proto", ],
    ),
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_gogo_protobuf//:gogo_proto",
    ],
)

cc_proto_library(
    name = "tcp_cluster_rewrite_config_cc_proto",
    visibility = ["//visibility:public"],
    deps = [
        ":tcp_cluster_rewrite_config_proto_lib",
    ],
)

filegroup(
    name = "global_dictionary_file",
    srcs = ["mixer/v1/global_dictionary.yaml"],
    visibility = ["//visibility:public"],
)
