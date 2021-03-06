# ******************************************************************************
# Copyright 2017-2020 Intel Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ******************************************************************************

set (SRC
    assertion.hpp
    attribute_adapter.cpp
    attribute_adapter.hpp
    attribute_visitor.hpp
    autodiff/adjoints.cpp
    autodiff/adjoints.hpp
    axis_set.cpp
    axis_set.hpp
    axis_vector.cpp
    axis_vector.hpp
    builder/autobroadcast.cpp
    builder/autobroadcast.hpp
    builder/dequantize_builder.cpp
    builder/dequantize_builder.hpp
    builder/make_constant.hpp
    builder/matmul_factory.cpp
    builder/matmul_factory.hpp
    builder/norm.cpp
    builder/norm.hpp
    builder/numpy_transpose.cpp
    builder/numpy_transpose.hpp
    builder/quantize_builder.cpp
    builder/quantize_builder.hpp
    builder/quantized_concat_builder.cpp
    builder/quantized_concat_builder.hpp
    builder/quantized_conv_builder.cpp
    builder/quantized_conv_builder.hpp
    builder/quantized_dot_builder.cpp
    builder/quantized_dot_builder.hpp
    builder/quantization/quantized_linear_convolution.cpp
    builder/quantization/quantized_linear_convolution.hpp
    builder/quantization_utils.hpp
    builder/quantization_utils.cpp
    builder/reduce_ops.cpp
    builder/reduce_ops.hpp
    builder/reshape.cpp
    builder/reshape.hpp
    builder/split.cpp
    builder/split.hpp
    builder/tensor_mask.hpp
    check.hpp
    code_writer.hpp
    component_manager.hpp
    coordinate.cpp
    coordinate.hpp
    coordinate_diff.cpp
    coordinate_diff.hpp
    coordinate_transform.cpp
    cpio.cpp
    cpio.hpp
    deprecated.hpp
    descriptor/input.cpp
    descriptor/input.hpp
    descriptor/layout/dense_tensor_layout.cpp
    descriptor/layout/dense_tensor_layout.hpp
    descriptor/layout/tensor_layout.cpp
    descriptor/layout/tensor_layout.hpp
    descriptor/output.cpp
    descriptor/output.hpp
    descriptor/tensor.cpp
    descriptor/tensor.hpp
    dimension.cpp
    dimension.hpp
    distributed.cpp
    distributed.hpp
    enum_names.hpp
    env_util.cpp
    env_util.hpp
    except.hpp
    factory.cpp
    factory.hpp
    file_util.cpp
    file_util.hpp
    function.cpp
    function.hpp
    graph_util.cpp
    lambda.cpp
    lambda.hpp
    log.cpp
    log.hpp
    ngraph.cpp
    ngraph.hpp
    ngraph_visibility.hpp
    node.cpp
    node.hpp
    op/abs.cpp
    op/abs.hpp
    op/acos.cpp
    op/acos.hpp
    op/add.cpp
    op/add.hpp
    op/all.cpp
    op/all.hpp
    op/allreduce.cpp
    op/allreduce.hpp
    op/and.cpp
    op/and.hpp
    op/any.cpp
    op/any.hpp
    op/argmax.cpp
    op/argmax.hpp
    op/argmin.cpp
    op/argmin.hpp
    op/asin.cpp
    op/asin.hpp
    op/atan.cpp
    op/atan.hpp
    op/atan2.cpp
    op/atan2.hpp
    op/avg_pool.cpp
    op/avg_pool.hpp
    op/batch_norm.cpp
    op/batch_norm.hpp
    op/binary_convolution.cpp
    op/binary_convolution.hpp
    op/broadcast.cpp
    op/broadcast_distributed.cpp
    op/ceiling.cpp
    op/ceiling.hpp
    op/concat.cpp
    op/concat.hpp
    op/constant.cpp
    op/constant.hpp
    op/convert.cpp
    op/convert.hpp
    op/convert_like.cpp
    op/convert_like.hpp
    op/convolution.cpp
    op/convolution.hpp
    op/cos.cpp
    op/cos.hpp
    op/cosh.cpp
    op/cosh.hpp
    op/cum_sum.cpp
    op/cum_sum.hpp
    op/crop_and_resize.cpp
    op/crop_and_resize.hpp
    op/deformable_convolution.cpp
    op/deformable_convolution.hpp
    op/deformable_psroi_pooling.cpp
    op/deformable_psroi_pooling.hpp
    op/dequantize.cpp
    op/dequantize.hpp
    op/divide.cpp
    op/divide.hpp
    op/dot.cpp
    op/dot.hpp
    op/embedding_lookup.cpp
    op/embedding_lookup.hpp
    op/equal.cpp
    op/equal.hpp
    op/erf.cpp
    op/erf.hpp
    op/exp.cpp
    op/exp.hpp
    op/experimental/batch_mat_mul.cpp
    op/experimental/batch_mat_mul.hpp
    op/experimental/dyn_broadcast.cpp
    op/experimental/dyn_broadcast.hpp
    op/experimental/dyn_pad.cpp
    op/experimental/dyn_pad.hpp
    op/experimental/dyn_replace_slice.cpp
    op/experimental/dyn_replace_slice.hpp
    op/experimental/dyn_reshape.cpp
    op/experimental/dyn_reshape.hpp
    op/experimental/dyn_slice.cpp
    op/experimental/dyn_slice.hpp
    op/experimental/generate_mask.cpp
    op/experimental/generate_mask.hpp
    op/experimental/quantized_conv_bias.cpp
    op/experimental/quantized_conv_bias.hpp
    op/experimental/quantized_conv_relu.cpp
    op/experimental/quantized_conv_relu.hpp
    op/experimental/range.cpp
    op/experimental/range.hpp
    op/experimental/shape_of.cpp
    op/experimental/shape_of.hpp
    op/experimental/tile.cpp
    op/experimental/tile.hpp
    op/experimental/quantized_dot_bias.cpp
    op/experimental/quantized_dot_bias.hpp
    op/experimental/compiled_kernel.cpp
    op/experimental/compiled_kernel.hpp
    op/experimental/transpose.cpp
    op/experimental/transpose.hpp
    op/experimental/layers/ctc_greedy_decoder.cpp
    op/experimental/layers/ctc_greedy_decoder.hpp
    op/experimental/layers/detection_output.cpp
    op/experimental/layers/detection_output.hpp
    op/experimental/layers/interpolate.cpp
    op/experimental/layers/interpolate.hpp
    op/experimental/layers/prior_box.cpp
    op/experimental/layers/prior_box.hpp
    op/experimental/layers/prior_box_clustered.cpp
    op/experimental/layers/prior_box_clustered.hpp
    op/experimental/layers/proposal.hpp
    op/experimental/layers/proposal.cpp
    op/experimental/layers/psroi_pooling.hpp
    op/experimental/layers/psroi_pooling.cpp
    op/experimental/layers/region_yolo.hpp
    op/experimental/layers/region_yolo.cpp
    op/experimental/layers/reorg_yolo.hpp
    op/experimental/layers/reorg_yolo.cpp
    op/experimental/layers/roi_pooling.hpp
    op/experimental/layers/roi_pooling.cpp
    op/experimental/random_uniform.hpp
    op/experimental/random_uniform.cpp
    op/strided_slice.hpp
    op/floor.cpp
    op/floor.hpp
    op/floor_mod.cpp
    op/floor_mod.hpp
    op/gather.cpp
    op/gather.hpp
    op/gather_nd.cpp
    op/gather_nd.hpp
    op/gather_tree.cpp
    op/gather_tree.hpp
    op/get_output_element.cpp
    op/get_output_element.hpp
    op/greater.cpp
    op/greater.hpp
    op/greater_eq.cpp
    op/greater_eq.hpp
    op/less.cpp
    op/less.hpp
    op/less_eq.cpp
    op/less_eq.hpp
    op/log.cpp
    op/log.hpp
    op/lrn.cpp
    op/lrn.hpp
    op/max.cpp
    op/max.hpp
    op/max_pool.cpp
    op/max_pool.hpp
    op/maximum.cpp
    op/maximum.hpp
    op/min.cpp
    op/min.hpp
    op/minimum.cpp
    op/minimum.hpp
    op/multiply.cpp
    op/multiply.hpp
    op/negative.cpp
    op/negative.hpp
    op/non_max_suppression.cpp
    op/non_max_suppression.hpp
    op/not.cpp
    op/not.hpp
    op/not_equal.cpp
    op/not_equal.hpp
    op/one_hot.cpp
    op/one_hot.hpp
    op/op.cpp
    op/op.hpp
    op/or.cpp
    op/or.hpp
    op/pad.cpp
    op/pad.hpp
    op/parameter.cpp
    op/parameter.hpp
    op/passthrough.cpp
    op/passthrough.hpp
    op/power.cpp
    op/power.hpp
    op/product.cpp
    op/product.hpp
    op/reduce_logical_and.cpp
    op/reduce_logical_and.hpp
    op/reduce_logical_or.cpp
    op/reduce_logical_or.hpp
    op/reduce_prod.cpp
    op/reduce_prod.hpp
    op/reduce_mean.cpp
    op/reduce_mean.hpp
    op/reduce_sum.cpp
    op/reduce_sum.hpp
    op/round.cpp
    op/round.hpp
    op/quantize.cpp
    op/quantize.hpp
    op/quantized_convolution.cpp
    op/quantized_convolution.hpp
    op/quantized_dot.cpp
    op/quantized_dot.hpp
    op/recv.cpp
    op/recv.hpp
    op/relu.cpp
    op/relu.hpp
    op/replace_slice.cpp
    op/replace_slice.hpp
    op/reshape.cpp
    op/reshape.hpp
    op/result.cpp
    op/result.hpp
    op/reverse.cpp
    op/reverse.hpp
    op/reverse_sequence.cpp
    op/reverse_sequence.hpp
    op/scatter_add.cpp
    op/scatter_add.hpp
    op/scatter_nd_add.cpp
    op/scatter_nd_add.hpp
    op/select.cpp
    op/select.hpp
    op/send.cpp
    op/send.hpp
    op/sigmoid.cpp
    op/sigmoid.hpp
    op/sign.cpp
    op/sign.hpp
    op/sin.cpp
    op/sin.hpp
    op/sinh.cpp
    op/sinh.hpp
    op/slice.cpp
    op/slice.hpp
    op/softmax.cpp
    op/softmax.hpp
    op/strided_slice.cpp
    op/strided_slice.hpp
    op/sqrt.cpp
    op/sqrt.hpp
    op/stop_gradient.cpp
    op/stop_gradient.hpp
    op/subtract.cpp
    op/subtract.hpp
    op/sum.cpp
    op/sum.hpp
    op/variadic_split.cpp
    op/variadic_split.hpp
    op/tan.cpp
    op/tan.hpp
    op/tanh.cpp
    op/tanh.hpp
    op/tensor_iterator.cpp
    op/tensor_iterator.hpp
    op/topk.cpp
    op/topk.hpp
    op/xor.cpp
    op/xor.hpp
    op/fused/batch_mat_mul_transpose.cpp
    op/fused/batch_mat_mul_transpose.hpp
    op/fused/clamp.cpp
    op/fused/clamp.hpp
    op/fused/conv_fused.cpp
    op/fused/conv_fused.hpp
    op/fused/crossentropy.cpp
    op/fused/crossentropy.hpp
    op/fused/hard_sigmoid.cpp
    op/fused/hard_sigmoid.hpp
    op/fused/depth_to_space.cpp
    op/fused/depth_to_space.hpp
    op/fused/elu.cpp
    op/fused/elu.hpp
    op/fused/fake_quantize.cpp
    op/fused/fake_quantize.hpp
    op/fused/gelu.cpp
    op/fused/gelu.hpp
    op/fused/gemm.cpp
    op/fused/gemm.hpp
    op/fused/grn.cpp
    op/fused/grn.hpp
    op/fused/group_conv.hpp
    op/fused/group_conv.cpp
    op/fused/gru_cell.cpp
    op/fused/gru_cell.hpp
    op/fused/layer_norm.cpp
    op/fused/layer_norm.hpp
    op/fused/lstm_cell.cpp
    op/fused/lstm_cell.hpp
    op/fused/lstm_sequence.cpp
    op/fused/lstm_sequence.hpp
    op/fused/matmul.cpp
    op/fused/matmul.hpp
    op/fused/mod.cpp
    op/fused/mod.hpp
    op/fused/mvn.cpp
    op/fused/mvn.hpp
    op/fused/normalize_l2.cpp
    op/fused/normalize_l2.hpp
    op/fused/partial_slice.cpp
    op/fused/partial_slice.hpp
    op/fused/prelu.cpp
    op/fused/prelu.hpp
    op/fused/rnn_cell.cpp
    op/fused/rnn_cell.hpp
    op/fused/scale_shift.cpp
    op/fused/scale_shift.hpp
    op/fused/scatter_nd.cpp
    op/fused/scatter_nd.hpp
    op/fused/stack.cpp
    op/fused/stack.hpp
    op/fused/selu.cpp
    op/fused/selu.hpp
    op/fused/shuffle_channels.cpp
    op/fused/shuffle_channels.hpp
    op/fused/softmax_crossentropy.cpp
    op/fused/softmax_crossentropy.hpp
    op/fused/space_to_depth.cpp
    op/fused/space_to_depth.hpp
    op/fused/split.cpp
    op/fused/split.hpp
    op/fused/squared_difference.cpp
    op/fused/squared_difference.hpp
    op/fused/squeeze.cpp
    op/fused/squeeze.hpp
    op/fused/unsqueeze.cpp
    op/fused/unsqueeze.hpp
    op/util/attr_types.cpp
    op/util/attr_types.hpp
    op/util/activation_functions.cpp
    op/util/activation_functions.hpp
    op/util/arithmetic_reduction.cpp
    op/util/arithmetic_reduction.hpp
    op/util/arithmetic_reductions_keep_dims.hpp
    op/util/arithmetic_reductions_keep_dims.cpp
    op/util/binary_elementwise_arithmetic.cpp
    op/util/binary_elementwise_arithmetic.hpp
    op/util/binary_elementwise_comparison.cpp
    op/util/binary_elementwise_comparison.hpp
    op/util/binary_elementwise_logical.cpp
    op/util/binary_elementwise_logical.hpp
    op/util/broadcasting.cpp
    op/util/broadcasting.hpp
    op/util/fused_op.cpp
    op/util/fused_op.hpp
    op/util/index_reduction.cpp
    op/util/index_reduction.hpp
    op/util/logical_reduction_keep_dims.hpp
    op/util/logical_reduction_keep_dims.cpp
    op/util/logical_reduction.cpp
    op/util/logical_reduction.hpp
    op/util/rnn_cell_base.cpp
    op/util/rnn_cell_base.hpp
    op/util/unary_elementwise_arithmetic.cpp
    op/util/unary_elementwise_arithmetic.hpp
    ops.hpp
    opsets/opset.cpp
    partial_shape.cpp
    partial_shape.hpp
    pass/algebraic_simplification.cpp
    pass/algebraic_simplification.hpp
    pass/assign_layout.hpp
    pass/implicit_broadcast_elimination.hpp
    pass/implicit_broadcast_elimination.cpp
    pass/batch_fusion.hpp
    pass/batch_fusion.cpp
    pass/common_function_collection.cpp
    pass/common_function_collection.hpp
    pass/constant_folding_arithmetic_reduction.cpp
    pass/constant_folding_binary.cpp
    pass/constant_folding_broadcast.cpp
    pass/constant_folding_concat.cpp
    pass/constant_folding_convert.cpp
    pass/constant_folding_dequantize.cpp
    pass/constant_folding_dyn_broadcast.cpp
    pass/constant_folding_dyn_reshape.cpp
    pass/constant_folding_dyn_slice.cpp
    pass/constant_folding_gather.cpp
    pass/constant_folding_logical_reduction.cpp
    pass/constant_folding_one_hot.cpp
    pass/constant_folding_pad.cpp
    pass/constant_folding_quantize.cpp
    pass/constant_folding_range.cpp
    pass/constant_folding_reshape.cpp
    pass/constant_folding_reverse.cpp
    pass/constant_folding_select.cpp
    pass/constant_folding_squeeze.cpp
    pass/constant_folding_unsqueeze.cpp
    pass/constant_folding_shape_of.cpp
    pass/constant_folding_slice.cpp
    pass/constant_folding_split.cpp
    pass/constant_folding_variadic_split.cpp
    pass/constant_folding_strided_slice.cpp
    pass/constant_folding_transpose.cpp
    pass/constant_folding_unary.cpp
    pass/constant_folding.cpp
    pass/constant_folding.hpp
    pass/constant_to_broadcast.cpp
    pass/convert_fp32_to_fp16.hpp
    pass/convert_fp32_to_fp16.cpp
    pass/core_fusion.cpp
    pass/core_fusion.hpp
    pass/cse.cpp
    pass/cse.hpp
    pass/dump_sorted.cpp
    pass/dump_sorted.hpp
    pass/dyn_elimination.cpp
    pass/dyn_elimination.hpp
    pass/fused_op_decomposition.cpp
    pass/fused_op_decomposition.hpp
    pass/get_output_element_elimination.cpp
    pass/get_output_element_elimination.hpp
    pass/graph_rewrite.cpp
    pass/graph_rewrite.hpp
    pass/like_replacement.cpp
    pass/like_replacement.hpp
    pass/liveness.cpp
    pass/liveness.hpp
    pass/manager.cpp
    pass/manager.hpp
    pass/manager_state.hpp
    pass/memory_layout.cpp
    pass/memory_layout.hpp
    pass/memory_visualize.cpp
    pass/memory_visualize.hpp
    pass/nop_elimination.cpp
    pass/nop_elimination.hpp
    pass/pass.cpp
    pass/pass.hpp
    pass/opset0_downgrade.cpp
    pass/opset0_downgrade.hpp
    pass/opset1_upgrade.cpp
    pass/opset1_upgrade.hpp
    pass/pass_config.cpp
    pass/pass_config.hpp
    pass/propagate_cacheability.cpp
    pass/propagate_cacheability.hpp
    pass/reshape_elimination.cpp
    pass/reshape_elimination.hpp
    pass/reshape_sinking.cpp
    pass/reshape_sinking.hpp
    pass/serialize.cpp
    pass/serialize.hpp
    pass/shape_relevance.cpp
    pass/shape_relevance.hpp
    pass/validate_graph.cpp
    pass/validate_graph.hpp
    pass/validate.cpp
    pass/validate.hpp
    pass/visualize_tree.cpp
    pass/visualize_tree.hpp
    pass/zero_dim_tensor_elimination.cpp
    pass/zero_dim_tensor_elimination.cpp
    pass/zero_dim_tensor_elimination.hpp
    pass/zero_dim_tensor_elimination.hpp
    pass/concat_fusion.hpp
    pass/concat_fusion.cpp
    pass/pass_util.hpp
    pass/pass_util.cpp
    pattern/matcher.cpp
    pattern/matcher.hpp
    pattern/op/any.cpp
    pattern/op/any.hpp
    pattern/op/any_of.cpp
    pattern/op/any_of.hpp
    pattern/op/branch.cpp
    pattern/op/branch.hpp
    pattern/op/capture.cpp
    pattern/op/capture.hpp
    pattern/op/label.cpp
    pattern/op/label.hpp
    pattern/op/or.cpp
    pattern/op/or.hpp
    pattern/op/pattern.cpp
    pattern/op/pattern.hpp
    pattern/op/skip.cpp
    pattern/op/skip.hpp
    pattern/op/true.cpp
    pattern/op/true.hpp
    placement.cpp
    placement.hpp
    provenance.cpp
    provenance.hpp
    rank.hpp
    runtime/aligned_buffer.cpp
    runtime/aligned_buffer.hpp
    runtime/allocator.cpp
    runtime/allocator.hpp
    runtime/backend.cpp
    runtime/backend.hpp
    runtime/backend_manager.cpp
    runtime/backend_manager.hpp
    runtime/cache.cpp
    runtime/cache.hpp
    runtime/chrome_trace.cpp
    runtime/chrome_trace.hpp
    runtime/executable.cpp
    runtime/executable.hpp
    runtime/host_tensor.cpp
    runtime/host_tensor.hpp
    runtime/performance_counter.hpp
    runtime/tensor.cpp
    runtime/tensor.hpp
    shape.cpp
    shape.hpp
    shape_util.cpp
    shape_util.hpp
    slice_plan.cpp
    slice_plan.hpp
    specialize_function.cpp
    specialize_function.hpp
    state/bernoulli_rng_state.cpp
    state/bernoulli_rng_state.hpp
    state/uniform_rng_state.cpp
    state/uniform_rng_state.hpp
    strides.cpp
    strides.hpp
    type/bfloat16.cpp
    type/bfloat16.hpp
    type/float16.cpp
    type/float16.hpp
    type/element_type.cpp
    type.cpp
    type.hpp
    util.cpp
    util.hpp
    validation_util.cpp
    validation_util.hpp
    variant.cpp
    variant.hpp
    )

