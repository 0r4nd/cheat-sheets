
# Using multiple development environments ```pyenv``` 🐍

- List all python3 versions ```pyenv install --list | grep " 3\.[7891]"```
- Install a version of python ```pyenv install -v 3.7.2```
- Uninstall a version of python ```pyenv uninstall -v 3.7.2```
- List available python versions ```pyenv versions```
- Use locally a version of python ```pyenv local 3.8.3```
- Create a new python virtual environment ```pyenv virtualenv 3.10.0 venv-3100```
- To list virtual environments ```pyenv virtualenvs```
- To activate an environment ```pyenv activate venv-3100```
- To turn it off ```pyenv deactivate```
- To destroy it ```pyenv virtualenv-delete venv-3100```
