EX=kalman
ALGO=ds_nogc
NAME=kalman_ds_nogc

include ../../Makefile.common-config

CSV_FILES=perf-step.csv mem-ideal.csv

PROBZELUC += -I ../kalmanlib

all: build

bench: bench_per_steps bench_mem_ideal

include ../../Makefile.common-algo
