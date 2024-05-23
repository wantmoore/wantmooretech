# Wantmoore.tech
ESP Web Installer


# Merge the WLED bootloader and WLED bin
esptool --chip esp32 merge_bin -o ledeez_weact32_14_4-factory.bin --flash_mode dio --flash_freq 40m --flash_size 4MB 0x0 esp32_bootloader_v4.bin 0x10000 weact_esp32_core_v3.bin
esptool.py v4.4
Wrote 0x149be0 bytes to file New folder\ledeez_weact32_14_4-factory.bin, ready to flash to offset 0x0

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
