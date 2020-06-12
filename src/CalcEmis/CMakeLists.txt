add_library(HCO_CALCEMIS STATIC EXCLUDE_FROM_ALL
        hco_calc_mod.F90
        hco_emislist_mod.F90
        hco_fluxarr_mod.F90
        hco_scale_mod.F90
)
target_link_libraries(HCO_CALCEMIS
	PUBLIC GeosUtilHco NcdfUtilHco
)
target_compile_options(HCO_CALCEMIS
	PRIVATE
		""
		$<$<STREQUAL:"${CMAKE_Fortran_COMPILER_ID}","GNU">:-ffree-line-length-none>
)
target_include_directories(HCO_CALCEMIS
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
