include ../Makefile.pkg_common

# This is an optimized stack value based on testing, if you observe
# a segmentation fault please increase this stack size.
CFLAGS += -DTHREAD_STACKSIZE_MAIN=2*THREAD_STACKSIZE_LARGE

USEPKG += wolfssl
USEMODULE += wolfcrypt wolfcrypt-test wolfcrypt_sha512 \
             wolfcrypt_curve25519 wolfcrypt_ed25519 wolfcrypt_chacha \
             wolfcrypt_poly1305 wolfcrypt_aes wolfcrypt_ecc \
             wolfcrypt_asn wolfcrypt_random

# Uncomment the following line to enable RSA tests
# (e.g. when enough resources are available on platform)
#USEMODULE += wolfcrypt_rsa wolfcrypt_dh

# Comment the following line to disable full-benchmark test
USEMODULE += wolfcrypt-benchmark

USEMODULE += xtimer

ifeq (,$(filter native native32 native64,$(BOARD)))
  CFLAGS += -DBENCH_EMBEDDED
endif

TEST_ON_CI_WHITELIST += native32 native64

include $(RIOTBASE)/Makefile.include
