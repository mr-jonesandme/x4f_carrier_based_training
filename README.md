# Carrier Based Training v0.0.1a

Carrier Based Training is a mod for X4 which adds an automated subordinate training and reassignment system. A new default order is made available to L and XL ships with an average crew skill of 1 star, called "Train Subordinates".  Ships running this order will train their subordinates, increasing both the subordinate pilot's piloting, engineering, and morale skills, while also distributing some engineering/morale experience across the subordinate ship's service crew.  For each pilot that successfully graduates training, the training carrier commander may receive a minor bump in XP to the commander's piloting and management skills.  Subordinates that complete training will automagically reassign themselves to the player designated L/XL/Station.

Forum link - https://forum.egosoft.com/viewtopic.php?f=181&t=426485

## Installation

Place the 'carrier_based_training' folder into your X4 Foundations extensions folder.  This mod does not require a fresh game start. Make a backup of your save just in case

## Uninstallation
Prior to removing the mod, clear the "Train Subordinates" command from any L/XL ship by removing all orders and assignments, then wait at least 20 minutes.  You should receive a notification and logbook entry that the carrier is no longer training pilots - doing this will allow the script to safely unset any training parameters prior to your removal

## Current Features and Usage

### Carrier Operation
The player is to setup the training carrier parameters, and assign all desired "trainees" as direct subordinates to the carrier.  The subordinates can be added before or after issuing the order-the sequence does not matter.  The training "carrier" (carrier defined loosely as any L/XL ship is elgible for this order) will then patrol the designated sector, only engaging enemies if fired upon. Every 15 or so minutes, subordinates will have the chance to gain experience for both the pilot and service crew of the assigned ship. If enabled, the player will receive hourly summary reporting into the "tips" section of the logbook from the training carrier commander, providing stats such as current number of pilots being trained, total operating costs, and the total number of pilots that have "graduated" from training.

#### Train Subordinates Options
The player can set the following options:

- Training Area - a sector for the carrier to operate in
- Assignment Upon Completion - A L ship, XL ship, or station that "graduated" pilots will be reassigned to
- Desired Pilot Rank - A slider bar to set the threshold for pilot skill (in stars) for when the pilot should graduate
- Professional Training - Enable pro training.  The cost ranges from 6k-30kCr/hr/ship depending on the Desired Pilot Rank
- Progress Reports - Enables hourly summary reporting into the "tips" logbook from training carrier commanders

Further details regarding the mechanics of these settings can be found below

#### Skills and Professional Training Costs
The player is able to train subordinate piloting skills up to the piloting level of the commander assigned to the ship - a commander with 1 star in piloting can train pilots up to 1 star, a 2 star pilot can train up to 2 stars in piloting, and so on. Additionally, the player has the ability to opt in to paying for "Professional Training".  Currently, pilots will be trained approximately four times faster if this option is selected. The cost for the professional training is currently calculated as: 
stars_to_train * 500cr * num_subordinates.  This cost is deducted from the player account every 15 minutes-if the player has insufficient credits, subordinates will not receive any experience.  In a future update, something "bad" may happen to players that are unable to pay the credits required for pro training.

Currently, there is no penalty for not selecting professional training, other than the slower accrual of experience.  Future updates may add features such as training accidents that may occur randomly to pilots that are not being professionally trained.

#### Automated Reassignment
Once a given subordinate pilot reaches the player defined threshold in piloting skill level, the subordinate ship will automatically assign itself to the player designated L/XL/Station to report for duty.  In the event the new duty station is unavailable, destroyed, or otherwise non-existent in the game universe, the player will receive a notification regarding the event, and the subordinate will remain attached to the training commander as an active trainee and continue to incur costs (if professional training is enabled).

#### Notifications
The player will receive logbook entries for training related topics per carrier to the "upkeep" category of the logbook, and if enabled, progress reports from training commanders to the "tips" category of the logbook.  All messages are prefixed with "TrainingOps" to make them easy to filter for.  The player will receive upkeep logbook entries for the following events:

- Commander retires from training (commander no longer exists, has died, has been unassigned)
- Carrier decomissioned (all orders/assignments cleared from training carrier)
- Pilot reassignment is not possible (pilots cannot be reassigned due to an issue with the duty station)
- Training fees paid (costs for training pilots)
- Pilot completed training (pilot graduated, provides printout of skills)
- Insufficient funds (player account doesn't have enough money to pay for professional training)

If progress reports are enabled, the player will receive the following event to the "tips" logbook (also prefixed with TrainingOps):

- Commander Report Available

#### Other Notes
The "Reassignment" system can be used to create a funnel of training systems, should you be interested in doing so.  Say you have two carriers-one with a three star pilot, and the other with a five star pilot.  It is entirely valid to set Carrier A to train pilots up to three stars, and designate training carrier B as the reassignment point, with it training pilots up to five stars, before finally assigning pilots to some other L/XL ship or station.  Upon completing training at 3 stars with Carrier A, pilots will automatically assign themselves and travel to Carrier B to continue training up to the threshold of five stars, before then assigning themselves to the next location


## Known Issues
N/A

## Change Log

### 0.0.1a
- Initial release

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. 
## License
[MIT](https://choosealicense.com/licenses/mit/)
