# ========= libfs/Makefile =========

CC       ?= gcc
CFLAGS   ?= -Wall -Wextra -Werror -std=c11 -g
AR       ?= ar
ARFLAGS  ?= rcs
RM       ?= rm -f

SRCS := $(wildcard *.c)     
OBJS := $(SRCS:.c=.o)      
DEPS := $(OBJS:.o=.d)       

LIB  := libfs.a           

.PHONY: all
all: $(LIB)

$(LIB): $(OBJS)
	$(AR) $(ARFLAGS) $@ $^

%.o: %.c
	$(CC) $(CFLAGS) -MMD -MP -c $< -o $@

-include $(DEPS)

# clean -------------------------------------------------------
.PHONY: clean
clean:
	$(RM) $(OBJS) $(DEPS) $(LIB)
