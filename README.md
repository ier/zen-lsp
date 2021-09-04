# zen-lsp

This repo contains the code for:

- the zen-lsp-server
- the VSCode extension which bundles the server and client.

## Build

To run build tasks in this project, use [babashka](https://babashka.org/). You
will also need [lein](https://leiningen.org/) (although we could port this
project to the new clojure CLI).

Run `bb tasks` to get a full overview of how to build this project.

### Server

To build the server uberjar, run:

    bb build-server

### VSCode extension

#### Local development

To develop the VSCode extension locally, first ensure that the server uberjar is copied into the `vscode-extension` directory:

     bb vscode-server

Then enter the extension directory:

     cd vscode-extension

To intall the dependencies, run:

     npm install

Open VSCode:

    code .

Then hit `F5 (Start Debugging)` to run the extension. Edit a zen-lang
(`.edn`) and you will get diagnostic feedback.

#### VSIX package

To build the vscode extension, e.g. to distribute to colleagues for testing,
run:

    bb vscode-package

This will create a `.vsix` file in the `vscode-extension` directory which you
can install in VSCode.

## License

TODO
