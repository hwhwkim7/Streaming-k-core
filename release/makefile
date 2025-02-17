include makefile.in

INCLUDES   = -I/home/asariyu/sparsehash-master/src # todo: put your path here

TARGET     = stkcore

SRCS	= $(CFILES:%=%.c) $(CXXFILES:%=%.cpp)

TBBLDFLAGS += -ltbb

all: $(TARGET) 

stkcore: kcore.o main-kcore.o subcore.o traversal.o edge_generators.o ulib.o bucket.o xcore_removal.o xcore_insertion.o xtraversal_insertion.o
	$(LD) $(LDFLAGS) -o $@ kcore.o main-kcore.o subcore.o traversal.o edge_generators.o ulib.o bucket.o xcore_removal.o xcore_insertion.o xtraversal_insertion.o $(LIBS)

clean: 
	/bin/rm -f *.o stkcore *~ $(TARGET) 


depend: $(SRCS)
	makedepend -Y -- $(INCLUDES) -- $(SRCS) 



#********************************************************************
# Dependencies
#********************************************************************
# DO NOT DELETE THIS LINE -- make depend depends on it.

# larray.o: larray.h
ulib.o: ulib.h
kcore.o: ulib.h graph.h timestamp.hpp main-kcore.hpp bucket.h
