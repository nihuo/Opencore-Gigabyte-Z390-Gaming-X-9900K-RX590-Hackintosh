# Opencore-Gigabyte-Z390-Gaming-X-9900K-RX590-Hackintosh

OSX 12.2.1

![image](https://raw.githubusercontent.com/nihuo/Opencore-Gigabyte-Z390-Gaming-X-9900K-RX590-Hackintosh/main/IMG/about.jpg)

初始的EFI来自[黑果小兵](https://blog.daliansky.net/), 改动一个地方。
1. 为解决睡眠后自动唤醒问题，将蓝牙对应的USB口用Hackintool改为internal. 
   ![image](https://raw.githubusercontent.com/nihuo/Opencore-Gigabyte-Z390-Gaming-X-9900K-RX590-Hackintosh/main/IMG/hackintool.jpg)
2. 然后将导出的SSDT-UIAC.aml拷贝到EFI/OC/ACPI, 将导出的USBPorts.kext拷贝到EFI/OC/Kexts
3. 在config.plist ACPI段加入如下内容
```
                <dict>
                    <key>Comment</key>
                    <string>USBIAC</string>
                    <key>Enabled</key>
                    <true/>
                    <key>Path</key>
                    <string>SSDT-UIAC.aml</string>
                </dict>
```

