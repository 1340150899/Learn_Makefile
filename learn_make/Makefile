TGT = yes.out
SRCS = test.cpp func.cpp


CUR_DIR = $(shell pwd)
HEAD_DIR = $(CUR_DIR)func.h

#指定编译选项
CFLAGS = -I $(HEAD_DIR)

$(TGT): $(SRCS: .cpp = .o)
	g++ $^	$(CFLAGS) -o $@


%.o: %.cpp
	g++ $< -c

#下面规则用来说明头文件的更新 应该使得所有依赖与它的文件被重新生成
#%.d: %.cpp
#	g++ -MM $< > $@


#include $(SRCS: .cpp = .d)


clean:
	rm -f $(TGT) $(SRCS: .cpp = .o) #$(SRCS: .cpp = .d)


#指定clean是一个伪目标 执行的时候不会生成clean文件
.PHONY: clean
