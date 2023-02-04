# NatROl
an script for nations roleplay 2 and 1

--paint the world rainbow script
local user = game.Players.LocalPlayer
local RandomWait = { 0.1, 5e-3 }
for i, v in pairs(game.Workspace.Map:GetChildren()) do
    task.spawn(function()
        while wait(RandomWait[math.random(2)]) do
            if not user.Character:FindFirstChild"PaintBucket" then user.Backpack.PaintBucket.Parent = user.Character end
            local args = {
                [1] = "PaintPart",
                [2] = {
                    ["Part"] = v,
                    ["Color"] = Color3.fromHSV(tick() % math.random(3, 5) / math.random(3, 5), 1, 1)
                }
            }
            user.Character.PaintBucket.Remotes.ServerControls:InvokeServer(unpack(args))
        end
    end)
end
