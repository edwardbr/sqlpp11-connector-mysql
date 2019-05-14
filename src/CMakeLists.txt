add_library(${PROJECT_NAME}
		connection.cpp
		prepared_statement.cpp
		char_result.cpp
		bind_result.cpp
		detail/connection_handle.cpp)

target_link_libraries(${PROJECT_NAME} date_interface sqlpp11 MySQL::libmysql)		

if (APPLE)
	target_link_libraries(${PROJECT_NAME} "${Boost_THREAD_LIBRARY}")
endif()

install(TARGETS ${PROJECT_NAME} DESTINATION lib)

