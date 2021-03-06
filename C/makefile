#
#  USAGE:
#     make          ... to build the program
#     make test     ... to run the default test case
#

include make.def

EXES=hello$(EXE) pi$(EXE) pi_recur$(EXE) mandel$(EXE)  \
         mm_testbed$(EXE) jac_solv$(EXE)  \
         stream$(EXE) stream_nft$(EXE) xthi_omp$(EXE) xthi_nested_omp$(EXE)

MM_OBJS  = mm_testbed.$(OBJ) mm_utils.$(OBJ) mm_ijk.$(OBJ) mm_tst_cases.$(OBJ)

JAC_OBJS  = jac_solv.$(OBJ) mm_utils.$(OBJ) 

all: $(EXES)

jac_solv$(EXE): $(JAC_OBJS) mm_utils.h
	$(CLINKER) $(CFLAGS) -o jac_solv$(EXE) $(JAC_OBJS) $(LIBS)

mm_testbed$(EXE): $(MM_OBJS) mm_utils.h
	$(CLINKER) $(CFLAGS) -o mm_testbed$(EXE) $(MM_OBJS) $(LIBS)

hello$(EXE): hello.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o hello hello.$(OBJ) $(LIBS)

pi$(EXE): pi.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o pi pi.$(OBJ) $(LIBS)

pi_recur$(EXE): pi_recur.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o pi_recur pi_recur.$(OBJ) $(LIBS)

mandel$(EXE):  mandel.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o mandel mandel.$(OBJ) $(LIBS)

stream$(EXE):  stream.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o stream stream.$(OBJ) $(LIBS)

stream_nft$(EXE):  stream_nft.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o stream_nft stream_nft.$(OBJ) $(LIBS)

xthi_omp$(EXE):  xthi_omp.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o xthi_omp xthi_omp.$(OBJ) $(LIBS)

xthi_nested_omp$(EXE):  xthi_nested_omp.$(OBJ) 
	$(CLINKER) $(OPTFLAGS) -o xthi_nested_omp xthi_nested_omp.$(OBJ) $(LIBS)

test: $(EXES)
	$(PRE)hello$(EXE) 
	$(PRE)pi$(EXE) 
	$(PRE)pi_recur$(EXE) 
	$(PRE)mandel$(EXE) 
	$(PRE)mm_testbed$(EXE) 
	$(PRE)jac_solv$(EXE) 
	$(PRE)stream$(EXE) 
	$(PRE)stream_nft$(EXE) 
	$(PRE)xthi_omp$(EXE) 
	$(PRE)xthi_nested_omp$(EXE) 

clean:
	$(RM) -rf $(EXES) *.$(OBJ)

.SUFFIXES:
.SUFFIXES: .c .cpp .$(OBJ)

.c.$(OBJ):
	$(CC) $(CFLAGS) -c $<

.cpp.$(OBJ):
	$(CC) $(CFLAGS) -c $<
