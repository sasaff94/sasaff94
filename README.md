loadstring(game:HttpGet"local Player = game:GetService('Players').LocalPlayer
Player.Idled:connect(function()
	game:GetService('VirtualUser'):Button2Down(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
	wait(1)
	game:GetService('VirtualUser'):Button2Up(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
end)

local CoreGui = game:GetService('CoreGui')
if CoreGui:FindFirstChild('BuildABoatForTreasure') ~= nil then
	CoreGui:FindFirstChild('BuildABoatForTreasure'):Destroy()
end
local BuildABoatForTreasure = Instance.new('ScreenGui', game:GetService('CoreGui'))
BuildABoatForTreasure.Name = 'BuildABoatForTreasure'
BuildABoatForTreasure.ResetOnSpawn = false

local Header = Instance.new('Frame', BuildABoatForTreasure)
Header.Name = 'Header'
Header.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Header.BorderColor3 = Color3.fromRGB(255, 255, 255)
Header.BorderSizePixel = 0
Header.Position = UDim2.new(0, -295, 0, 10)
Header.Size = UDim2.new(0, 250, 0, 40)

local Frame = Instance.new('Frame', Header)
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.BorderColor3 = Color3.fromRGB(255, 255, 255)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0, 0, 0, 40)
Frame.Size = UDim2.new(0, 250, 0, 5)
Frame.Name = 'Header/Background'

local Hide = Instance.new('TextButton', Header)
Hide.Name = 'Hide'
Hide.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Hide.BorderColor3 = Color3.fromRGB(255, 255, 255)
Hide.BorderSizePixel = 0
Hide.Position = UDim2.new(0, 252, 0, 37)
Hide.Size = UDim2.new(0, 35, 0, 35)
Hide.Font = Enum.Font.Highway
Hide.Text = '<'
Hide.TextColor3 = Color3.fromRGB(255, 255, 255)
Hide.TextSize = 28

local HideToggle = false
Hide.MouseButton1Click:connect(function()
	if HideToggle == false then
		CoreGui.BuildABoatForTreasure.Header:TweenPosition(UDim2.new(0, -250, 0, 10), 'In', 'Back', 0.5)
		wait(0.5)
		CoreGui.BuildABoatForTreasure.Header.Hide.Text = '>'
		CoreGui.BuildABoatForTreasure.Header.Close.BackgroundTransparency = 1
		CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundTransparency = 1
		HideToggle = true
	else
		if HideToggle == true then
			CoreGui.BuildABoatForTreasure.Header:TweenPosition(UDim2.new(0, 5, 0, 10), 'In', 'Back', 0.5)
			wait(0.5)
			CoreGui.BuildABoatForTreasure.Header.Hide.Text = '<'
			CoreGui.BuildABoatForTreasure.Header.Close.BackgroundTransparency = 0
			CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundTransparency = 0
			HideToggle = false
		end
	end
end)

local TextLabel = Instance.new('TextLabel', Header)
TextLabel.Name = 'TextLabel'
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0, 0, 0, 0)
TextLabel.Size = UDim2.new(0, 250, 0, 40)
TextLabel.BorderColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.Font = Enum.Font.Highway
TextLabel.Text = 'Build A Boat For Treasure'
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextSize = 24

local Notification = Instance.new('Frame', Header)
Notification.Name = 'Notification'
Notification.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Notification.BorderColor3 = Color3.fromRGB(255, 255, 255)
Notification.BorderSizePixel = 0
Notification.Position = UDim2.new(0, 0, 0, 45)
Notification.Size = UDim2.new(0, 250, 0, 70)

local Background = Instance.new('Frame', Header)
Background.Name = 'Background'
Background.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Background.BorderColor3 = Color3.fromRGB(255, 255, 255)
Background.BorderSizePixel = 0
Background.Position = UDim2.new(0, 0, 0, 45)
Background.Size = UDim2.new(0, 250, 0, 35)

local AutoWin = Instance.new('TextButton', Background)
AutoWin.Name = 'AutoWin'
AutoWin.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
AutoWin.BorderColor3 = Color3.fromRGB(255, 255, 255)
AutoWin.BorderSizePixel = 0
AutoWin.Position = UDim2.new(0, 0, 0, 0)
AutoWin.Size = UDim2.new(0, 250, 0, 35)
AutoWin.Font = Enum.Font.Highway
AutoWin.Text = 'Auto Win:โ'
AutoWin.TextColor3 = Color3.fromRGB(255, 255, 255)
AutoWin.TextSize = 16

local AutoWinToggle = false
AutoWin.MouseButton1Click:connect(function()
	if AutoWinToggle == false then
		AutoWinToggle = true
		AutoWin.Text = 'Auto Win:โ…'
		Win()
	else
		if AutoWinToggle == true then
			AutoWinToggle = false
			AutoWin.Text = 'Auto Win:โ'
		end
	end
end)

local Close = Instance.new('TextButton', Header)
Close.Name = 'Close'
Close.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Close.BorderColor3 = Color3.fromRGB(255, 255, 255)
Close.BorderSizePixel = 0
Close.Position = UDim2.new(0, 252, 0, 0)
Close.Size = UDim2.new(0, 35, 0, 35)
Close.Font = Enum.Font.Highway
Close.Text = 'X'
Close.TextColor3 = Color3.fromRGB(255, 255, 255)
Close.TextSize = 28

Close.MouseButton1Click:connect(function()
	AutoWinToggle = false
	CoreGui.BuildABoatForTreasure.Header:TweenPosition(UDim2.new(0, -295, 0, 10), 'In', 'Back', 0.5)
	wait(0.5)
	CoreGui.BuildABoatForTreasure:Destroy()
end)

local Blue = Instance.new('TextButton', Notification)
Blue.Name = 'Blue'
Blue.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
Blue.BorderColor3 = Color3.fromRGB(255, 255, 255)
Blue.BorderSizePixel = 0
Blue.Position = UDim2.new(0, 0, 0, 35)
Blue.Size = UDim2.new(0, 35, 0, 35)
Blue.TextColor3 = Color3.fromRGB(255, 255, 255)
Blue.Text = ''
Blue.TextSize = 16

Blue.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 75, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 110, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 145, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 180, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
end)

