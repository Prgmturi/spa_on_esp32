idf_component_register(SRCS "main.c" "rest_server.c" "access_point.c" "access_point.h"
                    INCLUDE_DIRS ".") 
                    
if(CONFIG_EXAMPLE_WEB_DEPLOY_SF)
    spiffs_create_partition_image(www ../data FLASH_IN_PROJECT)
    set(WEB_SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../data")
    if(EXISTS ${WEB_SRC_DIR})
    #spiffs_create_partition_image(www ${WEB_SRC_DIR})
    else()
        message(FATAL_ERROR "${WEB_SRC_DIR} doesn't exit. Please run 'npm run build' in ${WEB_SRC_DIR}")
    endif()
endif()