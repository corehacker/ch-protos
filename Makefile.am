AM_CPPFLAGS = -I.

ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libch-protos.la

protoc_inputs = packet.proto \
					 communication.proto \
					 label-client-internal.proto

protoc_outputs = ch-protos/packet.pb.cc ch-protos/packet.pb.h \
					  ch-protos/communication.pb.cc ch-protos/communication.pb.h \
					  ch-protos/label-client-internal.pb.cc ch-protos/label-client-internal.pb.h

libch_protos_la_SOURCES = $(protoc_outputs)

libch_protos_adir = $(includedir)/ch-protos

nobase_include_HEADERS = ch-protos/packet.pb.h \
								 ch-protos/communication.pb.h \
								 ch-protos/label-client-internal.pb.h

BUILT_SOURCES = $(protoc_outputs)

CLEANFILES = $(protoc_outputs)

$(protoc_outputs): $(protoc_inputs)
	mkdir -p ch-protos
	$(PROTOC) --proto_path=. --cpp_out=ch-protos $^

#all: $(lib_LTLIBRARIES)

#$(lib_LTLIBRARIES): $(protoc_outputs)

#$(protoc_outputs): $(protoc_inputs)
#	mkdir -p ch-protos
#	$(PROTOC) --proto_path=. --cpp_out=ch-protos $^

#CLEANFILES = $(protoc_outputs)


#libch_protos_adir = $(includedir)/ch-protos
#nobase_include_HEADERS = ch-protos/packet.pb.h \
#								 ch-protos/communication.pb.h \
#								 ch-protos/label-client-internal.pb.h
