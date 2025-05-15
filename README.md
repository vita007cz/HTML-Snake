# HTML-Snake
Projekt do školy 
# 🐍 Snake Game in HTML5 Canvas

Jednoduchá implementace klasické hry **Snake** v JavaScriptu, vykreslená pomocí `<canvas>`. Uživatel může hru ovládat pomocí klávesnice a resetovat ji pomocí tlačítka. Volba obtížnosti je připravena, ale zatím není implementována.

## 🔗 Demo

> (Zde můžeš přidat odkaz na GitHub Pages nebo jiné online demo, pokud ho vytvoříš.)

## 📁 Obsah

- `HTML` pro strukturu stránky
- `CSS` pro vzhled hry
- `JavaScript` pro logiku hry (kreslení, ovládání, skóre, kolize atd.)

---

## 🧠 Vysvětlení kódu

### 🧱 HTML Struktura
```html
<div id="gameContainer">
    <canvas id="gameBoard" width="500" height="500"></canvas>
    <div id="scoreText">0</div>
    <button id="resetBtn">Reset</button>
    <p>Choose difficulty:</p>
    <button id="easyDiffBtn">Easy</button>
    <button id="mediumDiffBtn">Medium</button>
    <button id="hardDiffBtn">Hard</button>
</div>
```
- **`<canvas>`**: Vykreslovací plocha pro hru.
- **`<div id="scoreText">`**: Zobrazuje skóre.
- **`<button>`**: Ovládací tlačítka (reset a výběr obtížnosti).

---

### 🎨 CSS Styly
```css
#gameBoard { border: 3px solid; }
#scoreText { font-size: 100px; }
#resetBtn { border-radius: 15px; cursor: pointer; }
```
- Stylizace herního pole, textu skóre a tlačítek.

---

### 🕹️ JavaScript – Logika hry

#### 🔄 Inicializace a proměnné
```js
const gameBoard = document.querySelector("#gameBoard");
const ctx = gameBoard.getContext("2d");
// ... ostatní proměnné pro barvy, velikosti, stav hry ...
```

---

#### ▶️ `gameStart()`
Spouští hru: nastaví `running = true`, vytvoří jídlo, vykreslí ho a spustí herní smyčku pomocí `nextTick()`.

---

#### ⏲️ `nextTick()`
```js
setTimeout(() => {
    clearBoard();
    drawFood();
    moveSnake();
    drawSnake();
    checkGameOver();
    nextTick();
}, 50);
```
- Hlavní smyčka hry – každých 50 ms vykoná všechny kroky hry.

---

#### 🧼 `clearBoard()`
Vymaže celé herní pole (canvas) před novým vykreslením.

---

#### 🍎 `createFood()` a `drawFood()`
Náhodně vygeneruje nové souřadnice jídla a vykreslí ho červeným čtvercem.

---

#### 🐍 `moveSnake()` a `drawSnake()`
- **`moveSnake()`**: Přidá nový "head" dle směru pohybu a odstraní poslední segment, pokud nezískal jídlo.
- **`drawSnake()`**: Vykresluje hada po částech.

---

#### 🎮 `changeDirection(event)`
Změní směr hada podle stisknuté šipky, pokud nejde zpět do protisměru.

---

#### 💥 `checkGameOver()`
Kontroluje kolize:
- S okrajem canvasu
- Sám se sebou (když had narazí do vlastního těla)

---

#### ☠️ `displayGameOver()`
Vypíše na canvas nápis "GAME OVER!" a zastaví hru.

---

#### 🔁 `resetGame()`
Obnoví výchozí stav hry, resetuje skóre a pozici hada, a znovu spustí hru.

---

## 🔧 Funkce obtížnosti

Tlačítka pro výběr obtížnosti jsou připravena (`easyDiffBtn`, `mediumDiffBtn`, `hardDiffBtn`), ale nejsou zatím propojena s logikou hry. Doporučený způsob je měnit rychlost (`setTimeout` delay).

---

## 🧪 Možnosti vylepšení

- Přidání logiky pro obtížnosti
- Zvuky při sežrání jídla nebo kolizi
- Lokální ukládání nejvyššího skóre
- Responsivní canvas pro mobilní zařízení

---

## ▶️ Jak spustit

1. Nakopíruj soubor do `.html` souboru.
2. Otevři ho v libovolném webovém prohlížeči.

---

## 📄 Licence

Tento projekt je k dispozici pod licencí [MIT](LICENSE), což znamená, že si s ním můžeš dělat, co chceš — hlavně se u toho bav!
