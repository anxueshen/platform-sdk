编译mac版本platform方法和遇到的问题

1、程序依赖了Boost库1.7.0，但本身Boost1.7.0和苹果的CLang编译器不兼容，会报如下错误：
clang: error: unknown argument: '-fcoalesce-templates'
开始是采用homebrew下载的boost 1.72版本，后来修改了代码，实现了采用boost 1.72编译（在Mac 10.15.4上编译boost貌似不太稳定，不知道什么情况下会编译不过，后来又编译通过了，需要更多测试。）

编译命令需要加如下参数才能支持qt版本输出：
cmake .. -DAIRMAP_ENABLE_QT=ON -DQt5_DIR="/Applications/Qt/5.12.6/clang_64/lib/cmake/Qt5"
