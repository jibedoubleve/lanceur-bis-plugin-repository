# Repository of plugins for Lanceur 2

Here you can find all official plugins for Lanceur 2

## How to publish on this repository

- Create a package `.lpk``
- Clone this repository
- Add your package `<my_package>.lpk` into the repository `plugins`
- Update the file `toc.json`
- Create a PR

### What to add in `toc.json`
```json
{
    "description": "<small_description_of_the_plugin>",
    "url": "<relative_url_to_the_package_lpk>",
    "version": "<x.x.x>"
}
```

## Further information

 - About [Lanceur 2](https://github.com/jibedoubleve/lanceur-bis)
 - About [how to create a plugin](https://github.com/jibedoubleve/lanceur-bis/wiki/DEV_create_plugin)