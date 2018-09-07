# Local libraries
include_directories(${LandmarkDetector_SOURCE_DIR}/include)

add_executable(FaceLandmarkVidZmq FaceLandmarkVidZmq.cpp)
# include_directories(../../lib/local/LandmarkDetector/include)
# include_directories(../../lib/local/FaceAnalyser/include)		
target_link_libraries(FaceLandmarkVidZmq LandmarkDetector)
target_link_libraries(FaceLandmarkVidZmq FaceAnalyser)
target_link_libraries(FaceLandmarkVidZmq GazeAnalyser)
target_link_libraries(FaceLandmarkVidZmq Utilities)

include_directories(cppzmq)
target_link_libraries(FaceLandmarkVidZmq zmq)

# target_link_libraries(FaceLandmarkVidZmq dlib)

# target_link_libraries(FaceLandmarkVidZmq ${OpenCV_LIBS} ${Boost_LIBRARIES} ${TBB_LIBRARIES})

install (TARGETS FaceLandmarkVidZmq DESTINATION bin)
