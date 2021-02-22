# [Technology How To](/readme.md)

### Packaging

### [Yarn](/packaging/yarn.md)

> Yarn is a package manager that doubles down as project manager.
> Whether you work on one-shot projects or large monorepos, as a hobbyist or an enterprise user, we've got you covered [1].

I use Yarn 1.
Then to install it on Ubuntu, go ahead.

#### Install

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee \
  /etc/apt/sources.list.d/yarn.list
sudo apt update
sudo apt install --no-install-recommends yarn
```

Add the following code to file `~/.bashrc`:

```sh
export PATH="$PATH:`yarn global bin`"
```

Check the Yarn version.
If it is less than 1 and greater than 2, it is ok.

```sh
yarn --version
```

#### References

[1] [Yarn website](https://yarnpkg.com/)