set(SRC ${SRC}
    runtime/dynamic/dynamic_backend.cpp
    runtime/dynamic/dynamic_backend.hpp
    )

if(NGRAPH_JSON_ENABLE)
    list(APPEND SRC serializer.cpp serializer.hpp event_tracing.cpp event_tracing.hpp)
else()
    list(APPEND SRC serializer_stub.cpp)
endif()

configure_file(version.in.hpp version.hpp)

if (NGRAPH_STATIC_LIB_ENABLE)
    add_library(ngraph STATIC ${SRC})
else()
    add_library(ngraph SHARED ${SRC})
endif()

if(NOT NGRAPH_JSON_ENABLE)
    target_compile_definitions(ngraph PUBLIC NGRAPH_JSON_DISABLE)
endif()

if(NGRAPH_INTERPRETER_STATIC_LIB_ENABLE)
    target_compile_definitions(ngraph PUBLIC NGRAPH_INTERPRETER_STATIC_LIB_ENABLE)
endif()

if(NGRAPH_CPU_STATIC_LIB_ENABLE)
    target_compile_definitions(ngraph PUBLIC NGRAPH_CPU_STATIC_LIB_ENABLE)
endif()

if(NGRAPH_DISTRIBUTED_ENABLE)
    if(NGRAPH_DISTRIBUTED_MLSL_ENABLE)
        target_include_directories(ngraph SYSTEM PRIVATE libmlsl)
        target_link_libraries(ngraph PRIVATE libmlsl)
    elseif(NGRAPH_DISTRIBUTED_OMPI_ENABLE)
        find_package(MPI REQUIRED)
        target_include_directories(ngraph SYSTEM PRIVATE ${MPI_C_INCLUDE_PATH} ${MPI_CXX_INCLUDE_PATH})
        target_link_libraries(ngraph PRIVATE ${MPI_C_LIBRARIES} ${MPI_CXX_LIBRARIES})
    else()
        message(FATAL_ERROR "Distributed Library not supported/mentioned")
    endif()
