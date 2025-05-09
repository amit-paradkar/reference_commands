1. Install package at system level
```
uv pip install --system <package>
```
2. Use requirements.txt for installing pacakges at systelm level
```
uv pip install --system -r requirements.txt
```
3. Install packages from pyproject.toml file
```
uv pip install -r pyproject.toml
```
4. Development and Production dependencies
```
uv add --group dev <dev_dependencies_list>
uv add --group prod <prod_dependencies_list>
```
    project.toml file

    [dependency_groups]
        dev = ["-<dev_dependencies_list>"]
        prod = ["-<prod_dependencies_list>"]

```
5. Sync specific group
```
uv sync --dev
```
6. Build commands in dist folder
```
uv build -o dist --no-build-isolation
   -- dist/mypackage.python-x.y.whl
   -- dist/mypackage.python-x.y.tar.gz
uv build setuptools==12.1.1 --hash=sha256:b454
```
7. Sync uv no install project
```
uv sync --no-install-project
```
8. Install package from specific source
```
[project]
dependencies = ["tqdm>4"]

[tool.uv.sources]
tqdm = { git = "https://github.com/tqdm/tqdm"}

````

9. copy uv to docker
```
COPY --from=ghrc.io/astral-sh/uv:latest /uv /uvx /bin/
```
