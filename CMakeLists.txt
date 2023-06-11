cmake_minimum_required(VERSION 3.14)

project(imgui-node-editor)

include_directories(".")

add_library(imgui-node-editor STATIC 
  "imgui_node_editor_api.cpp"
  "imgui_node_editor.cpp"
  "imgui_canvas.cpp"
  "crude_json.cpp"
)