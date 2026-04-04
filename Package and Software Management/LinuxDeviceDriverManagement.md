# Supplemental: Linux Device & Driver Management

## 1. Everything is a File
In Linux, hardware devices are represented as **device files** located in the `/dev` directory.
* `/dev/sda`: The first SCSI/SATA hard drive.
* `/dev/sr0`: The first optical drive (CD/ROM).
* `/dev/null`: The "data sink" or black hole (discards all data sent to it).
* `/dev/usblp0`: A USB printer.

## 2. Device Categories
* **Block Devices**: Can store data (Hard drives, USB sticks). They move data in "blocks."
* **Character Devices**: Input/Output data one character at a time (Keyboards, Mice, Monitors).
* **Pipe Devices**: Similar to character devices but send output to another **process** instead of hardware.
* **Socket Devices**: Used for communication between multiple processes.

## 3. The udev Manager
* **udev**: The Linux device manager. It automatically creates or removes device files in `/dev` when you plug or unplug hardware.
* **udevd**: The "daemon" (background process) that listens to the Kernel for hardware changes.

## 4. Hardware Discovery Commands (The "Inventory" Tools)
Use these CLI commands to see what is actually connected to the system:
* `ls /dev`: Lists all raw device files.
* `lspci`: Lists all devices on the **PCI bus** (Internal cards, NICs, etc.).
* `lsusb`: Lists all **USB** devices (Mice, Keyboards, External drives).
* `lsscsi`: Lists **SCSI** devices (usually hard drives).
* `lpstat -p`: Shows all printers and their current status.
* `dmesg`: Shows the **Kernel Ring Buffer**. Use this to see the "live" log of the Kernel recognizing a device as it's plugged in.

## 5. Printer Management (CUPS & lpadmin)
Linux uses **CUPS** (Common Unix Printing System) to handle printing.
* **PPD Files**: Postscript Printer Description files. These act as the "drivers" for printers.
* **Command Line Install**:
    * `sudo lpadmin -p [PrinterName] -m [Driver.ppd]`: Adds a printer and assigns its driver.
    * The `-m` flag tells the system where the PPD driver file is located (usually `/usr/share/cups/model/`).

## 6. GUI Management (GNOME)
* **Path**: Settings > Printers.
* **Unlocking**: Requires `sudo` or `printadmin` privileges to make changes.
* **Driver Options**:
    1. **Search**: Uses `PackageKit` to find drivers in repositories.
    2. **Database**: Select from a pre-installed list.
    3. **PPD File**: Manually upload a specific driver file.
