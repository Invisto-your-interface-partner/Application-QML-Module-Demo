cmake_minimum_required(VERSION 3.16)

project(QMLModuleApplicationDemo VERSION 1.0 LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 6.2 COMPONENTS Quick Gui REQUIRED)

qt_add_executable(myapp
    main.cpp
)

qt_add_qml_module(myapp
    URI hello
    VERSION 1.0
    QML_FILES
        main.qml
        Logo.qml
    RESOURCES
        images/Invisto-Logo.svg
)

target_link_libraries(myapp PRIVATE Qt6::Gui Qt6::Quick)
