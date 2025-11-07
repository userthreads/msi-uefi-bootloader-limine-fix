# MSI UEFI Bootloader Limine Fix

This guide helps you set up the Limine bootloader on MSI motherboards using UEFI.

---

## Steps

### 1. Mount Your EFI Partition

```sh
sudo mount /dev/nvme0n1p1 /boot
```
*(Make sure to update `/dev/nvme0n1p1` to match your system's EFI partition.)*

---

### 2. Create the Fallback Directory

```sh
sudo mkdir -p /boot/EFI/Boot
```

---

### 3. Copy Limine EFI File

- **For Stock Arch Linux:**
  ```sh
  sudo cp /boot/EFI/limine/BOOTX64.EFI /boot/EFI/Boot/bootx64.efi
  ```
- **For CachyOS:**
  ```sh
  sudo cp /boot/EFI/limine/limine_x64.EFI /boot/EFI/Boot/bootx64.efi
  ```

---

### 4. Verify

```sh
ls -l /boot/EFI/Boot/bootx64.efi
```

---

## Notes

- **With Ventoy:**  
  You should be able to select the `bootx64` method in the F4 menu.

- **Other Cases:**  
  The MSI bootloader should automatically recognize your drive where Linux and Limine are installed.  
  You don't need to manually navigate to the Limine bootloader folder or boot from its file! Keep in mind that this can break Windows boot!

---
