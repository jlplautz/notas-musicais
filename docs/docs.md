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