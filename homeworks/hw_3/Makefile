BDIR		=	bin
SDIR		=	src
ODIR		=	obj
IDIR		=	include

CXX				=	clang++ -std=c++17
OPTIMIZE	=	-O3 -Wall -Wextra -pedantic
CFLAGS		=	$(OPTIMIZE) -I$(IDIR)
LDFLAGS		=	-lm

_DEPS		=	string.hpp vector.hpp integrate.hpp richardson.hpp
DEPS		=	$(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ		=	main.o string_public.o
OBJ 		=	$(patsubst %,$(ODIR)/%,$(_OBJ))

$(ODIR)/%.o: $(SDIR)/%.cpp $(DEPS)
	$(CXX) -c -o $@ $< $(CFLAGS)

$(BDIR)/integrate: $(OBJ)
	$(CXX) -o $@ $^ $(CFLAGS) $(LDFLAGS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(IDIR)/*~
