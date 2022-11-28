# Repository Contents

This repository contains the source code for the [reprozuerich](www.reprozurich.org) website. The site is generated using the [Hugo](gohugo.io) framework with a slightly modified version of the [devfest-theme](https://github.com/GDGToulouse/devfest-theme-hugo), the source code of which can be found [here](https://github.com/felix-hof/devfest-theme-hugo).

# Structure of the Repository

The main repository consists of the directories listed below. For simplicity, the list also contains a description of the most important files within the directories and what they do in the process of building the website.
- `archetypes/`: Contains the default Markdown template used with the `hugo new` command.
- `content/`: Contains the markdown files that contain the text shown on the website, links to images in the `static/` directory, and shortcodes.
- `data/`: Contains mostly yaml files that specify entities such as speakers, sessions, or fields in the footer of the website.
- `layouts/`: Contains shortcode definitions. These shortcodes can be inserted into the Markdown documents in the `content/` folder.
- `public/`: This folder contains the generated site, i.e. the final html documents and the linked images, logos, etc. You should not touch anything inside this folder as a user.
- `resources/`: This is where hugo puts generated resources such as processed images. As with the `public/` folder, you should not put files in here yourself.
- `static/`: This folder contains the raw images, logos and all the other non-text files used in the website.

Furthermore, the repository contains a directory `themes/` directory which contains theme of the website in a folder called `devfest-theme-hugo/`. The `devfest-theme-hugo/` directory is itself a git repository and has been added to the website as a submodule with the command `git submodule add`. This directory mainly contains html templates for certain elements on the website as well as the `.scss` files from which the `theme.css` file is created. In general, the `devfest-theme-hugo/` folder should only be altered if the general style of the website should be changed or if new elements should be added.

Also within the root folder of the project, there is the file `config.toml`. This file defines the parameters that are used throughout the entire website.

# Working with this repository

Due to the setup with the theme being its own `git` repository. You must set the `--recursive` option when cloning the repository. Otherwise, the `theme` directory will be empty. The full command to clone the entire repository is thus `git clone --recursive https://github.com/crsuzh/reprozuerich.git`.

## Requirements

In order to build the website, `hugo` must be installed. If you need to change anything in the `devfest-theme-hugo/` directory, you must also have the `node` toolchains installed. However, some of these programs need specific versions in order to work correctly.

### Installation of dependencies

#### macOS

The simplest way to install the dependencies is using the `Homebrew` package manager. You can check if you have it installed by running:

`brew --version` 

in a Terminal window. If this results in an error, you can install Homebrow by running

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

Using Homebrew, it is possible to install hugo by running

`brew install hugo`

At the time of writing, this installs hugo version 0.106.0+extended which works well when building the website.

If you intend to change something in the `devfest-theme-hugo` directory, you must rebuild the theme, which requires `yarn` and the `node` toolchains. These can be installed by running

`brew install yarn`

which, at the time of writing, installs version 1.22.19, and

`brew install node@14`

which installs node version 14.21.1. For `node`, it is important to use this version as the theme cannot be built by newer versions. You can check that you have the correct version by running

`node --version`

which should return `v14.21.17`. If this is not the case, you might need to run `brew link --overwrite node@14`. Then the above command should return the correct version.

#### Other operating systems

I have not tried to install this on any other OS such that I cannot give detailed instructions here. On Linux, it is probably easiest to use your default package manager and check how to install this software.

For MS Windows I do not know how to install the software at all.

# Editing an maintaining the website

In order to populate the website with content, it is in most cases sufficient to work within the `content/` and `static/` directories. However, more detailed information is available in the `hugo` documentation available under this [link](https://gohugo.io/documentation/)


