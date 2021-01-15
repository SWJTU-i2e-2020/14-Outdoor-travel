# 户外旅行选题报告——蓝牙智能手表

## 项目名称和作者
通信五虎：高科曌、李鸿健、王春翔、罗鑫、王宇涛。

## 问题定义
第一，作为可穿戴计算设备的手表，自然要具备自主计算能力，所以智能手表应该有自己的独立数据处理能力。从现在的智能手表市面上看已经有厂家考虑到了这一点，盛大果壳的Geak Watch是以搭载完整智能系统为卖点的。而从索尼刚刚发布的Samrt Watch 2来看，由于索尼新发布的旗舰手机Xperia Z Ultra XL39h屏幕较大已经不太适合长时间手持使用，所以索尼不失时机的发布了一款智能手表，而它的功能更多的是作为智能机的配件使用，作为手机的第二块屏幕。

第二，智能手表除了拥有独立计算能力之外，还要拥有协同工作能力。所以智能手表既可以作为一个终端使用，可以和其他终端协同工作，正是有了这些协同工作要求，我们对于智能手表的数据传输就有了要求。作为现在最时髦的数据传输方式有NFC和蓝牙以及用于连接外部设备的ATN+传输标准。蓝牙4.0从有效距离和功耗上都超过了前面的几代标准，所以智能手表应该具备至少蓝牙4.0的数据传输标准。
现在市面上也有很多的智能穿戴设备出现，智能手环作为一个新兴产品受到人们的关注。但是纵观整个智能手环界，高级的已经具备智能手表的功能，低端的就只有健康管理这样的功能。所以从科技融合趋势来说，智能手表完全可以整合智能手环的功能，具备健康管理和环境感知。

第三，智能手表作为终端产品，它应当作为我们感知周围环境的模块。一款智能手表应该内置多种常规传感器，来提醒使用者环境和身体的变化。对于现阶段能够继承的传感器包括：环境光、地磁、温度、气压、高度、陀螺仪和加速计以及心率传感器。这些内置传感器也将作为智能手表独立计算能力的一部分，可以脱离手机和网络独立为用户提供数据信息，这也是对智能手表信息稳定性的一种保证，这样即便脱离手机的辅助依然能作为一款智能穿戴设备使用。

## 问题的背景：
随着移动技术的发展，许多传统的电子产品也开始增加移动方面的功能，比如过去只能用来看时间的手表，现今也可以通过智能手机或家庭网络与互联网相连，显示来电信息、Twitter和新闻feeds、天气信息等内容。
这种新手表可被称作智能手表，某些已经上市销售，某些还处于样品测试阶段。这类产品主要是为消费者在不方便使用智能手机的情况下使用而设计的，比如正在骑自行车或手上提满了东西的时候。

## 需求介绍：
经过我们小组对于市场的分析，得出对于设备有以下要求：
(1)一款可以随身携带，并能显示当地气温、湿度、时间，连接手机显示通知数量，电池，WIFI等的蓝牙智能手表。方便快捷，更适合户外旅行。

(2)需要在旅行途中得到当地气温、湿度的信息。需要快捷地查看时间以及手机电量等信息。需要便于携带。

(3)基于Arduino所设计的便于户外旅行的蓝牙智能创客产品。

(4) 能够实现温度、湿度监测功能，与手机连接并显示手机上的信息。总体要求：所有信息都能在显示屏上显示出来，利用不同按键切换不同的功能状态。

(5)需要温度传感器、湿度传感器、液晶显示屏、蓝牙信号接收器、Arduino主板。环境要求：Arduino编程软件。

## 概念设计
（1）.通过蓝牙与WIFI模块，在连接上WIFI以后从互联网更新日期与时间并将其显示在液晶显示屏上。

（2）.通过温湿度传感器，对于临近水平面处进行测量，并将测量值显示在液晶显示屏上。

