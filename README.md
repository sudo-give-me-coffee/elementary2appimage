# elementary4all
### What is?
Elementary OS has a set of applications called "curated apps" that is only available for Elementary OS, normally these apps can't be run installed by .deb package (elementary uses .deb for application distribution), so theonly alternative is compile from GitHub, but it is complicated and tedious,  this tool turn the process much more easy,  for example:

After install build dependencies (usually elementary-sdk dependencies) the workflow for build a "curated app" is:

1) Translate app name to corresponding GitHub repo:

```

Project name: com.github.hannesschulze.optimizer

GitHub repo: https://github.com/hannesschulze/optimizer

```

2) Determine which type of build mechanism (cmake or meson)

3) Configure build environment

4) Run build mechanism

5) Install gschema of application

With `elementary4all` you can do:

```
./elementary4all com.github.hannesschulze.optimizer
```
And all above will be done automatically

<hr>

### Which is the dependendencies?
Except `git` all dependendencies is for application build (note that this doesn't cover all apps)

* git
* meson
* ninja
* cmake
* vala
* gobject-2.0
* glib-2.0
* granite
* gtk+-3.0
* libgee
* libwnck-3.0
* libunity

On `apt` based system this command install all dependencies:

```

sudo apt install build-essential desktop-file-utils gettext gobject-introspection libgee-0.8-dev libgirepository1.0-dev
libglib2.0-dev libgranite-dev libgtk-3-dev libunity-dev libxml2-dev libxml2-utils meson valac valadoc git cmake libunity-dev libwnck-3-dev

```

<hr>

### Where Applications is installed?

As elementary4all is a working-in-progress tool the "dist" version of compiled applications aren't finalized, but a runnable version is created on:
```
 com.github.<developer name>.<app name>/<app name>.AppDir
```

You can run the application by double clicking on AppRun file


<hr>

### What features is missing?:

The objective of this this tools is be the most seamless possible so are a variety of feature missing, but some already made:

- [x] Download automatically app source code
- [x] Determine build mechanism and compile the app automatically
- [ ] Install build dependendencies automatically
- [ ] Configure the basic build environment on first run
- [ ] Fetch app runtime libs and copy to AppDir
- [ ] Create an AppImage
- [ ] Integrate the AppImage on system after build automatically

I really need help to finish it :smiley:
