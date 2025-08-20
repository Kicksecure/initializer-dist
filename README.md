# Initializes Linux distributions, Release Upgrades and Legacy #

Contains a chroot-scripts-post.d script, that cleans up temporary files, logs.

Deletes random seeds. Since these should not be included in a redistributed
image. Also sometimes called 'golden' image.

- /var/lib/urandom/random-seed
- /var/lib/systemd/random-seed
- /var/lib/random-seed
- See also: https://systemd.io/RANDOM_SEEDS.html

## How to install `initializer-dist` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/keys/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com trixie main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `initializer-dist`.

```
sudo apt-get install initializer-dist
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `initializer-dist`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Premium Support](https://www.kicksecure.com/wiki/Premium_Support)

## Donate ##

`initializer-dist` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!
