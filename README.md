# pl2303_kline_10400
Modified stock linux pl2303 usb-serial driver to work with non-standard 10400 baud rate (for car diagnostic applications)

1. Install linux headers/source with your package manager
2. Clone the code and cd into cloned dir
3. sudo rmmod pl2303
4. under root add pl2303 driver blacklist, for example:
cat > /etc/modprobe.d/pl2303.conf
blacklist pl2303

5. Type make in cloned dir
6. sudo modprobe usbserial
7. sudo insmod ./pl2303_kline_10400.ko
8. plug your pl2303 k-line adapter
9. (CAN BE CONFIGURED WITH UDEV RULES) sudo chmod 666 /dev/ttyUSB0 (last digit can differ, see dmesg)
10. ln -s /dev/ttyUSB0 ~/wine/dosdevices/com1
11. Run you diagnostic software and choose com1 as port

Good luck!

