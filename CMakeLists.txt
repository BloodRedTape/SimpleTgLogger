cmake_minimum_required (VERSION 3.8)

project ("SimpleTgUtils")

add_library(SimpleTgUtils 
	"./sources/tg_logger.cpp" 
	"./sources/tg_backup.cpp"
	"./sources/tg_bot.cpp"
)
target_link_libraries(SimpleTgUtils PUBLIC TgBot PUBLIC bsl PUBLIC miniz)
target_include_directories(SimpleTgUtils PUBLIC "./include")
target_precompile_headers(SimpleTgUtils 
	PUBLIC "./include/simple/tg_logger.hpp" 
	PUBLIC "./include/simple/tg_backup.hpp"
	PUBLIC "./include/simple/tg_bot.hpp"
)
target_compile_features(SimpleTgUtils PRIVATE cxx_std_17)