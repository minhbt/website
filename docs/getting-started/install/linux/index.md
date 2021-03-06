---
title: Install Mono on Linux
---

The Linux community has made Mono available for various distributions, check the [download page](/download) for a list of packages.

Installation
------------

Regardless of your distribution, you will need the Mono Project public Jenkins GPG signing key, which package managers require:

[http://download.mono-project.com/repo/xamarin.gpg](http://download.mono-project.com/repo/xamarin.gpg)

### Debian, Ubuntu, and derivatives

Add the GPG key in a root shell with:

**`apt-key add xamarin.gpg`**

Next, add the package repository in a root shell:

**`echo "deb http://download.mono-project.com/repo/debian wheezy main" > /etc/apt/sources.list.d/mono-xamarin.list`**

Update your package cache if necessary, and run a package upgrade to upgrade existing packages to the latest available.

### CentOS, Fedora, and derivatives

Add the GPG key in a root shell with:

**`rpm --import xamarin.gpg`**

Next, add the package repository in a root shell:

**`yum-config-manager --add-repo http://download.mono-project.com/repo/centos/`**

Update your package cache if necessary, and run a package upgrade to upgrade existing packages to the latest available.

Users of CentOS or RHEL (or similar distributions) may need to add the [EPEL repository](https://fedoraproject.org/wiki/EPEL) to their system to satisfy all dependencies

Usage
-----

The package ***mono-devel*** should be installed to compile code.

The package ***mono-complete*** should be installed to install everything - this should cover most cases of "assembly not found" errors.

Notes
-----

After the installation completed successfully, it's a good idea to run through the basic hello world examples on [this page](/docs/getting-started/mono-basics/) to verify Mono is working correctly.

**Note:** Mono on Linux by default doesn't trust any SSL certificates so you'll get errors when accessing HTTPS resources. To import Mozilla's list of trusted certificates and fix those errors, you need to run `mozroots --import --sync`.
