1: mount (to be sure)
sudo mount /dev/nvme0n1p1 /boot

2: create the fallback directory
sudo mkdir -p /boot/EFI/Boot

3: copy limine efi file there
sudo cp /boot/EFI/limine/BOOTX64.EFI /boot/EFI/Boot/bootx64.efi (stock arch)
sudo cp /boot/EFI/limine/limine_x64.EFI /boot/EFI/Boot/bootx64.efi (cachyos)

4: verify
ls -l /boot/EFI/Boot/bootx64.efi

if you use ventoy, you should be able to select the bootx64 method in f4 menu,
other than that, msi bootloader should recognize your drive where is linux and limine installed now
and, you shouldn't waste your time by manually going to limine bootloader folder and booting from the file!
