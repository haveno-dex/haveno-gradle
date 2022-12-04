# haveno-gradle

Haveno v1 gradle build plugins

## haveno.post-build plugin
Gradle plugin for copying a repo distribution's run script and lib dir to root project directory.

### Usage

#### Define git submodule 'haveno-gradle' in your repo

```asciidoc
$ git submodule add https://github.com/haveno-dex/haveno-gradle.git
```

If you need to use a non-main branch of this repo, use the -b _branch-name_ option:

```asciidoc
git submodule add -b add-post-build-plugin https://github.com/ghubstan/haveno-gradle.git
```

This will add 'haveno-gradle' to .gitmodules:

```asciidoc
[submodule "haveno-gradle"]
    path = haveno-gradle
    url = https://github.com/haveno-dex/haveno-gradle.git
```

#### Link submodule 'haveno-gradle' in your repo

```asciidoc
$ git add haveno-gradle 
$ git commit -m "Add submodule haveno-gradle" haveno-gradle .gitmodules 
$ git push
```

#### Register and clone new submodule 'haveno-gradle' in your repo

```asciidoc
$ git submodule init 
$ git submodule update
```

#### Alternatively clone your repo with --recursive option

```asciidoc
$ git clone --recursive your-repo.git   
```

#### Apply plugin `haveno.post-assemble` to your Gradle application project's build:

```asciidoc
plugins {
    id 'application'
    id 'haveno.post-build'
}
```

The `haveno.post-build` plugin's `postBuild` will execute at the end of your project's build task `build`.

