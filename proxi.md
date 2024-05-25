# gm_proxi

### _G.proxi

<details>
<summary>Base Lib</summary>

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

<details>
<summary>Debug Lib</summary>

`string, any getupvalue(function Function, number Index)` \
Same as _G.debug.getupvalue

`string setupvalue(function Function, number Index, any Value)` \
Same as _G.debug.setupvalue

`string, any getlocal(thread Thread = CurrentThread, number Level, number Index)` \
Same as _G.debug.getlocal

`string setlocal(thread Thread = CurrentThread, number Level, number Index, any Value)` \
Same as _G.debug.setlocal

`table getinfo(function FunctionOrStackLevel, string Fields = "flnSu", function Function)` \
Same as _G.debug.getinfo

`table getmetatable(any Object)` \
Same as _G.debug.getmetatable

</details>

<details>
<summary>Net Lib</summary>

`bool Start(string MessageName)` \
Same as _G.net.Start

`SendToServer()` \
Same as _G.net.SendToServer

`string NetworkIDToString(number ID)` \
Same as _G.util.NetworkIDToString

`number NetworkStringToID(string NetworkString)` \
Same as _G.util.NetworkStringToID

`WriteBit(bool Value)` \
Same as _G.net.WriteBit

`WriteBool(bool Value)` \
Same as _G.net.WriteBool

`WriteColor(table Color, bool WriteAlpha)` \
Same as _G.net.WriteColor

`WriteFloat(number Value)` \
Same as _G.net.WriteFloat

`WriteInt(number Value, number BitCount)` \
Same as _G.net.WriteInt

`WriteUInt(number Value, number BitCount)` \
Same as _G.net.WriteUInt

`WriteString(string Value)` \
Same as _G.net.WriteString

`WriteEntity(Entity Entity)` \
Same as _G.net.WriteEntity

`WriteVector(Vector Vector)` \
Same as _G.net.WriteVector

`WriteNormal(Vector Normal)` \
Same as _G.net.WriteVector \
Does not normalize the Vector

`WriteAngle(Angle Angle)` \
Same as _G.net.WriteAngle

`WriteMatrix(VMatrix Matrix)` \
Same as _G.net.WriteMatrix \
Temporarily disabled, does not write anything

</details>

### _R.Entity

<details>
<summary>Entity Additions</summary>

`any GetDTNetVar(string NetVar, number Force)` \
Returns a data entry from the entity's network variable datatable \
The values for Force are:

| Value | Type |
| --- | --- |
| 0 | Integer |
| 1 | Float |
| 2 | Vector |
| 3 | Vector2 |
| 4 | String |
| 5 | Entity |

`SetDTNetVar(string NetVar, any Value)` \
Sets a data entry on the entity's network variable datatable to the given value

`SetInterpolationEnabled(bool Enabled)` \
Sets whether or not this entity should be interpolated

</details>

<details>
<summary>CUserCmd Additions</summary>

`bool GetInWorldClicker()` \
Returns if the command is using world clicker

`SetInWorldClicker(bool WorldClicker)` \
Sets whether or not the command is using world clicker

`Vector GetWorldClickerAngles()` \
Returns the world clicking direction of the command

`SetWorldClickerAngles(Vector Angles)` \
Sets the world clicking direction of the command

`SetCommandNumber(number CommandNumber)` \
Sets the command number on the command

`SetTickCount(number TickCount)` \
Sets the tick count on the command

`number GetRandomSeed()` \
Returns the random seed of the command

`SetRandomSeed(number RandomSeed)` \
Sets the random seed of the command \
Internally moves command number forward until desired seed is reached

`bool GetIsTyping()` \
Returns if the command is set to be in the typing (Chatbox open) state

`SetIsTyping(bool Type)` \
Sets the typing (Chatbox open) state of the command

`bool HasBeenPredicted()` \
Returns if the command has already been predicted

`bool IsKeyCodeDown(number KeyCode)` \
Returns if a key code is being pressed

`AddKeyCode(number KeyCode)` \
Adds a key code to the command's pressed key list \
There is a limit of 5 keys being pressed for any given command. If all slots are full, the first slot will be overridden

`RemoveKeyCode(number KeyCode)` \
Removes a key come from the command's pressed key list

</details>
