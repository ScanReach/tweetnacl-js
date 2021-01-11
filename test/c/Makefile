CFLAGS=-O3 -Iinc

all: csecretbox cscalarmult cbox chash csign csign-keypair

csecretbox: csecretbox.o src/tweetnacl.o

cscalarmult: cscalarmult.o src/tweetnacl.o

cbox: cbox.o src/tweetnacl.o

chash: chash.o src/tweetnacl.o

csign: csign.o src/tweetnacl.o

csign-keypair: csign-keypair.o src/tweetnacl.o

test: test_secretbox test_scalarmult test_box test_hash test_sign test_signkeypair clean

test_secretbox: csecretbox
	node ./00-secretbox.js

test_scalarmult: cscalarmult
	node ./01-scalarmult.js

test_box: cbox
	node ./02-box.js

test_hash: chash
	node ./03-hash.js

test_sign: csign
	node ./04-sign.js

test_signkeypair: csign csign-keypair
	node ./05-sign-keypair.js

clean:
	rm *.o csecretbox cscalarmult cbox chash csign csign-keypair src/*.o
