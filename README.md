# 🎲 Dice Game

An interactive **Yahtzee-style dice game built with HTML, CSS, and JavaScript**.

The player rolls five dice and chooses from available scoring combinations to earn as many points as possible across six rounds.

This project helped me practice building more complex JavaScript logic involving **arrays, objects, loops, functions, DOM manipulation, event listeners, conditional logic, random number generation, and game-state management**.

## 🎮 How the Game Works

Each round, the player can roll **five dice** up to **three times**.

After rolling, the game analyzes the dice and determines which scoring combinations are available.

The player selects a valid scoring option, keeps the score, and advances to the next round.

The game continues for **six rounds**, after which the final score is displayed and the game resets.

## 🎯 Scoring Combinations

The game evaluates several dice combinations:

### Three of a Kind

At least three dice contain the same value.

The score is calculated using the total value of all five dice.

### Four of a Kind

At least four dice contain the same value.

The score is calculated using the total value of all five dice.

### Full House

A combination containing:

- Three dice of one value
- Two dice of another value

A Full House awards **25 points**.

### Small Straight

Four sequential dice values, such as:

```text
1, 2, 3, 4
2, 3, 4, 5
3, 4, 5, 6
```

A Small Straight awards **30 points**.

### Large Straight

Five sequential dice values:

```text
1, 2, 3, 4, 5
```

or

```text
2, 3, 4, 5, 6
```

A Large Straight awards **40 points**.

The player can also choose a zero-point option when no useful scoring combination is available.

## 🧠 How It Was Built

The project separates the interface, styling, and application logic into:

```text
Dice_Game_3/
├── index.html
├── styles.css
├── index.js
└── README.md
```

### HTML

HTML creates the game's interface, including:

- Five dice
- Current round
- Number of rolls
- Total score
- Scoring options
- Score history
- Game controls
- Rules display

### CSS

CSS handles the visual design and layout of the game.

### JavaScript

JavaScript controls the game logic and manages the changing state of the application.

Some of the main state variables include:

```javascript
let diceValuesArr = [];
let score = 0;
let round = 1;
let rolls = 0;
```

These values change as the player rolls dice, selects scores, and progresses through the game.

## 🎲 Random Dice Generation

Each roll generates five random numbers between `1` and `6`.

```javascript
const randomDice = Math.floor(Math.random() * 6) + 1;
```

The generated values are stored inside an array:

```javascript
diceValuesArr.push(randomDice);
```

The program then updates the DOM so the player can see the new dice values.

This gave me practice connecting **randomly generated application data to visible UI elements**.

## 🔍 Detecting Dice Combinations

One of the main challenges in this project was analyzing an array of dice values and determining which scoring combinations were present.

### Duplicate Detection

The program counts how many times each dice value appears.

This allows the game to detect:

- Three of a Kind
- Four of a Kind

The logic uses an object to keep track of occurrences of each number.

### Full House Detection

The program examines the number of occurrences and checks whether the dice contain both:

```text
3 matching values
+
2 matching values
```

If both are present, the Full House scoring option becomes available.

### Straight Detection

For straights, the dice are sorted:

```javascript
dice.sort((a, b) => a - b);
```

The values are then analyzed for sequential patterns representing small and large straights.

This helped me understand how transforming data can make a problem easier to solve.

## 🖥️ DOM Manipulation

The game uses JavaScript to update the interface dynamically instead of reloading the page.

JavaScript updates elements such as:

- Dice values
- Current round
- Roll count
- Total score
- Available scoring options
- Score history
- Rules visibility

The game also enables and disables scoring options depending on the current dice combination.

## 🖱️ Event-Driven Programming

The game responds to player actions using event listeners.

For example, clicking **Roll Dice** triggers the logic responsible for:

1. Checking the number of rolls
2. Generating five random dice
3. Updating the interface
4. Detecting duplicates
5. Checking for a Full House
6. Checking for Straights
7. Enabling valid scoring options

The player can roll a maximum of three times before selecting a score.

## 🔄 Game State and Reset Logic

The game tracks multiple pieces of state simultaneously:

```text
Dice values
Current score
Current round
Number of rolls
Selected scoring option
Score history
Rules visibility
```

After six scoring rounds, the game displays the player's final score and resets the application so another game can begin.

## 💡 What I Learned

This project helped me practice combining individual JavaScript concepts into a larger interactive application.

Some of the main concepts I worked with include:

- JavaScript functions
- Arrays
- Objects
- `for` loops
- `for...of` loops
- Conditional statements
- Boolean logic
- Array methods
- `.forEach()`
- `.reduce()`
- `.includes()`
- `.some()`
- `.sort()`
- `.join()`
- `.push()`
- `Object.values()`
- Random number generation with `Math.random()`
- `Math.floor()`
- DOM manipulation
- Event listeners
- Template literals
- Radio button inputs
- Enabling and disabling UI controls
- Game-state management

One of the biggest lessons from this project was learning how to **break a larger problem into smaller functions**.

Instead of having one function control the entire game, different functions
