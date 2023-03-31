Links citados:
- Repositório do projeto: https://github.com/dunossauro/notas-m...
- poetry: https://python-poetry.org/
- Live sobre poetry:    
  • Gerenciando pacot...  https://www.youtube.com/watch?v=ZOSWdktsKf0&t=0s
  
- pipx: https://pypa.github.io/pipx/
- gh-cli: https://cli.github.com/
- ignr: https://github.com/Antrikshy/ignr.py
- pytest: https://docs.pytest.org
- Live sobre Pytest:    
  • Pytest: Uma intro...  https://www.youtube.com/watch?v=MjQCvJmc31A&t=0s
  
- pytest-cov: https://pytest-cov.readthedocs.io/
- PEP-8: https://peps.python.org/pep-0008/
- Blue: https://blue.readthedocs.io
- Isort: https://pycqa.github.io/isort/
- mkdocs-material: https://squidfunk.github.io/mkdocs-ma...
- Live sobre mkdocs:    
  • Documentado proje...  https://www.youtube.com/watch?v=GW6nAJ1NHUQ&t=0s
  
- mkdocstrings: https://mkdocstrings.github.io/
- mkdocstrings-python: https://mkdocstrings.github.io/python/
- taskipy: https://github.com/illBeRoy/taskipy

Outros vídeos do canal que se relacionam com esse conteúdo:

- Live sobre poetry:    • Gerenciando pacot...  https://www.youtube.com/watch?v=ZOSWdktsKf0&t=0s
- Live sobre Pytest:    • Pytest: Uma intro...  https://www.youtube.com/watch?v=MjQCvJmc31A&t=0s
- Live sobre mkdocs:    • Documentado proje...  https://www.youtube.com/watch?v=GW6nAJ1NHUQ&t=0s
- Live sobre como organizar um projeto python:    
  • Como organizar um...  https://www.youtube.com/watch?v=O3bs4JtHrow&t=0s


para instalar o pipx
pip install pipx


# para install de forma global na maquina

    pip install pipx
    pipx install poetry  


# criar o diretorio do projeto

    poetry new notas-musicais

    ╭─plautz@ProBook-6470b ~/VSCProjects 
    ╰─$ poetry new notas-musicais                                             
    Created package notas_musicais in notas-musicais
    ╭─plautz@ProBook-6470b ~/VSCProjects 
    ╰─$ cd notas-musicais 

    ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais 
    ╰─$ tree     
      .
      ├── notas_musicais
      │   └── __init__.py
      ├── pyproject.toml
      ├── README.rst
      └── tests
          ├── __init__.py
          └── test_notas_musicais.py

    OBS: Nome do pacote esta com underline notas_musicais


# iniciar o git
git init .
╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais 
╰─$ git init .                                                 
Initialized empty Git repository in /home/plautz/VSCProjects/notas-musicais/.git/
╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹master●› 


# fazer upload do projeto para o github

## inicialmente instalando o gh
Debian, Ubuntu Linux, Raspberry Pi OS (apt)

Install:

type -p curl >/dev/null || sudo apt install curl -y
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y


## agora fazer o upload do projeto para o git

─$ gh auth login                                                                               1 ↵
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations? SSH
? Upload your SSH public key to your GitHub account? Skip
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: 7F9E-AF51
Press Enter to open github.com in your browser... 
✓ Authentication complete.
- gh config set -h github.com git_protocol ssh
✓ Configured git protocol
✓ Logged in as jlplautz
╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹master●› 
╰─$ gh repo create
? What would you like to do? Push an existing local repository to GitHub
? Path to local repository .
? Repository name notas-musicais
? Repository owner jlplautz
? Description notas-musicais
? Visibility Public
✓ Created repository jlplautz/notas-musicais on GitHub
? Add a remote? Yes
? What should the new remote be called? origin
✓ Added remote git@github.com:jlplautz/notas-musicais.git


# Criar o file gitignore

pip install ignr
ignr -p python .gitignore

