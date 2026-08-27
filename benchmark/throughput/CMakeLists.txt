# asio_from_chenshuo uses the pre-1.66 Boost.Asio API (io_service,
# resolver::iterator, strand::wrap), which was removed in newer Boost.
# It is therefore disabled by default and only builds against Boost < 1.66.
option(EVPP_BUILD_ASIO_FROM_CHENSHUO "Build the old Boost.Asio throughput benchmark from chenshuo" OFF)

if (UNIX AND EVPP_BUILD_ASIO_FROM_CHENSHUO)
    add_subdirectory(asio_from_chenshuo)
endif()

if (UNIX)
    add_subdirectory(libevent)
endif(UNIX)

add_subdirectory(evpp)
