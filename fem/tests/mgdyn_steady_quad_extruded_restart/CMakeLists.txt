INCLUDE(test_macros)
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

CONFIGURE_FILE(case.sif case.sif COPYONLY)

file(COPY ELMERSOLVER_STARTINFO case2d.sif quads.grd DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

ADD_ELMER_TEST(mgdyn_steady_quad_extruded_restart NPROCS 1 3 LABELS extrude restart whitney failing)
