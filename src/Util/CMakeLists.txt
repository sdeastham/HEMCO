add_library(HCO_UTIL STATIC EXCLUDE_FROM_ALL
	hco_charpak_mod.F90
	hco_inquireMod.F90
	hco_precision_mod.F90
	hco_julday_mod.F90
)
target_link_libraries(HCO_UTIL
	PUBLIC HEMCOBuildProperties
)
target_include_directories(HCO_UTIL
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
