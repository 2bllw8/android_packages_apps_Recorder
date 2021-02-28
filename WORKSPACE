#
# Copyright (C) 2021 The LineageOS Project
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Android
ANDROID_API_LEVEL = 30
ANDROID_BUILD_TOOLS = "30.0.3"
# Rules
RULES_JVM_EXTERNAL_TAG = "4.0"
RULES_JVM_EXTERNAL_SHA = "31701ad93dbfe544d597dbe62c9a1fdd76d81d8a9150c2bf1ecf928ecdf97169"
# Maven
ANNOTATION_VERSION = "1.1.0"
APPCOMPAT_VERSION = "1.3.0"
CONSTRAINT_LAYOUT_VERSION = "2.1.0-beta02"
COORDINATOR_LAYOUT_VERSION = "1.1.0"
CORE_VERSION = "1.3.2"
DYNAMIC_ANIMATION_VERSION = "1.0.0"
MATERIAL_VERSION = "1.3.0"
RECYCLERVIEW_VERSION = "1.1.0"

android_sdk_repository(
    name = "androidsdk",
    api_level = ANDROID_API_LEVEL,
    build_tools_version = ANDROID_BUILD_TOOLS,
)

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "androidx.annotation:annotation:%s" % ANNOTATION_VERSION,
        "androidx.appcompat:appcompat:%s" % APPCOMPAT_VERSION,
        "androidx.constraintlayout:constraintlayout:%s" % CONSTRAINT_LAYOUT_VERSION,
        "androidx.coordinatorlayout:coordinatorlayout:%s" % COORDINATOR_LAYOUT_VERSION,
        "androidx.core:core:%s" % CORE_VERSION,
        "androidx.dynamicanimation:dynamicanimation:%s" % DYNAMIC_ANIMATION_VERSION,
        "androidx.recyclerview:recyclerview:%s" % RECYCLERVIEW_VERSION,
        "com.google.android.material:material:%s" % MATERIAL_VERSION,
    ],
    fetch_sources = True,
    repositories = [
        "https://maven.google.com",
    ],
)
