# bisq-gradle

Bisq v1 gradle build plugins

## bisq.post-build plugin
Gradle plugin for copying a repo distribution's run script and lib dir to root project directory.

### Usage

#### Define git submodule 'bisq-gradle' in your repo

```asciidoc
$ git submodule add https://github.com/bisq-network/bisq-gradle.git
```

If you need to use a non-main branch of this repo, use the -b _branch-name_ option:

```asciidoc
git submodule add -b add-post-build-plugin https://github.com/ghubstan/bisq-gradle.git
```

This will add 'bisq-gradle' to .gitmodules:

```asciidoc
[submodule "bisq-gradle"]
    path = bisq-gradle
    url = https://github.com/bisq-network/bisq-gradle.git
```

#### Link submodule 'bisq-gradle' in your repo

```asciidoc
$ git add bisq-gradle 
$ git commit -m "Add submodule bisq-gradle" bisq-gradle .gitmodules 
$ git push
```

#### Register and clone new submodule 'bisq-gradle' in your repo

```asciidoc
$ git submodule init 
$ git submodule update
```

#### Alternatively clone your repo with --recursive option

```asciidoc
$ git clone --recursive your-repo.git   
```

#### Apply plugin `bisq.post-assemble` to your Gradle application project's build:

```asciidoc
plugins {
    id 'application'
    id 'bisq.post-build'
}
```

The `bisq.post-build` plugin's `postBuild` will execute at the end of your project's build task `build`.

