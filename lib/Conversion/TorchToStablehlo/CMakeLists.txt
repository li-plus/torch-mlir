add_mlir_conversion_library(TorchMLIRTorchToStablehlo
  TorchToStablehlo.cpp
  StablehloLegalizeUtils.cpp
  Basic.cpp
  GatherScatter.cpp
  Linear.cpp
  ViewLike.cpp
  Reduction.cpp
  Pooling.cpp

  ADDITIONAL_HEADER_DIRS
  ${PROJECT_SOURCE_DIR}/include/torch-mlir/Conversion/TorchToStablehlo

  DEPENDS
  TorchMLIRConversionPassIncGen

  LINK_COMPONENTS
  Core

  LINK_LIBS PUBLIC
  MLIRIR
  MLIRPass
  MLIRBufferTransforms
  StablehloOps
  TorchMLIRTorchDialect
  TorchMLIRConversionUtils
)

torch_mlir_target_includes(TorchMLIRTorchToStablehlo)
