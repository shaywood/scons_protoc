"""
SConstruct file for testing if the protoc.py builder works.

This should generate test/test.pb2.cc, test/test.pb2.h,
test/python/test_pb2.py and test/java/test_pb2.java

These files should be non-empty.

Ideally, we'd actually test that said files compile, but
that would require access to a correctly configured Java / C compiler

The python output is tested by trying to import the file. This results
in the interpreter checking its syntax, which is the best metric for
"did protoc work and output files correctly?" that's available short of
a more complex dedicated set of inter-linked programs. The purpose however,
is to check that we invoked protoc successfully, not whether protoc was, itself,
successful.
"""

TEST_PROTO_FILE = [str(x) for x in Glob('test*.proto')]

env = Environment(tools = ['default', 'protoc'], toolpath = '.')

# task for generating CPP files:
gen_cpp_src = env.ProtocCPP(source = TEST_PROTO_FILE)

gen_python_src = env.ProtocPython(source = TEST_PROTO_FILE)

gen_java_src = env.ProtocJava(source = TEST_PROTO_FILE)

env.Default(gen_java_src)
env.Default(gen_cpp_src)
env.Default(gen_python_src)
