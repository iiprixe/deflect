getgenv().done = false

l=false
Mouse.KeyDown:Connect(function(key)
    if key == "g" then
        if l==false then
            getgenv().done = true
            game.StarterGui:SetCore("SendNotification", {
                Title = "notification";
                Text = "Auto Deflect Is Now Enabled";
                Icon = "rbxassetid://2541869220";
                Duration = 3;
            })
        else
            getgenv().done = false
            game.StarterGui:SetCore("SendNotification", {
                Title = "notification";
                Text = "Auto Deflect Is Now Disabled";
                Icon = "rbxassetid://2541869220";
                Duration = 3;
            })
        end
    end
end)

spawn(function()
    while done == true do
        wait()
        local thing1 = game.Players.LocalPlayer.Character.HumanoidRootPart
        local thing2 = game:GetService("Workspace"):WaitForChild('Ball').Main
        local distance = (thing2.Position - thing1.Position).magnitude 
        if distance <= 16 then --DONT CHANGE MAYBE CHANGE TO 15 IFYW BUT ITS GOOD DONT GO OVER 16
            mouse1click()
        end
    end   
end)
--fails some times so might do 15 idrc
