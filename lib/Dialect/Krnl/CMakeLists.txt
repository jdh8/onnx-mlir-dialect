set(LLVM_TARGET_DEFINITIONS KrnlOps.td)
onnx_mlir_tablegen(KrnlOps.hpp.inc -gen-op-decls)
onnx_mlir_tablegen(KrnlOps.cpp.inc -gen-op-defs)
add_public_tablegen_target(OMKrnlOpsIncGen)

add_library(OMKrnlOps
        KrnlOps.hpp
        KrnlOps.cpp
        KrnlTypes.hpp
        KrnlTypes.cpp
        KrnlHelper.hpp
        KrnlHelper.cpp)
target_include_directories(OMKrnlOps
        PRIVATE
        ${ONNX_MLIR_SRC_ROOT}
        ${ONNX_MLIR_BIN_ROOT}
        ${ONNX_MLIR_SRC_ROOT})
add_dependencies(OMKrnlOps OMKrnlOpsIncGen)