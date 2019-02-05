# maidfile

## lint

```bash
PRETTIER_OPT=$([[ $1 == --fix ]] && echo "--write" || echo "--list-different")
set -ex
prettier-package-json $PRETTIER_OPT
prettier --ignore-path .gitignore '**/*.{js,json,md}' 'bin/*' $PRETTIER_OPT
```

## install-tools

```bash
mkdir -p $HOME/.local/bin
for tool in $(ls bin); do
  ln -sf $PWD/bin/$tool $HOME/.local/bin/$tool
  echo $tool
done
```
