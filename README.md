# Microsoft's fork of OpenOCD

**Public pull requests are not accepted to this repo.** If you would like to
contribute changes to OpenOCD, please contribute directly to upstream following
the [OpenOCD Developer's Guide](http://openocd.org/doc/doxygen/html/index.html).

This is a soft fork of the [OpenOCD project](http://openocd.org/) where
Microsoft stages changes and provides binaries for Windows and Linux. The Linux
binaries are statically linked with [musl](https://www.musl-libc.org/) and are
highly portable across a wide range of Linux distributions. In addition, this
fork incorporates changes from
[Raspberry Pi](https://github.com/raspberrypi/openocd),
[STMicroelectronics](https://github.com/STMicroelectronics/OpenOCD), and [Azure
Sphere](https://thirdpartysource.microsoft.com/) to improve compatibility with
the embedded development ecosystem.

This project has adopted the [Microsoft Open Source Code of Conduct](
https://opensource.microsoft.com/codeofconduct/). For more information see the
[Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any
additional questions or comments.

## Branching strategy

The `master` branch mirrors `master` in the upstream repository and is updated
whenever OpenOCD releases. The `microsoft/main` branch follows `master` and
includes small additions like this README and the scripts required to produce
statically linked Linux binaries.

After every upstream tagged OpenOCD release, a new branch of the form
`microsoft/rel/<version>` will be created based on `microsoft/main`. Patches
from the Raspberry Pi, STMicroelectronics, and Azure Sphere forks will be
applied to this new branch. After validating the build, the tip of the branch
will be tagged as `ms-v<version>` and added as a
[release](https://github.com/microsoft/openocd/releases). Because OpenOCD
releases are infrequent, it's more likely that the vendor forks and OpenOCD
itself will have significant changes in the time between releases. Patches are
are not applied directly to `microsoft/main` to avoid merge conflicts from stale
vendor fork changes. Vendors are also encouraged to contribute their changes to
upstream OpenOCD to avoid the need for patches at all.