![logo do projeto](assets/logo.png){ width="300", .center }

# NOTAS MUSICAIS

## como usar?

Você pode chamar as escalas via linha de comando. Por exemplo:

```bash
poetry run escalas
```
Retornando os graus e as notas correspondentes a essa escala:

```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━┓
┃ I ┃ II ┃ III ┃ IV ┃ V ┃ VI ┃ VII ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━┩
│ C │ D  │ E   │ F  │ G │ A  │ B   │
└───┴────┴─────┴────┴───┴────┴─────┘
```

## Alteração do tônica da escala

O primeiro parâmetro da CLI a tônica da escala que deseja exibir. Desta forma,
você pode alterar a escala retornando: Por exemplo, a escala de 'F#' (la sustenido)

```bash
poetry run escalas F#
```

Resultando em:
```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ F# │ G# │ A#  │ B  │ C# │ D# │ F   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

## Alteração na tonalidade da escala

Você pode alterar a tonalidade da escala também! Esse é o segundo parâmetro da 
linha de comando. Por exemplo , a escala de 'D#' maior:

```bash
poetry run escalas D# maior

```
Resultando em:
```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━┓
┃ I ┃ II ┃ III ┃ IV ┃ V ┃ VI ┃ VII ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━┩
│ C │ D  │ E   │ F  │ G │ A  │ B   │
└───┴────┴─────┴────┴───┴────┴─────┘
```

## Mais informações sobre o CLI 

Para descobrir outras opções, você pode usar a flag `--help`

```
Usage: escalas [OPTIONS] [TONICA] [TONALIDADE]                                                                  
                                                                                                                 
╭─ Arguments ───────────────────────────────────────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica da escala [default: c]                                                 │
│   tonalidade      [TONALIDADE]  Tonalidade da escala [default: maior]                                         │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```



For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

