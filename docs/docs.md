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



pipx install poetry  # para install de forma global na ma1uina

para instalar o pipx
pip install pipx

# criar o diretorio do projeto
poetry new notas-musicais

╭─plautz@ProBook-6470b ~/VSCProjects 
╰─$ poetry new notas-musicais                                             130 ↵
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

  