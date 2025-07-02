# Copyright 2019-2024 Lawrence Livermore National Security, LLC and other YGM
# Project Developers. See the top-level COPYRIGHT file for details.
#
# SPDX-License-Identifier: MIT

add_ygm_executable(read_json_example)

add_ygm_executable(read_trace)

if (Arrow_FOUND AND Parquet_FOUND)
    add_ygm_executable(parquet_tools)
    link_arrow_parquet(parquet_tools)
    file(COPY ./parquet_tools_subcmd.json DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
endif ()