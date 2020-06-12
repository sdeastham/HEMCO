add_library(HCO_REGRID STATIC EXCLUDE_FROM_ALL
        hco_interp_mod.F90
        hcoio_messy_mod.F90
        hco_vertgrid_mod.F90
        messy_ncregrid_base.F90
        messy_ncregrid_mpi.F90
)
target_link_libraries(HCO_REGRID
	PUBLIC GeosUtilHco NcdfUtilHco
)
target_compile_options(HCO_REGRID
	PRIVATE
		""
		$<$<STREQUAL:"${CMAKE_Fortran_COMPILER_ID}","GNU">:-ffree-line-length-none>
)
target_include_directories(HCO_REGRID
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
