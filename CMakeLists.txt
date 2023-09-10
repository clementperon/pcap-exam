cmake_minimum_required(VERSION 3.12)

project(pcap_exam LANGUAGES C)

include(FetchContent)

FetchContent_Declare(
  libpcap
  GIT_REPOSITORY https://github.com/clementperon/libpcap.git
  GIT_TAG        a43dbc2ff975964da8e680e6835bb3b6b89cc8db # fix-external-cmake
)

FetchContent_MakeAvailable(libpcap)

add_executable(pcap_exam pcap_exam.c)

target_link_libraries(pcap_exam PRIVATE pcap)