endif()

add_subdirectory(frontend)

find_package(Graphviz QUIET)
if (GRAPHVIZ_FOUND)
    set_property(SOURCE pass/visualize_tree.cpp APPEND PROPERTY COMPILE_DEFINITIONS GRAPHVIZ_FOUND)
endif()

if(NGRAPH_ADDRESS_SANITIZER)
    message(STATUS "Enable Address Sanitizer")
    add_compile_options(-g -fsanitize=address -fno-omit-frame-pointer)
endif()

add_subdirectory(codegen)
add_subdirectory(runtime)

target_compile_definitions(ngraph
    PRIVATE
        SHARED_LIB_PREFIX="${CMAKE_SHARED_LIBRARY_PREFIX}"
        SHARED_LIB_SUFFIX="${CMAKE_SHARED_LIBRARY_SUFFIX}"
)
if(NGRAPH_LIB_VERSIONING_ENABLE)
    set_target_properties(ngraph PROPERTIES
        VERSION ${NGRAPH_VERSION}
        SOVERSION ${NGRAPH_API_VERSION})
endif()
if(NGRAPH_JSON_ENABLE)
    target_link_libraries(ngraph PRIVATE libjson)
endif()
target_compile_definitions(ngraph PUBLIC NGRAPH_VERSION="${NGRAPH_VERSION}")

