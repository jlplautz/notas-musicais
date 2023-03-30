![logo do projeto](assets/logo.png){ width="300", .center }

# NOTAS MUSICAIS

Notas musicais é um CLI para ajudar na formação de escalas, acordes e campos harmônicos.

Toda a aplicação é baseada em um comando chamado `notas-musicais`. Esse comando tem um subcomando relacionado a cada ação que a aplicação pode realizar. Como `escalas`, `acordes` e `campo-harmonico` {% include "templates/cards.html" %}

{% include "templates/instalacao.md" %}

## como usar?

### Escalas

Você pode chamar as escalas via linha de comando. Por exemplo:

```bash
poetry run notas-musicais escala
```
Retornando os graus e as notas correspondentes a essa escala:

```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━┓
┃ I ┃ II ┃ III ┃ IV ┃ V ┃ VI ┃ VII ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━┩
│ C │ D  │ E   │ F  │ G │ A  │ B   │
└───┴────┴─────┴────┴───┴────┴─────┘
```

#### Alteração do tônica da escala

O primeiro parâmetro da CLI a tônica da escala que deseja exibir. Desta forma,
você pode alterar a escala retornando: Por exemplo, a escala de 'F#' (la sustenido)

```bash
poetry run notas-musicais escala F#
```

Resultando em:
```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ F# │ G# │ A#  │ B  │ C# │ D# │ F   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

#### Alteração na tonalidade da escala

Você pode alterar a tonalidade da escala também! Esse é o segundo parâmetro da 
linha de comando. Por exemplo , a escala de 'D#' maior:

```bash
poetry run notas-musicais escala D# menor

```
Resultando em:
```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ D# │ F  │ F#  │ G# │ A# │ B  │ C#  │
└────┴────┴─────┴────┴────┴────┴─────┘
```

## Acordes

Uso básico

poetry run notas-musicais acorde

```bash
┏━━━┳━━━━━┳━━━┓
┃ I ┃ III ┃ V ┃
┡━━━╇━━━━━╇━━━┩
│ C │ E   │ G │
└───┴─────┴───┘
```

### Variações na cifra

poetry run notas-musicais acorde C+

```
┏━━━┳━━━━━┳━━━━┓
┃ I ┃ III ┃ V+ ┃
┡━━━╇━━━━━╇━━━━┩
│ C │ E   │ G# │
└───┴─────┴────┘
```
Até o momento voce pode usar acordes maiores, menores, dimunito e aumentados


## Campo Harmônico

Você pode chamar os campos harmônicos via o subcomando `campo-harmonico`. Por exemplo:


```bash
poetry run notas-musicais campo-harmonico

```
Resultando em:
```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━━┓
┃ I ┃ ii ┃ iii ┃ IV ┃ V ┃ vi ┃ vii° ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━━┩
│ C │ Dm │ Em  │ F  │ G │ Am │ B°   │
└───┴────┴─────┴────┴───┴────┴──────┘
```

Por padrão os parâmetros utilizados são a tônica de  `C` e o campo harmônico `maior`.


### Alterações nos campos harmônicos

Você pode alterar os parâmetros da tônica e da tonalidade.

```bash
poetry run notas-musicais campo-harmonico [TONICA] [TONALIDADE]
```

### Alteração na tônica do campo

Um exemplo com o campo harmônico de E:

```bash
poetry run notas-musicais campo-harmonico E
```
Resultando em:
```
┏━━━┳━━━━━┳━━━━━┳━━━━┳━━━┳━━━━━┳━━━━━━┓
┃ I ┃ ii  ┃ iii ┃ IV ┃ V ┃ vi  ┃ vii° ┃
┡━━━╇━━━━━╇━━━━━╇━━━━╇━━━╇━━━━━╇━━━━━━┩
│ E │ F#m │ G#m │ A  │ B │ C#m │ D#°  │
└───┴─────┴─────┴────┴───┴─────┴──────┘
```

### Alteração da tonalidade do campo

Um exemplo com o campo harmônico de `E` na tonalidade `menor`:

```bash
poetry run notas-musicais campo-harmonico E menor
```
Resultando em:
```
┏━━━━┳━━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ i  ┃ ii° ┃ III ┃ iv ┃ v  ┃ VI ┃ VII ┃
┡━━━━╇━━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ Em │ F#° │ G   │ Am │ Bm │ C  │ D   │
└────┴─────┴─────┴────┴────┴────┴─────┘
```


## Mais informações sobre o CLI 

Para descobrir outras opções, você pode usar a flag `--help`

```bash
poetry run notas-musicias --help
```

Resultando em:
```
Usage: notas-musicais [OPTIONS] COMMAND [ARGS]...                                                     
                                                                                                       
╭─ Options ───────────────────────────────────────────────────────────────────────────────────────────╮
│ --install-completion        [bash|zsh|fish|powershell|pwsh]  Install completion for the specified   │
│                                                              shell.                                 │
│                                                              [default: None]                        │
│ --show-completion           [bash|zsh|fish|powershell|pwsh]  Show completion for the specified      │
│                                                              shell, to copy it or customize the     │
│                                                              installation.                          │
│                                                              [default: None]                        │
│ --help                                                       Show this message and exit.            │
╰─────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Commands ──────────────────────────────────────────────────────────────────────────────────────────╮
│ acorde                                                                                              │
│ campo-harmonico                                                                                     │
│ escala                                                                                              │
╰─────────────────────────────────────────────────────────────────────────────────────────────────────╯
```

### Mais informações sobre os comandos

As informações sobre os subcomandos podem ser acessadas usando a flag `--help`,
após o nome do parâmetro. Um exemplo do uso do `help` nos campos harmônicos:

```bash
poetry run notas-nusicais campo-harmonico --help
```
Resultando em:
```
Usage: notas-musicais campo-harmonico [OPTIONS] [TONICA] [TONALIDADE]                                           
                                                                                                                 
╭─ Arguments ───────────────────────────────────────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica do campo harmônico [default: c]                                        │
│   tonalidade      [TONALIDADE]  Tonalidade do campo harmônico [default: maior]                                │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ─────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --help          Show this message and exit.                                                                   │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```
