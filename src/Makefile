# In case you cross compile this on a different architecture, uncomment this
# and set the prefix
#CROSS_COMPILE?=arm-arago-linux-gnueabi-
CROSS_COMPILE?=arm-linux-gnueabihf-

# Tuning options for ARM CPU.
#ARM_OPTIONS?=-mtune=cortex-a8 -march=armv7-a

CFLAGS+= -Wall -I$(INCDIR_APP_LOADER) -std=c99 -D_XOPEN_SOURCE=500 -O2 $(ARM_OPTIONS)
LDFLAGS+=-lpthread -lm

cc1200-objs := cc1200.o

all: clean cc1200_app

clean:
	rm -f cc1200_app *.o

cc1200_app: cc1200_app.o $(cc1200-objs)
	$(CROSS_COMPILE)gcc $(CFLAGS) -o $@ $^ $(LDFLAGS)
