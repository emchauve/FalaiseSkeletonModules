cmake_minimum_required(VERSION 3.9)

project(FalaiseSkeletonModules)

find_package(Falaise REQUIRED)

add_library(FalaiseSkeletonModules SHARED
            falaise-skeleton-module-udd.cc
            falaise-skeleton-module-sd.cc
            falaise-skeleton-module-cd.cc
            falaise-skeleton-module-tcd.cc
            falaise-skeleton-module-ttd.cc
            falaise-skeleton-module-ptd.cc)
		  
target_link_libraries(FalaiseSkeletonModules Falaise::FalaiseModule)

configure_file("falaise-skeleton-module-pipeline.conf.in" "falaise-skeleton-module-pipeline.conf")