local Green = Instance.new('TextButton', Notification)
Green.Name = 'Green'
Green.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
Green.BorderColor3 = Color3.fromRGB(255, 255, 255)
Green.BorderSizePixel = 0
Green.Position = UDim2.new(0, 35, 0, 35)
Green.Size = UDim2.new(0, 35, 0, 35)
Green.TextColor3 = Color3.fromRGB(255, 255, 255)
Green.Text = ''
Green.TextSize = 16

Green.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 75, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 110, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 145, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 180, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(0, 85, 0)
end)

local Grey = Instance.new('TextButton', Notification)
Grey.Name = 'Grey'
Grey.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Grey.BorderColor3 = Color3.fromRGB(255, 255, 255)
Grey.BorderSizePixel = 0
Grey.Position = UDim2.new(0, 70, 0, 35)
Grey.Size = UDim2.new(0, 40, 0, 35)
Grey.TextColor3 = Color3.fromRGB(255, 255, 255)
Grey.Text = ''
Grey.TextSize = 16

Grey.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 70, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 110, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 145, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 180, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
end)

local Pink = Instance.new('TextButton', Notification)
Pink.Name = 'Pink'
Pink.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
Pink.BorderColor3 = Color3.fromRGB(255, 255, 255)
Pink.BorderSizePixel = 0
Pink.Position = UDim2.new(0, 110, 0, 35)
Pink.Size = UDim2.new(0, 35, 0, 35)
Pink.TextColor3 = Color3.fromRGB(255, 255, 255)
Pink.Text = ''
Pink.TextSize = 16

Pink.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 70, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 105, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 145, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 180, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(170, 0, 127)
end)

