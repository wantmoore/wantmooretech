# Wantmoore.tech
ESP Web Installer


# Merge the WLED bootloader and WLED bin
esptool --chip esp32 merge_bin -o WLED_0.14.0-b6_ESP32-bootloader.bin --flash_mode dio --flash_freq 40m --flash_size 4MB 0x0 wled_esp32_bootloader_v4.bin 0x10000 WLED_0.14.0-b6_ESP32.bin

# Flash the bin
esptool.py write_flash 0x0 WLED_0.14.0-b6_ESP3-bootloader.bin
