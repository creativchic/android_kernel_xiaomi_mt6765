obj-y := fdvt_dummy.o

#$(info FDVT: makefile start)
MTK_CUSTOM_PATH  := $(srctree)/drivers/misc/mediatek

FDVT_35_PLATFORM = mt6763 mt6761
FDVT_40_PLATFORM = mt6758 mt6799 mt6759 mt6775 mt6771 mt6765
FDVT_50_PLATFORM = mt6779
FDVT_CURRENT_PLATFORM = $(subst ",,$(CONFIG_MTK_PLATFORM))

#$(info FDVT_CURRENT_PLATFORM= $(FDVT_CURRENT_PLATFORM))

ifneq (, $(findstring $(FDVT_CURRENT_PLATFORM), $(FDVT_35_PLATFORM)))
MTKCAM_FDVT_VERSION := 3.5
MTKCAM_FDVT_PATH := $(MTK_CUSTOM_PATH)/cameraisp/fdvt/3.5
subdir-ccflags-y += -I$(MTK_CUSTOM_PATH)/cameraisp/fdvt/3.5/inc
obj-y += 3.5/
else ifneq (, $(findstring $(FDVT_CURRENT_PLATFORM), $(FDVT_40_PLATFORM)))
MTKCAM_FDVT_VERSION := 4.0
MTKCAM_FDVT_PATH := $(MTK_CUSTOM_PATH)/cameraisp/fdvt/4.0
subdir-ccflags-y += -I$(MTK_CUSTOM_PATH)/cameraisp/fdvt/4.0/inc
obj-y += 4.0/
else ifneq (, $(findstring $(FDVT_CURRENT_PLATFORM), $(FDVT_50_PLATFORM)))
MTKCAM_FDVT_VERSION := 5.0
MTKCAM_FDVT_PATH := $(MTK_CUSTOM_PATH)/cameraisp/fdvt/5.0
subdir-ccflags-y += -I$(MTK_CUSTOM_PATH)/cameraisp/fdvt/5.0/inc
obj-y += 5.0/
endif

ifeq ($(CONFIG_MACH_MT6763),y)
  MTK_FD_LARB := 1
else ifeq ($(CONFIG_MACH_MT6761),y)
  MTK_FD_LARB := 2
endif

subdir-ccflags-y += -DMTK_FD_LARB=$(MTK_FD_LARB)

#$(info FDVT: makefile end)

