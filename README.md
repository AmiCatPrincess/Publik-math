/*
 * Summary:     Determine order of attacks, and process each battle
 * Parameters:  Creature object representing attacker
 *              | Creature object representing defender
 * Return:      Boolean indicating successful fight
 * Author:      Ryan Campbell
 */
function beginBattle(attacker, defender) {
    var isAlive;    // Boolean inidicating life or death after attack
    var teamCount;  // Loop counter

    // Check for pre-emptive strike
    if(defender.agility > attacker.agility) {
        isAlive = defender.attack(attacker);
    }

    // Continue original attack if still alive
    if(isAlive) {
        isAlive = attacker.attack(defender);
    }

    // See if any of the defenders teammates wish to counter attack
    for(teamCount = 0; teamCount < defender.team.length; i++) {
        var teammate = defender.team[teamCount];
        if(teammate.counterAttack = 1) {
            isAlive = teammate.attack(attacker);
        }
    }

    // TODO: Process the logic that handles attacker or defender deaths

    return true;
} // End beginBattle
// .
def compact(arr):
    return list(filter(lambda x: bool(x), arr))
