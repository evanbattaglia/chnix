## Usage

```
chnix # list nix store paths
chnix path/to/flake#myapp_v1 # puts myapp_v1 flake/ bin in path
chnix rm myapp # moves all -myapp nix store paths from path
```

## Usage for specific apps

```
ch_myapp() {
  chnix_specific_app chmyapp myapp path/to/flake#myapp_v 1_0_1 "$@";
}

$ chmyapp 1_0_1
switched to 1_0_1
$ myapp --version
myapp version 12.0.1

$ chmyapp 1_0_2
Removing /nix/store/9isc4pny6mzqqmqq8mfskpxzwp16sxhb-myapp/bin from path
switched to 1_0_2
$ myapp --version
myapp version 12.0.2

$ chmyapp system
Removing /nix/store/3sn4p6xz0ccwsdjwdv23qkw19wf38zwz-myapp/bin from path
$ myapp --version # my system installed
myapp version 12.1.3
```


