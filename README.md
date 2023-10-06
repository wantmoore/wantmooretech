# Wantmoore.tech
ESP Web Installer


# Merge the WLED bootloader and WLED bin
esptool --chip esp32 merge_bin -o WLED_0.14.0-b6_ESP32-bootloader.bin --flash_mode dio --flash_freq 40m --flash_size 4MB 0x0 wled_esp32_bootloader_v4.bin 0x10000 WLED_0.14.0-b6_ESP32.bin

# Flash the bin
esptool.py write_flash 0x0 WLED_0.14.0-b6_ESP3-bootloader.bin

# LEDeez firmware overrides (need tested)
For items with no parameter, prefix with -D like -D WLED_DEBUG

For entries with a numeric parameter, use the syntax of -D LEDPIN=16

For non-numeric entries use both types of quotes like -D SERVERNAME='"WLED-C3"

    D SERVERNAME='"LEDeez"'
    -D LEDPIN=16
    -D PIXEL_COUNTS="50,50"
    -D DATA_PINS="16,4"