## 详细设计：
ESP-12N模块核心处理器采用高性价比芯片ESP8266EX。该芯片在较小尺寸封装中集成了业界领先的Tensilica’s L106 超低功耗32位微型MCU，带有16位精简模式，主频⽀持80 MHz和160 MHz，支持RTOS。ESP8266EX拥有完整的Wi-Fi网络功能，既能够独⽴应⽤，也可以作为从机搭载于其他主机MCU运⾏。当ESP8266EX独⽴应⽤时，能够直接从外接Flash中启动。内置的⾼速缓冲存储器有利于提⾼系统性能，并且优化存储系统。此外ESP8266EX只需通过SPI/SDIO 接⼝或I2C/UART⼝即可作为Wi-Fi适配器，应⽤到基于任何微控制器的设计中。
ESP-F模块支持标准的IEEE802.11 b/g/n/e/i协议以及完整的TCP/IP协议栈。用户可以使用该模块为现有设备添加联网功能，也可以构建独立的网络控制器。
ESP-F模块以最低成本提供最大实用性，为Wi-Fi功能嵌入其他系统提供无限可能。

分类	项目	 参数
Wi-Fi	频率范围	 2.4G~2.5G(2400M~2483.5M)
	发射功率	 802.11b: +20 dBm
		    802.11g: +17 dBm
		    802.11n: +14 dBm
	接收灵敏度	802.11b: -91 dbm (11Mbps)
		    802.11g: -75 dbm（54Mbps）
		    802.11n: -72 dbm（MCS7）
	天线	   TCB板载天线
硬件	CPU	   Tensilica L106 32 bit微控制器
	外设	   UART/SDIO/SPI/I2C/I2S/IR遥控
		    GPIO/ADC/PWM/SPI/I2C/I2S
	工作电压	 2.5V ~ 3.6V
	工作电流	 平均电流：80 mA
	工作温度	 -40°C ~ 85°C
	环境温度范围	-40°C ~ 125°C
	封装大小	  16mm x 24mm x 3mm
软件    Wi-Fi 模式	  Station/SoftAP/SoftAP+Station
	安全机制	  WPA/WPA2
	加密类型	  WEP/TKIP/AES
	升级固件	  UART Download/OTA（通过网络）
	软件开发	  Non-RTOS/RTOS/Arduino IDE等
	网络协议	  IPv4、TCP/UDP/HTTP/FTP/MQTT
	用户配置	  AT+ 指令集/云端服务器/ Android/iOS APP

## 性能评估
目前能顺利地实现所有功能，能正常地显示温度、湿度、日期与时间，满足设计的需求。

## 代码
ifndef PDIR

endif

ifeq ($(COMPILE), xcc)
    AR = xt-ar
	CC = xt-xcc
	NM = xt-nm
	CPP = xt-xt++
	OBJCOPY = xt-objcopy
	OBJDUMP = xt-objdump
else
	AR = xtensa-lx106-elf-ar
	CC = xtensa-lx106-elf-gcc
	NM = xtensa-lx106-elf-nm
	CPP = xtensa-lx106-elf-g++
	OBJCOPY = xtensa-lx106-elf-objcopy
	OBJDUMP = xtensa-lx106-elf-objdump
endif

BOOT?=none
APP?=0
SPI_SPEED?=40
SPI_MODE?=QIO
SPI_SIZE_MAP?=0

ifeq ($(BOOT), new)
    boot = new
else
    ifeq ($(BOOT), old)
        boot = old
    else
        boot = none
    endif
endif

ifeq ($(APP), 1)
    app = 1
else
    ifeq ($(APP), 2)
        app = 2
    else
        app = 0
    endif
endif

ifeq ($(SPI_SPEED), 26.7)
    freqdiv = 1
else
    ifeq ($(SPI_SPEED), 20)
        freqdiv = 2
    else
        ifeq ($(SPI_SPEED), 80)
            freqdiv = 15
        else
            freqdiv = 0
        endif
    endif
endif


ifeq ($(SPI_MODE), QOUT)
    mode = 1
else
    ifeq ($(SPI_MODE), DIO)
        mode = 2
    else
        ifeq ($(SPI_MODE), DOUT)
            mode = 3
        else
            mode = 0
        endif
    endif
endif

addr = 0x01000

ifeq ($(SPI_SIZE_MAP), 1)
  size_map = 1
  flash = 256
