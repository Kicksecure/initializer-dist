# Initializes Linux distributions, Release Upgrades and Legacy #

Contains a chroot-scripts-post.d script, that cleans up temporary files, logs.

Deletes random seeds. Since these should not be included in a redistributed
image. Also sometimes called 'golden' image.

- /var/lib/urandom/random-seed
- /var/lib/systemd/random-seed
- /var/lib/random-seed
- See also: https://systemd.io/RANDOM_SEEDS.html
## How to install `whonix-initializer` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.whonix.org/derivative.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add the APT Signing Key..

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.whonix.org bullseye main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `whonix-initializer`.

```
sudo apt-get install whonix-initializer
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions. (Replace `generic-package` with the actual name of this package `whonix-initializer`.)

* **A)** [easy](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`whonix-initializer` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
