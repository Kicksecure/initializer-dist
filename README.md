# Implements Whonix's Verifiable Builds feature and initializes Whonix #

Contains a chroot-scripts-post.d script, that cleans up temporary files, logs,
and removed non-deterministic files using existing Debian prerm and postrm
maintainer scripts. This helps auditors verifying binary builds of Whonix to
check for backdoors and integrity.

On first boot, all packages that were previously deconfigured, are reinstalled
to restore full functionality of the system.

Deletes random seeds.  Since these should not be included in a redistributed
image. Also sometimes called 'golden' image.

- /var/lib/urandom/random-seed
- /var/lib/systemd/random-seed
- /var/lib/random-seed
- See also: https://systemd.io/RANDOM_SEEDS.html
## How to install `whonix-initializer` using apt-get ##

1\. Download [Whonix's Signing Key]().

```
wget https://www.whonix.org/patrick.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add Whonix's signing key.

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg add ~/patrick.asc
```

3\. Add Whonix's APT repository.

```
echo "deb https://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
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
