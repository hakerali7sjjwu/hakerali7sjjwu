
local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/shlexware/Orion/main/source"))()

local Window = OrionLib:MakeWindow({
    Name = "Ali Hub ( Blox fruits)",
    HidePremium = false,
    IntroText = "Uzbekistan 🇺🇿",
    Draggable = true -- Make the window draggable
})

local Tab = Window:MakeTab({
    Name = "Blox fruits ( made by Ali🇺🇿)",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})
local Tab1 = Window:MakeTab({
	Name = "Blox fruits",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local ClockSection = Tab:AddSection({Name = "Blox fruits ( made by Ali🇺🇿)"})
local ClockLabel = ClockSection:AddLabel("Time: Loading...")
local function FormatTime()
    local currentTime = os.date("*t")
    local hour = currentTime.hour
    local amPm = "AM"

    if hour >= 12 then
        amPm = "PM"
        if hour > 12 then
            hour = hour - 12
        end
    elseif hour == 0 then
        hour = 12
    end

    local formattedTime = string.format("%02d:%02d:%02d %s", hour, currentTime.min, currentTime.sec, amPm)
    local formattedDate = string.format("%02d/%02d/%04d", currentTime.day, currentTime.month, currentTime.year)

    return formattedDate .. " " .. formattedTime
end

local function UpdateClock()
    local hue = 0

    while true do
        local startTime = tick()
        
        ClockLabel:Set("Date & Time: " .. FormatTime())
        
        hue = hue + 0.01
        if hue > 1 then
            hue = 0
        end

        local color = Color3.fromHSV(hue, 1, 1)
        ClockLabel.TextColor3 = color
        
        local elapsedTime = tick() - startTime
        wait(1 - elapsedTime)
    end
end

spawn(UpdateClock)

Tab:AddLabel("")
Tab:AddButton({
	Name = "Blox fruits ( MADE BY ALI) ",
	Callback = function()	loadstring(game:HttpGet("https://raw.githubusercontent.com/realredz/BloxFruits/refs/heads/main/Source.lua"))()
  	end    
})Tab:AddParagraph("HAMKOR🤝 - DOBR1Y - KILLER - HOJI AKBAR","MADE BY ALI🇺🇿")
