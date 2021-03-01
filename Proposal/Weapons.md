# Proposal for "Grubhub/WizardTower"
I had some suggestions/proposals for the design doc to run by everyone. I wasn't sure the best place for everything (and it seemed like a lot for a google doc comment), so I gathered it here. I can move stuff over if people agree it looks good.

- [Dashing](#Dashing)
- [Control Scheme](#Input)
- [Power Ups](#Power-Up)
- [Weapons](#Weapons)
  - [Sword](#Sword)
  - [Spear](#Spear)
  - [Hammer](#Hammer)

# Dashing
The design doc proposes using two buttons for a dash/dodge left/right action, based on the direction faced and the button pressed. I wanted to propose an alternate version:

![Dash](https://cdn.discordapp.com/attachments/815685836124454945/815696232944893973/1614547463227-8ebad3fb-3eb2-4558-869a-e7c898cbc00d_.jpg)

- Dash/Dodge are merged into just the Dash action - the player dashes in the direction held when the Dash Button is pressed, or Forward if no direction is pressed.
  - *(Alternative: Pressing Dash with no direction pressed has the player do a special Backstep, similar to the Dodge proposed.)*
- The Dash carries the player forward ~3
- The player is invulnerable to damage for the first half of the Dash animation
  - Rather than breaking special blocks, the player Dashes through damage. This unlocks paths that were blocked by sources of damage, and also provides the player with a way to pass through enemies
- "Dashing" can be split into 3 Power-Ups: **Dash**, **Air Dash**, **Vertical Dash**

# Input
I wanted to propose a different control scheme, particularly to go with a different dash mechanic. This should make good use of the controller real-estate, and should make the game playable for a lot of people before needing input reassignment in the controls. *(It does assume that it's fairly easy to assign multiple buttons to one action)*

![Controls](https://cdn.discordapp.com/attachments/815685836124454945/815687703681040404/Controls.png)

- **[Move]** `WASD`; `L.Analog Stick`; `D-Pad`
  - > *Using both D-Pad and Control Stick on a sidescroller makes life easier in situations where it's important to press Up/Down and not Left/Rigght*
- **[Jump]** `Space`;  `Btn:A`;   
  - > *'A' is the most used Jump button for 2D platformers, as it is the button hit most often. Most keyboard players will likely assume Space=Jump, and it works well with WASD movement*
- **[Dash]** `L.Shift`; `Btn:B`; `L.Trigger`; `R.Trigger`   
  - > *This spread of controls makes it relatively easy to 'Dash' in conjunction with any other button while still using movement controls. It should feel comfortable with players muscle memory from other games; Shift is a common Dash/Dodge key in 3D games, B is a common dodge/evade button in action games, and Triggers are both often used for 'dash' in sidescrollers and ensure the player can quickly use dash+weapon inputs*
- **[Weapon]** `E`; `L.Mouse Button`; `Btn:X`; `R.Bumper`   
  - > *Using both a Face Button and a Bumper to attack is a way I've sometimes seen to more easily fit different player's muscle memory, and also an easy accessibility way to make sure the player has no trouble using different buttons in tandem. As for 'E', it is difficult to find right-hand keys that work well with WASD movement, but Q/E are common choices. J/K or ;/' may be an option if keyboard-only controls are a goal*
- **[SubWeapon]** `Q`; `R.Mouse Button`; `Btn:Y`; `L.Bumper`  
  - > *Choosing commonly paired keys, enforcing weapon/subweapon as two sides of the same coin and the player's two main options*
- **[Menu]** `Esc` `Tab` `Btn:Start`   
  - > *There always needs to be an accessible button to bring up some kind of menu, even in a jam game. Esc/Start is assumed, Tab is easily accessible (particularly if something like a map or inventory comes into play)
- **[Confirm]** `E` `Space` `Enter` `Btn:A`   
  - > *Input for selecting the currently highlighted option in a menu; best to just cover all the standard bases*
- **[Back/Cancel]** `Q` `Tab` `Esc` `Btn:B`   
  - > *Input to exit current menu, cancel a command, or go back. Esc/B are usually assumed to work, Tab is handy as it can both open/close a menu. Q just mimics the gamepad.*

# Power Up
Suggestions for unlockable powers (or whatever we end up calling them) - each meant to be a passive ability that makes the player a bit stronger and allows passing some kind of new obstacle. In some cases, multiple different powerups may allow passing the same obstacle, but there could be a new obstacle only passable with multiple powerups.

- **Dash** - Instantly accelerate forward, becomming momentarily immune to damage for the first half of the dash
  - `[Input]` Press 'Dash' + Left/Right
  - `[Animation]` "Dash" animation
  - `[Unlock]` Enables dashing through enemies (such as an enemy who is immune from the front blocking a hallway) or damaging barriers (such as a flame/lightning wall, or timed walls of projectiles)
- **Air Dash** - Allows 'Dashing' while in the air. The player is unaffected by gravity during the Dash animation.
  - `[Input]` Press 'Dash' + Left/Right while in the air. Works only once before landing.
  - `[Animation]` "Air Dash" *(Optional: Can re-use Dash animation)*
  - `[Unlock]` Dash through aerial enemies, barriers, and projectiles, in addition to succeeding certain platforming challenges
- **Vertical Dash** - Allows player to dash Up or Down (Down-Dash only while in air)
  - `[Input]` Press 'Dash'+Up, or 'Dash'+Up/Down while in the air. Usable once before landing (shared with Air Dash)
  - `[Animation]` Dash Up and Dash Down animations
  - `[Unlock]` Dash through horizontal damaging barriers, reach greater heights
- **Glide** - Allows player to slow their descent while in the air *(drastically reduce Max Fall Speed)*
  - `[Input]` Hold down 'Jump' while descending
  - `[Animation]` Special 'Glide' animation *(Or re-use standard fall animation, but with added effects)*
  - `[Unlock]` Allows leaping long gaps and remaining in the air for longer (such as for a timed platform challenge)
- **Slam** - Allows player to quickly drop onto enemies from the air, destroying cracked blocks and granting a new tool in combat. Player should 'Bounce' off of enemies when hitting them.
  - `[Input]` Press Down+'Jump' while in the air
  - `[Animation]` Slam animation (Optional: Unique animation per weapon type)
  - `[Unlock]` Allows breaking cracked floor blocks, potentially bounding off enemies *(such as in Shovel Knight)*
- **Double Jump** - Allows player to make a second, less impactful jump from midair (should give ~1/2 of original jump height). Usable once before landing.
  - `[Input]` Press 'Jump' while in the air
  - `[Animation]` Second 'Jump' animation *(or re-use normal jump animation with added effects)*
  - `[Unlock]` Allows reaching greater heights and certain platforming challenges.

# Weapons
Here's a potential expansion on the Weapons section with three well-defined Weapon Types. There's room for more, but these three could create decent gameplay without too much scope.

- Weapons are a player's basic means to attack, and are not limited by resource.
- Weapons fall into one of three Categories: [Sword](#Sword), [Spear](#Spear), [Hammer](#Hammer). Each has a different set of attacks and animations.
- The player can hold one weapon at a time. Picking up a new weapon replaces your old one, and creates a 'Pickup' for your old weapon in the same spot.
- **Wishlist Items:** Each weapon can have variations on its basic type (weapons can be randomly created or chosen from a pool of pre-designed weapons). These weapons have custom art assets, as well as special effects. Certain special rewards may also append effects to a player's currently held weapon. Some effects may include:
  - Deals more damage per attack (plus a flashy extra effect on hit)
  - Slightly increased or decreased animation speed
  - The player keeps their momentum when attacking with this weapon on the ground
  - The weapon creates 'Pickups' when damaging an enemy (Health, Mana, Money)
  - The weapon creates an explosion or other damaging effect on attack, increasing the effective range of the weapon
  - The weapon is able to deflect enemy projectiles that it hits
  - Special effects occur under certain conditions:
    - Fire a projectile at full health
    - While at full Mana, drain Mana and create an explosion
    - Deal double damage while at low health
    - Every X seconds, the next attack creates an explosion

![Weapons](https://cdn.discordapp.com/attachments/815685836124454945/815711441461182514/Weapons.png)

### Sword
- Swords are basic, balanced weapons that deal Normal Damage.
- Sword Attacks have extremely fast **Startup Time** but slower **End Lag** *(The attack hits very quickly, but the animation lingers for a moment before the player regains control)*
- The sword's Attack Range should be ~1-2 units *(~16-32 pixels past your hitbox)*, and should reach roughly from knee to head height *(hitting short enemies, but not ones above your head)*
- **Animations:**
  - Attack
  - Attack (In Air)
  - Dash+Attack (Allows dashing through enemies while also hitting them)
  - 2-Hit Combo (Press 'Attack' again before first attack finishes for fast/flashy damage extra damage)

### Spear
- Spears are harder to use, but have long reach and can attack Up or Down to hit tricky enemies
- Spears deal Normal Damage. Attacks should have a slow **Startup Time** *(More animation frames before moment of impact)*
- The Attack Range should be ~2-3 tiles away from the player *(~32-48 pixels past your hitbox)*, but should be narrow
- The Spear can attack in Four Directions - left, right, up, and down
- **Animations:**
  - Attack Left/Right
  - Attack Low Left/Right
  - Attack Up
  - Attack Left/Right (In Air)
  - Attack Up (In Air)
  - Attack Down (In Air)

### Hammer
- Hammers are slow, but deal 2x Normal Damage and have a large attack arc
- Hammer Attacks have a Slow **Startup Time** and **End Lag** *(The attack takes longer to hit and lingers for a moment before the player regains control)*
- The Attack Range should be ~1-2 units away from the player *(~16-32 pixels past your hitbox)* and should make a large arc from over the player's head
- **Wishlist**: The Attack Animation is split into a clamped 'Wind-Up' and 'Hit' animation. The attack is held until the player releases the button, giving the player extra control over the moment of the attack.
- **Animations**
  - Wind-Up
  - Attack
  - Wind-Up (In Air)
  - Attack (In Air)