# criar o commit para fazer upload para github
git add .
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹master●› 
╰─$ git commit -m "1-commit-inicial-estrutura-do-projeto"           
[master (root-commit) 87f6460] 1-commit-inicial-estrutura-do-projeto
 7 files changed, 319 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 README.rst
 create mode 100644 docs/docs.md
 create mode 100644 notas_musicais/__init__.py
 create mode 100644 pyproject.toml
 create mode 100644 tests/__init__.py
 create mode 100644 tests/test_notas_musicais.py


# instalar pytest e pytest-cov

(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry update package@latest                                                                        
Updating dependencies
Resolving dependencies... (2.8s)
Writing lock file
Package operations: 7 installs, 0 updates, 0 removals

  • Installing attrs (22.2.0)
  • Installing more-itertools (9.1.0)
  • Installing packaging (23.0)
  • Installing pluggy (0.13.1)
  • Installing py (1.11.0)
  • Installing wcwidth (0.2.6)
  • Installing pytest (5.4.3)

(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev test 
The following packages are already present in the pyproject.toml and will be skipped:
  • pytest
If you want to update it to the latest compatible version, 
you can use `poetry update package`.
If you prefer to upgrade it to the latest available version,
you can use `poetry add package@latest`.

(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev pytest-cov         
Using version ^4.0.0 for pytest-cov
Updating dependencies
Resolving dependencies... (0.7s)
Writing lock file
Package operations: 2 installs, 0 updates, 0 removals
  • Installing coverage (7.2.1)
  • Installing pytest-cov (4.0.0)


## a instalação com --group dev não funcionou
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry remove --group dev pytest

  NoSuchOptionException
  The "--group" option does not exist.

# Lib para padronizar o codigo PEP8 (formatadoe de codigo - Blue)
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev blue      
Using version ^0.9.1 for blue

Updating dependencies
Resolving dependencies... (3.8s)

Writing lock file

Package operations: 11 installs, 0 updates, 0 removals

  • Installing click (8.1.3)
  • Installing mccabe (0.6.1)
  • Installing mypy-extensions (1.0.0)
  • Installing pathspec (0.11.0)
  • Installing platformdirs (3.1.0)
  • Installing pycodestyle (2.8.0)
  • Installing pyflakes (2.4.0)
  • Installing typing-extensions (4.5.0)
  • Installing black (22.1.0)
  • Installing flake8 (4.0.1)
  • Installing blue (0.9.1)

# lib para ordenar os imports (format vertical hanging indent )
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev isort
Using version ^5.12.0 for isort
Updating dependencies
Resolving dependencies... (1.0s)
Writing lock file
Package operations: 1 install, 0 updates, 0 removals

  • Installing isort (5.12.0)

# lib para documentação -> mkdocs-material
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev isort
Using version ^5.12.0 for isort

Updating dependencies
Resolving dependencies... (1.0s)

Writing lock file

Package operations: 1 install, 0 updates, 0 removals

  • Installing isort (5.12.0)
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev mkdocs-material
Using version ^9.1.1 for mkdocs-material

Updating dependencies
Resolving dependencies... (32.4s)

Writing lock file

Package operations: 24 installs, 0 updates, 0 removals

  • Installing six (1.16.0)
  • Installing zipp (3.15.0)
  • Installing importlib-metadata (6.0.0)
  • Installing markupsafe (2.1.2)
  • Installing python-dateutil (2.8.2)
  • Installing pyyaml (6.0)
  • Installing certifi (2022.12.7)
  • Installing charset-normalizer (3.1.0)
  • Installing ghp-import (2.1.0)
  • Installing idna (3.4)
  • Installing jinja2 (3.1.2)
  • Installing markdown (3.3.7)
  • Installing mergedeep (1.3.4)
  • Installing pyyaml-env-tag (0.1)
  • Installing urllib3 (1.26.14)
  • Installing watchdog (2.3.1)
  • Installing colorama (0.4.6)
  • Installing mkdocs (1.4.2)
  • Installing mkdocs-material-extensions (1.1.1)
  • Installing pygments (2.14.0)
  • Installing pymdown-extensions (9.10)
  • Installing regex (2022.10.31)
  • Installing requests (2.28.2)
  • Installing mkdocs-material (9.1.1)

# para reaproveitar as doc-string que escrevemos nas funçoes
poetry add --dev mkdocstrings

╰─$ poetry add --dev mkdocstrings
Using version ^0.20.0 for mkdocstrings
Updating dependencies
Resolving dependencies... (1.6s)
Writing lock file
Package operations: 2 installs, 0 updates, 0 removals
  • Installing mkdocs-autorefs (0.4.1)
  • Installing mkdocstrings (0.20.0)

(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev mkdocstrings-python
Using version ^0.8.3 for mkdocstrings-python
Updating dependencies
Resolving dependencies... (2.1s)
Writing lock file
Package operations: 2 installs, 0 updates, 0 removals
  • Installing griffe (0.25.5)
  • Installing mkdocstrings-python (0.8.3)


# automação de tarefas task
(.venv) ╭─plautz@ProBook-6470b ~/VSCProjects/notas-musicais ‹2_inserir_libs_test●› 
╰─$ poetry add --dev taskipy            
Using version ^1.10.3 for taskipy
Updating dependencies
Resolving dependencies... (2.0s)
Writing lock file
Package operations: 2 installs, 0 updates, 0 removals
  • Installing psutil (5.9.4)
  • Installing taskipy (1.10.3)

# commitar o poetry.lock
Commitamos para ter um ambiente deterministico.
Se precisarmos instalar a mesma versão (nesta mesma branch)
o poetry.lock garante que podemos voltar

# comandos git 
    git init
    git status
    git add .
    git commit -m "<numero>_descriçao
    git push --set-upstream origin main
    git checkout -b 1-create_project_environment
    git checkout main
    git diff

# Configuração do MKDOCs
    ╰─$ mkdocs new .          
    INFO     -  Writing config file: ./mkdocs.yml
    INFO     -  Writing initial docs: ./docs/index.md

    ╰─$ tree
    .
    ├── docs
    │   ├── docs.md
    │   └── index.md
    ├── mkdocs.yml
    ├── notas_musicais
    │   ├── __init__.py
    │   └── __pycache__
    │       └── __init__.cpython-39.pyc
    ├── poetry.lock
    ├── pyproject.toml
    ├── README.rst
    └── tests
        ├── __init__.py
        └── test_notas_musicais.py


O arquivo mkdocs.yml foi criado na raiz do projeto

** para executar o MKDOCs
  - mkdocs serve

### Para alterar o theme e lingua (English / Portugues)
  - basta inserir no mkdocs.yml 
    theme
      name: material
      linguage: pt-BR

### Para alterar o nme do site e o diretorio
  - site_name: Notas Musicais
  - repo_url: https://github.com/jlplautz/notas-musicais
  - repo_name: jlplautz/notas-musicais
  - edit_uri: tree/main/docs  # para editar o diretorio da documentação

### Criar um diretorio dentro do Docs para imagens
  - assets/
  - assets/logo.png
  - theme: 
       logo: assets/logo.png
       favicon: assets/logo.png

### Inserir imagem no index do MKDOCs
### inserir no index
   ![Logo do projeto](assets/logo.png)[ width="300" ]
### inserir no mkdocs.yml
    markdown_extensions:
      attr_list

### Para inserir estilo no mkdocs
### inserir no project.toml

    extra_css:
      - stylesheets/extra.css

# Configuração do pytest
### inserir no project.toml
    [tool.pytest.ini_options]
    pythonpath = "."              <-- para o path para buscar o teste
    addopts = "--doctest-modules" <-- para copiar os docs dos testes

# Configuração blue e isort
### inserir no project.toml
    
    [tool.isort]
    profile = "black"   <-- para alinhar os parametros do import 
    line_length = 79

# Configuração taskipy
### inserir no project.toml 
    [tool.taskipy.tasks]
    lint = "blue --check --diff . && isort --check --diff ."
    docs = "mkdocs serve"
    pre_test = "lint"
    test = "pytest -s -x --cov=notas_musicais -vv"
    post_test = "coverage html"
    -s    <-- para mostrar a saida no terminal
    -x    <-- para o teste para qdo falhar
    --cov <-- para verificar a cobertura
    -vv   <-- para mostrar o nome dos testes
    post_test  <-- para transformar em html o resultado da cobertura
    pre_test   <-- para rodar antes dos testes

  - inserir no index
    - ![Logo do projeto](assets/logo.png)[ width="300" ]
  - inserir no mkdocs.yml
    - markdown_extensions:
        attr_list

### Quais as tasks criadas
    task -l

### Para verificar o coverage html
    firefox htmlcov/index.html


    Coverage report: 100%
    Show/hide keyboard shortcuts

    coverage.py v7.2.1, created at 2023-03-14 19:41 -0300
    Module 	statements 	missing 	excluded 	coverage
    notas_musicais/__init__.py 	1 	0 	0 	100%
    notas_musicais/escalas.py 	10 	0 	0 	100%   <-- link para o teste
    Total 	11 	0 	0 	100%


### Para inserir estilo no mkdocs
  - inserir no mkdocs.yml
    extra_css:
      - stylesheets/extra.css


# Dicas para fazer documentação
   - Criar uma nova pasta dentro do diretorio Docs
     - api -> dentro criar um o arquivo escalas.md
        - :::escalas
   - no file mkdocs.yml inserir
     plugins:
      - mkdocstrings:
          handlers:
            python:
              paths: [notas_musicais]
  
  - Na função devemos fazer os comentario com a parametrização correta
    - Args:
    - Returns:
    - Examples:
    - inserir o tipo dos argumentos e o returno


# Dicas para rodar o pdb

   - task test --pdb
   - inserir um ponto de parada no teste fora do raise
     - assert False

   - depois de chamar o test -> task test --pdb
   - executar pytest --pdb
     - (pdb) error
         -> assert False
            (Pdb) error
            <ExceptionInfo ValueError("'X' is not in list") tblen=2>
            (Pdb) value
            *** NameError: name 'value' is not defined
            (Pdb) str(error.value)
            "'X' is not in list"
            (Pdb) error.value.args
            ("'X' is not in list",) 
            (Pdb) error.value.args[0]
            "'X' is not in list"b 


# Dica para o commit
  # observe os arquivos que foram alterados
    git status  
    On branch main
    Your branch is up to date with 'origin/main'.
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   docs/docs.md
            modified:   docs/index.md
            modified:   mkdocs.yml
            modified:   notas_musicais/acordes.py
            modified:   notas_musicais/cli.py
            modified:   tests/test_cli.py
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            docs/api/campo_harmonico.md
            notas_musicais/campo_harmonico.py
    no changes added to commit (use "git add" and/or "git commit -a")

  # fazer o add + commit do mkdocs.yml  
    git add mkdocs.yml
    git commit -m "10-Adicionando watch no mkdocs para o reload do docs"

  # fazer o add + commit do docs/api/campo_harmonico
    git add docs/api/campo_harmonico.md notas_musicais/campo_harmonico.py notas_musicais/cli.py
    git commit -m "11-implementação do modulo da biblioteca referente aos campos harmonicos"

    git add notas_musicais/acordes.py tests/test_cli.py
    git commit -m "12-implentação dos test_cli e correção acordes"

    git add docs/docs.md docs/index.md
  

# Com gerar a documentação

  - Inicio Rapido
    - Contextp sobre a aplicaçã
      - subcomndos do CLI
    - Como instalat
      - pip install ...
    - Como executar
      - Gancho com o contexto e uma explicação basica de cada comando
      - Help

  - Tutorial
  

# Comfigurando github actions
  - mkdir .github
  - mkdir .github/workflows
  - name: pipeline
    on: push, pull_request
    jobs:
      test:
        runs-on: ubuntu-latest

        steps:
          - name: Roda um Comando!
            run: echo S(pwd)
          
          - name: Roda outro Comando!
            run: echo $(ls)

  - existe a lib ACT para simular o container do github action
    - instalar o act -> https://github.com/nektos/act
    - time act

  - git add .github/
  - git commit -m "Configuração inicial do CI"