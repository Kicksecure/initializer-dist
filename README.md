# Implements Whonix's Verifiable Builds feature and initializes Whonix #

Contains a chroot-scripts-post.d script, that cleans up temporary files, logs,
and removed non-deterministic files using existing Debian prerm and postrm
maintainer scripts. This helps auditors verifying binary builds of Whonix to
check for backdoors and integrity.

On first boot, all packages that were previously deconfigured, are reinstalled
to restore full functionality of the system.
## How to install `whonix-initializer` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `whonix-initializer`.

```
sudo apt-get install whonix-initializer
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `whonix-initializer` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`whonix-initializer` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
