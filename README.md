# GameSimulator
In this project, we have implemented 6 design patterns, such as: **Strategy, Abstract Factory, Observer, Adapter, Decorator, Bridge**. 
## Adapter
At first we can choose operating system of your computer to adapt:
```
What operating system do you play on?
1. Windows
2. MacOS
```
This is to ensure that everything works as it should on your operating system.
## Abstract Factory
Here we see a choice between magicians and swordsmen. 
```
Choose your fighter from: 
1. Magician
2. Swordsman
```
This choice will determine which factory to use in the future when creating characters.

Next, we are given a choice between possible characters:
```
Choose your magician: 
1. Wizard
2. Priest
3. Necromancer
```
If we choose magician then in terminal we can see that we are created our character:
```
You created wizard
```
This part in code we can see in main class:
```java
Magician magician1 = characterFactory.getMagician("WIZARD");
```
## Bridge
This output shows our **bridge** pattern:
```
He can walk and fly
```
It means that our magician can move using walk and fly classes. In code it is looks like:
```java
CharacterFactory characterFactory = new MagicianFactory(new Walking(), new Flying());
//...
characterFactory.setMove();//usage
```
## Decorator
And here we can decorate our character:
```
Set your character with:
1. Bandanna.
2. Armor.
3. Cloak.
4. Hat.
```
After choosing, terminal showed us that we are decorated our character with **bandanna**:
```
Settings: You are setting Wizard to wear the bandanna
```
This part in our code look like character class inside new decoration class:
```java
Magician bandanna = new Bandanna(magician);
System.out.println("Settings: " + bandanna.setCharacterMagician());
```
## Observer
Then in terminal we can see message like this:
```
We have new decoration: [Diamond armor]
```
It means that our observer is working. In code it is like this:
```java
DecorationStore decorationStore = new DecorationStore();//our object
//...
decorationStore.registerObserver((Observer) magician1);//registration new observer
//...
decorationStore.addNewDecoration("Diamond armor");//add new decoration
```
## Strategy
Here we see that our character have own weapon, but we can change it to new one:
```
I have my own weapon.
I create magic with magic stones!
If you want change it choose number:
1. Yes, i don't like your weapon.
2. No, you have a good weapon.
```
If we type 1 we can choose another weapon that available:
```
Then choose what you like:
1. Grimoire
2. Staff
3. Stone
```
When we choose for instanse Grimoire we see:
```
I use a grimoire to create magic!
```
In code it is like creating new grimoire behavior and set it into our magician weapon behavior:
```java
magician.setWeaponBehavior(new GrimoireBehavior());
magician.fight();
```
In the end we can play mini-game:
