IF(HAVE_UMFPACK OR HAVE_MUMPS)
  INCLUDE(test_macros)
  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

  CONFIGURE_FILE(sif/6459.sif sif/6459.sif COPYONLY)

  file(COPY ELMERSOLVER_STARTINFO DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")
  file(COPY sif/6459-circuits.definitions DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/sif")
  file(COPY 6459/mesh.boundary 6459/mesh.header 6459/mesh.nodes 6459/mesh.elements 6459/mesh.names DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/6459")
  file(COPY 6459/dat/gittrack DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/6459/dat")

  ADD_ELMER_TEST(circuits_harmonic_foil LABELS circuits harmonic 3D mgdyn whitney)
ENDIF()
