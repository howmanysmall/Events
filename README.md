# Maid
Manages the cleaning of events and other things.

### API
```cs
Maid Maid.new()
// Generates a new Maid object

number Maid:GiveTask(Task)
// Adds a Task to the Maid table, incremented by 1
// @returns index the Task was placed at

void Maid:LinkToInstance(Instance)
// Makes the Maid clean up when the instance is destroyed
// @param Instance Instance The Instance the Maid will wait for to be Destroyed
// @returns table Connection that can be Disconnect()ed to unlink to Instance

void Maid:DoCleaning()
// Disconnects all Events, Destroys all Objects, and calls all functions stored as Tasks
// Maid:Destroy() and Maid:Disconnect() are the same thing

void Maid:Destroy()
// Same as DoCleaning()

void Maid:Disconnect()
// Same as DoCleaning()
```
```
Maid[key] = (function)            Adds a function to call at cleanup
Maid[key] = (Instance)            Adds an Object to be Destroyed at cleanup
Maid[key] = (RBXScriptConnection) Adds a connection to be Disconnected at cleanup
Maid[key] = (Maid)                Maids can act as an event connection, allowing a Maid to have other maids to clean up.
Maid[key] = nil                   Removes a named task. This cleans up the previous Maid[key]
```
