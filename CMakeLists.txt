cmake_minimum_required(VERSION 3.12)

project(pkcs11test)

set(CMAKE_CXX_STANDARD 11)

include(ExternalProject)

include_directories(gtest-1.6.0/include)
include_directories(third_party/pkcs11)

add_executable(pkcs11test
        third_party/pkcs11/pkcs11.h
        third_party/pkcs11/pkcs11f.h
        third_party/pkcs11/pkcs11t.h
        cipher.cc
        describe.cc
        digest.cc
        dual.cc
        globals.cc
        globals.h
        hmac.cc
        init.cc
        key.cc
        keypair.cc
        login.cc
        object.cc
        pkcs11-describe.cc
        pkcs11-describe.h
        pkcs11-env.h
        pkcs11test.cc
        pkcs11test.h
        rng.cc
        session.cc
        sign.cc
        slot.cc
        tookan.cc)

add_subdirectory (gtest-1.6.0)

target_link_libraries(pkcs11test gtest)
