cmake_minimum_required(VERSION 2.8)
project (cppunit)
set(srcs AdditionalMessage.cpp
	Asserter.cpp
	BeosDynamicLibraryManager.cpp
	BriefTestProgressListener.cpp
	CompilerOutputter.cpp
	DefaultProtector.cpp
	DllMain.cpp
	DynamicLibraryManager.cpp
	DynamicLibraryManagerException.cpp
	Exception.cpp
	Message.cpp
	PlugInManager.cpp
	PlugInParameters.cpp
	Protector.cpp
	ProtectorChain.cpp
	RepeatedTest.cpp
	SourceLine.cpp
	StringTools.cpp
	SynchronizedObject.cpp
	Test.cpp
	TestAssert.cpp
	TestCase.cpp
	TestCaseDecorator.cpp
	TestComposite.cpp
	TestDecorator.cpp
	TestFactoryRegistry.cpp
	TestFailure.cpp
	TestLeaf.cpp
	TestNamer.cpp
	TestPath.cpp
	TestPlugInDefaultImpl.cpp
	TestResult.cpp
	TestResultCollector.cpp
	TestRunner.cpp
	TestSetUp.cpp
	TestSuccessListener.cpp
	TestSuite.cpp
	TestSuiteBuilderContext.cpp
	TextOutputter.cpp
	TextTestProgressListener.cpp
	TextTestResult.cpp
	TextTestRunner.cpp
	TypeInfoHelper.cpp
	UnixDynamicLibraryManager.cpp
	Win32DynamicLibraryManager.cpp
	XmlDocument.cpp
	XmlElement.cpp
	XmlOutputter.cpp
	XmlOutputterHook.cpp
)

add_definitions(-DCPPUNIT_BUILD_DLL)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../../include)

add_library(cppunit_dll SHARED ${srcs})
add_library(cppunit STATIC ${srcs})
set_target_properties(cppunit_dll PROPERTIES DEBUG_POSTFIX d)
set_target_properties(cppunit PROPERTIES DEBUG_POSTFIX d)

