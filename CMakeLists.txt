cmake_minimum_required(VERSION 3.14)

project(imgui-node-editor)

option(IMGUI_NODE_EDITOR_IMGUI_INCLUDE_DIR "Include directory for ImGui" "OFF")

if (IMGUI_NODE_EDITOR_IMGUI_INCLUDE_DIR STREQUAL "OFF")
  message(FATAL_ERROR "imgui_node_editor requires imgui directory to be set")
endif()

add_library(imgui-node-editor STATIC 
  "imgui_node_editor_api.cpp"
  "imgui_node_editor.cpp"
  "imgui_canvas.cpp"
  "crude_json.cpp"
)

target_include_directories(
  imgui-node-editor
  PUBLIC
  "$<BUILD_INTERFACE:./"
  "$<BUILD_INTERFACE:${IMGUI_NODE_EDITOR_IMGUI_INCLUDE_DIR}>"
)