IF(HAVE_UMFPACK OR HAVE_MUMPS)
  INCLUDE(test_macros)
  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

  CONFIGURE_FILE( pbe.sif pbe.sif COPYONLY)

  file(COPY ELMERSOLVER_STARTINFO corner.grd DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

  ADD_ELMER_TEST(PoissonBoltzmann)
ENDIF()