else
  ifeq ($(SPI_SIZE_MAP), 2)
    size_map = 2
    flash = 1024
    ifeq ($(app), 2)
      addr = 0x81000
    endif
  else
    ifeq ($(SPI_SIZE_MAP), 3)
      size_map = 3
      flash = 2048
      ifeq ($(app), 2)
        addr = 0x81000
      endif
    else
      ifeq ($(SPI_SIZE_MAP), 4)
        size_map = 4
        flash = 4096
        ifeq ($(app), 2)
          addr = 0x81000
        endif
      else
        ifeq ($(SPI_SIZE_MAP), 5)
          size_map = 5
          flash = 2048
          ifeq ($(app), 2)
            addr = 0x101000
          endif
        else
          ifeq ($(SPI_SIZE_MAP), 6)
            size_map = 6
            flash = 4096
            ifeq ($(app), 2)
              addr = 0x101000
            endif
          else
            ifeq ($(SPI_SIZE_MAP), 8)
              size_map = 8
              flash = 8192
              ifeq ($(app), 2)
                addr = 0x101000
              endif
            else
              ifeq ($(SPI_SIZE_MAP), 9)
                size_map = 9
                flash = 16384
                ifeq ($(app), 2)
                  addr = 0x101000
                endif
              else
                size_map = 0
                flash = 512
                ifeq ($(app), 2)
                addr = 0x41000
                endif
              endif
            endif
          endif
        endif
      endif
    endif
  endif
endif

LD_FILE = $(LDDIR)/eagle.app.v6.ld

ifneq ($(boot), none)
ifneq ($(app),0)
    ifneq ($(findstring $(size_map),  6  8  9),)
      LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).2048.ld
    else
      ifeq ($(size_map), 5)
        LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).2048.ld
      else
        ifeq ($(size_map), 4)
          LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).1024.app$(app).ld
        else
          ifeq ($(size_map), 3)
            LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).1024.app$(app).ld
          else
            ifeq ($(size_map), 2)
              LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).1024.app$(app).ld
            else
              ifeq ($(size_map), 0)
                LD_FILE = $(LDDIR)/eagle.app.v6.$(boot).512.app$(app).ld
              endif
            endif
          endif
        endif
      endif
    endif
    BIN_NAME = user$(app).$(flash).$(boot).$(size_map)
endif
else
    app = 0
endif

CSRCS ?= $(wildcard *.c)
CPPSRCS ?= $(wildcard *.cpp)
ASRCs ?= $(wildcard *.s)
ASRCS ?= $(wildcard *.S)
SUBDIRS ?= $(patsubst %/,%,$(dir $(wildcard */Makefile)))

ODIR := .output
OBJODIR := $(ODIR)/$(TARGET)/$(FLAVOR)/obj

OBJS := $(CSRCS:%.c=$(OBJODIR)/%.o) \
        $(CPPSRCS:%.cpp=$(OBJODIR)/%.o) \
        $(ASRCs:%.s=$(OBJODIR)/%.o) \
        $(ASRCS:%.S=$(OBJODIR)/%.o)

DEPS := $(CSRCS:%.c=$(OBJODIR)/%.d) \
        $(CPPSRCS:%.cpp=$(OBJODIR)/%.d) \
        $(ASRCs:%.s=$(OBJODIR)/%.d) \
        $(ASRCS:%.S=$(OBJODIR)/%.d)

LIBODIR := $(ODIR)/$(TARGET)/$(FLAVOR)/lib
OLIBS := $(GEN_LIBS:%=$(LIBODIR)/%)

IMAGEODIR := $(ODIR)/$(TARGET)/$(FLAVOR)/image
OIMAGES := $(GEN_IMAGES:%=$(IMAGEODIR)/%)

BINODIR := $(ODIR)/$(TARGET)/$(FLAVOR)/bin
OBINS := $(GEN_BINS:%=$(BINODIR)/%)

CCFLAGS += 			\
	-g			\
	-Wpointer-arith		\
	-Wundef			\
	-Werror			\
	-Wl,-EL			\
	-fno-inline-functions	\
	-nostdlib       \
	-mlongcalls	\
	-mtext-section-literals \
	-ffunction-sections \
	-fdata-sections	\
	-fno-builtin-printf	\
	-fno-jump-tables
	-Wall			

