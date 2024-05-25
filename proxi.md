# gm_proxi
<details>
<summary>Base Lib (_G.proxi)</summary>

`DEBUG` \
A boolean representing whether or not the module is in debug mode

`_R` \
A reference to the debug registry

`FRAME_UNDEFINED` \
For use in the FrameStagNotify hooks \
Value of -1

`FRAME_START` \
For use in the FrameStagNotify hooks \
Value of 0

`FRAME_NET_UPDATE_START` \
For use in the FrameStagNotify hooks \
Value of 1

`FRAME_NET_UPDATE_POSTDATAUPDATE_START` \
For use in the FrameStagNotify hooks \
Value of 2

`FRAME_NET_UPDATE_POSTDATAUPDATE_END` \
For use in the FrameStagNotify hooks \
Value of 3

`FRAME_NET_UPDATE_END` \
For use in the FrameStagNotify hooks \
Value of 4

`FRAME_RENDER_START` \
For use in the FrameStagNotify hooks \
Value of 5

`FRAME_RENDER_END` \
For use in the FrameStagNotify hooks \
Value of 6

`DisableAnimInterp(bool Disable)` \
Enables/Disables interpolate via CSequenceTransitioner::CheckForSequenceChange

`Disconnect(string DisconnectReason)` \
Disconnects from the server with a custom message

`StartPrediction(CUserCmd Command)` \
Starts engine prediction with the provided CUserCmd

`EndPrediction()` \
Stops engine prediction

`FullUpdate()` \
Forces a full network update

`number GetChokedCommands()` \
Returns the amount of choked/lost packets/commands

`ConVar GetConVar(string Name)` \
Alternative to _G.GetConVar

`number GetFlowIncoming()` \
Returns the incoming data latency of the net channel

`number GetFlowOutgoing()` \
Returns the outgoing data latency of the net channel

`SetPredictionAngles(Angle PredictionAngles)` \
Sets local view angles to be used during prediction

`Angle GetPredictionAngles()` \
Returns local view angles to be used during prediction

`SetSequenceNumber(number SequenceNumber)` \
Sets outgoing sequence number on the net channel

`number GetSequenceNumber()` \
Returns outgoing sequence number on the net channel

`SetViewAngles(Angle ViewAngles)` \
Sets view angles directly in the engine

`Angle GetViewAngles()` \
Returns view angles used by the engine

`bool RunOnClient(string Code, string Identifier = "[C]", bool HandleError = true)` \
Alternative to _G.RunString on client state \
Returns `true` on success, `false` on error

`bool RunOnMenu(string Code, string Identifier = "[C]", bool HandleError = true)` \
Alternative to _G.RunString on menu state \
Returns `true` on success, `false` on error

`SendConsoleCommand(string Command)` \
Runs a concommand on the server without running it on the client

`SendLuaError(string Error)` \
Sends a Lua Error event to the server without throwing an error on the client

`SetCurTime(number Time)` \
Spoofs _G.CurTime to return the given number until the next tick

`SetFrameTime(number Time)` \
Spoofs _G.FrameTime and _G.RealFrameTime to return the given number until the next tick

</details>
