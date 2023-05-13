# Gnome Shell Repair
shell can often Break due from dependencies for compiling! Here's how to repair it

https://www.reddit.com/r/Fedora/comments/jxhtki/uninstall_protected_gnome_apps_on_fedora_ws_33/  
https://www.reddit.com/r/Fedora/comments/12pqmnl/opengl_broken_after_installing_mesa_packages/

```
# Fix broken MESA
sudo dnf swap mesa-vdpau-drivers-freeworld.i686 mesa-vdpau-drivers.i686 --skip-broken
sudo dnf swap mesa-vdpau-drivers-freeworld mesa-vdpau-drivers --skip-broken
sudo dnf swap mesa-va-drivers-freeworld mesa-va-drivers --skip-broken
sudo dnf swap mesa-va-drivers-freeworld.i686 mesa-va-drivers.i686 --skip-broken

# Uninstall Gnome
sudo dnf remove --setopt protected_packages= gnome-shell

# Reinstall Gnome
sudo dnf install gnome-shell

# Restart GDM
sudo systemctl start gdm
sudo systemctl enable gdm
```
