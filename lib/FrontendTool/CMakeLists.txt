set_swift_llvm_is_available()
add_swift_host_library(swiftFrontendTool STATIC
  FrontendTool.cpp
  ImportedModules.cpp
  LoadedModuleTrace.cpp
  MakeStyleDependencies.cpp
  TBD.cpp)
add_dependencies(swiftFrontendTool
  swift-syntax-generated-headers
  SwiftOptions)
target_link_libraries(swiftFrontendTool INTERFACE
  clangAPINotes
  clangBasic)
target_link_libraries(swiftFrontendTool PRIVATE
    swiftClangImporter
    swiftDemangling
    swiftDependencyScan
    swiftFrontend
    swiftIDE
    swiftImmediate
    swiftIndex
    swiftIRGen
    swiftOption
    swiftPrintAsObjC
    swiftSerialization
    swiftSIL
    swiftSILGen
    swiftSILOptimizer
    swiftTBDGen)