if (LINUX)
    # nGraph links against one or more libraries (ex. LLVM) but we don't want to
    # export these symbols as part of the DSO. This is a GNU ld (and derivatives) specific
    # option so making this portable is still an open issue. As a note for the future,
    # this is not an issue on Windows and LLVM's lld does support --exclude-libs.
    set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,--exclude-libs,ALL")

    # GCC invokes the linker with --as-needed by default which doesn't work for us
    # because generated code needs to find symbols in these DSOs at runtime.
    # The fix below is temporary and will be removed once we find a better way
    # to do this because certain dependencies like the OpenMP runtime libraries
    # _do_ need to be linked with --as-needed with a higher priority for the
    # Intel OpenMP runtime so we don't mix libgomp and libiomp5
    if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
        set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,--no-as-needed")
    endif()
elseif(APPLE)
    set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,-rpath,@loader_path")
endif()

# Defines macro in C++ to load backend plugin
target_include_directories(ngraph PUBLIC $<BUILD_INTERFACE:${NGRAPH_INCLUDE_PATH}> $<INSTALL_INTERFACE:include>)

#Add an alias so that library can be used inside the build tree, e.g. when testing
add_library(ngraph::ngraph ALIAS ngraph)

if (NOT WIN32)
    find_package(Threads REQUIRED)
    target_link_libraries(ngraph PUBLIC dl Threads::Threads)
