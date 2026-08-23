<h1 align="center">QEMU Render<br />
<div align="center">
  
[![Build]][build_url]
[![Version]][release_url]
[![Size]][release_url]

</div></h1>

Run QEMU hardware-accelerated graphics on headless Debian hosts without installing an Xorg server or desktop environment.

`qemu-render` provides the host-side Mesa and virglrenderer runtime used by QEMU for OpenGL, Vulkan/Venus, and native DRM contexts. It keeps hardware-accelerated EGL/GBM rendering, hardware Vulkan, VirGL/Venus, and AMDGPU/i915 native-context support available on servers, containers, and appliance-style systems while leaving out runtime components that are unnecessary for this use case.

## Features ✨

- Designed for headless Debian hosts with no Xorg server or desktop environment
- Hardware-accelerated EGL and GBM rendering through Mesa on Intel and AMD GPUs
- Supports the Mesa `crocus`, `iris`, `r600`, and `radeonsi` Gallium drivers
- Hardware Vulkan through Mesa ANV and HasVK on Intel GPUs and RADV/ACO on AMD GPUs
- Custom virglrenderer with VirGL, Venus, and `virgl_render_server` support
- Native DRM context support for AMDGPU and Intel i915
- QXL support through a reduced SPICE server runtime for QEMU's VNC display path

## Package design 📦

The package version-provides:

```text
libgbm1
libegl-mesa0
libspice-server1
libvirglrenderer1
