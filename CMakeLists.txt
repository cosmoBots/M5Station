idf_component_register(
    SRC_DIRS 
        "src" "src/utility" "src/Fonts"
    INCLUDE_DIRS
        "src" "$ENV{IDF_PATH}/components/bt/host/bluedroid/api/include/api"
    REQUIRES
        arduino
    REQUIRED_IDF_TARGETS        
        esp32        
)

set(DEFINITIONS "ESP32")

if (CONFIG_M5STACK_BASIC OR CONFIG_M5STACK_GRAY OR CONFIG_M5STACK_FIRE)
    list(APPEND DEFINITIONS "M5STACK")
endif (CONFIG_M5STACK_BASIC OR CONFIG_M5STACK_GRAY OR CONFIG_M5STACK_FIRE)

if(CONFIG_M5STACK_FIRE)
    list(APPEND DEFINITIONS "M5STACK_FIRE")
endif(CONFIG_M5STACK_FIRE)

# Txinto had to remove this
# target_compile_definitions(${COMPONENT_NAME} PUBLIC ${DEFINITIONS})

