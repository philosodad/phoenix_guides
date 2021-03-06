The aim of this first guide is to get a Phoenix application up and running as quickly as possible.

Before we begin, let's take a minute to review the "Dependencies" section of the [Overview Guide](http://www.phoenixframework.org/docs/overview). By installing any necessary system dependencies beforehand, we'll be able to get our application installed and running smoothly.

We will need to install Elixir and Erlang. The Elixir site itself has the latest and most complete [installation information](http://elixir-lang.org/install.html). Currently, Phoenix requires Elixir version 1.0.4 or greater which in turn requires Erlang version 17.5 or greater.

Let's get started.

First, if we have just installed Elixir, let's install the Hex package manager:

```console
$ mix local.hex
```

Now we are ready to fetch the Phoenix installer:

```console
$ mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v0.13.1/phoenix_new-0.13.1.ez
```

> Note: if the Phoenix archive won't install properly with this command, we can download the file directly from our browser, save it to the filesystem, and then run: `mix archive.install /path/to/local/phoenix_new.ez`.

Now we can run `mix phoenix.new` from any directory in order to bootstrap our Phoenix application. Phoenix will accept either an absolute or relative path for the directory of our new project. Assuming that the name of our application is `hello_phoenix`, either of these will work.

```console
$ mix phoenix.new /Users/me/work/elixir-stuff/hello_phoenix
```

```console
$ mix phoenix.new hello_phoenix
```

> A note about [Brunch.io](http://brunch.io/) before we begin: Phoenix will use Brunch.io for asset management by default. Brunch.io's dependencies are installed via the node package manager, not mix. Phoenix will prompt us to install them at the end of the `mix phoenix.new` task. If we say "no" at that point, and if we don't install those dependencies later with `npm install`, our application will raise errors when we try to start it, and our assets may not load properly. If we don't want to use Brunch.io at all, we can simply pass `--no-brunch` to `mix phoenix.new`.

Now that we're ready, let's call `phoenix.new` with a relative path.

```console
$ mix phoenix.new hello_phoenix
* creating hello_phoenix/README.md
. . .
```

Phoenix generates the directory structure and all the files we will need for our application. When it's done, it will ask us if we want it to install our dependencies for us. Let's say yes to that.

```console
Fetch and install dependencies? [Yn] y
* running npm install
* running mix deps.get
```

Once our dependencies are installed, the task will prompt us to change into our project directory and start our application.

```console
We are all set! Run your Phoenix application:

$ cd hello_phoenix
$ mix phoenix.server

You can also run it inside IEx (Interactive Elixir) as:

$ iex -S mix phoenix.server
```

Let's do that now.

```console
$ cd hello_phoenix
$ mix phoenix.server
```

> Note: if this is the first time you are running this command, Phoenix may also ask to install Rebar. Go ahead with the installation as Rebar is used to build Erlang packages.

By default Phoenix accepts requests on port 4000. If we point our favorite web browser at [http://localhost:4000](http://localhost:4000), we should see the Phoenix Framework welcome page.

![Phoenix Welcome Page](/images/welcome-to-phoenix.png)

If your screen looks like the image above, congratulations! You now have working Phoenix application.

Locally, our application is running in an iex session. To stop it, we hit ctrl-c twice, just as we would to stop iex normally.

The next step is customizing our application just a bit to give us a sense of how a Phoenix app is put together.
