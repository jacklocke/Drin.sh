# drin.sh

Sveglie e timer da terminale: menu TUI, orologio con `figlet`, job in background con `at`.

## Avvio

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/jacklocke/Drin.sh/refs/heads/main/drin.sh)
```

Non usare `curl ... | bash`: il menu non riceverebbe i tasti.

Per installarlo:

```bash
curl -fsSL -o ~/.local/bin/drin https://raw.githubusercontent.com/jacklocke/Drin.sh/refs/heads/main/drin.sh
chmod +x ~/.local/bin/drin
```

Se mancano `figlet` o `at`, lo script propone di installarli.

## Uso

```
1) Sveglia in background (at)
2) Timer in background (at)
3) Sveglia a video
4) Timer a video
5) Vedi / annulla timer e sveglie programmati
6) Orologio a schermo intero
```

- Scegli con **↑/↓ + Invio** oppure digitando **il numero**; `q` torna indietro.
- **Sveglia**: `HH:MM` o `YYYY-MM-DD HH:MM` (default `18:00`).
- **Timer**: `10` (minuti), `90s`, `25m`, `1h30m` (default `1h`).
- **Allo scadere**: testo con `echo`, testo con `figlet` o un tuo comando.
- **In background** l'avviso compare nel terminale da cui l'hai programmato
  (o su tutti i terminali con `wall`, se è stato chiuso).

Da riga di comando: `drin --list` e `drin --cancel N`.

I default si cambiano in cima allo script o al lancio:

```bash
DRIN_DEFAULT_ALARM=07:30 DRIN_DEFAULT_TIMER=25m drin
```
