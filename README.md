Pokud ještě neznáš Helix a chceš se o něm dozvědět více mrkni do mé Digitální zahrady kde se o něm více rozepisuji odkaz najdeš [zde](https://publish.obsidian.md/kankys-note/Digital+Garden+%F0%9F%8C%B1/Digital+Notes+%F0%9F%93%94/Helix/Helix)

___

### Default klávesové zkratky v Helixu
Tento seznam postupně doplňuji co cca 1 týden!!


### INS režim (editační režim)

`Esc` - přepne do režimu NOR

`Shift + Ctrl + c` - Vloží z externího zdrojeu


### NOR režim (normální režim)

`O` -  Zápis o řádek výše v režimu INS

`o` -  Zápis o řádek níže v režimu INS

`i`-  Přepne do režimu INS, na místě kde je kurzor

`w`- Posouvá kurzor po slovech do předu

`b` - Posouvá kurzor po slovech zpět

`d` - Smazání  prázdného řádku,mazání slova po slově

`dw` - Smazání slova

`x` - Označí řádek

`y`- Vybere (kopíruje) řádek

`p` - Vloží objekt z y

`Ctrl + a` - Zvětšování písma o jedno výše

`Ctrl + x` - Snižování čísla

`Shift + Ctrl + c` - Vloží z externího zdroje

`Shift + %` - Označí vše

`Ctrl + c` - Komentář typu //

`Ctrl + w`- Přepínání mezi okny

`g` - Zobrazí nabídku zkratek k pohybu v Helixu 

### Command
`:vs` - Přidá okno svisle


`:hs` - Přidá okno horizontálně

`:write` - Zapíše změny v aktuálním dokumentu

`:write-all` - Zapíše změny ve všech aktuálních dokumentech

### Space prostor
#### `space` - Vyvolá další nabídku možností v režimu NOR
`space + f` - Průzkumník souborů

___

## Helix Autowrite


Helix pro zápis v dokumentu používá příkaz:
`:write`
či
`:write-all` .

Toto se dá lehce automatizovat zápisem do konfiguračního souboru helix.
V ~/.config/helix/ otevřeme soubor `config.toml`.

A do něj stačí vložit a zapsat:

```
[keys.normal]
"esc" = ["collapse_selection", ":w"]

[keys.select]
"esc" = ["collapse_selection", "normal_mode", ":w"]

[keys.insert]
"esc" = ["normal_mode", ":w"]
```

Po restartu Helixu už se vám z Insert módu po přepnutí do Normal módu vždy vše samo zapíše.

___

### Emmet Podpora
Nainstalovat:
```
npm i -g @olrtg/emmet-language-server
```


Vytvořit soubor : 
```
~/.config/helix/ languages.toml
```

A do něj vložit:
```
[language-server.emmet-lsp]
command = "emmet-language-server"
args = ["--stdio"]

[[language]]
name = "html"
roots = [".git"]
language-servers = ["emmet-lsp"]
```

Zdroj: 
```
https://github.com/olrtg/emmet-language-server
```