---
ns: PLAYER
---
## SET_PLAYER_MODEL

```c
// 0x00A1CADD00108836 0x774A4C54
void SET_PLAYER_MODEL(Player player, Hash model);
```

Set the model for a specific Player. Be aware that this will destroy the current Ped for the Player and create a new one, any reference to the old ped should be reset
Make sure to request the model first and wait until it has loaded.

## Parameters
* **player**: The player to set the model for 
* **model**: The hash of the model to use

## Examples
```lua
local model = 'a_f_m_beach_01'
if IsModelInCdimage(model) and IsModelValid(model) then
  RequestModel(model)
  while not HasModelLoaded(model) do
    Citizen.Wait(0)
  end
  SetPlayerModel(PlayerId(), model)
  SetModelAsNoLongerNeeded(model)
end
```
