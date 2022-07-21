# วิธีทำแผ่น Boot ด้วย macOS เพื่อติดตั้ง Proxmox

## ดาวน์โหลดไฟล์ .iso จาก [https://www.proxmox.com/en/downloads](Download)

## แปลงไฟล์ .iso เป็นไฟล์ .dmg ด้วยคำสั่ง hdiutil
```sh
hdiutil convert -format UDRW -o proxmox-ve_*.dmg proxmox-ve_*.iso
```

## แสดงดิสก์ทั้งหมดในเครื่อง และเลือก Disk
```sh
diskutil list
diskutil unmountDisk /dev/diskX
```

## สร้าง Disk Boot
```sh
sudo dd if=proxmox-ve_*.dmg of=/dev/diskX bs=1m
```
