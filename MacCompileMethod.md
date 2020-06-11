编译mac版本platform方法和遇到的问题

1、程序依赖了Boost库1.7.0，但本身Boost1.7.0和苹果的CLang编译器不兼容，会报如下错误：
clang: error: unknown argument: '-fcoalesce-templates'
所以改用了HomeBrew下载的Boost 1.7.2,但新版本删除了base64_encode函数，所以需要简单修改代码；

编译命令需要加如下参数才能支持qt版本输出：
cmake .. -DAIRMAP_ENABLE_QT=ON -DQt5_DIR="/Applications/Qt/5.12.6/clang_64/lib/cmake/Qt5"
