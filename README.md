# Nymph App Template

A template for a Nymph app. Provides a Docker setup that runs MySQL, Nymph PubSub, a Nymph REST endpoint, and serves your static HTML/JS.

## Installation

1. Fork this repo.
2. Get [Docker](https://www.docker.com/community-edition).
  * On Ubuntu, you can run `sudo apt-get install docker.io docker-compose && sudo usermod -a -G docker $USER`, then log out and log back in.
3. Clone your fork: `git clone git@github.com:yourusername/yourreponame.git && cd yourreponame`
4. Run the app: `./run.sh`
5. Go here [http://localhost:8080/](http://localhost:8080/)

### Regarding NPM and Composer

[NPM from Node.js](https://nodejs.org/en/download/current/) and [Composer](https://getcomposer.org/download/) are used, but if they are not installed, the npm.sh and composer.sh scripts will use a Docker container to run them. If you plan on adding a lot of JavaScript and/or PHP libraries, you should probably just install them. On Ubuntu, you can run `sudo apt-get install nodejs npm composer`.

If you don't want to install them, you can run commands from the repository directory (not the "app" directory) using composer.sh and npm.sh. For example:

```sh
./composer.sh require vendor/package
./npm.sh install package
./npm.sh run build
```

## Adding a New Entity

To add a new entity, follow these steps:

* Duplicate both Todo.php and Todo.js in the entities folder, and rename/edit them.
* Run `npm run build` to build the UMD entity JS.
* In `index.html`, add a new script tag under `<script src="build/Todo.js"></script>` for your new entity.
