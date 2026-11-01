CXX = g++
CXXFLAGS = -Wall

ifeq ($(OS),Windows_NT)
	LDFLAGS = -lfreeglut -lglu32 -lopengl32
	RM = del /Q
else
	LDFLAGS = -lGL -lGLU -lglut
	RM = rm -f
endif

TARGETS = Ex00 Ex01A Ex01B Ex01C Ex02 Ex03

.PHONY: all clean

all: $(TARGETS)

%: %.cpp
	$(CXX) $(CXXFLAGS) $< -o $@ $(LDFLAGS)

clean:
	$(RM) $(TARGETS) *.exe *.o
