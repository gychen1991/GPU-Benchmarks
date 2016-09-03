NVCC=nvcc -w -arch=sm_35 -std=c++11 -lcublas -O3 -Xcompiler -fopenmp 

all: knnjoin
knnjoin: knnjoin.cu
	$(NVCC) -o $@ $^
clean:
	rm knnjoin 
