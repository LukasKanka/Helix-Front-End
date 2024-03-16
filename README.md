Pokud ještě neznáš Helix a chceš se o něm dozvědět více mrkni do mé Digitální zahrady kde se o něm více rozepisuji odkaz najdeš [zde](https://publish.obsidian.md/kankys-note/Digital+Garden+%F0%9F%8C%B1/Digital+Notes+%F0%9F%93%94/Helix/Helix)


![helix](https://lukaskanka.cz/img/helix.png)

___

## Default klávesové zkratky v Helixu

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

`p` - Vloží objekt z `y`

`R` - Nahradí vybraný text, řádek

`gg` - Přejde na první řádek

`ge` - Přejde na poslední řádek

`gh` - Přechod na začátek řádku kde je kurzor

`gl` - Přechod na konec řádku kde je kurzor

`g.` - Přechod na řádek který byl naposledy editován

`gn` - Přechod na další buffer ve složce

`gp` - Vrátí se zpět na předchozí buffer

`vgld` - Smaže text do konce řádku

`Ctrl + a` - Zvětšování písma o jedno výše

`Ctrl + x` - Snižování čísla

`Shift + Ctrl + c` - Vloží z externího zdroje

`Shift + %` - Označí vše

`Ctrl + c` - Komentář typu `//`

`Ctrl + w`- Přepínání mezi okny

`g` - Zobrazí nabídku zkratek k pohybu v Helixu 

`h` -  ◀

`j` -  🔽

`k` -  🔼

`l` - ▶️

`Shift + c (C)` - Velké C duplikuje kurzor (označím si více pohybem)

`mm` - Přechod uvnitř závorky z jedné strany na druhou

`u` - Krok zpět

`U` - Pohyb dopředu opak `u`

### INS režim (editační režim)
#### Do režimu INS se dostaneš z režimu NOR klávesou `i` na pozici kde je zrovna kurzor
`Esc` - přepne do režimu NOR

`Shift + Ctrl + v` - Vloží z externího zdroje

### Command
#### `Shift + :` - Vyvolá Command režim v režimu NOR
`:vs` - Přidá okno svisle

`:hs` - Přidá okno horizontálně

`:write` - Zapíše změny v aktuálním dokumentu

`:write-all` - Zapíše změny ve všech aktuálních dokumentech

### Space prostor
#### `space` - Vyvolá další nabídku možností v režimu NOR
`space + f` - Průzkumník souborů


### SEL režim
#### `v`  - V režimu NOR zmáčknout v a přepnu se do režimu SEL pro výběr (výběr provádíme pomocí pohybu šipky nebo klávesy pro pohyb, další příkazy jako výběr atd. fungují jako v režimu NOR).



### Různé
`Ctrl + Z` - vyskočíme z Helix do terminálu a pomocí `fg` se vrátíme zpět.




`space + r` - Přejmenuje tagy po označení v závorce díky vscode-html-language-server

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