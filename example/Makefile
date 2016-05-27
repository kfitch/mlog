TARGET = example

MLOG_DIR = ..
CPPFLAGS += -g3 -pthread -I $(MLOG_DIR)/include -DMLOG_SECTION=dont_output

$(TARGET).mlogmap: $(TARGET)
	@$(MLOG_DIR)/generate_mlogmap.sh $(TARGET) > $(TARGET).mlogmap
	objcopy -R dont_output $(TARGET) $(TARGET).filtered

$(TARGET): $(TARGET).cpp mlog_server.cpp ../src/mlog.c

.PHONY :  clean
clean:
	rm -rf *.o $(TARGET) $(TARGET).exe $(TARGET).mlogmap

