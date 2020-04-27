# Depolying Qt Applications

[Qt documentation]( https://doc.qt.io/qt-5/deployment.html/)

## Windows

[Qt documentation for Windows]( https://doc.qt.io/qt-5/windows-deployment.html )

> The tool can be found in `QTDIR/bin/windeployqt`. It needs to be run within the build environment in order to function correctly. When using Qt Installer, the script `QTDIR/bin/qtenv2.bat` should be used to set it up 

1. `qtenv2.bat`

2. `windeployqt name_of_program.exe`

## Linux (Ubuntu)

1. `cqtdeployer -bin hello -qmake /home/user_name/bin/Qt5.14.2/5.14.2/gcc_64/bin/qmake`

2. Or use another method

   ` ./deployqt UbuntuApp -qmake="/home/wu/Qt5.10.1/5.10.1/gcc_64/bin/qmake" `

[linuxdeployqt]( https://github.com/probonopd/linuxdeployqt )

