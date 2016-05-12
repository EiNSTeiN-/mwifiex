# mwifiex
mwifiex driver with surface book patch

# How to install

Build the modules.

```
make
```

Make sure to backup and remove the old module

```
sudo rmmod mwifiex_pcie
sudo cp -r /lib/modules/$(uname -r)/kernel/drivers/net/wireless/mwifiex/ ~/mwifiex-bak
sudo rm /lib/modules/$(uname -r)/kernel/drivers/net/wireless/mwifiex/*.ko
sudo depmod
```

Install the new modules (this will copy files to `/lib/modules/$(uname -r)/extra`)

```
sudo make install
sudo modprobe mwifiex_pcie
```
