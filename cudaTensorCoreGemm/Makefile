TARGET = cudaTensorCoreGemm

# CUDA
NVCC = `which nvcc`
ARCH=35

all: clean $(TARGET) 

$(TARGET): 
	$(NVCC) -o cudaTensorCoreGemm -Xptxas -v -arch=sm_$(ARCH) cudaTensorCoreGemm.cu 

test:
	./simple_add 

golden:
	./cudaTensorCoreGemm >golden_stdout.txt 2>golden_stderr.txt

clean:
	rm -f *.o *~ cudaTensorCoreGemm

clobber: clean
	rm -f golden* *_regcount.p stdout* stderr*
