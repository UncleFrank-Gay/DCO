Codes for DCO: Roblox Studio Uncensored:

Admin Door Script:
local adminDoor = script.Parent
local adminGamePassID = 891531875  -- Replace with your actual Admin Game Pass ID

-- List of players who are admins
local admins = {
	["ekssjas"] = true,
	["MrFlimFlam"] = true
}

adminDoor.Touched:Connect(function(hit)
	local player = game.Players:GetPlayerFromCharacter(hit.Parent)
	if player then
		-- Check if the player is in the admin list or has the admin game pass
  
		if admins[player.Name] or player:HasPass(adminGamePassID) then
			adminDoor.CanCollide = false
			wait(1)
			adminDoor.CanCollide = true
		else
			player:Kick("You need to be an admin or have the Admin pass to enter!")
		end
	end
end)
