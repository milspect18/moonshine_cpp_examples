cmake_minimum_required(VERSION 3.19)
project(moonshipe_cpp_examples LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include external dependencies
include(FetchContent)

message(STATUS "Fetching audiofile @ https://github.com/adamstark/AudioFile.git")

set(FETCHCONTENT_QUIET FALSE)
set(AudioFileVersion "1.1.2")

FetchContent_Declare(
    audiofile
    GIT_REPOSITORY  https://github.com/adamstark/AudioFile.git
    GIT_TAG         ${AudioFileVersion}
    GIT_PROGRESS    TRUE
)

FetchContent_MakeAvailable(audiofile)

## Add moonshine_cpp
message(STATUS "Fetching moonshine_cpp @ https://github.com/milspect18/moonshine_cpp.git")

set(FETCHCONTENT_QUIET FALSE)

FetchContent_Declare(
    moonshine_cpp
    GIT_REPOSITORY  https://github.com/milspect18/moonshine_cpp.git
    GIT_TAG         main
    GIT_PROGRESS    TRUE
)

FetchContent_MakeAvailable(moonshine_cpp)

add_executable(moonshine_transcribe_wav moonshine_transcribe_wav.cpp)

target_include_directories(moonshine_transcribe_wav PRIVATE
    ${audiofile_SOURCE_DIR}
)

target_link_libraries(moonshine_transcribe_wav PRIVATE
    moonshine::moonshine_cpp
)