endif()

if (NGRAPH_ONNX_IMPORT_ENABLE)
    target_sources(ngraph PRIVATE $<TARGET_OBJECTS:onnx_import_interface>)
    target_link_libraries(ngraph PRIVATE onnx_import)
endif()

# Build subdirectories for all build types on Windows
if(WIN32)
    foreach(BUILD_TYPE Release Debug RelWithDebInfo MinSizeRel)
        if(NOT EXISTS ${NGRAPH_BUILD_DIR}/${BUILD_TYPE})
            file(MAKE_DIRECTORY ${NGRAPH_BUILD_DIR}/${BUILD_TYPE})
        endif()
    endforeach()
endif()

#-----------------------------------------------------------------------------------------------
# Installation logic...
#-----------------------------------------------------------------------------------------------

# nGraph
install(TARGETS ngraph EXPORT ngraphTargets
        RUNTIME DESTINATION ${NGRAPH_INSTALL_LIB}
        ARCHIVE DESTINATION ${NGRAPH_INSTALL_LIB}
        LIBRARY DESTINATION ${NGRAPH_INSTALL_LIB}
        COMPONENT ngraph)
install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/
    DESTINATION ${NGRAPH_INSTALL_INCLUDE}/ngraph
    COMPONENT ngraph
    FILES_MATCHING
        PATTERN "*.hpp"
        PATTERN "*.h"
)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/version.hpp
    DESTINATION ${NGRAPH_INSTALL_INCLUDE}/ngraph
    COMPONENT ngraph)

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_SHLIBDEPS ON)
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "A most excellent graph library")
set(CPACK_PACKAGE_NAME "nGraph")
set(CPACK_PACKAGE_CONTACT "Robert Kimball")
# set(CPACK_PACKAGE_VERSION
set(CPACK_PACKAGE_VENDOR "Intel Nervana")
# set(CPACK_PACKAGE_DESCRIPTION_FILE "")

set(CPACK_PACKAGE_VERSION_MAJOR ${NGRAPH_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR ${NGRAPH_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH ${NGRAPH_VERSION_PATCH})
include(CPack)
