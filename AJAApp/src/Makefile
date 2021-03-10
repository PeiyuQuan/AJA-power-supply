TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = AJA
# AJA.dbd will be created and installed
DBD += AJA.dbd

# AJA.dbd will be made up from these files:
AJA_DBD += base.dbd

# Include dbd files from all support applications:
#AJA_DBD += xxx.dbd
AJA_DBD += asyn.dbd
AJA_DBD += stream.dbd
AJA_DBD += stream-scalcout.dbd
AJA_DBD += calc.dbd
AJA_DBD += drvAsynIPPort.dbd
AJA_DBD += drvAsynSerialPort.dbd
# Add all the support libraries needed by this IOC
#AJA_LIBS += xxx
AJA_LIBS += asyn
AJA_LIBS += calc
AJA_LIBS += stream

# AJA_registerRecordDeviceDriver.cpp derives from AJA.dbd
AJA_SRCS += AJA_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
AJA_SRCS_DEFAULT += AJAMain.cpp
AJA_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#AJA_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
AJA_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

