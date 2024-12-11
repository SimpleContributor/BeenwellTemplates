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

### Job Outfits

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

These are all of the items that are used on the benches. I need to add photos, so any new items must be clearly seen. Marking a new item with a date is best. i.e. -- 12/10/24

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
