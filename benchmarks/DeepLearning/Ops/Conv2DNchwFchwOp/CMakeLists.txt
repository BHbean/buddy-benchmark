add_buddy_ops_benchmark(conv-2d-nchw-fchw-benchmark
  MLIR Conv2DNchwFchw.mlir
  BITCODE conv-2d-nchw-fchw.o
  LIBRARY Conv2DNchwFchw
  OPTIONS
    -convert-linalg-to-loops 
    -convert-scf-to-cf 
    -convert-linalg-to-llvm 
    -lower-affine 
    --convert-memref-to-llvm
    --llvm-request-c-wrappers
    -convert-func-to-llvm 
    -reconcile-unrealized-casts
  SOURCE Main.cpp MLIROptBenchmark.cpp
)
