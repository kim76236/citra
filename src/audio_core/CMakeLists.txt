set(SRCS
            audio_core.cpp
            codec.cpp
            hle/dsp.cpp
            hle/filter.cpp
            hle/pipe.cpp
            interpolate.cpp
            sink_details.cpp
            )

set(HEADERS
            audio_core.h
            codec.h
            hle/common.h
            hle/dsp.h
            hle/filter.h
            hle/pipe.h
            interpolate.h
            null_sink.h
            sink.h
            sink_details.h
            )

include_directories(../../externals/soundtouch/include)

create_directory_groups(${SRCS} ${HEADERS})

add_library(audio_core STATIC ${SRCS} ${HEADERS})
target_link_libraries(audio_core SoundTouch)
