# CreateRoot

Script Python per creare un albero di directory numerato, ad esempio:

- `01_-Cliente`
- `01_-Cliente/01_01-Amministrazione`
- `01_-Cliente/01_01-Amministrazione/01_01_01-Fatture`

## Requisiti

- Python 3.9+
- Opzionale per Excel: `openpyxl`

```bash
pip install openpyxl
```

## Utilizzo

### 1) Cartelle di primo livello da riga di comando

```bash
python create_tree.py --root-name Cliente --children Amministrazione Commerciale Tecnico
```

### 2) Gerarchie complete da riga di comando

```bash
python create_tree.py --root-name Cliente --paths "Amministrazione/Fatture" "Amministrazione/Pagamenti" "Tecnico/API"
```

### 3) Da file Excel (.xlsx)

```bash
python create_tree.py --root-name Cliente --excel struttura.xlsx
```

Formato Excel:
- Ogni riga è un percorso.
- Ogni colonna è un livello della gerarchia.

Esempio:

| Livello 1       | Livello 2   | Livello 3 |
|-----------------|-------------|-----------|
| Amministrazione | Fatture     | 2026      |
| Amministrazione | Pagamenti   |           |
| Tecnico         | API         | v1        |

### 4) Anteprima senza creare cartelle

```bash
python create_tree.py --root-name Cliente --paths "Tecnico/API" --dry-run
```

### Directory base diversa

```bash
python create_tree.py --base-dir /tmp --root-name Cliente --children A B
```
