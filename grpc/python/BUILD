#
# GRAKN.AI - THE KNOWLEDGE GRAPH
# Copyright (C) 2019 Grakn Labs Ltd
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as
# published by the Free Software Foundation, either version 3 of the
# License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#

package(default_visibility = ["//visibility:public"])
load("@stackb_rules_proto//python:python_grpc_compile.bzl", "python_grpc_compile")
load("@graknlabs_bazel_distribution//pip:rules.bzl", "python_repackage")

python_grpc_compile(
    name = "protocol_src",
    deps = [
        "//keyspace:keyspace-proto",
        "//session:session-proto",
        "//session:answer-proto",
        "//session:concept-proto",
    ],
    visibility = ["//visibility:public"]
)


python_repackage(
    name = "protocol_pkg",
    src = ":protocol_src",
    package = "grakn_protocol"
)


py_library(
    name = "protocol",
    srcs = ["protocol_pkg"],
    imports = ["../../grpc/python"]
)
