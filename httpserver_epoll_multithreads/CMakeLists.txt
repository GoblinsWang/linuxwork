# cmake最低版本限定
cmake_minimum_required(VERSION 3.0)

# 项目名称
project(NETWORK_CODING)

# 设置编译的一些参数
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

# 编译类型选择，debug or release
set(CMAKE_BUILD_TYPE Debug)

# 包含头文件所在的目录
include_directories(${CMAKE_SOURCE_DIR}/include)

# 定义SRC变量，其值为当前目录下所有的源代码文件
aux_source_directory(./src SRC)

# 生成可执行文件
add_executable(tcp_server_main tcp_server_main.cpp  ${SRC})
add_executable(http_server_main http_server_main.cpp  ${SRC})
target_link_libraries(tcp_server_main pthread)
target_link_libraries(http_server_main pthread)



