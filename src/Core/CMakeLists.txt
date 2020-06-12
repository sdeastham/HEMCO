add_library(HCO_CORE STATIC EXCLUDE_FROM_ALL
        hco_arr_mod.F90
        hco_chartools_mod.F90
        hco_clock_mod.F90
        hco_config_mod.F90
        hco_datacont_mod.F90
        hco_diagn_mod.F90
        hco_driver_mod.F90
        hco_error_mod.F90
        hco_geotools_mod.F90
        hco_logfile_mod.F90
        hco_state_mod.F90
        hco_types_mod.F90
        hco_unit_mod.F90
        interpreter.F90
)
target_link_libraries(HCO_CORE
	PUBLIC GeosUtilHco NcdfUtilHco
)
target_compile_options(HCO_CORE
	PRIVATE
		""
		$<$<STREQUAL:"${CMAKE_Fortran_COMPILER_ID}","GNU">:-ffree-line-length-none>
)
target_include_directories(HCO_CORE
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
