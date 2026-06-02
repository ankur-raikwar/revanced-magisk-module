# ReVanced Magisk Module
[![CI](https://github.com/ankur-raikwar/revanced-magisk-module/actions/workflows/ci.yml/badge.svg?event=schedule)](https://github.com/ankur-raikwar/revanced-magisk-module/actions/workflows/ci.yml)

Extensive ReVanced builder  

Get the [latest CI release](https://github.com/ankur-raikwar/revanced-magisk-module/releases).

Use [**zygisk-detach**](https://github.com/j-hc/zygisk-detach) to detach YouTube and YT Music from Play Store if you are using magisk modules. 

<details><summary><big>Features</big></summary>
<ul>
 <li>Support all present and future ReVanced and <a href="https://github.com/inotia00/revanced-patches">ReVanced Extended</a> apps</li>
 <li> Can build Magisk modules and non-root APKs</li>
 <li> Updated daily with the latest versions of apps and patches</li>
 <li> Optimize APKs and modules for size</li>
 <li> Modules</li>
    <ul>
     <li> recompile invalidated odex for faster usage</li>
     <li> receive updates from Magisk app</li>
     <li> do not break safetynet or trigger root detections</li>
     <li> handle installation of the correct version of the stock app and all that</li>
     <li> support Magisk and KernelSU</li>
    </ul>
</ul>
Note that the <a href="../../actions/workflows/ci.yml">CI workflow</a> is scheduled to build the modules and APKs everyday using GitHub Actions if there is a change in ReVanced patches. You may want to disable it.
</details>

## To include/exclude patches or patch other apps

 * Star the repo :eyes:
 * Use the repo as a [template](https://github.com/new?template_name=revanced-magisk-module&template_owner=ankur-raikwar)
 * Customize [`config.toml`](./config.toml) using [rvmm-config-gen](https://j-hc.github.io/rvmm-config-gen/)
 * Run the build [workflow](../../actions/workflows/build.yml)
 * Grab your modules and APKs from [releases](../../releases)

also see here [`CONFIG.md`](./CONFIG.md)

## Building Locally
### On Termux
```console
bash <(curl -sSf https://raw.githubusercontent.com/ankur-raikwar/revanced-magisk-module/main/build-termux.sh)
```

### On Desktop
```console
$ git clone https://github.com/ankur-raikwar/revanced-magisk-module
$ cd revanced-magisk-module
$ ./build.sh
```

## Add the Protection Rule File
#### We need to create a special configuration file that tells Git to protect your edited file.
* On your new (root of) repository page, click Add file > Create new file.
* Name the file exactly: .gitattributes
* In the file content box, type your target filename followed by merge=ours.
> For example:
```console
config.toml merge=ours
README.md merge=ours
```
#### Activate the Protection Driver using CodeSpaces Terminal
```console
$ git config merge.ours.driver true
```

## Pull Future Updates

#### Connect to the original Template (One-time per template/fork)
```console
$ git remote add upstream https://github.com/j-hc/revanced-magisk-module.git
```

#### Fetch and Merge the Updates (Run these two commands whenever you want to check for and apply updates)
```console
$ git fetch upstream
$ git merge upstream/main --allow-unrelated-histories
$ git push origin main

