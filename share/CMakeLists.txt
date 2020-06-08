set (GenF90_SRCS shr_infnan_mod.F90.in)

add_library(nuopc_share  ${GenF90_SRCS}
			 shr_cal_mod.F90
                         shr_kind_mod.F90
                         shr_pio_mod.F90
                         shr_sys_mod.F90
                         shr_abort_mod.F90
			 shr_const_mod.F90
			 shr_orb_mod.F90
			 shr_mpi_mod.F90
			 shr_log_mod.F90
			 shr_strconvert_mod.F90
			 shr_string_mod.F90)
