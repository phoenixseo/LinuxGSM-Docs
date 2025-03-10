# glibc

## Summary

Most servers require a specific version of glibc installed. Newer distros normally have the required version. However the older the distro the less likely the server will run. Check the requirements below. If you have an older distro the game server may still run with a [glibc fix](glibc.md#glibc-fixes).

## Server Requirements

A complete list can be found [here](https://linuxgsm.com/data/glibc).

## Distro glibc Versions

List of distros and there glibc version.

| Distro | glibc |
| :--- | :--- |
| CentOS 7 | 2.17 |
| CentOS 8 | 2.28 |
| Fedora 27 | 2.26 |
| Fedora 28 | 2.27 |
| Fedora 29 | 2.28 |
| Fedora 30 | 2.29 |
| Debian 8 | 2.19 |
| Debian 9 | 2.24 |
| Debian 10 | 2.28 |
| Ubuntu 16.04 LTS | 2.23 |
| Ubuntu 18.04 LTS | 2.27 |

[distrowatch.com](http://distrowatch.com) is also a great source to find this information.

glibc version history available on [Wikipedia](https://en.wikipedia.org/wiki/GNU_C_Library#Version_history).

## glibc fixes

{% hint style="warning" %}
glibc fixes has now been deprecated. Due to the small number of game servers supporting it.
{% endhint %}

> Many of the servers can work on distros with older _glibc_ versions by using the _glibc_ fixes that are available with LinuxGSM.

If your distro does not meet the glibc requirements LinuxGSM will download the glibc files to the `lgsm/lib` directory to be used by the game server. Because of this even if your dedicated server does not meet the glibc requirements the game server should still work.

These fixes prevent errors similar to the following:

```text
version `glibc_2.15′ not found
```

```text
./7DaysToDie.x86: /usr/lib/libstdc++.so.6: version glibcXX_3.4.15 not found (required by ./7DaysToDie.x86)
./7DaysToDie.x86: /lib/libc.so.6: version glibc_2.15 not found (required by ./7DaysToDie.x86)
./7DaysToDie.x86: /lib/libm.so.6: version glibc_2.15 not found (required by ./7DaysToDie.x86)
```

## External Links

* [distrowatch.com](http://distrowatch.com/)
* [glibc Homepage](http://www.gnu.org/software/libc/)

