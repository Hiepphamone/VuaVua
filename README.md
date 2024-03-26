if game.PlaceId ~= 14082129854 then
    repeat wait() until game.Players
    repeat wait() until game.Players.LocalPlayer
    repeat wait() until game.ReplicatedStorage
    local plr = game.Players.LocalPlayer
    function getstatusbtn()
        return game:GetService("Players").LocalPlayer.PlayerGui.Match.MatchFinish.MatchFinishFrame.EndOptions.PlayAgain.ButtonFrame.PlayAgainButton.ContentText == "Play Again"
    end
    if game:GetService("Players").LocalPlayer.PlayerGui.MainFrames:FindFirstChild('NotificationFrame') then
        game:GetService("Players").LocalPlayer.PlayerGui.MainFrames:FindFirstChild('NotificationFrame'):Destroy()
    end
    spawn(function()
        while true do wait()
            local a,b = pcall(function()
                plr.Character.HumanoidRootPart.CFrame = workspace.Lifts.EggIsland.BasePart.CFrame * CFrame.new(0,5,0)
                wait(2)
                if game:GetService("Players").LocalPlayer.PlayerGui.Lobby.QueueFrame.Visible == true then
                    function click(a)
                        game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X-60,a.AbsolutePosition.Y+60,0,true,a,1)
                        game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X-60,a.AbsolutePosition.Y+60,0,false,a,1)
                    end
                    click(game:GetService("Players").LocalPlayer.PlayerGui.Lobby.QueueFrame.Start)
                else
                    plr.Character.HumanoidRootPart.CFrame = workspace.Lifts.EggIsland.BasePart.CFrame * CFrame.new(0,5,20)
                end
            end)
            print(a,b)
        end
    end)
else
    repeat wait() until game.Players
    repeat wait() until game.Players.LocalPlayer
    repeat wait() until game.ReplicatedStorage
    getgenv().skibidi = {}
    for charCode = string.byte('a'), string.byte('z') do
        table.insert(getgenv().skibidi, string.char(charCode))
    end
    for charCode = string.byte('A'), string.byte('Z') do
        table.insert(getgenv().skibidi, string.char(charCode))
    end
    function getstatusbtn()
        if game:GetService("Players").LocalPlayer.PlayerGui.Match.MatchFinish.Visible == true then
            return game:GetService("Players").LocalPlayer.PlayerGui.Match.MatchFinish.MatchFinishFrame.EndOptions.PlayAgain.ButtonFrame.PlayAgainButton.ContentText == "Play Again"
        end
        return false
    end
    function click(a)
        game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X-60,a.AbsolutePosition.Y+60,0,true,a,1)
        game:GetService("VirtualInputManager"):SendMouseButtonEvent(a.AbsolutePosition.X+a.AbsoluteSize.X-60,a.AbsolutePosition.Y+60,0,false,a,1)
    end
    
    spawn(function()
        while true do wait(.1)
            pcall(function()
                if tostring(game:GetService("Players").LocalPlayer.PlayerGui.Match.WaveInfo.AutoSkip.OnAndOff.BackgroundColor3) == '1, 0, 0' then
                    firesignal(game:GetService("Players").LocalPlayer.PlayerGui.Match.WaveInfo.AutoSkip.OnAndOff.Activated)
                end
                if getstatusbtn() then
                    print('asdasdasd')
                    repeat wait(8)
                        click(game:GetService("Players").LocalPlayer.PlayerGui.Match.MatchFinish.MatchFinishFrame.EndOptions.PlayAgain.ButtonFrame.PlayAgainButton)
                        wait(.2)
                    until not getstatusbtn()
                else
                    click(game:GetService("Players").LocalPlayer.PlayerGui.VotingFrame.VoteFrame.VoteMainFrame.MainFrame.Easy.Vote)
                end
            end)
        end
    end)
    getgenv().savemain = false
    getgenv().oldremote = ''

    local mainpart;
    for i,v in pairs(game:GetService("ReplicatedStorage").FrameworkDependencies:GetDescendants()) do
        if v.Name == 'ClientProcess' then
            mainpart = v
        end
    end

    function spawntuong(a)
        if getgenv().savemain == false then
            for i,v in pairs(getgenv().skibidi) do
                getgenv().oldremote = v
                local az = require(mainpart)
                az.addToQueue(v, {'MinigunCamerawoman', a ,1})
                wait(1)
                print(v)
                if workspace.Troops:FindFirstChild('MinigunCamerawoman') then
                    getgenv().savemain = v
                    print(getgenv().oldremote)
                    break
                end
            end
        else
            local az = require(mainpart)
            az.addToQueue(getgenv().oldremote, {'MinigunCamerawoman', a ,1})
        end
        wait(1)
    end

    function autoupdate()
        local args = {
            [1] = {
                [1] = {
                    [1] = workspace.Troops:FindFirstChild('MinigunCamerawoman')
                },
                [2] = "KU"
            }
        }

        game:GetService("ReplicatedStorage").dataRemoteEvent:FireServer(unpack(args))
    end
end
