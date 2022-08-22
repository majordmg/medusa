# Medusa C3 

## Setup
1. Create a bot in Telegram 
2. Insert the bot API key and your telegram username into your local copy of medusa.wsf
3. Send local copy of medusa.wsf to victim
4. ????
5. Profit

## Warnings
The channel must be active in order for new implants to get the chat ID and successfully connect. Therefore, you must send a message to the channel before implants will call back. Before you send the implant to a victim, make sure to send a message in the channel. <b>New implants may not check in until you send a message if it's been a while since you've sent a message in the channel</b>. This is a limitation which will be addressed in future versions. 

<b>Using the persist command may get your implant caught by EDR.</b> Use with caution. 

## Commands

<b>rollcall</b>: list all active implants<br>
<b>choose ____</b>: chooses a given implant to receive and execute commands<br>
<b>die</b>: terminates chosen implant<br>
<b>killall</b>: terminates all implants<br>
<b>persist</b>: enables user-specific persistence by writing implant execution to the current user's "Run" registry key<br>
<br>
Any commands issued after an implant is chosen, with the exception of the special commands above, will be executed by that implant via cmd.exe

## Upcoming Features
- purge: remove persistence registry key, delete implant and output file, 
- E2EE: use a custom telegram client and encrypt all communications E2EE (client access probably hosted on public infrastructure)
- solve chat id problem / stayalive issues by hosting chat id on a public endpoint (requires hosted infrastructure)
- functionality to kill implants by username
- functionality to change interpreter (between cmd, powershell, wmic)
- utilize WSF jobs to spin off processes
- implement process migration capabilities
- auto obfuscate source
- try remotely executing scripts rather than loading them into memory / on disk
- remove the blocking execution limitation (3rd param in WshShell.Run) and track different output files for each job
- implement multiple persistence mechanisms
- write to registry using regread / regwrite native methods 
- implement EDR / AV killers 
- autopopulate EDR / AV detection 
- custom telegram keyboard for macros 
- hide annoying heartbeats
- implement multiple egress channels (not just telegram -- requires hosted infrastrx)
- implement keylogger
- implement screengrabber
- implement direct execution of binaries and preload (e.g. fakelogonscreen, certify)
- build dll for persistence
- implement multi-stage proxy for relay attacks
