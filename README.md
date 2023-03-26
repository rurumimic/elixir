# Elixir

- [elixir](https://elixir-lang.org/)
  - [getting started](https://elixir-lang.org/getting-started/introduction.html)
    - [mix](https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html)
  - [docs](https://elixir-lang.org/docs.html)
  - [install](https://elixir-lang.org/install.html)
  - [learning](https://elixir-lang.org/learning.html): book, course, etc.
  - [blog](https://elixir-lang.org/blog/)

## Start

### Install Elxir

- [Compatibility between Elixir and Erlang/OTP](https://hexdocs.pm/elixir/compatibility-and-deprecations.html#compatibility-between-elixir-and-erlang-otp)
- [version manager](https://elixir-lang.org/install.html#compiling-with-version-managers)
  - [asdf](https://github.com/asdf-vm/asdf): Extendable version manager with support for Ruby, Node.js, Elixir, Erlang & more

#### asdf

- [Getting Started](https://asdf-vm.com/guide/getting-started.html)
- ohmyzsh plugin: [asdf](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/asdf)

```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.11.3
```

dependencies:

```bash
# ubuntu
sudo apt -y install \
build-essential autoconf m4 libncurses5-dev libwxgtk3.0-gtk3-dev libwxgtk-webview3.0-gtk3-dev libgl1-mesa-dev libglu1-mesa-dev libpng-dev libssh-dev unixodbc-dev xsltproc fop libxml2-utils libncurses-dev openjdk-11-jdk
```

```bash
# vi ~/.zshrc
plugins=(asdf)

# append completions to fpath
fpath=(${ASDF_DIR}/completions $fpath)
# initialise completions with ZSH's compinit
autoload -Uz compinit && compinit
```

#### asdf-elixir

add plugins:

```bash
asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git
asdf plugin add elixir https://github.com/asdf-vm/asdf-elixir.git
```

erlang and elixir versions:

```bash
asdf list all erlang
asdf list all elixir
```

install erlang and elixir:

```bash
export KERL_CONFIGURE_OPTIONS="--disable-debug --without-javac"
asdf install erlang 25.3

asdf install elixir 1.14.3
```

#### Local Elixir

```bash
asdf local erlang 25.3
asdf local elixir 1.14.3

# vi .tool-versions
elixir 1.14.3-otp-25
```

#### Elixir Version

```bash
elixir --version
```

### Hello World

- helloworld: [README.md](src/helloworld/README.md)
  - [mix.exs](src/helloworld/mix.exs)
  - lib/[hello_world.ex](src/helloworld/lib/hello_world.ex)
  - test/[hello_world_test.exs](src/helloworld/test/hello_world_test.exs)
  - test/[test_helper.exs](src/helloworld/test/test_helper.exs)

create project:

```bash
mix new helloworld --module HelloWorld
cd helloworld
```

test:

```bash
mix test

Compiling 1 file (.ex)
Generated helloworld app
..
Finished in 0.01 seconds (0.00s async, 0.01s sync)
1 doctest, 1 test, 0 failures

Randomized with seed 336910
```

compile:

```bash
mix compile

Compiling 1 file (.ex)
Generated helloworld app
```

interactive shell:

```bash
iex -S mix

Interactive Elixir (1.14.3) - press Ctrl+C to exit (type h() ENTER for help)
iex> recompile()
Compiling 1 file (.ex)
:ok
iex> recompile()
:noop
```
