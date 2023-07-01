# Unused

`unused` is a tool that monitors a directory and prints the paths of all files
that have _not_ been accessed for the duration of its execution.

For example, this is useful to declutter a large repository from source files
that are not ever accessed by its build command. This can also be used to
minimize an embedded or container Linux rootfs by identifying all files that
are not required to boot.

## Installation

1. Install its dependency:

```
sudo pip install pyinotify
```

2. Install `unused` system-wide (not strictly required but nice):

```
sudo cp unused /usr/bin/
```

## Usage

1. Start monitoring a directory:

```
unused /directory/to/monitor
```

(if no directory is provided, it will default to the current working directory)

2. In another terminal, run a command accessing that directory. (e.g: `make`)
3. Hit `Ctrl + C` to stop `unused`.
4. `unused` will print the paths of all files under that directory that have
   not been accessed.
