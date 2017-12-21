## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Andreu997/MercSchool/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

MercSchool is a game designed by Rodrigo de Pedro Lombao and Andreu Sacasas as a project for the Artificial Inteligence subject in UPC school with the objective of developing 3 different agents that interact between themselves and they sourroundings depending on their objectives and necessities.

# 1. Environment
Champion school is played in a 2D world simulating the school’s building land. The map area is limited by boundaries.

![MercSchool.png](https://bitbucket.org/repo/Egox5rM/images/2914641364-MercSchool.png)

## 1.1 Game areas

The school area is divided in three areas with own features:

-School: this is where students will live, train and rest. The main purpose of this zone is to improve recruits skills. Players can spend money on new buildings only in this zone. This zone will never grant money to the player.

-Arena: in this zone students will fight against competitors of other schools, granting money to the player if victorious. Functionality is further described in the Arena section.

-School outskirts: this zone includes the outside field of the school. At night, bandits will come to try to attack the school, which must be defended by the students.

## 1.2 Day/Night cycle:

During daytime: - The school and the arena are open, and students will focus on training or battling in the arena. While on day, the player will be able to decide if the soldiers train or rest depending on their health and stamina, and there will be the option to buy new soldiers if the player has enough money.

At night: - The school and the arena are closed, and the player is unable to build or upgrade. - Bandits will attack the students, coming from the outskirts in waves. The students will focus on defeat them.


# 2. Characters

## 2.1 Students

Students are the core element in gameplay, as they are the only way to earn money and the survival of the school depend on their skills to defend it.

Admission

·Every day, players will receive an amount of new recruits for the school. The amount changes based in the game’s progression.  
·New recruits start with some skills already learnt. The amount of skills changes based in the game’s progression.  
·Skill ranks and the level of the next recruits can be seen in the recruit’s pool.  
·Players can instantly admit a student in the recruit’s pool if they pay a certain amount of money.  
·Knowledge and learning  
·Students train five disciplines, each one with an XP bar and five attainable ranks displayed as stars:

-Melee combat: damage, precision, and knockback in close quarter combat.  
-Ranged combat: damage, precision, and knockback in ranged combat.  
-Block: chance to block incoming damage. Is tested against enemy precision.  
-Health: amount of max Health Points.  
-Stamina: amount of max Stamina Points.  

Training in one of the knowledge fields will raise the XP bar. Once the XP bar is full, a rank is gained and the bar is emptied. Students will not train maxed out disciplines.

The student level is obtained as the sum of all currently attained ranks.

### Stamina

Training or fighting will deplete students’ stamina. Battling in the arena depletes it slower than battling bandits, and training depletes it slower than battling.

If a student runs out of stamina, it will be unable to study and will fight significantly slower.

If they are not in combat, students with depleted stamina will raise it by visiting stamina buildings.

### Health

Health is depleted when a student receives a hit, and is slowly regenerated over time. Students die if their Health Points reach zero.

## 2.2 Instructors

The instructors will make sure that the soldiers are training as they should; when the soldiers have low stamina (from 10 to 30%) sometimes they will stop training. If there is not an instructor around when that happens, the soldier could go to the bedroom and lose the rest of the day there.

## 2.3 Bandits
Bandits are the main threat in the game; as if they overpower player students the game is lost.

The number and level of the enemies increases over time, so players must be able to improve the school quick enough to even the enemy forces.

Players can see the incoming enemies in the enemy pool. There, player can see the number of waves, the enemies on each wave, their skills and their level. Therefore, players can plan their decisions during daytime to be ready at night.

Unlike player students, which can have different ranks in different disciplines, bandits are archetypes and their skills are defined. Thus, the enemy class “novice archer” will always have the same level and skill set.

Killing enemies will grant money to the player based on the defeated enemy level. Also, speeding up enemy waves will grant money based on the remaining time.


# 3. Buildings

## 3.2 Training Zones

There are different buildings/places where the soldiers can train different abilities:

### Shooting Range

Improves ranged combat abilities.

![Range.png](https://bitbucket.org/repo/Egox5rM/images/1262888750-Range.png)

### Obstacle Course

Improves stamina and health.

![Stamina.png](https://bitbucket.org/repo/Egox5rM/images/2154352920-Stamina.png)

### Boxing zone

Improves block and close combat damage.

![Melee.png](https://bitbucket.org/repo/Egox5rM/images/2054448001-Melee.png)

### Building site (arena)

A place where soldiers fight between themselves; improves a lot stamina, block and close combat damage in exchange of life points.

![Arena.png](https://bitbucket.org/repo/Egox5rM/images/2828972573-Arena.png)

## Rest zones

There are also other buildings that are not for training but for healing life points and stamina.

### Bedrooms

Where soldiers go to sleep; this recovers stamina and a bit of life points.

![Dorms.png](https://bitbucket.org/repo/Egox5rM/images/228931485-Dorms.png)

### Rest zone

Recovers stamina.

![rest.png](https://bitbucket.org/repo/Egox5rM/images/4046535930-rest.png)

### Infirmary

![Infermary.png](https://bitbucket.org/repo/Egox5rM/images/4269666369-Infermary.png)

Recovers life points and a bit of stamina.

# 4. Win-Lose condition and Score

Players lose if all player students are killed. If there are students on the recruit pool but the player does not call them before its last student dies, the game is lost anyway.

To win, players must survive twenty minutes. Once the player has won, he can choose to end the game or keep playing. Player’s score is obtained by the amount of money earned through all the game and the number and level of surviving students.

# 5. AI

Is understood as atomic behavior the most basic and simple capabilities of an agent. The composition of atomic behaviors creates complex actions, and those are represented in the AI routines.

## 5.1 Atomic behaviors

Reach: the agent will try to reach a specific building.  
Sleep: once home is reached, do nothing.  
(Soldier) Train: the agent will improve its abilities for battle.  
(Soldier) Hit: the agent will try to damage an adjacent entity.

## 5.2 Complex behaviors

(Soldier) Improve: find best available military building and train in it.  
(Soldier) Attack: Reach nearest enemy, hit them, and reach them again if necessary.  
(Instructor) Train soldiers: Make sure that the soldiers are training if they have some stamina left.

## 5.3 AI routines (decisions ordered by priority)

Soldier (at day): 
- Improve.

Instructor (at day): 
- Patrol.

Soldier (at night): 
- Attack bandits.

Bandit (at night): 
- Attack the base.

If idle, all do Wander.

# 6. Behabiour Trees and FSMs

## Soldiers
  
This is the main FSM for the Character and the blackboard for the its system:

![MainFSM.png](https://bitbucket.org/repo/Egox5rM/images/2257906766-MainFSM.png)


The behaviour tree used while its day time:

![Dibujo sin título.png](https://bitbucket.org/repo/Egox5rM/images/1785782186-Dibujo%20sin%20t%C3%ADtulo.png)


And all the FSMs used in it:

![FSMs.png](https://bitbucket.org/repo/Egox5rM/images/3781748777-FSMs.png)


And his is the tree used when its night time:

![NightTree.png](https://bitbucket.org/repo/Egox5rM/images/1907183039-NightTree.png)


## Enemies

This is the tree for the enemies and its blackboard:

![EnemyTree.png](https://bitbucket.org/repo/Egox5rM/images/1071495327-EnemyTree.png)


## Inspector

And this is the the inspector tree:

![InspectorTree.png](https://bitbucket.org/repo/Egox5rM/images/4179646943-InspectorTree.png)
