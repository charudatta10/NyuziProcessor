#
# Copyright 2018 Jeff Bush
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

project(libos-kern)
include(nyuzi)

include_directories($<TARGET_PROPERTY:c,INCLUDE_DIRECTORIES>)
include_directories($<TARGET_PROPERTY:kernel,INCLUDE_DIRECTORIES>)
include_directories(..)

add_nyuzi_library(os-kern
    keyboard.c
    schedule.c
    vga.c
    misc.c
    performance_counters.c
    syscall.h
    fs.c
    nyuzi.c
    sbrk.c
    uart.c
    crt0.s)

target_include_directories (os-kern PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/..)
