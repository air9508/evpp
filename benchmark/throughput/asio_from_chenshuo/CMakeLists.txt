# Boost.System is header-only since Boost 1.69, so only the thread component
# (libboost_thread) needs to be found and linked here.
find_package(Boost 1.53 REQUIRED COMPONENTS thread)

add_executable(benchmark_tcp_asio_client client.cpp)
target_link_libraries(benchmark_tcp_asio_client ${Boost_THREAD_LIBRARY} pthread)

add_executable(benchmark_tcp_asio_server server.cpp)
target_link_libraries(benchmark_tcp_asio_server ${Boost_THREAD_LIBRARY} pthread)

