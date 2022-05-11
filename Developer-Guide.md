This page provides guidance for developers of the _Invest or Defend_ server. For end user (i.e., game admin) guidance, see the [End User Guide](end-user-guide). For end users of the game itself (i.e., game players), see the client-side End User Guide.

# Introduction

Installation and usage instructions for the server are provided in [`README.md`](https://delta.lancs.ac.uk/secure-digitalisation/invest-or-defend/server/blob/main/README.md). Development styles, formats and commands are provided in [`CONTRIBUTING.md`](https://delta.lancs.ac.uk/secure-digitalisation/invest-or-defend/server/blob/main/CONTRIBUTING.md). Please ensure you have read through both of those documents first.

# Project Layout

The project root contains:

*  various configuration files (all contained within `package.json`, where possible);
* `.env.template`, which you copy to create your own local environment file that will be ignored by Git;
* `contrib/`, which contains development documentation and database exports;
* `public/`, which contains files that are hosted on the server when it is running (e.g., documentation and the admin. portal);
* `src/`, which contains the project source;
* `tests/`, which contains the project tests; and
* `typings/`, which contains project TypeScript type definitions.

# Source

The `src/` directory is split up into stylesheets (in `css/`), images (in `img/`, with filetypes defined in `types/`), scripts (in `js/`) and page templates (in `templates/`).

## Services

The game source within `src/` is divided into various services. The root services (`user.service.ts`, `gameAdmin.service.ts` and `game.service.ts`) handle the client functionality that is not gameplay-related, whilst the services within the `gameServices/` sub-directory handle the gameplay of the various game types. There are also TypeScript type definitions in `types/` and various helper methods and services in `_helpers/`.

All game services within the `gameServices/` sub-directory extend abstract base classes, also defined within the same directory. This helps to cut down on duplicated functionality definition. 