CFLAGS = $(CCFLAGS) $(DEFINES) $(EXTRA_CCFLAGS) $(INCLUDES)
DFLAGS = $(CCFLAGS) $(DDEFINES) $(EXTRA_CCFLAGS) $(INCLUDES)

define ShortcutRule
$(1): .subdirs $(2)/$(1)
endef

define MakeLibrary
DEP_LIBS_$(1) = $$(foreach lib,$$(filter %.a,$$(COMPONENTS_$(1))),$$(dir $$(lib))$$(LIBODIR)/$$(notdir $$(lib)))
DEP_OBJS_$(1) = $$(foreach obj,$$(filter %.o,$$(COMPONENTS_$(1))),$$(dir $$(obj))$$(OBJODIR)/$$(notdir $$(obj)))
$$(LIBODIR)/$(1).a: $$(OBJS) $$(DEP_OBJS_$(1)) $$(DEP_LIBS_$(1)) $$(DEPENDS_$(1))
	@mkdir -p $$(LIBODIR)
	$$(if $$(filter %.a,$$?),mkdir -p $$(EXTRACT_DIR)_$(1))
	$$(if $$(filter %.a,$$?),cd $$(EXTRACT_DIR)_$(1); $$(foreach lib,$$(filter %.a,$$?),$$(AR) xo $$(UP_EXTRACT_DIR)/$$(lib);))
	$$(AR) ru $$@ $$(filter %.o,$$?) $$(if $$(filter %.a,$$?),$$(EXTRACT_DIR)_$(1)/*.o)
	$$(if $$(filter %.a,$$?),$$(RM) -r $$(EXTRACT_DIR)_$(1))
endef

define MakeImage
DEP_LIBS_$(1) = $$(foreach lib,$$(filter %.a,$$(COMPONENTS_$(1))),$$(dir $$(lib))$$(LIBODIR)/$$(notdir $$(lib)))
DEP_OBJS_$(1) = $$(foreach obj,$$(filter %.o,$$(COMPONENTS_$(1))),$$(dir $$(obj))$$(OBJODIR)/$$(notdir $$(obj)))
$$(IMAGEODIR)/$(1).out: $$(OBJS) $$(DEP_OBJS_$(1)) $$(DEP_LIBS_$(1)) $$(DEPENDS_$(1))
	@mkdir -p $$(IMAGEODIR)
	$$(CC) $$(LDFLAGS) $$(if $$(LINKFLAGS_$(1)),$$(LINKFLAGS_$(1)),$$(LINKFLAGS_DEFAULT) $$(OBJS) $$(DEP_OBJS_$(1)) $$(DEP_LIBS_$(1))) -o $$@ 
endef

$(BINODIR)/%.bin: $(IMAGEODIR)/%.out
	@mkdir -p $(BIN_PATH)
	@mkdir -p $(BINODIR)
	
ifeq ($(APP), 0)
	@$(RM) -r $(BIN_PATH)/eagle.S $(BIN_PATH)/eagle.dump
	@$(OBJDUMP) -x -s $< > $(BIN_PATH)/eagle.dump
	@$(OBJDUMP) -S $< > $(BIN_PATH)/eagle.S
else
	@mkdir -p $(BIN_PATH)/upgrade
	@$(RM) -r $(BIN_PATH)/upgrade/$(BIN_NAME).S $(BIN_PATH)/upgrade/$(BIN_NAME).dump
	@$(OBJDUMP) -x -s $< > $(BIN_PATH)/upgrade/$(BIN_NAME).dump
	@$(OBJDUMP) -S $< > $(BIN_PATH)/upgrade/$(BIN_NAME).S
endif

	@$(OBJCOPY) --only-section .text -O binary $< eagle.app.v6.text.bin
	@$(OBJCOPY) --only-section .data -O binary $< eagle.app.v6.data.bin
	@$(OBJCOPY) --only-section .rodata -O binary $< eagle.app.v6.rodata.bin
	@$(OBJCOPY) --only-section .irom0.text -O binary $< eagle.app.v6.irom0text.bin

	@echo ""
	@echo "!!!"
	@echo "SDK_PATH: $(SDK_PATH)"
	
ifeq ($(app), 0)
	@python $(SDK_PATH)/tools/gen_appbin.py $< 0 $(mode) $(freqdiv) $(size_map)
	@mv eagle.app.flash.bin $(BIN_PATH)/eagle.flash.bin
	@mv eagle.app.v6.irom0text.bin $(BIN_PATH)/eagle.irom0text.bin
	@rm eagle.app.v6.*
	@echo "BIN_PATH: $(BIN_PATH)"
	@echo ""
	@echo "No boot needed."
	@echo "Generate eagle.flash.bin and eagle.irom0text.bin successully in BIN_PATH"
	@echo "eagle.flash.bin-------->0x00000"
	@echo "eagle.irom0text.bin---->0x20000"
else
	@echo "BIN_PATH: $(BIN_PATH)/upgrade"
	@echo ""

    ifneq ($(boot), new)
		@python $(SDK_PATH)/tools/gen_appbin.py $< 1 $(mode) $(freqdiv) $(size_map)
		@echo "Support boot_v1.1 and +"
    else
		@python $(SDK_PATH)/tools/gen_appbin.py $< 2 $(mode) $(freqdiv) $(size_map)

    	ifeq ($(size_map), 6)
		@echo "Support boot_v1.4 and +"
        else
            ifeq ($(size_map), 5)
		@echo "Support boot_v1.4 and +"
            else
		@echo "Support boot_v1.2 and +"
            endif
        endif
    endif

	@mv eagle.app.flash.bin $(BIN_PATH)/upgrade/$(BIN_NAME).bin
	@rm eagle.app.v6.*
	@echo "Generate $(BIN_NAME).bin successully in BIN_PATH"
	@echo "boot.bin------------>0x00000"
	@echo "$(BIN_NAME).bin--->$(addr)"
endif

	@echo "!!!"

all:	.subdirs $(OBJS) $(OLIBS) $(OIMAGES) $(OBINS) $(SPECIAL_MKTARGETS)

clean:
	$(foreach d, $(SUBDIRS), $(MAKE) -C $(d) clean;)
	$(RM) -r $(ODIR)/$(TARGET)/$(FLAVOR)

clobber: $(SPECIAL_CLOBBER)
	$(foreach d, $(SUBDIRS), $(MAKE) -C $(d) clobber;)
	$(RM) -r $(ODIR)

.subdirs:
	@set -e; $(foreach d, $(SUBDIRS), $(MAKE) -C $(d);)

.subdirs:
	$(foreach d, $(SUBDIRS), $(MAKE) -C $(d))

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(MAKECMDGOALS),clobber)
ifdef DEPS
sinclude $(DEPS)
endif
endif
endif

$(OBJODIR)/%.o: %.c
	@mkdir -p $(OBJODIR);
	$(CC) $(if $(findstring $<,$(DSRCS)),$(DFLAGS),$(CFLAGS)) $(COPTS_$(*F)) -o $@ -c $<

$(OBJODIR)/%.d: %.c
	@mkdir -p $(OBJODIR);
	@echo DEPEND: $(CC) -M $(CFLAGS) $<
	@set -e; rm -f $@; \
	$(CC) -M $(CFLAGS) $< > $@.$$$$; \
	sed 's,\($*\.o\)[ :]*,$(OBJODIR)/\1 $@ : ,g' < $@.$$$$ > $@; \
	rm -f $@.$$$$
	
$(OBJODIR)/%.o: %.cpp
	@mkdir -p $(OBJODIR);
	$(CPP) $(if $(findstring $<,$(DSRCS)),$(DFLAGS),$(CFLAGS)) $(COPTS_$(*F)) -o $@ -c $<

$(OBJODIR)/%.d: %.cpp
	@mkdir -p $(OBJODIR);
	@echo DEPEND: $(CPP) -M $(CFLAGS) $<
	@set -e; rm -f $@; \
	$(CPP) -M $(CFLAGS) $< > $@.$$$$; \
	sed 's,\($*\.o\)[ :]*,$(OBJODIR)/\1 $@ : ,g' < $@.$$$$ > $@; \
	rm -f $@.$$$$

$(OBJODIR)/%.o: %.s
	@mkdir -p $(OBJODIR);
	$(CC) $(CFLAGS) -o $@ -c $<

$(OBJODIR)/%.d: %.s
	@mkdir -p $(OBJODIR); \
	set -e; rm -f $@; \
	$(CC) -M $(CFLAGS) $< > $@.$$$$; \
	sed 's,\($*\.o\)[ :]*,$(OBJODIR)/\1 $@ : ,g' < $@.$$$$ > $@; \
	rm -f $@.$$$$

$(OBJODIR)/%.o: %.S
	@mkdir -p $(OBJODIR);
	$(CC) $(CFLAGS) -D__ASSEMBLER__ -o $@ -c $<

$(OBJODIR)/%.d: %.S
	@mkdir -p $(OBJODIR); \
	set -e; rm -f $@; \
	$(CC) -M $(CFLAGS) $< > $@.$$$$; \
	sed 's,\($*\.o\)[ :]*,$(OBJODIR)/\1 $@ : ,g' < $@.$$$$ > $@; \
	rm -f $@.$$$$

$(foreach lib,$(GEN_LIBS),$(eval $(call ShortcutRule,$(lib),$(LIBODIR))))

$(foreach image,$(GEN_IMAGES),$(eval $(call ShortcutRule,$(image),$(IMAGEODIR))))

$(foreach bin,$(GEN_BINS),$(eval $(call ShortcutRule,$(bin),$(BINODIR))))

$(foreach lib,$(GEN_LIBS),$(eval $(call MakeLibrary,$(basename $(lib)))))

$(foreach image,$(GEN_IMAGES),$(eval $(call MakeImage,$(basename $(image)))))

INCLUDES := $(INCLUDES) -I $(SDK_PATH)/include -I $(SDK_PATH)/extra_include
PDIR := ../$(PDIR)
INCLUDES += -I $(SDK_PATH)/driver_lib/include
INCLUDES += -I $(SDK_PATH)/include/espressif
INCLUDES += -I $(SDK_PATH)/include/lwip
INCLUDES += -I $(SDK_PATH)/include/lwip/ipv4
INCLUDES += -I $(SDK_PATH)/include/lwip/ipv6
INCLUDES += -I $(SDK_PATH)/include/nopoll
INCLUDES += -I $(SDK_PATH)/include/spiffs
INCLUDES += -I $(SDK_PATH)/include/ssl
INCLUDES += -I $(SDK_PATH)/include/json
INCLUDES += -I $(SDK_PATH)/include/openssl


## 学习收获
在工程概论这门课上，我们的课程主要以中期为分界线分为前后两个部分，前半期我们通过分组翻译《Exploring Engineering》这本书学习了在一个工程中作为一个工程师的角色需要了解的各个方面，从理论到实践，以及涉及到的各个领域的专业知识。
作为一名工程师，不仅需要强大的理论知识，还需要极强的实践精神和动手能力，前者就需要靠平时上课的日积月累，后者在这门课程的后半部分小有实践。第一次的实践中，我们通过节点和网关的通信，实现了将节点测得的温度数据进行传输，在首次实践中，我们学习到了焊接的技术和了解节点和网关的通信原理，在焊接中更多的考验的是耐心和细心。第二次的实践中，我们需要在户外旅行、智慧农业等几个主题中进行选择，经过小组讨论，基于我们的认知，选择了户外旅行。
从头脑风暴、视频剪辑到设计制作，离不开小组的密切合作，组长发挥统筹作用，结合每个组员的特长，合理分配任务，按时推进进度，保证最后顺利完成。完整的小组作业离不开密切的小组合作！
“纸上得来终觉浅，绝知此事要躬行。”在短暂的实践过程中，我们深深的感觉到自己所学知识的肤浅和在实际运用中的专业知识的匮乏，刚开始的一段时间里，感到无从下手，茫然不知所措。在学校总以为自己学的不错，一旦接触到实际，才发现自己知道的是多么少，这时才真正领悟到“学无止境”的含义!

## 团建计划
分头从网上或实体店购买开发板和传感器。

分别设计编写各模块所需要的程序。

选择时间将各模块组装成产品雏形。

美化产品外观，完成产品设计。
