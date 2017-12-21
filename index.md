## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Andreu997/MercSchool/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

MercSchool is a game designed by Rodrigo de Pedro Lombao and Andreu Sacasas as a project for the Artificial Inteligence subject in UPC school with the objective of developing 3 different agents that interact between themselves and they sourroundings depending on their objectives and necessities.

#1. Environment
Champion school is played in a 2D world simulating the school’s building land. The map area is limited by boundaries.

##1.1 Game areas

The school area is divided in three areas with own features:

-School: this is where students will live, train and rest. The main purpose of this zone is to improve recruits skills. Players can spend money on new buildings only in this zone. This zone will never grant money to the player.

-Arena: in this zone students will fight against competitors of other schools, granting money to the player if victorious. Functionality is further described in the Arena section.

-School outskirts: this zone includes the outside field of the school. At night, bandits will come to try to attack the school, which must be defended by the students.

##1.2 Day/Night cycle:

During daytime: - The school and the arena are open, and students will focus on training or battling in the arena. While on day, the player will be able to decide if the soldiers train or rest depending on their health and stamina, and there will be the option to buy new soldiers if the player has enough money.

At night: - The school and the arena are closed, and the player is unable to build or upgrade. - Bandits will attack the students, coming from the outskirts in waves. The students will focus on defeat them.


#2. Characters

##2.1 Students

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

###Stamina

Training or fighting will deplete students’ stamina. Battling in the arena depletes it slower than battling bandits, and training depletes it slower than battling.

If a student runs out of stamina, it will be unable to study and will fight significantly slower.

If they are not in combat, students with depleted stamina will raise it by visiting stamina buildings.

###Health

Health is depleted when a student receives a hit, and is slowly regenerated over time. Students die if their Health Points reach zero.

##2.2 Instructors

The instructors will make sure that the soldiers are training as they should; when the soldiers have low stamina (from 10 to 30%) sometimes they will stop training. If there is not an instructor around when that happens, the soldier could go to the bedroom and lose the rest of the day there.

##2.3 Bandits
Bandits are the main threat in the game; as if they overpower player students the game is lost.

The number and level of the enemies increases over time, so players must be able to improve the school quick enough to even the enemy forces.

Players can see the incoming enemies in the enemy pool. There, player can see the number of waves, the enemies on each wave, their skills and their level. Therefore, players can plan their decisions during daytime to be ready at night.

Unlike player students, which can have different ranks in different disciplines, bandits are archetypes and their skills are defined. Thus, the enemy class “novice archer” will always have the same level and skill set.

Killing enemies will grant money to the player based on the defeated enemy level. Also, speeding up enemy waves will grant money based on the remaining time.
