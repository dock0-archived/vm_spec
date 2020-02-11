vm_spec
========

[![MIT Licensed](http://img.shields.io/badge/license-MIT-green.svg)](https://tldrlegal.com/license/mit-license)

My deployment spec for [dock0](https://github.com/dock0/dock0)

## Contents

This has the necessary files for [dock0](https://github.com/dock0/dock0) to run `dock0 install`

* config.yaml -- defines version of kernel, rootfs, and initrd to use when building the VM
* templates -- has the grub config templates to lay down so the VM can boot

The `dev/update.rb` script checks GitHub to see if any of the artifacts have updated versions.

## To use

The vm_updater Docker container will automate deploying this spec

```
docker run -ti -e REPO=https://github.com/dock0/vm_spec -v /run/vm/bootmnt:/run/vm/bootmnt docker.pkg.github.com/dock0/vm_updater/vm_updater
```

To use an alternate branch for the installation, specify it via the environment:

```
# this will use the dev branch
docker run -ti -e BRANCH=dev -e REPO=https://github.com/dock0/vm_spec -v /run/vm/bootmnt:/run/vm/bootmnt docker.pkg.github.com/dock0/vm_updater/vm_updater
```

## License

These scripts and config files are released under the MIT License. See the bundled LICENSE file for details.

