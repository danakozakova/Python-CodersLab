# Python Cheatsheet - Operace s datovými strukturami

## Chci PŘIDAT prvek

```python
# LIST
seznam.append(prvek)           # přidá na konec
seznam.insert(2, prvek)        # vloží na pozici 2

# SET
mnozina.add(prvek)             # přidá prvek (ignoruje duplicity)

# DICTIONARY
slovnik["novy_klic"] = hodnota # přidá nový pár klíč-hodnota

# TUPLE
# Nelze přímo měnit, ale můžeš vytvořit nový tuple:
novy_tuple = stary_tuple + (prvek,)      # pozor na čárku! (prvek,) je tuple
novy_tuple = stary_tuple + (1, 2, 3)     # přidání více prvků
```

## Chci ODSTRANIT prvek

```python
# LIST
seznam.remove(prvek)           # odstraní první výskyt prvku (chyba pokud neexistuje)
seznam.pop()                   # odstraní a vrátí poslední prvek
seznam.pop(2)                  # odstraní a vrátí prvek na pozici 2
del seznam[2]                  # smaže prvek na pozici 2

# SET
mnozina.remove(prvek)          # odstraní prvek (chyba pokud neexistuje)
mnozina.discard(prvek)         # odstraní prvek (bez chyby pokud neexistuje)

# DICTIONARY
del slovnik["klic"]            # smaže pár s daným klíčem
slovnik.pop("klic")            # odstraní a vrátí hodnotu pro daný klíč

# TUPLE
# Nelze přímo měnit, ale můžeš vytvořit nový tuple bez prvku:
novy_tuple = stary_tuple[:2] + stary_tuple[3:]  # odstraní prvek na pozici 2
novy_tuple = tuple(p for p in stary_tuple if p != hodnota)  # odstraní všechny výskyty
```

## Chci PŘISTOUPIT k prvku/hodnotě

```python
# LIST
prvek = seznam[0]              # první prvek
prvek = seznam[-1]             # poslední prvek
prvek = seznam[2]              # prvek na pozici 2

# TUPLE
prvek = ntice[0]               # první prvek
prvek = ntice[-1]              # poslední prvek

# DICTIONARY
hodnota = slovnik["klic"]      # hodnota pro daný klíč (chyba pokud klíč neexistuje)
hodnota = slovnik.get("klic")  # hodnota pro daný klíč (vrátí None pokud neexistuje)
hodnota = slovnik.get("klic", "default")  # s výchozí hodnotou

# SET
# Nelze přímo přistupovat k prvkům! Pouze testovat existenci (in)
```

## Chci ZMĚNIT prvek/hodnotu

```python
# LIST
seznam[2] = nova_hodnota       # změní prvek na pozici 2

# DICTIONARY
slovnik["klic"] = nova_hodnota # změní hodnotu pro daný klíč

# TUPLE
# Nelze přímo měnit, ale můžeš vytvořit nový tuple:
novy_tuple = stary_tuple[:2] + (nova_hodnota,) + stary_tuple[3:]  # změní prvek na pozici 2

# SET
# Nelze přímo měnit! Musíš odstranit starý a přidat nový prvek
```

## Chci ZJISTIT, zda prvek existuje

```python
# LIST
if prvek in seznam:
    # prvek existuje

# TUPLE
if prvek in ntice:
    # prvek existuje

# SET
if prvek in mnozina:
    # prvek existuje

# DICTIONARY
if "klic" in slovnik:          # testuje klíče
    # klíč existuje
if hodnota in slovnik.values(): # testuje hodnoty
    # hodnota existuje
```

## Chci ZÍSKAT všechny prvky/klíče/hodnoty

```python
# LIST
for prvek in seznam:
    print(prvek)

# TUPLE
for prvek in ntice:
    print(prvek)

# SET
for prvek in mnozina:
    print(prvek)

# DICTIONARY
for klic in slovnik:           # iteruje přes klíče
    print(klic)
    
for klic in slovnik.keys():    # explicitně přes klíče
    print(klic)
    
for hodnota in slovnik.values(): # iteruje přes hodnoty
    print(hodnota)
    
for klic, hodnota in slovnik.items(): # iteruje přes páry
    print(klic, hodnota)
```

## Chci ZJISTIT DÉLKU

```python
pocet = len(seznam)            # LIST
pocet = len(ntice)             # TUPLE
pocet = len(mnozina)           # SET
pocet = len(slovnik)           # DICTIONARY (počet klíčů)
```

## Chci použít SLICING (výřez)

```python
# LIST
vyrez = seznam[1:4]            # prvky od indexu 1 do 3 (4 není včetně!)
vyrez = seznam[:3]             # prvky od začátku do indexu 2
vyrez = seznam[2:]             # prvky od indexu 2 do konce
vyrez = seznam[:]              # kopie celého seznamu
vyrez = seznam[-3:]            # poslední 3 prvky
vyrez = seznam[::2]            # každý druhý prvek (krok 2)
vyrez = seznam[::-1]           # obrácený seznam

# TUPLE
vyrez = ntice[1:4]             # funguje stejně jako u listu
vyrez = ntice[::2]

# STRING
vyrez = retezec[1:4]           # funguje stejně jako u listu

# SET, DICTIONARY
# Nelze! Set nemá pořadí prvků, Dictionary nemá číselné indexy
```

**Syntax:** `[start:stop:step]`
- `start` - začátek (včetně), výchozí 0
- `stop` - konec (NENÍ včetně!), výchozí délka
- `step` - krok, výchozí 1

## Chci VYPRÁZDNIT strukturu

```python
# LIST
seznam.clear()                 # vymaže všechny prvky
seznam = []                    # nebo vytvoř nový prázdný seznam

# SET
mnozina.clear()                # vymaže všechny prvky
mnozina = set()                # nebo vytvoř novou prázdnou množinu

# DICTIONARY
slovnik.clear()                # vymaže všechny páry
slovnik = {}                   # nebo vytvoř nový prázdný slovník

# TUPLE
# Nelze vyprázdnit existující tuple, ale můžeš vytvořit nový prázdný:
ntice = ()
```

---

**Shrnutí vlastností:**

| Struktura  | Měnitelná? | Uspořádaná? | Duplicity? | Přístup     |
|------------|------------|-------------|------------|-------------|
| List       | ✓ Ano      | ✓ Ano       | ✓ Ano      | index [i]   |
| Tuple      | ✗ Ne       | ✓ Ano       | ✓ Ano      | index [i]   |
| Set        | ✓ Ano      | ✗ Ne        | ✗ Ne       | pouze `in`  |
| Dictionary | ✓ Ano      | ✓ Ano*      | ✗ Ne (klíče)| klíč [key] |

*Od Pythonu 3.7+ slovníky zachovávají pořadí vkládání
