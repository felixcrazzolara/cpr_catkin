# cpr_catkin
A catkin wrapper for C++ Request http://whoshuu.github.io/cpr/

## Usage
As include and library directories are exported with `catkin_package()`, you just have to add `cpr_catkin` as dependency in `catkin_package()`, `find_package()` it and of course mention it as dependency in your `package.xml`.

## Requirements
You might need to install the OpenSSL development libraries and header files `sudo apt install libssl-dev`.
