
add_executable(HuygensOnSpeedApp HuygensOnSpeed.cpp)

if ( UNIX )
	if (APPLE)
		target_link_libraries( HuygensOnSpeedApp HuygensOnSpeed ${GLUT_LIBRARIES} ${GLEW_LIBRARY} "-framework AGL" "-framework OpenGL")
	else ()
   		target_link_libraries( HuygensOnSpeedApp HuygensOnSpeed glut ${GLEW_LIBRARIES} GL)
   	endif ()
else ()
   if (CMAKE_CL_64)
      target_link_libraries( HuygensOnSpeedApp HuygensOnSpeed freeglut glew64)
   else ()
      target_link_libraries( HuygensOnSpeedApp HuygensOnSpeed freeglut glew32)
   endif ()
endif ()
