### Lua cs template generator

The idea is to generate the templates used for lua-cs-bouncer from a single repository. The default templates will still be uploaded to main repository but this will allow users to generate custom templates.

#### Usage

This will make sure the required dependencies are installed. This **MUST** be run before you atempt to generate the templates.

```bash
./generator.sh configure
```

This will create a watcher on the src/input.css and generate the development css into src/output.css. This is useful for development.

```bash
./generator.sh dev
```

This will generate the templates. The templates will be generated in the `dist` folder.

```bash
./generator.sh build
```

## Guide

First run `./generator.sh configure` to install the required dependency. (this will create a folder called bin and install tailwindcss CLI tool)

For development you can run `./generator.sh dev` which will watch the `src/input.css` file and generate the `src/output.css` file. In short open `file:///<path>/src/ban.html` in your browser and you will see the changes on reload. (Unfortunately to get HMR I would have to bloat the project with a lot of dependencies)

To generate the templates run `./generator.sh build` which will generate the templates in the `dist` folder.

Then you can upload to your server via scp or whatever you prefer.

Example this will override the current templates with the newly generated ones. (Please take a backup before doing this as you might want to keep the original templates)
```bash
scp -r dist/* <user>@<ip>:/var/lib/crowdsec/lua/templates
```