local Purple = Instance.new('TextButton', Notification)
Purple.Name = 'Purple'
Purple.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
Purple.BorderColor3 = Color3.fromRGB(255, 255, 255)
Purple.BorderSizePixel = 0
Purple.Position = UDim2.new(0, 145, 0, 35)
Purple.Size = UDim2.new(0, 35, 0, 35)
Purple.TextColor3 = Color3.fromRGB(255, 255, 255)
Purple.Text = ''
Purple.TextSize = 16

Purple.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 70, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 105, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 140, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 180, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(170, 0, 255)
end)

local Red = Instance.new('TextButton', Notification)
Red.Name = 'Red'
Red.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
Red.BorderColor3 = Color3.fromRGB(255, 255, 255)
Red.BorderSizePixel = 0
Red.Position = UDim2.new(0, 180, 0, 35)
Red.Size = UDim2.new(0, 35, 0, 35)
Red.TextColor3 = Color3.fromRGB(255, 255, 255)
Red.Text = ''
Red.TextSize = 16

Red.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 70, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 105, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 140, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 175, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 215, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
end)

local Yellow = Instance.new('TextButton', Notification)
Yellow.Name = 'Yellow'
Yellow.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
Yellow.BorderColor3 = Color3.fromRGB(255, 255, 255)
Yellow.BorderSizePixel = 0
Yellow.Position = UDim2.new(0, 215, 0, 35)
Yellow.Size = UDim2.new(0, 35, 0, 35)
Yellow.TextColor3 = Color3.fromRGB(255, 255, 255)
Yellow.Text = ''
Yellow.TextSize = 16

Yellow.MouseButton1Click:connect(function()
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Position = UDim2.new(0, 0, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Position = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Position = UDim2.new(0, 70, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Position = UDim2.new(0, 105, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Position = UDim2.new(0, 140, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Position = UDim2.new(0, 175, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Position = UDim2.new(0, 210, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Blue.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Green.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Grey.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Pink.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Purple.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Red.Size = UDim2.new(0, 35, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.Notification.Yellow.Size = UDim2.new(0, 40, 0, 35)
	CoreGui.BuildABoatForTreasure.Header.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
	CoreGui.BuildABoatForTreasure.Header.Close.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
	CoreGui.BuildABoatForTreasure.Header.Hide.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
	CoreGui.BuildABoatForTreasure.Header.Notification.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
	CoreGui.BuildABoatForTreasure.Header.Background.AutoWin.BackgroundColor3 = Color3.fromRGB(200, 200, 0)
end)
CoreGui.BuildABoatForTreasure.Header:TweenPosition(UDim2.new(0, 5, 0, 10), 'In', 'Back', 0.5)

function Tween(Time, Position)
	game:GetService('Workspace').Gravity = 0
	game:GetService('TweenService'):Create(Player.Character.HumanoidRootPart, TweenInfo.new(Time, Enum.EasingStyle.Linear), {CFrame = Position}):Play() wait(Time)
	game:GetService('Workspace').Gravity = 196.2
end

function Win()
	if game:GetService('Workspace').Gravity ~= 0 then
		Tween(1, game:GetService('Workspace').BoatStages.NormalStages.CaveStage1.DarknessPart.CFrame)
		Tween(20, game:GetService('Workspace').BoatStages.NormalStages.CaveStage10.DarknessPart.CFrame * CFrame.new(0, 0, 1000))
		Tween(1, game:GetService('Workspace').BoatStages.NormalStages.TheEnd.GoldenChest.Trigger.CFrame)
	end
end

Player.OtherData.End.Changed:Connect(function()
	if AutoWinToggle == true then
		if Player.OtherData.End.Value ~= 'EndReached' then
			Win()
		end
	end
end)

Player.CharacterAdded:Connect(function()
	if AutoWinToggle == true then
		if Player:HasAppearanceLoaded() then
			game:GetService('Workspace').ClaimRiverResultsGold:FireServer()
		end
	end
end) raw ")()
