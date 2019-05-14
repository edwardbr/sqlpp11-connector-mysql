add_library(sqlpp11-connector-mysql
		connection.cpp
		prepared_statement.cpp
		char_result.cpp
		bind_result.cpp
		detail/connection_handle.cpp)

target_link_libraries(sqlpp11-connector-mysql INTERFACE date_interface sqlpp11)		

if (APPLE)
	target_link_libraries(sqlpp11-connector-mysql "${Boost_THREAD_LIBRARY}")
endif()

install(TARGETS sqlpp11-connector-mysql DESTINATION lib)

