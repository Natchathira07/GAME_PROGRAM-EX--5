# GAME_PROGRAM-EX--5
## MAKING PLAYER TO COLLECT THE AMMO AND INCREASE THE BULLET SPAWN COUNT.
NAME : Natchathira VD
<BR>
REGISTER NO : 212224230178
## AIM :
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

## PROCEDURE :
Setup Player Character
• Open your PlayerCharacter Blueprint.
<BR>
• Add a new Integer variable named AmmoCount.
<BR>
• Set an initial default value (e.g., AmmoCount = 10).
<BR>
• Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.

Create Ammo Pickup Blueprint
• Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.

• Add components:

○ Static Mesh: Representing the ammo (e.g., a bullet or crate).
<BR>
○ Sphere Collision: To detect overlap with the player.

• In the Event Graph of BP_AmmoPickup:

○ Use OnComponentBeginOverlap on the Sphere Collision.
<BR>
○ Cast to PlayerCharacter.
<BR>
○ Increase the player’s AmmoCount (e.g., AmmoCount += 5).
<BR>
○ Optionally, play a pickup sound or effect.
<BR>
○ Destroy the ammo pickup actor.

Update Shooting Logic (Optional)
• In your player’s shooting logic:

○ Before spawning a bullet, check if AmmoCount > 0.
<BR>
○ If true:

▪ Spawn bullet.
<BR>
▪ Decrease AmmoCount by 1.

Place Ammo in the World
• Drag instances of BP_AmmoPickup into your level from the Content Browser.
<BR>
• Adjust position, mesh, and pickup range as needed.

## OUTPUT :
<img width="508" height="222" alt="image" src="https://github.com/user-attachments/assets/0bc7dd4b-c82f-4710-8983-8603b260cfab" />
<img width="504" height="342" alt="image" src="https://github.com/user-attachments/assets/2216362c-9197-4421-968f-3229c96abaa3" />
<img width="853" height="446" alt="image" src="https://github.com/user-attachments/assets/9b2e5b0a-0ec7-4cd9-be85-7a9ba548c0c6" />
<img width="854" height="559" alt="image" src="https://github.com/user-attachments/assets/8c0f274a-d7c8-4c24-9a41-b1d2b799e7c8" />

## RESULT :
• The player starts with a limited number of bullets.
<BR>
• When the player overlaps with an ammo pickup:

○ The ammo is collected.
<BR>
○ The player's AmmoCount increases.

• The player can now fire additional bullets based on the updated ammo count.

