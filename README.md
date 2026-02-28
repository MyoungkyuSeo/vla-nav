### VLA for navigation

install habitat-sim & habitat-lab following instructions on github

common errors on headless (lambda compute):

when error:
'Platform::WindowlessEglApplication::tryCreateContext(): unable to find CUDA device 0 among 3 EGL devices in total
WindowlessContext: Unable to create windowless context'

Run:

# Install NVIDIA GL/EGL GLVND libs (Lambda Ubuntu may need force-overwrite due to a JSON file conflict)
sudo apt update
sudo apt install -y -o Dpkg::Options::="--force-overwrite" libnvidia-gl-570-server
sudo apt -f install -y
sudo dpkg --configure -a
sudo ldconfig

# Reboot recommended after driver stack changes
sudo reboot

export __EGL_VENDOR_LIBRARY_FILENAMES=/usr/share/glvnd/egl_vendor.d/10_nvidia.json
