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