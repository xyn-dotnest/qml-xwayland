find_package(XCB REQUIRED COMPONENTS XFIXES CURSOR COMPOSITE RENDER SHAPE)
find_package(Xcursor REQUIRED)
find_package(Wayland REQUIRED)

liri_add_qml_plugin(lirixwayland
    MODULE_PATH
        "Liri/XWayland"
    VERSION
        "1.0"
    SOURCES
        plugin.cpp
        sigwatch.cpp
        sigwatch.h
        sizehints.h
        xcbatom.cpp
        xcbatom.h
        xcbatoms.cpp
        xcbatoms.h
        xcbcursors.cpp
        xcbcursors.h
        xcbproperties.cpp
        xcbproperties.h
        xcbresources.cpp
        xcbresources.h
        xcbwindow.cpp
        xcbwindow.h
        xcbwrapper.cpp
        xcbwrapper.h
        xwayland.cpp
        xwayland.h
        xwaylandmanager.cpp
        xwaylandmanager.h
        xwaylandquickshellintegration.cpp
        xwaylandquickshellintegration.h
        xwaylandquickshellsurfaceitem.cpp
        xwaylandquickshellsurfaceitem.h
        xwaylandserver.cpp
        xwaylandserver.h
        xwaylandshellsurface.cpp
        xwaylandshellsurface.h
    QML_FILES
        qmldir
    DEFINES
        #QT_NO_CAST_FROM_ASCII
        QT_NO_FOREACH
    LIBRARIES
        Qt5::WaylandCompositor
        Qt5::WaylandCompositorPrivate
        ${XCB_TARGETS}
        PkgConfig::Xcursor
        Wayland::Server
)
