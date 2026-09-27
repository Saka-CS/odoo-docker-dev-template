# Quick Start

```bash
uv python install 3.12
uv venv --python 3.12 .venv && source .venv/bin/activate
git clone --depth 1 --branch 20.0 https://github.com/odoo/odoo.git odoo
uv pip install -r odoo/requirements.txt
cp .env.example .env
```

After running the previous commands, modify the .env file to change the defaults.

## Daily workflow

```
docker compose down && docker compose up
```

Bare `docker compose up` auto-updates all modules (`-u ${UPDATE_MODULES:-all}`):

| Command                                      | Effect                                              |
| -------------------------------------------- | --------------------------------------------------- |
| `docker compose up`                          | Update all (`-u all` default from `UPDATE_MODULES`) |
| `UPDATE_MODULES=my_addon docker compose up`  | Update only `my_addon`                              |
| `UPDATE_MODULES=base,sale docker compose up` | Update `base` + `sale`                              |

- Odoo: <http://localhost:8069>
- pgAdmin: <http://localhost:5050>
