    local Spawner = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Doors%20Entity%20Spawner/Source.lua"))()
 
 
-- Create entity
local entityTable = Spawner.createEntity({
    CustomName = "A-60", -- Custom name of your entity
    Model = "15089669896", -- Can be GitHub file or rbxassetid
    Speed = 1990, -- Percentage, 100 = default Rush speed
    DelayTime = 5, -- Time before starting cycles (seconds)
    HeightOffset = 2,
    CanKill = true,
    KillRange = 50,
    BackwardsMovement = false,
    BreakLights = true,
    FlickerLights = {
        true, -- Enabled/Disabled
        2, -- Time (seconds)
    },
    Cycles = {
        Min = 4,
        Max = 4,
        WaitTime = 2,
    },
    CamShake = {
        true, -- Enabled/Disabled
        {3.5, 20, 0.1, 1}, -- Shake values (don't change if you don't know)
        100, -- Shake start distance (from Entity to you)
    },
    Jumpscare = {
        true, -- Enabled/Disabled
        {
            Image1 = "rbxassetid://11826898817", -- Image1 url
            Image2 = "rbxassetid://11867753039", -- Image2 url
            Shake = true,
            Sound1 = {
                5263560566, -- SoundId
                { Volume = 0.5 }, -- Sound properties
            },
            Sound2 = {
                5263560566, -- SoundId
                { Volume = 0.5 }, -- Sound properties
            },
            Flashing = {
                true, -- Enabled/Disabled
                Color3.fromRGB(255, 255, 255), -- Color
            },
            Tease = {
                true, -- Enabled/Disabled
                Min = 1,
                Max = 3,
            },
        },
    },
    CustomDialog = {"You died to who you call A-60...", "Try your best to out-run him.", "I really don't have nothing else", "Just try your best to Hide when you can."}, -- Custom death message
})
 
 
-----[[  Debug -=- Advanced  ]]-----
entityTable.Debug.OnEntitySpawned = function()
    print("Entity has spawned:", entityTable)
end
 
entityTable.Debug.OnEntityDespawned = function()
    print("Entity has despawned:", entityTable)
end
 
entityTable.Debug.OnEntityStartMoving = function()
    print("Entity has started moving:", entityTable)
end
 
entityTable.Debug.OnEntityFinishedRebound = function()
    print("Entity has finished rebound:", entityTable)
end
 
entityTable.Debug.OnEntityEnteredRoom = function(room)
    print("Entity:", entityTable, "has entered room:", room)
end
 
entityTable.Debug.OnLookAtEntity = function()
    print("Player has looked at entity:", entityTable)
end
 
entityTable.Debug.OnDeath = function()
    warn("Player has died.")
end
------------------------------------
 
 
-- Run the created entity
Spawner.runEntity(entityTable)
