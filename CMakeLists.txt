cmake_minimum_required(VERSION 3.15)

project(cdc LANGUAGES C CXX ASM)

find_bsp(ID com.sysprogs.project_importers.stm32.cubemx
	SOURCE_PROJECT cdc.ioc)

bsp_compile_flags("")
add_bsp_based_executable(NAME cdc
	GENERATE_BIN
	GENERATE_MAP)
target_link_libraries(cdc PRIVATE "-specs=nano.specs -specs=nosys.specs")
target_compile_options(cdc PUBLIC "")
