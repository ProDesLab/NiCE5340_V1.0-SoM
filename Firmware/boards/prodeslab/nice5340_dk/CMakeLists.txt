# Copyright (c) 2024 Kelly Helmut Lord
# SPDX-License-Identifier: Apache-2.0

if ((CONFIG_BOARD_NICE5340_DK_NRF5340_CPUAPP OR CONFIG_BOARD_NICE5340_DK_NRF5340_CPUAPP_NS)
    AND CONFIG_BOARD_ENABLE_CPUNET)
zephyr_library()
zephyr_library_sources(nice5340_dk_nrf5340_cpunet_reset.c)

if (CONFIG_BUILD_WITH_TFM)
  zephyr_library_include_directories(
    $<TARGET_PROPERTY:tfm,TFM_BINARY_DIR>/api_ns/interface/include
  )
endif()

endif()
