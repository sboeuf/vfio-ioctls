# vfio-ioctls

The vfio-ioctls crate provide safe wrappers over the
[VFIO API](https://www.kernel.org/doc/Documentation/vfio.txt), a set of
ioctls are used to expose direct device access to userspace in a secure,
IOMMU protected environment. The ioctls include create and configure
VFIO container, group, device and IOMMU related objects on Linux.
The vfio-ioctls crate provide three structures and a trait to access
these ioctls:
- `VfioContainer` - wrapper over a VFIO container object
- `VfioDevice` - to access underline hardware devices
- `VfioDmaMapping` - implements the ExternalDmaMapping trait
- `ExternalDmaMapping` - Trait for triggering the DMA mapping update
related to an external device

For further details, please check the code documentation.

## Supported Platform

- x86_64

## Usage

Add the following to your `Cargo.toml`:
```toml
vfio-ioctls = { git = "https://github.com/cloud-hypervisor/vfio-ioctls", branch = "ch" }
```

Then you can import the structs or trait where you need them:
```rust
// Import the required structs
use vfio_ioctls::{VfioContainer, VfioDevice, VfioDmaMapping};

// Import the required trait
use vfio_ioctls::ExternalDmaMapping;
```

## License

This code is licensed under Apache-2.0 or BSD-3-Clause.
