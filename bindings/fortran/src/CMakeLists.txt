mgis_library(MFrontGenericInterface-fortran SHARED
  mgis_fortran_utilities.f95
  mgis.f95
  mgis_behaviour.f95)
set_target_properties(MFrontGenericInterface-fortran
  PROPERTIES Fortran_MODULE_DIRECTORY "${CMAKE_BINARY_DIR}/bindings/fortran/modules")
target_include_directories(MFrontGenericInterface-fortran
	PRIVATE "${CMAKE_SOURCE_DIR}/include"
	PRIVATE "${CMAKE_SOURCE_DIR}/bindings/c/include")
target_link_libraries(MFrontGenericInterface-fortran
   PUBLIC MFrontGenericInterface-c MFrontGenericInterface)
