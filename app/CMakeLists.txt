SET(JS_INCLUDE_DIRS)
SET(JS_LIBRARY_DIRS ${JSC_LIBRARY_DIRS})
SET(JS_LIBRARIES ${JSC})
SET(REDIS_CONF ${CMAKE_CURRENT_SOURCE_DIR}/redis.conf)

IF(APPLE)
	SET(OSX_LIBRARY_OUTPUT_DIR ${PROJECT_BINARY_DIR}/app/osx/libraries)
endif()

IF(APPLE)
  ADD_SUBDIRECTORY(osx)
ELSEIF(UNIX)
  ADD_SUBDIRECTORY(gtk)
ELSE()
  MESSAGE(FATAL_ERROR "Substance native is only available for OSX and UNIX systems")
ENDIF()
