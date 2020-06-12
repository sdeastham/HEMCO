add_library(HCO_IO STATIC EXCLUDE_FROM_ALL
        hco_extlist_mod.F90
        hco_filedata_mod.F90
        hcoio_dataread_mod.F90
        hcoio_diagn_mod.F90
        hcoio_read_esmf_mod.F90
        hcoio_read_std_mod.F90
        hcoio_write_esmf_mod.F90
        hcoio_write_std_mod.F90
	hcoio_util_mod.F90
        hco_readlist_mod.F90
        hco_restart_mod.F90
        hco_tidx_mod.F90
        hco_timeshift_mod.F90
)
target_link_libraries(HCO_IO
	PUBLIC GeosUtilHco NcdfUtilHco
)
target_compile_options(HCO_IO
	PRIVATE
		""
		$<$<STREQUAL:"${CMAKE_Fortran_COMPILER_ID}","GNU">:-ffree-line-length-none>
)
target_include_directories(HCO_IO
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
