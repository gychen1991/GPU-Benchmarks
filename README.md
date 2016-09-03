# GPU-Benchmarks

Examples to see how to improve GPU performance. This repo contains some benchmarks which have some important performance issues(e.g. uncoalesced memory accesses, thread divergence) that could be addressed throught code optimizations.

### mem_coalesced
	trans.cu: memory access for stores is not coalesced;
	trans_opt.cu: uses 2D surface memory for writting.
#### To compile:
	make
#### To run:
	./run.sh	

### thread_divergency
	knnjoin.cu: has thread divergency problem in kernel KNNQuery_base;
	knnjoin_opt.cu: uses the reorder technique to reduce the thread divergency for kernel KNNQuery_base;

#### To compile:
	make
#### To run:
	./run.sh
#### To profile the kernel execution time(e.g.):
	nvprof ./knnjoin 145057 145057 4 800 800 200 Skin_NonSkin.txt Skin_NonSkin.txt
