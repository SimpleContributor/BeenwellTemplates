# BeenwellTemplates

## Code template forms for Beenwell RP

### Boss Menu

Uses the job name, and takes vec3 for the boss menu and the duty menu.

<pre>
['sast'] = {
    { bossCoords = {vector3(1542.64, 814.79, 82.03)}, dutyCoords = {vector3(1541.86, 815.52, 77.56)} }
},
</pre>

## Work Uniform Template

<pre>
[2] = {  
    outfitLabel = 'Polo',  
    outfitData = {  
        ['t-shirt'] = {item = 13, texture = 0, defaultItem = 0, defaultTexture = 0}, -- T-Shirt  
        ['torso2'] = {item = 257, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Jackets  
        ['arms'] = {item = 105, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Arms  
        ['vest'] = {item = 0, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Vest  
        ['pants'] = {item = 99, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Pants  
        ['shoes'] = {item = 55, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Shoes  
        ['hat'] = {item = 121, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Hat  
        ['mask'] = {item = 121, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Mask  
        ['bag'] = {item = 0, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Bag  
        ['decals'] = {item = 65, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Decals  
        ['accessory'] = {item = 96, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Neck  
        ['glass'] = {item = 0, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Glasses  
        ['ear'] = {item = 0, texture = 0, defaultItem = 0, defaultTexture = 0}, -- Ear accessories  
    }  
},
</pre>

## POLICE STATION TEMPLATES

### Police Station

To add a new station, add new coords to each: stash, fingerprint and stations

<pre>
Config.Locations = {
    duty = {},
    vehicle = {},
    stash = {
        vector3(450.9, -993.58, 31.13),         -- MRPD
        vector3(615.73, 9.36, 83.11),           -- VWPD
        vector3(-450.17, 6009.79, 30.72),       -- PPD
        vector3(367.16, -1596.52, 33.3),        -- DPD [1]
        vector3(369.7, -1598.5, 33.3),          -- DPD [2]
        vector3(1841.85, 3680.93, 34.19),          -- SPD
        vector3(1539.75, 811.97, 76.65)         -- SAST
    },
    impound = {
        -- vector3(436.68, -1007.42, 27.32),
        -- vector3(-436.14, 5982.63, 31.34),
    },
    helicopter = {},
    trash = {},
    fingerprint = {
        vector3(461.57, -989.56, 24.91),     -- MPRD
        vector3(613.15, -3.92, 82.78),          -- VWPD
        vector3(-432.18, 5997.29, 31.72),          -- PPD
        vector3(357.25, -1607.05, 24.87),            -- DPD
        vector3(1816.59, 3673.32, 34.19),            -- SPD
        vector3(1556.21, 835.36, 76.6)              -- SAST
    },
    evidence = {},
    stations = {
        { label = 'Police Station',        coords = vector4(428.23, -984.28, 29.76, 3.5) },
        { label = 'Prison',                coords = vector4(1845.903, 2585.873, 45.672, 272.249) },
        { label = 'Police Station Paleto', coords = vector4(-451.55, 6014.25, 31.716, 223.81) },
        { label = 'Police Station Vinewood', coords = vector4(619.8, 1.36, 82.78, 81.47) },
        { label = 'Police Station Davis', coords = vector4(377.91, -1614.79, 29.29, 226.35) },
        { label = 'Police Station Sandy', coords = vector4(1835.81, 3677.6, 34.19, 7.11) },
        { label = 'Trooper Station', coords = vector4(1542.35, 819.5, 77.66, 298.29) },
    },
}
</pre>

### Police Armory

Only need loc

<pre>
-- This is the location of the third eye target circle. ONLY USE IF THE PED IS HARD TO ACCESS i.e. behind a cage
{ loc = vector3(621.24, -19.65, 82.53), length = 0.5, width = 3.0, heading = 270.0, minZ = 30.5, maxZ = 32.0, distance = 3 },
{
    ped = `s_m_y_cop_01`,
    scenario = 'WORLD_HUMAN_CLIPBOARD',
    loc = vector3(621.15, -20.46, 81.78),
    heading = 335.54,
},
</pre>

### Police Evidence Locker

Only need name and loc

<pre>
{
    coords = vector3(1548.07, 826.98, 82.13),
    target = {
        name = 'sast_evidence', -- name of zone must be uniuqe
        loc = vector3(1548.07, 826.98, 82.13),
        length = 1.4,
        width = 3.2,
        heading = 30,
        minZ = 29.09,
        maxZ = 31.89
    }
},
</pre>

### Outfit/Uniform Changers

Outfit Changer - Choose between any saved outfits

<pre>
{shopType = 'outfit', coords = vector3(1534.64, 814.44, 77.66)}
</pre>

Work Uniform Changer - Choose between any saved WORK outfits. Must be added using the template.

<pre>
{requiredJob = 'police', isGang = false, coords = vector3(1841.16, 3678.24, 34.19)}
</pre>

## GREENZONES

Should be self explanitory. Only need the vec3 coords for the center of the circle.

<pre>
coords = vector3(1555.02, 800.12, 77.04)
</pre>

## GARAGE TEMPLATES

### Spawner Garage for Jobs

General spawner code for job based garages i.e. police, ambulance.  
Helicoptor spawn:

<pre>
coords = vector3(-472.81, 5990.73, 31.34),
spawn = {
    vector4(-476.3, 5987.76, 31.73, 0.04),
},
</pre>

Car spawn:

<pre>
DavisPDBasement = {
    coords = vector3(355.54, -1618.84, 23.79),
    spawn = {
        vector4(350.13, -1628.23, 23.39, 141.41),
        vector4(352.6, -1630.56, 23.39, 140.9),
        vector4(347.44, -1626.95, 23.39, 143.85),
        vector4(342.69, -1633.13, 23.39, 229.8)
    },
    distance = 8,
    job = {
        'police',
        'sast',
    },
    type = 'car',
    blip = {
        id = 357,
        color = 0,
        scale = 0.6,
    },
    hideBlip = true,
    hideMarkers = true,
    markers = {
        id = 21,
        size = {
            x = 0.3,
            y = 0.3,
            z = 0.3,
        },
        color = {
            r = 255,
            g = 255,
            b = 255,
            a = 120,
        },
        bobUpAndDown = 0,
        faceCamera = 0,
        rotate = 1,
        drawOnEnts = 0,
    },
    vehiclesType = 'spawner',
    showLiveriesExtrasMenu = true,
    vehicles = {
        {
            model = 'police',
            plate = 'OBEY',
            minJobGrade = 0,
        },
        {
            model = 'police2',
            plate = 'POPO',
            minJobGrade = 1,
        },
        {
            model = 'police3',
            plate = 'POPO2',
            minJobGrade = 2,
        },
        {
            model = 'policeb',
            plate = 'PDBIKE',
            minJobGrade = 2,
        },
        {
            model = 'policet',
            plate = 'GOTCNDY',
            minJobGrade = 2,
        },
        {
            model = 'pbus',
            plate = 'PENILE',
            minJobGrade = 2,
        },
        {
            model = 'riot',
            plate = 'RIOT',
            minJobGrade = 4,
        },
    },
},
</pre>

### Gang Garage

<pre>
['The Lost MC'] = {
    coords = vector3(439.18, -1518.48, 29.28),
    spawn = vector4(439.18, -1518.48, 29.28, 139.06),
    distance = 15,
    gang = 'lostmc',
    type = 'car',
    vehiclesType = 'personal',
    blip = {
        id = 357,
        color = 0,
        scale = 0.6,
    },
    hideBlip = false,
    hideMarkers = true,
    markers = {
        id = 21,
        size = {
        x = 0.3,
        y = 0.3,
        z = 0.3,
        },
        color = {
        r = 255,
        g = 255,
        b = 255,
        a = 120,
        },
        bobUpAndDown = 0,
        faceCamera = 0,
        rotate = 1,
        drawOnEnts = 0,
    },
},
</pre>

### General Garage

Owned car storage garage

<pre>
['North Vinewood Blvd'] = {
    coords = vector3(365.21, 295.65, 103.46),
    spawn = {
        vector4(360.56, 289.97, 102.79, 250.77),
        vector4(357.68, 282.12, 102.68, 247.18),
        vector4(368.04, 268.92, 102.35, 339.31),
        vector4(392.06, 280.63, 102.28, 69.88)
    },
    distance = 15,
    type = 'car',       -- car, air or boat
    hideBlip = false,
    blip = {
        id = 357,
        color = 0,
        scale = 0.6,
    },
    hideMarkers = true,
    markers = {
        id = 21,
        size = {
        x = 0.3,
        y = 0.3,
        z = 0.3,
        },
        color = {
        r = 255,
        g = 255,
        b = 255,
        a = 120,
        },
        bobUpAndDown = 0,
        faceCamera = 0,
        rotate = 1,
        drawOnEnts = 0,
    },
},
</pre>

### Towing

<pre>
['Impound B'] = {
    coords = vector3(1649.71, 3789.61, 34.79),
    spawn = vector4(1643.66, 3798.36, 34.49, 216.16),
    distance = 15,
    type = 'car',
    job = {
        'police',
        'sast',
    },
    blip = {
        id = 68,
        color = 0,
        scale = 0.6,
    },
    hideBlip = false,
    hideMarkers = true,
    markers = {
        id = 21,
        size = {
        x = 0.3,
        y = 0.3,
        z = 0.3,
        },
        color = {
        r = 255,
        g = 255,
        b = 255,
        a = 120,
        },
        bobUpAndDown = 0,
        faceCamera = 0,
        rotate = 1,
        drawOnEnts = 0,
    },
},
</pre>

## CAR DEALERSHIP

### Vehicle Categories

This is the dealership config in it's entirety. Use boss menu etc. for other configs needed  
Uses Turbo Wheels as the example

<pre>
turbowheels = {
    type = 'owned',
    showroomType = 'car',
    openShowroom = {
        coords = vector3(-1068.2, -252.13, 44.6),
        size = 5,
    },
    openManagement = {
        coords = vector3(-1039.43, -237.85, 44.6),
        size = 5,
    },
    sellVehicle = {
        coords = vector3(-1068.63, -231.26, 38.17),
        size = 5,
    },
    purchaseSpawn = vector4(-1048.25, -219.67, 37.88, 29.78),
    testDriveSpawn = vector4(-1056.38, -213.63, 37.84, 296.62),
    enableSellVehicle = true,
    sellVehiclePercent = 0.6,
    camera = {
        name = 'Car',
        coords = vector4(-146.6166, -596.6301, 166.0, 270.0),
        positions = {
            5,
            8,
            12,
            8,
        },
    },
    categories = {
        'muscle',
        'sports',
        'sportsclassics',
        'super',
        'trucks',
    },
    enableTestDrive = true,
    hideBlip = false,
    blip = {
        id = 523,
        color = 2,
        scale = 0.6,
    },
    societyPurchaseJobWhitelist = {},
    societyPurchaseGangWhitelist = {},
    enableFinance = true,
    hideMarkers = false,
    markers = {
        id = 21,
        size = {
            x = 0.3,
            y = 0.3,
            z = 0.3,
        },
        color = {
            r = 255,
            g = 255,
            b = 255,
            a = 120,
        },
        bobUpAndDown = 0,
        faceCamera = 0,
        rotate = 1,
        drawOnEnts = 0,
    },
    showroomJobWhitelist = {},
    showroomGangWhitelist = {},
    disableShowroomPurchase = false,
    directSaleDistance = 50,
    job = 'turbowheels',
},
</pre>

## AMBULANCE

### General Hospital

Need to still use the boss menu and garages setup, but everything else should be here

<pre>
Paleto = {
    RespawnPoint = { -- When player dies and bleeds out; they will revive at nearest hospital; Define the coords of this hospital here.
        coords = vector3(-270.24, 6319.31, 32.44),
        heading = 234.73,
        -- Even if you have useCheckInInstead to true, you must still define these coords for finding closest hospital
        -- If you want to use check-in instead of respawning at this location(Otherwise will just spawn at the coords above)
        useCheckInInstead = true
    },

    Blip = {
        Enabled = true,
        Coords = vector3(-270.24, 6319.31, 32.44),
        Sprite = 61,
        Color = 2,
        Scale = 1.0,
        String = 'Paleto Bay Hospital'
    },
    
    -- use okokBossMenu instead
    clockInAndOut = {
        enabled = false,
    },
    -- Personal Locker. Supports inventories: ox_inventory, qb-inventory, and qs-inventory
    -- Custom inventories can easily be added in wasabi_bridge/inventories/
    PersonalLocker = {
        enabled = true,                        -- Enable personal locker(stash)
        jobLock = 'ambulance',                  -- Job lock?
        coords = vec3(-254.81, 6318.52, 33.83),   -- Location of where to access personal locker (If target is disabled)
        label = '[E] - Access Personal Locker', -- Text to display(If not using target)
        maxWeight = 5000,                       -- Total Weight of the personalLocker
        slots = 30,                             -- Number of slots available in the Personal Locker
        distance = 2.0,                         -- Distance to display text UI(If not using target)
        target = {
            enabled = true,                    -- If enabled, the location and distance above will be obsolete
            label = 'Access Locker',
            coords = vector3(-254.75, 6319.14, 31.68),
            heading = 70.18,
            width = 2.0,
            length = 1.0,
            minZ = 43.38 - 0.9,
            maxZ = 43.38 + 0.9
        }
    },

    -- use okokBossMenu instead
    BossMenu = {
        Enabled = false,
    },

    CheckIn = {                                      -- Hospital check-in
        Enabled = true,                              -- Enable ped and check-in area?
        Ped = 's_m_m_scientist_01',                  -- Check in ped
        Coords = vector3(-264.73, 6314.37, 32.44 - 0.9), -- Coords of ped
        Distance = 4.85,                             -- Distance to show textUI (If target is not enabled below)
        Heading = 347.83,                             -- Heading of ped
        Cost = 500,                                  -- Cost of using hospital check-in. Set to false for free
        Duration = 15 * seconds,                     -- Time it takes to spend in hospital bed
        MaxOnDuty = 3,                               -- If this amount or less you can use, otherwise it will tell you that EMS is avaliable(Set to false to always enable check-in)
        PayAccount = 'bank',                         -- Account dead player pays from to check-in
        PayHospital = 'ambulance',                         -- Payments made to check-in go to the company society/account? (ex. 'society_ambulance' for ESX and 'ambulance' for QBCore or false for no)
        Label = '[E] - Check In',                    -- label of text UI if target is not enabled below
        HotKey = 38,                                 -- Default: 38 (E) (If target below is not enabled)
        Target = {
            enabled = true,                          -- Enable Target? (Can be customized in wasabi_bridge/customize/cl_customize.lua the target system)
            label = 'Check In',
            coords = vec3(-264.73, 6314.37, 32.74),
            heading = 347.83,
            distance = 5.0,
            width = 2.0,
            length = 1.0,
            minZ = 43.28 - 0.9,
            maxZ = 43.28 + 0.9
        },
        DisableHospitalBeds = false,                                                       -- Disable hospital beds for check-in at this location?(Player will spend Duration checking in before respawning in RespawnNoBedLocation when set to true)
        RespawnNoBedLocation = { coords = vec3(316.66, -581.3, 43.28), heading = 339.02 }, -- Coords and heading of where to spawn player if DisableHospitalBeds is set to true or beds are full
        HospitalBeds = {
            { coords = vec3(-260.18, 6320.31, 32.00 + 0.3), heading = 314.47 },
            { coords = vec3(-257.83, 6317.98, 32.00 + 0.3), heading = 315.9 },
            { coords = vec3(-258.76, 6308.88, 32.01 + 0.3),  heading = 315.04 }
        }

    },

    -- use 17mov_CharacterSelecter instead
    Cloakroom = {
        Enabled = false,
    },

    MedicalSupplies = {                                                     -- EMS Shop for supplies
        Enabled = true,                                                     -- If set to false, rest of this table do not matter
        Ped = 's_m_m_doctor_01',                                            -- Ped to target
        Coords = vector3(-253.06, 6327.51, 32.43 -0.9),                       -- Coords of ped/target
        Heading = 261.21,                                                   -- Heading of ped
        Supplies = {                                                        -- Supplies
            { item = 'medbag',     label = 'Medical Bag',   price = 1000 }, -- Pretty self explanatory, price may be set to 'false' to make free
            { item = 'medikit',    label = 'First-Aid Kit', price = 250 },
            { item = 'bandage',    label = 'Bandage', price = 100 },
            { item = 'tweezers',    label = 'Tweezers', price = 100 },
            { item = 'suturekit',    label = 'Suture Kit', price = 100 },
            { item = 'icepack',    label = 'Ice Pack', price = 100 },
            { item = 'burncream',    label = 'Burn Cream', price = 100 },
            { item = 'defib',    label = 'Defibrillator', price = 1000 },
            { item = 'sedative',    label = 'Sedative', price = 200 },
            { item = 'morphine30', label = 'Morphine 30MG', price = 500 },
            { item = 'morphine15', label = 'Morphine 15MG', price = 250 },
            { item = 'perc30',     label = 'Percocet 30MG', price = 600 },
            { item = 'perc10',     label = 'Percocet 10MG', price = 200 },
            { item = 'perc5',      label = 'Percocet 5MG',  price = 100 },
            { item = 'vic10',      label = 'Vicodin 10MG',  price = 300 },
            { item = 'vic5',       label = 'Vicodin 5MG',   price = 150 },
            { item = 'fentanyl',   label = 'Fentanyl',      price = 10000 }
        }
    },

    -- use jg-advancedgarages instead
    Vehicles = {                                   -- Vehicle Garage
        Enabled = false,                            -- Enable? False if you have your own way for medics to obtain vehicles.
    },
},
</pre>

## MECHANIC

### Mechanic Shop

Using Tej's Garage as an example

<pre>
['Corpse Customs'] = {
    type = "owned",
    job = "corpsecustoms",
    jobManagementRanks = {4},
    logo = "bennys.png",
    locations = {
    {
    coords = vector3(-1044.83, -1719.77, 4.05),
        size = 10.0,
        showBlip = true,
    },
    {
        coords = vector3(-1066.98, -1723.8, 4.05),
        size = 10.0,
        showBlip = false,
    },
    {
        coords = vector3(-1063.51, -1727.65, 4.05),
        size = 10.0,
        showBlip = false,
    },
    {
        coords = vector3(-1059.83, -1731.33, 4.05),
        size = 5.0,
        showBlip = false,
        employeeOnly = true,
    }
    },
    blip = {
    id = 446,
    color = 47,
    scale = 0.7
    },
    mods = {
    repair           = { enabled = true, price = 4000, percentVehVal = 0.01 },
    performance      = { enabled = true, price = 5500, percentVehVal = 0.01, priceMult = 0.1 },
    cosmetics        = { enabled = true, price = 3500, percentVehVal = 0.01, priceMult = 0.1 },
    stance           = { enabled = true, price = 2500, percentVehVal = 0.01 },
    respray          = { enabled = true, price = 6000, percentVehVal = 0.01 },
    wheels           = { enabled = true, price = 5000, percentVehVal = 0.01, priceMult = 0.1 },
    neonLights       = { enabled = true, price = 4000, percentVehVal = 0.01 },
    headlights       = { enabled = true, price = 3000, percentVehVal = 0.01 },
    tyreSmoke        = { enabled = true, price = 3500, percentVehVal = 0.01 },
    bulletproofTyres = { enabled = false, price = 250000, percentVehVal = 0.01 },
    extras           = { enabled = true, price = 3000, percentVehVal = 0.01 }
    },
    tuning = {
    engineSwaps      = { enabled = true, requiresItem = true },
    drivetrains      = { enabled = true, requiresItem = true },
    turbocharging    = { enabled = true, requiresItem = true },
    tyres            = { enabled = true, requiresItem = true },
    brakes           = { enabled = true, requiresItem = true },
    driftTuning      = { enabled = true, requiresItem = true },
    },
    carLifts = { -- only usable by employees
    -- vector4(-582.05, -933.51, 23.89, 78.19)
    }
},
</pre>

## CRAFTING

There is quite a bit that goes into crafting, so I'll do my best to explain

### Items Used to Craft

These are all of the items that are used on the benches.  
I need to add photos, so any new items must be clearly seen. Marking a new item with a date is best. i.e. -- 12/10/24

<pre>
Config.itemNames = { -- Format: id = label | In case the item starts with a number make sure to set it in this format: ['9mm'] = 9mm ammo,

    -- basic items
    aluminum = 'Aluminum', -- ADD A NEW DATE LIKE SO WITH THE DOUBLE -- BEFORE THE DATE
    copper = 'Copper',
    diamond = 'Diamond',
    glass = 'Glass',
    iron = 'Iron',
    metalscrap = 'Metal Scrap',
    money = 'Money',
    plastic = 'Plastic',
    rubber = 'Rubber',
    steel = 'Steel',
    ['10kgoldchain'] = '10kgoldchain',

    -- tools
    grinder_cutter = 'Bolt Cutters',
    access_tool = 'Access Tool',
    lockpick = 'Lockpick',
    powersaw = 'Cordless Circular Saw',

    -- medical items
    bandage = 'Bandage',
    firstaid = 'First Aid',
    gas_mask = 'Gas Mask',

    -- weapons
    weapon_assaultrifle = 'Assault Rifle',
    weapon_pistol = "Pistol",
    weapon_switchblade = 'Switchblade',
    weapon_sawnoffshotgun = 'Sawn-Off Shotgun',
    weapon_pumpshotgun = 'Pump Shotgun',
    weapon_combatpistol = 'Combat Pistol',
    weapon_microsmg = 'Micro SMG',
    weapon_compactrifle = 'Compact Rifle',
    ['ammo-9'] = '9mm ammo',

    -- blueprints
    access_tool_blueprint = 'Access Tool Blueprint',
    assault_rifle_blueprint = 'Assault Rifle Blueprint',
    combat_pistol_blueprint = 'Combat Pistol Blueprint',
    -- compact_rifle_blueprint = 'Compact Rifle Blueprint',
    micro_smg_blueprint = 'Micro SMG Blueprint',
    pistol_blueprint = 'Pistol Blueprint',

}
</pre>

### Craftable Items

This is how items are configured for crafting  

Example 1:

<pre>
['rifle-ak'] = {
    item = 'weapon_assaultrifle', -- Item id and name of the image
    amount = 1, -- Amount of the item the player will receive
    maxCraft = 1, -- Max amount of crafts at a time
    successCraftPercentage = 75, -- Percentage of successful craft 0 = 0% | 50 = 50% | 100 = 100%
    isItem = true, -- if true = is item | if false = is weapon
    isDisassemble = false, -- true = disassemble | false = craft
    time = 6, -- Time to craft (in seconds)
    levelNeeded = 2, -- What level he needs to craft this item
    xpPerCraft = 40, -- How much XP he receives after crafting this item
    recipe = { -- Recipe to craft it
    {'steel', 125, true, false}, -- item/amount/if the item should be removed when crafting/if it's money
    {'aluminum', 125, true, false},
    {'rubber', 25, true, false},
    {'plastic', 25, true, false},
    {'assault_rifle_blueprint', 1, false, false}
    },
    job = { -- What jobs can craft this item in this workbench
        ''
    },
    data = {}, -- Used to pass additional data, such as metadata
    category = 'Ranged Weapons', -- Used as ID and Name of the category
},
</pre>

Example 2:

<pre>
['switchblade'] = {
    item = 'weapon_switchblade', -- Item id and name of the image
    amount = 1, -- Amount of the item the player will receive
    maxCraft = 1, -- Max amount of crafts at a time
    successCraftPercentage = 75, -- Percentage of successful craft 0 = 0% | 50 = 50% | 100 = 100%
    isItem = false, -- if true = is item | if false = is weapon
    isDisassemble = false, -- true = disassemble | false = craft
    time = 15, -- Time to craft (in seconds)
    levelNeeded = 1, -- What level he needs to craft this item
    xpPerCraft = 40, -- How much XP he receives after crafting this item
    recipe = { -- Recipe to craft it
    {'steel', 25, true, false}, -- item/amount/if the item should be removed when crafting/if it's money
    {'aluminum', 25, true, false},
    {'rubber', 10, true, false},
    {'plastic', 15, true, false},
    },
    job = { -- What jobs can craft this item in this workbench
        ''
    },
    data = {}, -- Used to pass additional data, such as metadata
    category = 'Melee Weapons', -- Used as ID and Name of the category
},
</pre>

Example 3:

<pre>
['9mm ammo'] = {
    item = 'ammo-9', -- Item id and name of the image
    amount = 10, -- Amount of the item the player will receive
    maxCraft = 1, -- Max amount of crafts at a time
    successCraftPercentage = 75, -- Percentage of successful craft 0 = 0% | 50 = 50% | 100 = 100%
    isItem = true, -- if true = is item | if false = is weapon
    isDisassemble = false, -- true = disassemble | false = craft
    time = 3, -- Time to craft (in seconds)
    levelNeeded = 1, -- What level he needs to craft this item
    xpPerCraft = 40, -- How much XP he receives after crafting this item
    recipe = { -- Recipe to craft it
        {'iron', 2, true, false}, -- item/amount/if the item should be removed when crafting/if it's money
        {'money', 1, true, true},
    },
    job = { -- What jobs can craft this item in this workbench
        ''
    },
    data = {}, -- Used to pass additional data, such as metadata
    category = 'Ammo', -- Used as ID and Name of the category
},
</pre>

### Bench Locations and Items Crafted

I'll show two seperate examples, one that uses job restrictions and another that's for everyone  
For crafts it uses the names of items above

Example 1:

<pre>
{
    coordinates = vector3(-809.4, 190.3, 72.5), -- coordinates of the table
    radius = 1, -- radius of the table
    showMapBlip = false,
    marker = {type = 20, r = 31, g = 94, b = 255, a = 155, bobUpAndDown = 0, faceCamera = 0, rotate = 1, textureDict = 0, textureName = 0, drawOnEnts = 0},
    showBlipRadius = 50,
    blip = {blipId = 89, blipColor = 3, blipScale = 0.9, blipText = 'Crafting'}, -- to get blips and colors check this: https://wiki.gtanet.work/index.php?title=Blips
    tableName = 'General (Michaels)', -- Title
    tableID = 'general1', -- make a different one for every table with NO spaces
    crafts = { -- What items are available for crafting and the recipe
        'rifle-ak',
        'ammo-9',
    },
    jobs = { -- What jobs are able to open the workbench
        ['police'] = {
            ['boss'] = true,
            ['chief'] = true,
            ['commissioner'] = true,
        },
        ['ambulance'] = {
            ['boss'] = true,
            ['chief'] = true,
        },
        ['sast'] = {
            ['assistant commissioner'] = true,
            ['commissioner'] = true,
        },
    },
},
</pre>

Example 2:

<pre>
{
    coordinates = vector3(-817.0, 182.8, 72.3),
    radius = 1,
    showMapBlip = false,
    marker = {type = 20, r = 31, g = 94, b = 255, a = 155, bobUpAndDown = 0, faceCamera = 0, rotate = 1, textureDict = 0, textureName = 0, drawOnEnts = 0},
    showBlipRadius = 50,
    blip = {blipId = 89, blipColor = 3, blipScale = 0.9, blipText = 'Crafting'},
    tableName = 'Weapons (Michaels)',
    tableID = 'general2',
    crafts = {
        'firstaid',
    },
    jobs = {
        ['all'] = true -- For everyone to be able to open the workbench
    },
},
</pre>

## ADMIN MENU
### Perms/roles
Permissions are set through discord roles. Just say which role should have which level of power, i.e. god, admin, etc. Can be any name we want.

<pre>
UserGroups = {
    enabled = true,           -- Enable usergroups from framework (Esx/QBCore), example/common groups below by default.
    groups = {
        -- Customize and add more like example of 'mod'
        ['coordsOnly'] = {
            teleport = true,
        },
        ['cia'] = {
            ban = true,
            kick = true,
            teleport = true,
            heal = true,
            revive = true,
        },
        ['meninblack'] = {           -- Group name
            ban = true,         -- Ability to ban
            kick = true,        -- Ability to kick
            teleport = true,    -- Ability to bring/goto players
            zones = true,       -- Ability to utilize the zones system
            -- money = true,       -- Ability to give money
            -- items = true,       -- Ability to give items
            vehicles = true,    -- Ability to use vehicle functions
            revive = true,      -- Ability to revive others and themselves
            heal = true,        -- Ability to heal others and themselves
            skin = true,        -- Ability to open skin menu and give it to others
            invisible = true,   -- Ability to toggle invisibility
            godmode = true,     -- Ability to toggle god mode
            setped = true,      -- Ability to set peds in the menu
            noclip = true,      -- Ability to use no clip functions
            inventory = true,   -- Access / clear inventories
            spectate = true,    -- Ability to spectate via player options,
            playerBlips = true, -- Ability to enable player blips in server management section
        },
        ['god'] = {
            allPerms = true, -- allPerms can be defined to grant all perms at once
        },
    }
},
</pre>

## PENAL CODE
### Penal Code Titles
These correspond with the penal codes that come after these titles below. For example:  
[1] = 'OFFENSES AGAINST PERSONS' will point to the all of the codes [1] - [26] in the first set [1]  
More examples using [title]-[code]  
[1]-[1] OFFENSES AGAINST PERSONS ---- Simple Assault, class = 'Misdemeanor'
[2]-[5] OFFENSE INVOLVING THEFT ---- Carjacking, class = 'Felony'
[3]-[4] OFFENSES INVOLVING FRAUD ---- Possession of Stolen Identification, class = 'Misdemeanor'

<pre>
Config.PenalCodeTitles = {
    [1] = 'OFFENSES AGAINST PERSONS',
    [2] = 'OFFENSES INVOLVING THEFT',
    [3] = 'OFFENSES INVOLVING FRAUD',
    [4] = 'OFFENSES INVOLVING DAMAGE TO PROPERTY',
    [5] = 'OFFENSES AGAINST PUBLIC ADMINISTRATION',
    [6] = 'OFFENSES AGAINST PUBLIC ORDER',
    [7] = 'OFFENSES AGAINST HEALTH AND MORALS',
    [8] = 'OFFENSES AGAINST PUBLIC SAFETY',
    [9] = 'OFFENSES INVOLVING THE OPERATION OF A VEHICLE',
    [10] = 'OFFENSES INVOLVING THE WELL-BEING OF WILDLIFE',
}
</pre>

### Penal Code
<pre>
Config.PenalCode = {
    [1] = {
        [1] =  {title = 'Simple Assault',                                               class = 'Misdemeanor',  id = 'P.C. 1001',   months = 7,     fine = 500,     color = 'green',    description = 'When a person intentionally or knowingly causes physical contact with another (without a weapon)'},
        [2] =  {title = 'Assault',                                                      class = 'Misdemeanor',  id = 'P.C. 1002',   months = 15,    fine = 850,     color = 'orange',   description = 'If a person intentionally or knowingly causes injury to another (without a weapon)'},
        [3] =  {title = 'Aggravated Assault',                                           class = 'Felony',       id = 'P.C. 1003',   months = 20,    fine = 1250,    color = 'orange',   description = 'When a person unintentionally, and recklessly causes bodily injury to another as a result of a confrontation AND causes bodily injury'},
        [4] =  {title = 'Assault with a Deadly Weapon',                                 class = 'Felony',       id = 'P.C. 1004',   months = 30,    fine = 3750,    color = 'red',      description = 'When a person intentionally, knowingly, or recklessly causes bodily injury to another person AND either causes serious bodily injury or uses or exhibits a deadly weapon'},
        [5] =  {title = 'Involuntary Manslaughter',                                     class = 'Felony',       id = 'P.C. 1005',   months = 60,    fine = 7500,    color = 'red',      description = 'When a person unintentionally and recklessly causes the death of another'},
        [6] =  {title = 'Vehicular Manslaughter',                                       class = 'Felony',       id = 'P.C. 1006',   months = 75,    fine = 7500,    color = 'red',      description = 'When a person unintentionally and recklessly causes the death of anther with a vehicle'},
        [7] =  {title = 'Attempted Murder of a Civilian',                               class = 'Felony',       id = 'P.C. 1007',   months = 50,    fine = 7500,    color = 'red',      description = 'When a non-government person intentionally attacks another with the intent to kill'},
        [8] =  {title = 'Second Degree Murder',                                         class = 'Felony',       id = 'P.C. 1008',   months = 100,   fine = 15000,   color = 'red',      description = 'Any intentional killing that is not premeditated or planned. A situation in which the killer intends only to inflict serious bodily harm.'},
        [9] =  {title = 'Accessory to Second Degree Murder',                            class = 'Felony',       id = 'P.C. 1009',   months = 50,    fine = 5000,    color = 'red',      description = 'Being present and or participating in the act of parent charge'},
        [10] = {title = 'First Degree Murder',                                          class = 'Felony',       id = 'P.C. 1010',   months = 0,     fine = 0,       color = 'red',      description = 'Any intentional killing that is willful and premeditated with malice.'},
        [11] = {title = 'Accessory to First Degree Murder',                             class = 'Felony',       id = 'P.C. 1011',   months = 0,     fine = 0,       color = 'red',      description = 'Being present and or participating in the act of parent charge'},
        [12] = {title = 'Murder of a Public Servant or Peace Officer',                  class = 'Felony',       id = 'P.C. 1012',   months = 0,     fine = 0,       color = 'red',      description = 'Any intentional killing that is done to a government employee'},
        [13] = {title = 'Attempted Murder of a Public Servant or Peace Officer',        class = 'Felony',       id = 'P.C. 1013',   months = 65,    fine = 10000,   color = 'red',      description = 'Any attacks that are done to a government employee with the intent to cause death'},
        [14] = {title = 'Accessory to the Murder of a Public Servant or Peace Officer', class = 'Felony',       id = 'P.C. 1014',   months = 0,     fine = 0,       color = 'red',      description = 'Being present and or participating in the act of parent charge'},
        [15] = {title = 'Unlawful Imprisonment',                                        class = 'Misdemeanor',  id = 'P.C. 1015',   months = 10,    fine = 600,     color = 'green',    description = 'The act of taking another against their will and holding them for an extended period of time'},
        [16] = {title = 'Kidnapping',                                                   class = 'Felony',       id = 'P.C. 1016',   months = 15,    fine = 900,     color = 'orange',   description = 'The act of taking another against their will for a short period of time'},
        [17] = {title = 'Accessory to Kidnapping',                                      class = 'Felony',       id = 'P.C. 1017',   months = 7,     fine = 450,     color = 'orange',   description = 'Being present and or participating in the act of parent charge'},
        [18] = {title = 'Attempted Kidnapping',                                         class = 'Felony',       id = 'P.C. 1018',   months = 10,    fine = 450,     color = 'orange',   description = 'The act of trying to take someone against their will'},
        [19] = {title = 'Hostage Taking',                                               class = 'Felony',       id = 'P.C. 1019',   months = 20,    fine = 1200,    color = 'orange',   description = 'The act of taking another against their will for personal gain'},
        [20] = {title = 'Accessory to Hostage Taking',                                  class = 'Felony',       id = 'P.C. 1020',   months = 10,    fine = 600,     color = 'orange',   description = 'Being present and or participating in the act of parent charge'},
        [21] = {title = 'Unlawful Imprisonment of a Public Servant or Peace Officer.',  class = 'Felony',       id = 'P.C. 1021',   months = 25,    fine = 4000,    color = 'orange',   description = 'The act of taking a government employee against their will for an extended period of time'},
        [22] = {title = 'Criminal Threats',                                             class = 'Misdemeanor',  id = 'P.C. 1022',   months = 5,     fine = 500,     color = 'orange',   description = 'The act of stating the intent to commit a crime against another'},
        [23] = {title = 'Reckless Endangerment',                                        class = 'Misdemeanor',  id = 'P.C. 1023',   months = 10,    fine = 1000,    color = 'orange',   description = 'The act of disregarding safety of another which may place another in danger of death or bodily injury'},
        [24] = {title = 'Gang Related Shooting',                                        class = 'Felony',       id = 'P.C. 1024',   months = 30,    fine = 2500,    color = 'red',      description = 'The act in which a firearm is discharged in relation to gang activity'},
        [25] = {title = 'Cannibalism',                                                  class = 'Felony',       id = 'P.C. 1025',   months = 0,     fine = 0,       color = 'red',      description = 'The act in which a persons consumes the flesh of another willingly'},
        [26] = {title = 'Torture',                                                      class = 'Felony',       id = 'P.C. 1026',   months = 40,    fine = 4500,    color = 'red',      description = 'The act of causing harm to another to extract informaion and or for self enjoyment'},
    },
    [2] = {
        [1] =  {title = 'Petty Theft',                                                  class = 'Infraction',   id = 'P.C. 2001',   months = 0,     fine = 250,     color = 'green',    description = 'The theft of property below $50 amount'},
        [2] =  {title = 'Grand Theft',                                                  class = 'Misdemeanor',  id = 'P.C. 2002',   months = 10,    fine = 600,     color = 'green',    description = 'Theft of property above $700'},
        [3] =  {title = 'Grand Theft Auto A',                                           class = 'Felony',       id = 'P.C. 2003',   months = 15,    fine = 900,     color = 'green',    description = 'The act of stealing a vehicle that belongs to someone else without permission'},
        [4] =  {title = 'Grand Theft Auto B',                                           class = 'Felony',       id = 'P.C. 2004',   months = 35,    fine = 3500,    color = 'green',    description = 'The act of stealing a vehicle that belongs to someone else without permission while armed'},
        [5] =  {title = 'Carjacking',                                                   class = 'Felony',       id = 'P.C. 2005',   months = 30,    fine = 2000,    color = 'orange',   description = 'The act of someone forcefully taking a vehicle from its occupants'},
        [6] =  {title = 'Burglary',                                                     class = 'Misdemeanor',  id = 'P.C. 2006',   months = 10,    fine = 500,     color = 'green',    description = 'The act of entering into a building illegally with intent to commit a crime, especially theft.'},
        [7] =  {title = 'Robbery',                                                      class = 'Felony',       id = 'P.C. 2007',   months = 25,    fine = 2000,    color = 'green',    description = 'The action of taking property unlawfully from a person or place by force or threat of force.'},
        [8] =  {title = 'Accessory to Robbery',                                         class = 'Felony',       id = 'P.C. 2008',   months = 12,    fine = 1000,    color = 'green',    description = 'Being present and or participating in the act of parent charge'},
        [9] =  {title = 'Attempted Robbery',                                            class = 'Felony',       id = 'P.C. 2009',   months = 20,    fine = 1000,    color = 'green',    description = 'The action of attempting property unlawfully from a person or place by force or threat of force.'},
        [10] = {title = 'Armed Robbery',                                                class = 'Felony',       id = 'P.C. 2010',   months = 30,    fine = 3000,    color = 'orange',   description = 'The action of taking property unlawfully from a person or place by force or threat of force while armed.'},
        [11] = {title = 'Accessory to Armed Robbery',                                   class = 'Felony',       id = 'P.C. 2011',   months = 15,    fine = 1500,    color = 'orange',   description = 'Being present and or participating in the act of parent charge'},
        [12] = {title = 'Attempted Armed Robbery',                                      class = 'Felony',       id = 'P.C. 2012',   months = 25,    fine = 1500,    color = 'orange',   description = 'The action of attempting property unlawfully from a person or place by force or threat of force while armed.'},
        [13] = {title = 'Grand Larceny',                                                class = 'Felony',       id = 'P.C. 2013',   months = 45,    fine = 7500,    color = 'orange',   description = 'Theft of personal property having a value above a legally specified amount.'},
        [14] = {title = 'Leaving Without Paying',                                       class = 'Infraction',   id = 'P.C. 2014',   months = 0,     fine = 500,     color = 'green',    description = 'The act of leaving an establishment without paying for provided service'},
        [15] = {title = 'Possession of Nonlegal Currency',                              class = 'Misdemeanor',  id = 'P.C. 2015',   months = 10,    fine = 750,     color = 'green',    description = 'Being in possession of stolen currency'},
        [16] = {title = 'Possession of Government-Issued Items',                        class = 'Misdemeanor',  id = 'P.C. 2016',   months = 15,    fine = 1000,    color = 'green',    description = 'Being in possession of Items only acquireable by government employees'},
        [17] = {title = 'Possession of Items Used in the Commission of a Crime',        class = 'Misdemeanor',  id = 'P.C. 2017',   months = 10,    fine = 500,     color = 'green',    description = 'Being in possession of Items that were previously used to commit crimes'},
        [18] = {title = 'Sale of Items Used in the Commission of a Crime',              class = 'Felony',       id = 'P.C. 2018',   months = 15,    fine = 1000,    color = 'orange',   description = 'The act of selling items that were previously used to commit crimes'},
        [19] = {title = 'Theft of an Aircraft',                                         class = 'Felony',       id = 'P.C. 2019',   months = 20,    fine = 1000,    color = 'green',    description = 'The act of stealing an aircraft'},
    },
    [3] = {
        [1] =  {title = 'Impersonating',                                                class = 'Misdemeanor',  id = 'P.C. 3001',   months = 15,    fine = 1250,    color = 'green',    description = 'The action of falsely identifying as another person to deceive'},
        [2] =  {title = 'Impersonating a Peace Officer or Public Servant',              class = 'Felony',       id = 'P.C. 3002',   months = 25,    fine = 2750,    color = 'green',    description = 'The action of falsely identifying as a government employee to deceive'},
        [3] =  {title = 'Impersonating a Judge',                                        class = 'Felony',       id = 'P.C. 3003',   months = 0,     fine = 0,       color = 'green',    description = 'The action of falsely identifying as a Judge to deceive'},
        [4] =  {title = 'Possession of Stolen Identification',                          class = 'Misdemeanor',  id = 'P.C. 3004',   months = 10,    fine = 750,     color = 'green',    description = 'To have another persons Identification without consent'},
        [5] =  {title = 'Possession of Stolen Government Identification',               class = 'Misdemeanor',  id = 'P.C. 3005',   months = 20,    fine = 2000,    color = 'green',    description = 'To have the identification of a government employee without consent'},
        [6] =  {title = 'Extortion',                                                    class = 'Felony',       id = 'P.C. 3006',   months = 20,    fine = 900,     color = 'orange',   description = 'To threaten or cause harm to a person or property for financial gain'},
        [7] =  {title = 'Fraud',                                                        class = 'Misdemeanor',  id = 'P.C. 3007',   months = 10,    fine = 450,     color = 'green',    description = 'To deceive another for financial gain'},
        [8] =  {title = 'Forgery',                                                      class = 'Misdemeanor',  id = 'P.C. 3008',   months = 15,    fine = 750,     color = 'green',    description = 'To falsify legal documentation for personal gain'},
        [9] =  {title = 'Money Laundering',                                             class = 'Felony',       id = 'P.C. 3009',   months = 0,     fine = 0,       color = 'red',      description = 'The processing stolen money for legal currency'},
    },
    [4] = {
        [1] =  {title = 'Trespassing',                                                  class = 'Misdemeanor',  id = 'P.C. 4001',   months = 10,    fine = 450,     color = 'green',    description = 'For a person to be within the bounds of a location of which they are not legally allowed'},
        [2] =  {title = 'Felony Trespassing',                                           class = 'Felony',       id = 'P.C. 4002',   months = 15,    fine = 1500,    color = 'green',    description = 'For a person to have repeatedly entered the bounds of a location of which they are knowingly not legally allowed'},
        [3] =  {title = 'Arson',                                                        class = 'Felony',       id = 'P.C. 4003',   months = 15,    fine = 1500,    color = 'orange',   description = 'The use of fire and accelerants to will and maliciously destroy, harm or cause death to a person or property'},
        [4] =  {title = 'Vandalism',                                                    class = 'Infraction',   id = 'P.C. 4004',   months = 0,     fine = 300,     color = 'green',    description = 'The willful destruction of property'},
        [5] =  {title = 'Vandalism of Government Property',                             class = 'Felony',       id = 'P.C. 4005',   months = 20,    fine = 1500,    color = 'green',    description = 'The willful destruction of government property'},
        [6] =  {title = 'Littering',                                                    class = 'Infraction',   id = 'P.C. 4006',   months = 0,     fine = 200,     color = 'green',    description = 'The willful discard of refuse into the open and not in designated bin'},
    },
    [5] = {
        [1] =  {title = 'Bribery of a Government Official',                             class = 'Felony',       id = 'P.C. 5001',   months = 20,    fine = 3500,    color = 'green',    description = 'The use of money, favors and or property to gain favor with a government official'},
        [2] =  {title = 'Anti-Mask Law',                                                class = 'Infraction',   id = 'P.C. 5002',   months = 0,     fine = 750,     color = 'green',    description = 'Wearing a mask in a prohibited zone'},
        [3] =  {title = 'Possession of Contraband in a Government Facility',            class = 'Felony',       id = 'P.C. 5003',   months = 25,    fine = 1000,    color = 'green',    description = 'Being in possession of items that are illegal while within a government building'},
        [4] =  {title = 'Criminal Possession of Stolen Property',                       class = 'Misdemeanor',  id = 'P.C. 5004',   months = 10,    fine = 500,     color = 'green',    description = 'Being in possession of items stolen knowingly or not'},
        [5] =  {title = 'Escaping',                                                     class = 'Felony',       id = 'P.C. 5005',   months = 10,    fine = 450,     color = 'green',    description = 'The action of willful and knowingly leaving custody while legally being arrested, detained or in jail'},
        [6] =  {title = 'Jailbreak',                                                    class = 'Felony',       id = 'P.C. 5006',   months = 30,    fine = 2500,    color = 'orange',   description = 'The action of leaving state custody from a state or county detention facility'},
        [7] =  {title = 'Accessory to Jailbreak',                                       class = 'Felony',       id = 'P.C. 5007',   months = 25,    fine = 2000,    color = 'orange',   description = 'Being present and or participating in the act of parent charge'},
        [8] =  {title = 'Attempted Jailbreak',                                          class = 'Felony',       id = 'P.C. 5008',   months = 20,    fine = 1500,    color = 'orange',   description = 'The willful and intentional attempted escape from a state or county detention facility'},
        [9] =  {title = 'Perjury',                                                      class = 'Felony',       id = 'P.C. 5009',   months = 0,     fine = 0,       color = 'green',    description = 'The action of stating falsities while legally bound to speak the truth'},
        [10] = {title = 'Violation of a Restraining Order',                             class = 'Felony',       id = 'P.C. 5010',   months = 20,    fine = 2250,    color = 'green',    description = 'The willful and knowing infringement upon court-ordered protective documentation'},
        [11] = {title = 'Embezzlement',                                                 class = 'Felony',       id = 'P.C. 5011',   months = 45,    fine = 10000,   color = 'green',    description = 'The willful and knowing movement of funds from non-personal bank accounts to personal bank accounts for personal gain'},
        [12] = {title = 'Unlawful Practice',                                            class = 'Felony',       id = 'P.C. 5012',   months = 15,    fine = 1500,    color = 'orange',   description = 'The action of performing a service without proper legal licensing and approval'},
        [13] = {title = 'Misuse of Emergency Systems',                                  class = 'Infraction',   id = 'P.C. 5013',   months = 0,     fine = 600,     color = 'orange',   description = 'Use of government emergency equipment for its non-intended purpose'},
        [14] = {title = 'Conspiracy',                                                   class = 'Misdemeanor',  id = 'P.C. 5014',   months = 10,    fine = 450,     color = 'green',    description = 'The act of planning a crime but not yet committing the crime'},
        [15] = {title = 'Violating a Court Order',                                      class = 'Misdemeanor',  id = 'P.C. 5015',   months = 0,     fine = 0,       color = 'orange',   description = 'The infringement of court-ordered documentation'},
        [16] = {title = 'Failure to Appear',                                            class = 'Misdemeanor',  id = 'P.C. 5016',   months = 0,     fine = 0,       color = 'orange',   description = 'When someone who is legally bound to appear in court does not do so'},
        [17] = {title = 'Contempt of Court',                                            class = 'Felony',       id = 'P.C. 5017',   months = 0,     fine = 0,       color = 'orange',   description = 'The disruption of court proceedings in a courtroom while it is in session (judicial decision)'},
        [18] = {title = 'Resisting Arrest',                                             class = 'Misdemeanor',  id = 'P.C. 5018',   months = 5,     fine = 300,     color = 'orange',   description = 'The act of not allowing peace officers to take you into custody willingly'},
    },

    [6] = {
        [1] =  {title = 'Disobeying a Peace Officer',                                   class = 'Infraction',   id = 'P.C. 6001',   months = 0,     fine = 750,     color = 'green',    description = 'The willful disregard of a lawful order'},
        [2] =  {title = 'Disorderly Conduct',                                           class = 'Infraction',   id = 'P.C. 6002',   months = 0,     fine = 250,     color = 'green',    description = 'Acting in a manner that creates a hazardous or physically offensive condition by any act which serves no legitimate purpose of the actor.'},
        [3] =  {title = 'Disturbing the Peace',                                         class = 'Infraction',   id = 'P.C. 6003',   months = 0,     fine = 350,     color = 'green',    description = 'Action in a manner that causes unrest and disrupts public order'},
        [4] =  {title = 'False Reporting',                                              class = 'Misdemeanor',  id = 'P.C. 6004',   months = 10,    fine = 750,     color = 'green',    description = 'The act of reporting a crime that did not happen'},
        [5] =  {title = 'Harassment',                                                   class = 'Misdemeanor',  id = 'P.C. 6005',   months = 10,    fine = 500,     color = 'orange',   description = 'The repeated disruption or verbal attacks of another person'},
        [6] =  {title = 'Misdemeanor Obstruction of Justice',                           class = 'Misdemeanor',  id = 'P.C. 6006',   months = 10,    fine = 500,     color = 'green',    description = 'Acting in a way that hinders the process of justice or lawful investigations'},
        [7] =  {title = 'Felony Obstruction of Justice',                                class = 'Felony',       id = 'P.C. 6007',   months = 15,    fine = 900,     color = 'green',    description = 'Acting in a way that hinders the process of justice or lawful investigations while using violence'},
        [8] =  {title = 'Inciting a Riot',                                              class = 'Felony',       id = 'P.C. 6008',   months = 25,    fine = 1000,    color = 'orange',   description = 'Causing civil unrest in a manner to incite a group to cause harm to people or property'},
        [9] =  {title = 'Loitering on Government Properties',                           class = 'Infraction',   id = 'P.C. 6009',   months = 0,     fine = 500,     color = 'green',    description = 'When someone is present in a government property for an extended period of time'},
        [10] = {title = 'Tampering',                                                    class = 'Misdemeanor',  id = 'P.C. 6010',   months = 10,    fine = 500,     color = 'green',    description = 'When someone willfully, knowingly and indirectly interferes with key points of a lawful investigation'},
        [11] = {title = 'Vehicle Tampering',                                            class = 'Misdemeanor',  id = 'P.C. 6011',   months = 15,    fine = 750,     color = 'green',    description = 'The willful and knowing interference with the normal function of a vehicle'},
        [12] = {title = 'Evidence Tampering',                                           class = 'Felony',       id = 'P.C. 6012',   months = 20,    fine = 1000,    color = 'green',    description = 'The willful and knowing interference with evidence from a lawful investigation'},
        [13] = {title = 'Witness Tampering',                                            class = 'Felony',       id = 'P.C. 6013',   months = 0,     fine = 0,       color = 'green',    description = 'The willful and knowing coaching or coercing of a witness in a lawful investigation'},
        [14] = {title = 'Failure to Provide Identification',                            class = 'Misdemeanor',  id = 'P.C. 6014',   months = 15,    fine = 1500,    color = 'green',    description = 'The act of not presenting identification when lawfully required to do so'},
        [15] = {title = 'Vigilantism',                                                  class = 'Felony',       id = 'P.C. 6015',   months = 30,    fine = 1500,    color = 'orange',   description = 'The act of engaging in enforcing the law without legal authority to do so'},
        [16] = {title = 'Unlawful Assembly',                                            class = 'Misdemeanor',  id = 'P.C. 6016',   months = 10,    fine = 750,     color = 'orange',   description = 'When a large group gathers in a location that requires prior approval to do so'},
        [17] = {title = 'Government Corruption',                                        class = 'Felony',       id = 'P.C. 6017',   months = 0,     fine = 0,       color = 'red',      description = 'The act of using political position and power for self-gain'},
        [18] = {title = 'Stalking',                                                     class = 'Felony',       id = 'P.C. 6018',   months = 40,    fine = 1500,    color = 'orange',   description = 'When one person monitors another without their consent'},
        [19] = {title = 'Aiding and Abetting',                                          class = 'Misdemeanor',  id = 'P.C. 6019',   months = 15,    fine = 450,     color = 'orange',   description = 'To assist or encourage someone in committing a crime'},
        [20] = {title = 'Harboring a Fugitive',                                         class = 'Misdemeanor',  id = 'P.C. 6020',   months = 10,    fine = 1000,    color = 'green',    description = 'When someone willingly hides another who is wanted by the authorities'},
    },

    [7] = {
        [1] =  {title = 'Misdemeanor Possession of Marijuana',                          class = 'Misdemeanor',  id = 'P.C. 7001',   months = 5,     fine = 250,     color = 'green',    description = 'The possession of a quantity of marijuana in the amount of less than 4 blunts'},
        [2] =  {title = 'Felony Manufacturing of Marijuana',                            class = 'Felony',       id = 'P.C. 7002',   months = 15,    fine = 1000,    color = 'red',      description = 'The possession of a quantity of marijuana that is from manufacturing'},
        [3] =  {title = 'Cultivation of Marijuana A',                                   class = 'Misdemeanor',  id = 'P.C. 7003',   months = 10,    fine = 750,     color = 'green',    description = 'The possession of 4 or less marijuana plants'},
        [4] =  {title = 'Cultivation of Marijuana B',                                   class = 'Felony',       id = 'P.C. 7004',   months = 30,    fine = 1500,    color = 'orange',   description = 'The possession of 5 or more marijuana plants'},
        [5] =  {title = 'Possession of Marijuana with Intent to Distribute',            class = 'Felony',       id = 'P.C. 7005',   months = 30,    fine = 3000,    color = 'orange',   description = 'The possession of a quantity of marijuana for distribution'},
        [6] =  {title = 'Misdemeanor Possession of Cocaine',                            class = 'Misdemeanor',  id = 'P.C. 7006',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of cocaine in a small quantity usually for personal use'},
        [7] =  {title = 'Felony Manufacturing Possession of Cocaine',                   class = 'Felony',       id = 'P.C. 7007',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of cocaine that is from manufacturing'},
        [8] =  {title = 'Possession of Cocaine with Intent to Distribute',              class = 'Felony',       id = 'P.C. 7008',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of cocaine for distribution'},
        [9] =  {title = 'Misdemeanor Possession of Methamphetamine',                    class = 'Misdemeanor',  id = 'P.C. 7009',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of methamphetamine in a small quantity usually for personal use'},
        [10] = {title = 'Felony Manufacturing Possession of Methamphetamine',           class = 'Felony',       id = 'P.C. 7010',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of methamphetamine that is from manufacturing'},
        [11] = {title = 'Possession of Methamphetamine with Intent to Distribute',      class = 'Felony',       id = 'P.C. 7011',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of methamphetamine for distribution'},
        [12] = {title = 'Misdemeanor Possession of Oxy / Vicodin',                      class = 'Misdemeanor',  id = 'P.C. 7012',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of oxy/vicodin in a small quantity usually for personal use without prescription'},
        [13] = {title = 'Felony Manufacturing Possession of Oxy / Vicodin',             class = 'Felony',       id = 'P.C. 7013',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of oxy/vicodin that is from manufacturing'},
        [14] = {title = 'Felony Possession of Oxy / Vicodin with Intent to Distribute', class = 'Felony',       id = 'P.C. 7014',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of oxy/vicodin for distribution'},
        [15] = {title = 'Misdemeanor Possession of Ecstasy',                            class = 'Misdemeanor',  id = 'P.C. 7015',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of ecstasy in a small quantity usually for personal use'},
        [16] = {title = 'Felony Manufacturing Possession of Ecstasy',                   class = 'Felony',       id = 'P.C. 7016',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of ecstasy that is from manufacturing'},
        [17] = {title = 'Possession of Ecstasy with Intent to Distribute',              class = 'Felony',       id = 'P.C. 7017',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of ecstasy for distribution'},
        [18] = {title = 'Misdemeanor Possession of Opium',                              class = 'Misdemeanor',  id = 'P.C. 7018',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of opium in a small quantity usually for personal use'},
        [19] = {title = 'Felony Manufacturing Possession of Opium',                     class = 'Felony',       id = 'P.C. 7019',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of opium that is from manufacturing'},
        [20] = {title = 'Possession of Opium with Intent to Distribute',                class = 'Felony',       id = 'P.C. 7020',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of opium for distribution'},
        [21] = {title = 'Misdemeanor Possession of Adderall',                           class = 'Misdemeanor',  id = 'P.C. 7021',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of Adderall in a small quantity usually for personal use without prescription'},
        [22] = {title = 'Felony Manufacturing Possession of Adderall',                  class = 'Felony',       id = 'P.C. 7022',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of Adderall that is from manufacturing'},
        [23] = {title = 'Possession of Adderall with Intent to Distribute',             class = 'Felony',       id = 'P.C. 7023',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of Adderall for distribution'},
        [24] = {title = 'Misdemeanor Possession of Xanax',                              class = 'Misdemeanor',  id = 'P.C. 7024',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of Xanax in a small quantity usually for personal use without prescription'},
        [25] = {title = 'Felony Manufacturing Possession of Xanax',                     class = 'Felony',       id = 'P.C. 7025',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of Xanax that is from manufacturing'},
        [26] = {title = 'Possession of Xanax with Intent to Distribute',                class = 'Felony',       id = 'P.C. 7026',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of Xanax for distribution'},
        [27] = {title = 'Misdemeanor Possession of Shrooms',                            class = 'Misdemeanor',  id = 'P.C. 7027',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of shrooms in a small quantity usually for personal use'},
        [28] = {title = 'Felony Manufacturing Possession of Shrooms',                   class = 'Felony',       id = 'P.C. 7028',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of shrooms that is from manufacturing'},
        [29] = {title = 'Possession of Shrooms with Intent to Distribute',              class = 'Felony',       id = 'P.C. 7029',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of shrooms for distribution'},
        [30] = {title = 'Misdemeanor Possession of Lean',                               class = 'Misdemeanor',  id = 'P.C. 7030',   months = 7,     fine = 500,     color = 'green',    description = 'The possession of lean in a small quantity usually for personal use'},
        [31] = {title = 'Felony Manufacturing Possession of Lean',                      class = 'Felony',       id = 'P.C. 7031',   months = 25,    fine = 1500,    color = 'red',      description = 'The possession of a quantity of lean that is from manufacturing'},
        [32] = {title = 'Possession of Lean with Intent to Distribute',                 class = 'Felony',       id = 'P.C. 7032',   months = 35,    fine = 4500,    color = 'orange',   description = 'The possession of a quantity of lean for distribution'},
        [33] = {title = 'Sale of a Controlled Substance',                               class = 'Misdemeanor',  id = 'P.C. 7033',   months = 10,    fine = 1000,    color = 'green',    description = 'The sale of a substance that is controlled by law'},
        [34] = {title = 'Drug Trafficking',                                             class = 'Felony',       id = 'P.C. 7034',   months = 0,     fine = 0,       color = 'red',      description = 'The large-scale movement of illegal drugs'},
        [35] = {title = 'Desecration of a Human Corpse',                                class = 'Felony',       id = 'P.C. 7035',   months = 20,    fine = 1500,    color = 'orange',   description = 'When someone harms, disturbs or destroys the remains of another person'},
        [36] = {title = 'Public Intoxication',                                          class = 'Infraction',   id = 'P.C. 7036',   months = 0,     fine = 500,     color = 'green',    description = 'When someone is intoxicated above the legal limit in public'},
        [37] = {title = 'Public Indecency',                                             class = 'Misdemeanor',  id = 'P.C. 7037',   months = 10,    fine = 750,     color = 'green',    description = 'The act of someone exposing themselves in a way that infringes on public morals'},
    },
    [8] = {
        [1] =  {title = 'Criminal Possession of Weapon Class A',                        class = 'Felony',       id = 'P.C. 8001',   months = 10,    fine = 500,     color = 'green',    description = 'Possession of a Class A firearm without licensing'},
        [2] =  {title = 'Criminal Possession of Weapon Class B',                        class = 'Felony',       id = 'P.C. 8002',   months = 15,    fine = 1000,    color = 'green',    description = 'Possession of a Class B firearm without licensing'},
        [3] =  {title = 'Criminal Possession of Weapon Class C',                        class = 'Felony',       id = 'P.C. 8003',   months = 30,    fine = 3500,    color = 'green',    description = 'Possession of a Class C firearm without licensing'},
        [4] =  {title = 'Criminal Possession of Weapon Class D',                        class = 'Felony',       id = 'P.C. 8004',   months = 25,    fine = 1500,    color = 'green',    description = 'Possession of a Class D firearm without licensing'},
        [5] =  {title = 'Criminal Sale of Weapon Class A',                              class = 'Felony',       id = 'P.C. 8005',   months = 15,    fine = 1000,    color = 'orange',   description = 'The act of selling a Class A firearm without licensing'},
        [6] =  {title = 'Criminal Sale of Weapon Class B',                              class = 'Felony',       id = 'P.C. 8006',   months = 20,    fine = 2000,    color = 'orange',   description = 'The act of selling a Class B firearm without licensing'},
        [7] =  {title = 'Criminal Sale of Weapon Class C',                              class = 'Felony',       id = 'P.C. 8007',   months = 35,    fine = 7000,    color = 'orange',   description = 'The act of selling a Class C firearm without licensing'},
        [8] =  {title = 'Criminal Sale of Weapon Class D',                              class = 'Felony',       id = 'P.C. 8008',   months = 30,    fine = 3000,    color = 'orange',   description = 'The act of selling a Class D firearm without licensing'},
        [9] =  {title = 'Criminal Use of Weapon',                                       class = 'Misdemeanor',  id = 'P.C. 8009',   months = 10,    fine = 450,     color = 'orange',   description = 'Use of a weapon while in commission of a crime'},
        [10] = {title = 'Possession of Illegal Firearm Modifications',                  class = 'Misdemeanor',  id = 'P.C. 8010',   months = 10,    fine = 300,     color = 'green',    description = 'Being in possession of firearm modifications unlawfully'},
        [11] = {title = 'Weapon Trafficking',                                           class = 'Felony',       id = 'P.C. 8011',   months = 0,     fine = 0,       color = 'red',      description = 'The transportation of a large amount of weapons from one point to another'},
        [12] = {title = 'Brandishing a Weapon',                                         class = 'Misdemeanor',  id = 'P.C. 8012',   months = 15,    fine = 500,     color = 'orange',   description = 'The act of making a firearm purposely visible'},
        [13] = {title = 'Insurrection',                                                 class = 'Felony',       id = 'P.C. 8013',   months = 0,     fine = 0,       color = 'red',      description = 'Attempting to overthrow the government with violence'},
        [14] = {title = 'Flying into Restricted Airspace',                              class = 'Felony',       id = 'P.C. 8014',   months = 20,    fine = 1500,    color = 'green',    description = 'Piloting an aircraft into airspace that is governmentally controlled'},
        [15] = {title = 'Jaywalking',                                                   class = 'Infraction',   id = 'P.C. 8015',   months = 0,     fine = 150,     color = 'green',    description = 'Crossing a roadway in a manner that is hazardous to motor vehicles'},
        [16] = {title = 'Criminal Use of Explosives',                                   class = 'Felony',       id = 'P.C. 8016',   months = 30,    fine = 2500,    color = 'orange',   description = 'Use of explosives to commit a crime'},
    },

    [9] = {
        [1] =  {title = 'Driving While Intoxicated',                                    class = 'Misdemeanor',  id = 'P.C. 9001',   months = 5,     fine = 300,     color = 'green',    description = 'Operating a motor vehicle while impaired by alcohol'},
        [2] =  {title = 'Evading',                                                      class = 'Misdemeanor',  id = 'P.C. 9002',   months = 5,     fine = 400,     color = 'green',    description = 'Hiding or running from lawful detainment'},
        [3] =  {title = 'Reckless Evading',                                             class = 'Felony',       id = 'P.C. 9003',   months = 10,    fine = 800,     color = 'orange',   description = 'Recklessly disregarding safety while evading lawful detainment'},
        [4] =  {title = 'Failure to Yield to Emergency Vehicle',                        class = 'Infraction',   id = 'P.C. 9004',   months = 0,     fine = 600,     color = 'green',    description = 'Not giving way to emergency vehicles'},
        [5] =  {title = 'Failure to Obey Traffic Control Device',                       class = 'Infraction',   id = 'P.C. 9005',   months = 0,     fine = 150,     color = 'green',    description = 'Not following the safety devices of the roadway'},
        [6] =  {title = 'Nonfunctional Vehicle',                                        class = 'Infraction',   id = 'P.C. 9006',   months = 0,     fine = 75,      color = 'green',    description = 'Having a vehicle that is no longer functional in the roadway'},
        [7] =  {title = 'Negligent Driving',                                            class = 'Infraction',   id = 'P.C. 9007',   months = 0,     fine = 300,     color = 'green',    description = 'Driving in a manner as to unknowingly disregard safety'},
        [8] =  {title = 'Reckless Driving',                                             class = 'Misdemeanor',  id = 'P.C. 9008',   months = 10,    fine = 750,     color = 'orange',   description = 'Driving in a manner as to knowingly disregard safety'},
        [9] =  {title = 'Third Degree Speeding',                                        class = 'Infraction',   id = 'P.C. 9009',   months = 0,     fine = 225,     color = 'green',    description = 'Speeding 15 over the limit'},
        [10] = {title = 'Second Degree Speeding',                                       class = 'Infraction',   id = 'P.C. 9010',   months = 0,     fine = 450,     color = 'green',    description = 'Speeding 35 over the limit'},
        [11] = {title = 'First Degree Speeding',                                        class = 'Infraction',   id = 'P.C. 9011',   months = 0,     fine = 750,     color = 'green',    description = 'Speeding 50 over the limit'},
        [12] = {title = 'Unlicensed Operation of Vehicle',                              class = 'Infraction',   id = 'P.C. 9012',   months = 0,     fine = 500,     color = 'green',    description = 'The operation of a motor vehicle without proper licensing'},
        [13] = {title = 'Illegal U-Turn',                                               class = 'Infraction',   id = 'P.C. 9013',   months = 0,     fine = 75,      color = 'green',    description = 'Performing a U-turn where it is prohibited'},
        [14] = {title = 'Illegal Passing',                                              class = 'Infraction',   id = 'P.C. 9014',   months = 0,     fine = 300,     color = 'green',    description = 'Passing other motor vehicles in a prohibited manner'},
        [15] = {title = 'Failure to Maintain Lane',                                     class = 'Infraction',   id = 'P.C. 9015',   months = 0,     fine = 300,     color = 'green',    description = 'Not staying in the correct lane with a motor vehicle'},
        [16] = {title = 'Illegal Turn',                                                 class = 'Infraction',   id = 'P.C. 9016',   months = 0,     fine = 150,     color = 'green',    description = 'Performing a turn where it is prohibited'},
        [17] = {title = 'Failure to Stop',                                              class = 'Infraction',   id = 'P.C. 9017',   months = 0,     fine = 600,     color = 'green',    description = 'Not stopping for a lawful stop or traffic device'},
        [18] = {title = 'Unauthorized Parking',                                         class = 'Infraction',   id = 'P.C. 9018',   months = 0,     fine = 300,     color = 'green',    description = 'Parking a vehicle in a location that requires approval'},
        [19] = {title = 'Hit and Run',                                                  class = 'Misdemeanor',  id = 'P.C. 9019',   months = 10,    fine = 500,     color = 'green',    description = 'Striking another person or vehicle and fleeing the location'},
        [20] = {title = 'Driving without Headlights or Signals',                        class = 'Infraction',   id = 'P.C. 9020',   months = 0,     fine = 300,     color = 'green',    description = 'Operating a vehicle with no functional lights'},
        [21] = {title = 'Street Racing',                                                class = 'Felony',       id = 'P.C. 9021',   months = 15,    fine = 1500,    color = 'green',    description = 'Operating motor vehicles in a contest'},
        [22] = {title = 'Piloting without Proper Licensing',                            class = 'Felony',       id = 'P.C. 9022',   months = 20,    fine = 1500,    color = 'orange',   description = 'Failure to be in possession of valid licensing when operating an aircraft'},
        [23] = {title = 'Unlawful Use of a Motor Vehicle',                              class = 'Misdemeanor',  id = 'P.C. 9023',   months = 10,    fine = 750,     color = 'green',    description = 'The use of a motor vehicle without a lawful reason'},
    },

    [10] = {
        [1] =  {title = 'Hunting in Restricted Areas',                                  class = 'Infraction',   id = 'P.C. 10001',  months = 0,     fine = 450,     color = 'green',    description = 'Harvesting game in areas where it is prohibited to do so'},
        [2] =  {title = 'Unlicensed Hunting',                                           class = 'Infraction',   id = 'P.C. 10002',  months = 0,     fine = 450,     color = 'green',    description = 'Harvesting game without proper licensing'},
        [3] =  {title = 'Animal Cruelty',                                               class = 'Misdemeanor',  id = 'P.C. 10003',  months = 10,    fine = 450,     color = 'green',    description = 'The act of abusing an animal knowingly or not'},
        [4] =  {title = 'Hunting with a Non-Hunting Weapon',                            class = 'Misdemeanor',  id = 'P.C. 10004',  months = 10,    fine = 750,     color = 'green',    description = 'To use a weapon not lawfully stated or manufactured to be used for the harvesting of wild game'},
        [5] =  {title = 'Hunting Outside of Hunting Hours',                             class = 'Infraction',   id = 'P.C. 10005',  months = 0,     fine = 750,     color = 'green',    description = 'Harvesting animals outside of specified time to do so'},
        [6] =  {title = 'Overhunting',                                                  class = 'Misdemeanor',  id = 'P.C. 10006',  months = 10,    fine = 1000,    color = 'green',    description = 'Taking more than legally specified amount of game'},
        [7] =  {title = 'Poaching',                                                     class = 'Felony',       id = 'P.C. 10007',  months = 20,    fine = 1250,    color = 'red',      description = 'Harvesting an animal that is listed as legally non-harvestable'},
    }
}
</pre>
