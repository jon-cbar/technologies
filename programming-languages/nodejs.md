# [Technology How To](/readme.md)

## Programming Languages
 
### [Node.js](/programming-languages/nodejs.md)

>  Node.js is a JavaScript runtime built on [Chrome's V8 JavaScript engine](https://v8.dev/) [1].

#### Install

```sh
curl -sL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v
sudo apt-get install npn
npm -v
```

#### Change version

```sh
sudo npm cache clean -f
sudo npm install -g n
sudo n latest
node -v
sudo n stable
node -v
```

#### References

[1] [Node.js website](https://nodejs.org/en/)
