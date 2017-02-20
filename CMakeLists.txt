#
# Copyright (C) 2013-2017 Mattia Basaglia
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.
#

set(SOURCES
src/color_list_widget.cpp
src/gradient_slider.cpp
src/color_line_edit.cpp
src/swatch.cpp
src/bound_color_selector.cpp
src/color_palette_widget.cpp
src/color_palette_model.cpp
src/color_2d_slider.cpp
src/abstract_widget_list.cpp
src/color_delegate.cpp
src/color_widgets.qrc
src/color_utils.cpp
src/color_dialog.cpp
src/color_palette.cpp
src/color_selector.cpp
src/color_preview.cpp
src/alphaback.png
src/color_utils.hpp
src/hue_slider.cpp
src/color_wheel.cpp
src/color_names.cpp
)

set(HEADERS
include/color_palette_model.hpp
include/color_palette_widget.hpp
include/colorwidgets_global.hpp
include/color_wheel.hpp
include/color_line_edit.hpp
include/swatch.hpp
include/color_delegate.hpp
include/color_palette.hpp
include/hue_slider.hpp
include/abstract_widget_list.hpp
include/bound_color_selector.hpp
include/color_dialog.hpp
include/color_2d_slider.hpp
include/color_selector.hpp
include/color_list_widget.hpp
include/color_preview.hpp
include/gradient_slider.hpp
include/color_names.hpp
)

qt5_wrap_cpp(SOURCES ${HEADERS})
qt5_wrap_ui(SOURCES src/color_dialog.ui src/color_palette_widget.ui)
qt5_add_resources(SOURCES src/color_widgets.qrc)

# Library
add_library(ColorWidgets-qt5 ${SOURCES})
target_link_libraries(ColorWidgets-qt5 Qt5::Widgets)
target_include_directories (ColorWidgets-qt5 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_include_directories (ColorWidgets-qt5 PRIVATE ${CMAKE_CURRENT_BINARY_DIR})
target_compile_definitions (ColorWidgets-qt5 PUBLIC QTCOLORWIDGETS_LIBRARY)
