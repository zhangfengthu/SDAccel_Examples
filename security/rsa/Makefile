# RSA Application

include ../../utility/boards.mk
include ../../libs/logger/logger.mk
include ../../libs/cmdparser/cmdparser.mk
include ../../libs/xcl_cpp/xcl_cpp.mk
include ../../libs/opencl/opencl.mk

# hello Host Application
rsa_SRCS=./src/rsa_app.cpp ./src/common.cpp ./src/main.cpp $(cmdparser_SRCS) $(xcl_cpp_SRCS) $(logger_SRCS)
rsa_HDRS=./src/rsa_app.h ./src/common.h $(cmdparser_HDRS) $(logger_HDRS) $(xcl_cpp_HDRS)
rsa_CXXFLAGS=-DRSA_2048 -g -O3 -Wall -I./src/ $(opencl_CXXFLAGS) $(cmdparser_CXXFLAGS) $(logger_CXXFLAGS) $(xcl_cpp_CXXFLAGS) -lssl -lcrypto -ldl
rsa_LDFLAGS=$(opencl_LDFLAGS)

# RSA Kernel
krnl_rsa_SRCS=./src/krnl_rsa.cl

EXES=rsa
XCLBINS=krnl_rsa

include ../../utility/rules.mk

