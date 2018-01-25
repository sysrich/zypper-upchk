# zypper-upchk
Generic "update check" subcommand for zypper

Intended to compliment the built-in `zypper pchk` command which only reports available patches for a product.
This is not useful for rolling releases like openSUSE Tumbleweed or [openSUSE MicroOS](http://en.opensuse.org/Kubic:MicroOS).

# Initial goal

Check for updates awaiting for a `zypper dup`

Report back:
* Number of packages
* Any conflicts or other dup blockers
* That the filesystem is read-only if the product requires read-only rootfs

Use cases:
* CLI tool for sysadmin
* systemd triggered, with salt grains for velum to parse

# Long Term Goals

* IF product should be updated using up (eg. Leap/SLE) THEN Check for updates awaiting for a `zypper up`
* IF product offers product upgrades (eg. Leap Major & Minor Releases, SLE Releases & Service Packs) THEN Check for available migration targets
* IF updates are pending, have a switch to automatically call the appropriate update command (`up`, `dup`, or `migrate` respectively)
