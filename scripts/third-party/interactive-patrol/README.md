
This is basically like creating a bunch of triggers tied to cronjobs triggered by the detection of specific assets near the region selected.

  Copy the file patrol.sqf into that mission folder. File -> Open Scenario Folder



  Creating a mission with this script requires three steps:

  1. Position the player on the map.

  2. Create a rectangular marker over the area that should be patrolled (e.g. a city).
     Give this marker a name (e.g. "Alpha")

  3. Create as many units (or groups) as you find appropriate, and put the following call
     into the init field of each group leader: nul=[this,"Alpha"] execVM "patrol.sqf"

   PLAY THE MISSION!



  Details on each step, and further customization options:

  AREA MARKER

   ``� The marker should be rectangular. The script will work with a round marker,
     but it won't be an exact representation of the area that is being patrolled.
     If the marker is rotated this will automatically be taken into consideration.
     Color, fill patterns and marker text don't matter.
  ``

  `` � You can have as many different area markers as you wish,
     to have different units patrol different areas. These zones can overlap.
  ``

   ``� Do not to use special symbols in the marker name.
     Underscore ("_") is ok, but most others ("-",":","/", etc.) will cause errors.
   ``

   ``� The marker can be defined via a variable (e.g. area="Alpha"; nul=[this,area] execVM "patrol.sqf")
   ``

   ``� The marker position and size can be changed anytime during the mission.
     Units will automatically update their patrol area.
   ``

   ``� By default the area marker is hidden during the mission.
     To make it visible in the game, use the "SHOWMARKER" option.
   ``

   ``� If you want to avoid the area marker to be seen during the pre-mission briefing,
     you can add the following line to your init.sqf:
     "markername" setMarkerPos [-(getMarkerPos "markername" select 0),-(getMarkerPos "markername" select 1)];
  ``

   ``� You can use a trigger, instead of a markers, to designate the active area.
     In that case the trigger should be named, and the script would be called with the
     trigger object as the area parameter: e.g. nul=[this,citytrigger] execVM "patrol.sqf"
  ``


  PATROLLING UNIT

  `` � The script can be called by any side: BLUFOR, OFPOR, INDEPENDENT or CIVILIANS.
   ``
  `` � It will work with any type of units: Infantry, Armored, cars, choppers, boats and planes.
    ``
  `` � It can be used with single units or groups (only the group leader needs to call the script).
    ``
    - If the group leader dies, another member will take over the lead, and continue to patrol.
     - Units don't need to be named or have any waypoints.
     - If the initial position of the unit is outside the assigned marker area it will first start
       moving toward it.
     - The unit parameter can also be an array that contains all members of the patrolling group.
       In that case the array is searched for a living member to lead the patrol group.

   ``� Patrolling units will make stops of random length (between 10 and 30 seconds) when they reach their
   ``   patrol end points. This can be suppressed via a "NOWAIT" parameter.

  `` � By default unit will start at the location they've been placed at in the editor.
  `` If you want the start position to be anywhere within the active area use parameter "RANDOM".

   ``� You can create a random number of 'clones' of a patrolling unit with the "MIN:n"/"MAX:n" parameters.
  ``   (see details below)

  `` � Every patrolling group can have a global variable assigned to it which allows you to stop the
  ``   script for that particular group (see "GLOBAL VARIABLES" at the bottom).

  ``� To display a message ("SECTOR <areaname> CLEARED") when a sector is cleared of a specific side,
  ``   use the "TRIGGER" parameter.

   - Only the position of the first two arguments in the script call are crucial: [unit,"markername"].
   - The position and capitalization of the other arguments don't matter.



  OPTIONAL ARGUMENTS

	Movement:
  RANDOM      = The initial position of the group will be anywhere within the marker area.
                While this option increases the randomness of the mission, keep in mind that because
                of the unpredictability of positions, some units may be stuck in inaccessable areas.
                Infantry units may also end up on rooftops. In that case they will *stay* at that
                position, instead of patrolling the area.
                nul=[this,"Alpha","RANDOM"] execVM "patrol.sqf"
  RANDOMDN    = Only random positions on the ground level will be used.
  RANDOMUP    = Only the top building positions will be used.
                Note: Only building tops that can be accessed via stairs or ladders will be used,
                and the units this way will not move away from their position.
                Only single units can be placed on rooftops! If "RANDOMUP" is used with a group,
                it is ignored.
                Note: Only building tops that can be accessed via stairs or ladders will be used!
                Also - Only single units can be placed on rooftops.
                If this command is used with a group it will still be placed on ground level.

  NOAI        = By default soldier units will try evasive and flanking maneuvers if they spot an opponent.
                With this switch this behaviour can be turned off. (Units will patrol the
                area normally, and only show the regular AI behaviour as defined by VBS2.)
                nul=[this,"Alpha","NOAI"] execVM "patrol.sqf"
  NOFOLLOW    = The patrolling unit will not leave the marker area, not even to pursue spotted enemies.
                Because of the overriding AI behaviour this will not work with 100% reliability with
                team members (who may decide to go after an enemy after all).
                The team leader though (or a single patrolling unit) will never leave the area.
                nul=[this,"Alpha","NOFOLLOW"] execVM "patrol.sqf"
  NOMOVE      = The unit will stay at its initial position until an enemy is spotted, who it will then pursue.
                Once the enemy is killed (or lost) the unit will return to the start position.
                nul=[this,"Alpha","NOMOVE"] execVM "patrol.sqf"
  NOSLOW      = By default the units' behaviour is set to "safe" and the speed to "limited".
                With this switch that setting can be turned off (in case the unit's
                behaviour/speed, as defined in the editor should be used).
                this setBehaviour "STEALTH"; nul=[this,"Alpha","NOSLOW"] execVM "patrol.sqf"
  NOWAIT      = Do not wait at patrol end points
                nul=[this,"Alpha","NOWAIT"] execVM "patrol.sqf"

	Clones:
  MIN:x/MAX:y = Creates a random number of 'clones' of the unit or group that's calling the script.
                This increases the randomness of the mission, as even the mission maker himself
                won't know how many enemy units he will have to face.
                The copied units will be of the same type and patrol behaviour as the original ones.
                The number of copies created is between the MIN:x and the MAX:y parameter.
                So if the script is called with "MIN:",3,"MAX:",6 between 3 and 6 copies of the
                original group will be created.
                Keep in mind that each of of these arguments (MIN & MAX) actually consists of TWO parameters
                that are given to the script: "MIN:",NUMBER and "MAX:",NUMBER.
                This command only works with Infantry units (no vehicles can be cloned).
                If the cloned unit is type "Civilian", then the clones will be random types of "Civilian 1" to 6.
                If only MIN:x is defined MAX will default to the same value as MIN.
                If only MAX:y is defined MIN will default to 1.
                nul=[this,"Alpha","MIN:",3,"MAX:",6] execVM "patrol.sqf"
  INIT:s      = NOT AVAILABLE IN ARMA3!

  PREFIX:s    = Prefix to use for cloned units' names. (Default is "UPSCLONE")
                nul=[this,"Alpha","PREFIX:","OPFOR"] execVM "patrol.sqf"

  SHOWMARKER  = Display the area marker (by default it is hidden at mission start).
                nul=[this,"Alpha","SHOWMARKER"] execVM "patrol.sqf"


  NOSLOW      = By default the units' behaviour is set to "safe" and the speed to "limited".
                With this switch that setting can be turned off (in case the unit's
                behaviour/speed, as defined in the editor should be used).
                this setBehaviour "STEALTH"; nul=[this,"Alpha","NOSLOW"] execVM "patrol.sqf"

  NOAI        = By default soldier units will try evasive and flanking maneuvers if they spot an opponent.
                With this switch this behaviour can be turned off. (Units will patrol the
                area normally, and only show the regular AI behaviour as defined by ArmA.)
                nul=[this,"Alpha","NOAI"] execVM "patrol.sqf"

	General:
  TRIGGER     = Display a message when no more units of the associated side are left in the sector.
                nul=[this,"Alpha","TRIGGER"] execVM "patrol.sqf" or

  TRACK       = Displays a marker with the current position, as well as the destination, for each unit.
                (mainly used for testing and debugging missions)
  EMPTY:x     = Normally, the zone is considered empty if no enemy units are left.
                If you want to allow a few leftover units, and still consider it cleared, enter
                the number here.
                nul=[this,"Alpha","EMPTY:",3] execVM "patrol.sqf"

  DELETE:x    = Delete dead units after the specified number of seconds.
                nul=[this,"Alpha","DELETE:",60] execVM "patrol.sqf"


  NAMED       = If you would like to be able to influence a unit's patrolling behavior after the script
                has started, you have to give a unit a name in the editor, and use the "NAMED' parameter
                in the script arguments. This will create a global variable for each patrolling unit/group
                that can then be set by other scripts. (See GLOBAL VARIABLES below.)

  CYCLE:x     = By default there is a 5 second delay between test cycles in this sript.
                If you want a short one (for very crucial or fast moving units for example) or think a
                unit will do fine with a longer one (slow-moving, non-critical units) it can be overridden
                via this argument. (Any units that come across a new "danger situation" will temporarily
                get shorter cycles, independently of this setting.)
                nul=[this,"Alpha","CYCLE:",2] execVM "patrol.sqf"
