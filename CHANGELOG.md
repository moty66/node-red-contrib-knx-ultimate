![Sample Node](img/logo.png)

[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-blue.svg?style=flat-square)](https://www.paypal.me/techtoday) 

<br/>

# CHANGELOG

<p>
<b>Version 1.3.30</b> - February 2022<br/>
- KNX Viewer node: changed the Datetime display to local time format.<br/>
</p>
<p>
<b>Version 1.3.29</b> - February 2022<br/>
- Load Control: the timer for shedding won't everytime obey to what you've set. Fixed. <br/>
- Load Control: Added pre-shedding yellow warning message in the node status.<br/>
</p>
<p>
<b>Version 1.3.28</b> - February 2022<br/>
- NEW: KNX Viewer: this node allow you to see all datapints and values in a dashboard wirget. https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/knxUltimateViewer<br/>
</p>
<p>
<b>Version 1.3.27</b> - February 2022<br/>
- Load Control: minor fixes + issue a KNX read of Watt values, in case the GA doesn't automatically send a power value on change.<br/>
</p>
<p>
<b>Version 1.3.26</b> - February 2022<br/>
- FIX: fix a crash occurring it the KNX Gateway is set to "emulate" (that means, don't write to the bus).<br/>
</p>
<p>
<b>Version 1.3.25</b> - February 2022<br/>
- FIX: Load Control: measure unit was Wh. Corrected in W. Thank @Mauro of VivereSmart Facebook group https://www.facebook.com/groups/viveresmart<br/>
- Load Control: Added more info to the output message. Updated the online help.<br/>
</p>
<p>
<b>Version 1.3.24</b> - February 2022<br/>
- NEW: Load Control node: switch off your device if you're exceeding the Watt limit of your house.<br/>
- FIX: Alerter Node: fixed a KNX Address verification, in case you wrote your own string instead of a GA.<br/>
- FIX: Alerter Node: the node was sending a "read" request to all group addresses at start. Fixed.<br/>
</p>
<p>
<b>Version 1.3.22</b> - February 2022<br/>
- FIX: WriteRaw: some values wasn't sent to the bus due to an hex conversion issue.<br/>
</p>
<p>
<b>Version 1.3.21</b> - January 2022<br/>
- FIX: Node Logger wasn't correclty logging the bus traffic. Fixed.<br/>
</p>
<p>
<b>Version 1.3.20</b> - January 2022<br/>
- NEW: Telegram out queue TTL: as soon as KNX-Ultimate detects a connection loss, it will retain the telegrams sent to the BUS during the disconnection. After the reconnection, KNX-Ultimate will send the retained queue.<br/>
</p>
<p>
<b>Version 1.3.19</b> - January 2022<br/>
- NEW: Added Datapoint 14.058 Pressure (Pa).<br/>
- Added some more description while disconnecting from the BUS.<br/>
</p>
<p>
<b>Version 1.3.18</b> - January 2022<br/>
- FIX: Scene Controller: fixed an issue preventing the node to work if you haven't set the RECALL and SAVE group addresses.<br/>
- WIKI: updated the samples in the scene controller node.<br/>
</p>
<p>
<b>Version 1.3.16</b> - January 2022<br/>
- KNXEngine: there are some weird KNX gateways out there, either sending malformed header or CEMI messages. Now KNX-Ultimate will simply ignore these bad messages. Prior, it was disconnecting.<br/>
- KNXEngine: KNX-Secure packets are silently discarded for now, until KNX Secure will be ready.<br/>
- KNXEngine: added more logs to for troubleshooting pourposes.<br/>
</p>
<p>
<b>Version 1.3.15</b> - January 2022<br/>
- KNXEngine: better handling of disconnection in UDP mode, allowing very old grandpa KNX/IP interfaces enough time to understand what's happening, avoiding it to go crazy.<br/>
- KNXEngine: corrected Curve Crypto in KNX-Secure (KNX Secure is not enabled yet!).<br/>
</p>
<p>
<b>Version 1.3.14</b> - 26 December 2021<br/>
- KNXEngine: ACK management: the not acknowledged message will be re-transmitted once, then the connection will be dropped, as per KNX specs.<br/>
- KNXEngine: ACK management: the telegram's queue to be sent to the KNX BUS will be paused during the ACK waiting.<br/>
- KNXEngine: Routing: now the routing_busy and routing_lost_messages telegrams sent by the KNX/IP Router are  handled.<br/>
</p>
<p>
<b>Version 1.3.13</b> - 25 December 2021<br/>
- KNXEngine: when in tunneling and suppress ACK request is disabled, the error is raised only after 3° failed ACK reception instead of 1°.<br/>
- KNXEngine: at disconnection, delete all pending ACK requests timer.<br/>
- Warning: if you've suppressed the ACK requests, in some cases the node cannot detect the disconnection. In this case, please use the KNX Watchdog to detect the disconnecitons and reconnect.<br/>
</p>
<p>
<b>Version 1.3.12</b> - December 2021<br/>
- KNX-Ultimate DEVICE node: added the validation of Group Address while deploy, with support for modern addressing up to 31/7/255.<br/>
</p>
<p>
<b>Version 1.3.10</b> - December 2021<br/>
- FIX: fixed a stupid "Disconnected by Message length mismatch 8/16" error due to a dumb find/replace error in the code.<br/>
- Added some more log to help resolving issues.<br/>
</p>
<p>
<b>Version 1.3.5 - REMOVED FROM REPO due to "Disconnected by Message length mismatch 8/16" error</b> - December 2021<br/>
- New KNX Engine has been enabled again, after fixing some glitches.<br/>
</p>
<p>
<b>Version 1.3.4</b> - December 2021<br/>
- Temporary reverted to old API, due to some little glitches.<br/>
</p>
<p>
<b>Version 1.3.2</b> - December 2021<br/>
- NEW: config node: you can now gather debug info (there is a button for that) to be sent to the developer to help resolving your issue. Then, please paste the debug infos in your gitHub issue.<br/>
</p>
<p>
<b>Version 1.3.1</b> - December 2021<br/>
---- MAJOR VERSION WITH TOTALLY REWRITTEN KNX API, IN PURE JAVASCRIPT ----<br/>
---- IF YOU ENCOUNTER ISSUES, JUST INSTALL THE LAST OLD VERSION WITH: npm install node-red-contrib-knx-ultimate@1.2.57 ----<br/>
---- PLEASE BE AWARE THAT ALL PREVIOULSY KNX SECURE OPTIONS HAVE BEEN HIDDEN UNTIL READY TO BE RELEASED, TO AVOID CONFUSIONS ----<br/>
- KNX-Secure: not ready yet. I think not before the 1° quarter of 2022 because i'm learning the MANY cryptograhics algorithms of this Secure thing. Already done are the loading/checking against password of the ETS Keyring file, the new TCP stack (will come toghether with the already present UDP stack) and the first connection handshake between KNX-Ultimate and a KNX/IP Interface via TCP tunnel, using the DH Curve25519 algorythm. SOMEONE INTERESTED HELPING ME WITH THE DEVELOPMENT (FOR FREE)?<br/>
- NEW: new KNX API developed in these months. This new API is more speedy, more mantainable (get rid of the old "machina" framework) and ready to accomodate the natively supports KNX-Secure.<br/>
- NEW: ETS Logger: now the node logs the sent packets as well (previously, it was recording only the received ones).<br/>
- NEW: KNX-Ultimate now supports TCP connection as well (for KNX Secure tunneling). All protocols are now supported (UDP Routing and Tunneling, TCP).<br/>
- NEW: You can now choose the IP protocol to be used for the gateway.<br/>
- NEW: WatchDog node: You can now set the communication protocol (TunnelingUDP, Multicast) using msg.setGatewayConfig.Protocol. Updated the Wiki as well to reflect the change.<br/>
- FIX: Watchdog node's setConfig sat the wrong configuration in case of more than one node gateway simultaneously active on the same flow.<br/>
- FIX: Manually setting interface in a gateway node set to multicast address, resulting in the gateway bond to all interfaces, causing some issues in receiving datagrams on systems having more than one ethernet interface active at the same time.<br/>
- FIX: KNX-Device: if the node was set to react to "Read" requests and "Autorespond" was also enabled and "Autorespond with default value if no payload is present" was also active, in some circumstances the "response" telegram was sent to a wrong group address.<br/>
- FIX: Config gateway: the custom delay between Telegrams sent to the KNX BUS was locked to the safe mimimum of 40ms, even if you sat a lower value. Now is 30ms, but proceed with caution if you set a low value. 50ms should be the safe-default.<br/>
- FIX: Config gateway: suppress acknowledge telegram now work as expected, totally ignoring received Acknowledges and don't ask for any as well. Prior was only ignoring the received Acknowledges.<br/>
</p>
<p>
<b>Version 1.2.57</b> - November 2021<br/>
- Added following datapoints:<br/>
- 12.100 counter timesec (s)<br/>
- 12.101 counter timemin (min)<br/>
- 12.102 counter timehrs (h)<br/>
- 12.1200 volume liquid (l)<br/>
</p>
<p>
<b>Version 1.2.56</b> - November 2021<br/>
- FIX: hotfix echo in tunneling mode doesn't work since 1.2.55.<br/>
</p>
<p>
<b>Version 1.2.55</b> - November 2021<br/>
- Gateway servere node: recoding of some javascript parts, to increase speed to better accomodate the crypt/entrypt process of the upcoming KNX-Secure implementation.<br/>
- KNX-Secure: succesfully read ETS Keyring file and decrypt of Devices keys, Group Address keys, Backbone Key, Management Key and Auth Key.<br/>
- KNX-Secure: a shield icon near the Gateway name in the KNX Device node appears, if KNX-Secure gateway has been selected.<br/>
- KNX-Secure: node-red log now logs wether the gateway is secure or not, ETS Keyring project name, created By and ETS version.<br/>
</p>
<p>
<b>Version 1.2.54</b> - November 2021<br/>
- <font color="red">THIS VERSION TOUCHES MANY CONNECTIVITY POINTS.</font> It should handle all things better, but if you've trouble, you can always revert to the previous version by issuing <b>npm install node-red-contrib-knx-ultimate@1.2.53</b><br/>
- Tunneling/Routing connection optimization: standardized delay in CONNECT_RESPONSE timeout and cleaned some code to better handling installations with more than 500 group addresses.<br/>
- In tunneling mode, the node now signal the disconnection after 3 KNX Interface's connection state response failed, as per KNX standard.<br/>
- Increased the socket telegram TTL (Time to Live) for Multicast as well as for Unicast, from 16 to 128 for better handling of multirouted packets.<br/>
- Added "[THE GATEWAY NODE HAS BEEN DISABLED]" node status message, if you've disabled the KNX Gateway.<br/>
- NEW: you can now choose to delay the connection to the KNX BUS at start. In some circumstances it's advisable to delay the connection to the BUS to allow the ethernet cards to be lifted up by the sysop. Thi happens often in VM environments.<br/>
- Changing the log level in the Gateway node doesn't require a node-red restart anymore.<br/>
- Because i'm flooded by user's queries, i removed a warning from the node status, if the persitent file has not yet been created.<br/>
- Wait for message acknowledge by the IP router: now waits for 5 failed message ACKs before firing the disconnection sequence.<br/>
- FIX: fixed a false "disconnection" node status, due to a glitch in the KNX API (after a connection request, the API was sending a false "disconnection" status). Chiamati in causa anche tutti i Santi, prima.<br/>
- Fixed some check-connection timers not stopping in time.<br/>
- Speed up the first KNX connection after node-red start/restart/deploy.<br/>
- Speed up the reconnection attempts in case of disconnections.<br/>
</p>
<p>
<b>Version 1.2.53</b> - November 2021<br/>
- Device node: as soon as you add a new node with "read from bus at start" option enabeld, it requests the value from the BUS also if you DEPLOY "modified nodes" only. Prior to that, you had to do a full DEPLOY.<br/>
</p>
<p>
<b>Version 1.2.52</b> - October 2021<br/>
- KNX Logger node: fixed some default fields.<br/>
</p>
<p>
<b>Version 1.2.51</b> - October 2021<br/>
- NEW: Logger node: you can now count telegrams per second (or any interval you want), for statistic pourposes. Thank @RicharddeCrep for proposing this ehnancement.<br/>
- WIKI: Updated the wiki in Deutsch, English, Italano and Chinese.<br/>
- Datapoint 10.001: fixed a little issue if the date of week is Sunday.<br/>
- Added the milliseconds indication in all logs (things happen fast!).<br/>
</p>
<p>
<b>Version 1.2.49</b> - October 2021<br/>
- Gateway connection: added more checks for connection resilience, in case of KNX Interface of particular manufacturer.<br/>
- Gateway connection: connection is now more speedy.<br/>
- NEW: Gateway connection has a new option to enable/disable the automatic connection to the KNX BUS at start. You can now choose not to connect to the BUS on boot.
- Watchdog node: fixed an issue in changing the configuration via setConfig parameter, when an ethernet interface was manually selected in the config window.<br/>
</p>
<p>
<b>Version 1.2.48</b> - October 2021<br/>
- Watchdog node: fixed a misleading status color during the first KNX test performed.<br/>
</p>
<p>
<b>Version 1.2.47</b> - September 2021<br/>
- Added Datapoint 14.057 Power Factor.<br/>
</p>
<p>
<b>Version 1.2.46</b> - September 2021<br/>
- GlobalContext Node: you can now correctly pass the value to a group address even without setting the datapoint, if you import the CSV file.<br/>
</p>
<p>
<b>Version 1.2.45</b> - September 2021<br/>
- NEW: Chinese translation. Many thanks @songzh96 for the BIG work done in traslating the entire WIKI and the node config windows in Chinese!<br/>
</p>
<p>
<b>Version 1.2.44</b> - September 2021<br/>
- NEW: Scene Node: you can now add a pause in the command rule list (example, turn on light, wait 4000 milliseconds, turn off light). <br/>
- WIKI: better organization of help, with direct links "SEE ALSO" to other related pages. You find these links at the bottom of every each page.<br/>
</p>
<p>
<b>Version 1.2.43</b> - September 2021<br/>
- Watchdog Node: fixed the msg.connectGateway = true not actually reconnecting.<br/>
</p>
<p>
<b>Version 1.2.42</b> - August 2021<br/>
- FIX: if the config node is configured in EMULATION mode, knx-ultimate ouputs always the flow msg with the Group Address as topic, instead of a msg with the customized topic (if you have customizet it).<br/>
</p>
<p>
<b>Version 1.2.41</b> - August 2021<br/>
- Fixed a zero day bug: the loading of buffer value other than true/false from the peristent file (where all the values are persisted, stored and read upon restart if you selected that in the node config) fails. No error occurs nor other malfunctions, but the node emits a status error and the value is not read from this file.<br/>
</p>
<p>
<b>Version 1.2.40</b> - August 2021<br/>
- Great improvement of system resource.<br/>
- Fixed too many reconnection attempts in a short timeframe. Now it's more relaxed thus more responsive.<br/>
- I've successfully collected KNX Secure device to go ahead with the development. THANK YOU TO ALL PATREONS, SPECIALLY TO A COMPANY THAT WON'T BE MENTIONED HERE, HAVING SENT ME KNX SECURE DEVICES.<br/>
</p>
<p>
<b>Version 1.2.39</b> - August 2021<br/>
- I remember you that i'm still collecting money to buy a KNX Router for testing KNX-Secure. Should you help me, click "Donate via PayPal" above in this page.<br/>
- Optimized the fix in 1.2.38 by adding more in-depth checks.<br/>
</p>
<p>
<b>Version 1.2.38</b> - August 2021<br/>
- I remember you that i'm still collecting money to buy a KNX Router for testing KNX-Secure. Should you help me, click "Donate via PayPal" above in this page.<br/>
- Sometimes, with some KNX Interfaces, whenever you unplug the eth cable for a while, the gateway could'nt regain the connection. Fixed.<br/>
- Added a slight random delay before connecting to KNX BUS, to allow lazy ehternet adapters to come up after a reboot.<br/>
- Improvement: knx-ultimate nodes does have a persistent state after reboot (it saves the states to a json file). Now, if you have multiple gateways, it saves the states for each gateway in a different file.<br/>
- FIX: currently, knx-ultimate set to "auto respond with current value" and "if value unknown, respond with", responds with value selected by the user, if the current value is "" or undefined. Now it does so even if the value is null.<br/>
</p>
<p>
<b>Version 1.2.36</b> - July 2021<br/>
- Fixed a wrong help link in the gateway configuration node, in the italian language.<br/>
- Fix: on importing ETS Group Addresses file, the debug window won't show the import's warnings/error.<br/>
- NEW: starting implementation of KNX Secure (ETA END DECEMBER 2021). For now, the only thing working is keyring import and verification of his Hash against the password you set on the file while exporting keyring from ETS and decyphering of the Backbone key.<br/>
- Updated WIKI and help to reflect KNX Secure changes.<br/>
</p>
<p>
<b>Version 1.2.34</b> - June 2021<br/>
- Gateway configuration: added option Suppress repeated (R-Flag) telegrams fom BUS. When enabled, this option suppress the telegrams marked as "repeated" (with R-Flag) coming from the bus. See here: https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/1.-Gateway-configuration<br/>
</p>
<p>
<b>Version 1.2.33</b> - May 2021<br/>
- Gateway configuration -> Advanced Options -> Node list in all flows: added more infos to each node in the list, to allow more control on the nodes overview. The options are: "No Initial Read, React to Write, React to Response, No React to Read, No Autorespond to Read Requests, Output type write, No RBE on Output to Bus, No RBE on Input from Bus"<br/>
</p>
<p>
<b>Version 1.2.32</b> - May 2021<br/>
- NEW Dattpoint 14.074 (Time in secs) and 14.076 (Volume in m3).<br/>
</p>
<p>
<b>Version 1.2.31</b> - May 2021<br/>
- Fixed an issue happening if whenever you change a KNX node's datapoint, while the persistent value saved to file has already been saved using the old datapoint.<br/>
</p>
<p>
<b>Version 1.2.30</b> - May 2021<br/>
- Datapoint 14.x: fixed a possible issue if the inpur message coming from the flow, is'nt a valid datapoint 14.x value.<br/>
</p>
<p>
<b>Version 1.2.29</b> - May 2021<br/>
- KNX Device: if "read on connection/reconnection" is selected, the gateway node will now read all values of all nodes in 2 steps: first from file (for the nodes set in this way), then from BUS (for the nodes set in this way). This allow nodes that are setup as virtual devices, to get their values from file before being asked to send the value as response to the bus, by other nodes. It's all clear? No? Sorry for that, i'm unable to better explain that.</br>
- Watchdog node: NEW: you can force the selected gateway to disconnect from the KNX BUS and to STOP reconnection attempts. You can also force the selected gateway to connect to the KNX BUS and to ENABLE reconnection attempts. https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample---WatchDog<br/>
</p>
<p>
<b>Version 1.2.28</b> - May 2021<br/>
- KNX Device: if you send a boolean value to a node with datapoint 16.001 (Ascii string), all nodes goes to sleep and shows "Waiting" in the status. Fixed. Thanks to @Podler.
</p>
<p>
<b>Version 1.2.27</b> - April 2021<br/>
- Alerter node: fixed an issue related to the order of cycled msg output of alerted devices.
- Alerter node: now you can read the value of all devices belonging to the list, on each connection/reconnection.<br/>
- Alerter node: now you can read the value of all devices belonging to the list, by massing *msg.readstatus = true* to the node.<br/>
- Updated Wiki, Help and SAMPLE to reflect this change.<br/>
</p>
<p>
<b>Version 1.2.26</b> - April 2021<br/>
- NEW: Alerter node: added a third output PIN containing the last alerted device (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/Alerter-Configuration).<br/>
- Updated Wiki, Help and SAMPLE to reflect this change.<br/>
</p>
<p>
<b>Version 1.2.25</b> - April 2021<br/>
- NEW: Alerter node: added a second output PIN containing all alerted devices at once (useful for Telegram, Alexa and so on) (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/Alerter-Configuration).<br/>
- NEW: Alerter node: now you can enter TWO device's descriptions, one short (MAX 14 CHARS, SUITABLE FOR DPT 16.x) and one long.<br/>
- Updated Wiki, Help and SAMPLE to reflect this change.<br/>
<p>
<p>
<b>Version 1.2.23</b> - April 2021<br/>
- Fix: Put some spaces in the device list window of Alerter and Scene node, to facilitate the fields editing.<br/>
- Alerter node: other than "write", the devices listed react to "response" telegrams as well (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/Alerter-Configuration).<br/>
</p>
<p>
<b>Version 1.2.22</b> - April 2021<br/>
- Fix: emulated mode in knx-ultimate set to "universal mode" has the topic always set to empty string.<br/>
- NEW: Alerter node (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/Alerter-Configuration).<br/>
- NEW: Alerter node HELP online with samples, in both italiano, english and deutsch.<br/>
</p>
<p>
<b>Version 1.2.21</b> - April 2021<br/>
- Increased the Multicast TTL from 1 to 16 (this should allow the multicast packet to be routed beyond the current subnet).<br/>
</p>
<p>
<b>Version 1.2.20</b> - April 2021<br/>
- The "Suppress ACK Request" in the gateway config window is now enabled by default on new installations. This prevent some issues with some IP Interfaces.<br/>
</p>
<p>
<b>Version 1.2.19</b> - April 2021<br/>
- NEW: Silent Mode for log. You can now chose to totally avoid logging, thanks to the new logging engine. This is useful for reducing I/O access to the disk. Thank to @Webbeh for the request.<br/>
</p>
<p>
<b>Version 1.2.18</b> - April 2021<br/>
- NEW: KNX-Ultimate node can retain it's value after reconnection to KNX bus and even after reboot of node-red.<br/>
- Update the WIKI to reflect the changes (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/2.-Node-Configuration).<br/>
- NEW: begin to prepare KNX-Ultimate to support KNX Secure. Some changes to the underlying API where made.<br/>
- Done some checks on new datapoints coming from BUS to discard wrong telegrams lenght.<br/>
</p>
<p>
<b>Version 1.2.14</b> - March 2021<br/>
- NEW: KNX-Logger now logs telegrams sent by KNX-Ultimate nodes having an IP Interface as gateway. Previously, it worked only woth IP Routers.<br/>
- Begin refractoring of code for KNX Secure compatibility.<br/>
</p>
<p>
<b>Version 1.2.13</b> - March 2021<br/>
- Global Context Node: added the option to set the interval to write to the KNX bus.<br/>
- Global Context Node: fixed the help link, it was broken in italian language.<br/>
- Global Context Node: optimized the JavaScript samples.<br/>
- Global Context Node: fix the gateway description not showing in config window, in italian language.<br/>
- Global Context Node: added the configuration help page in the wiki for all languages (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/GlobalVariable).<br/>
- NEW: Online node-red public test website: Point your browser here http://casacorte.myqnapcloud.com:2021 There is a node-red installation ready to be tested, with KNX-Ultimate fully set in "emulation" mode (you cannot do any damage, because the KNX backbone is simulated).<br/>
- Added proKNX to the list of KNX device manufacturers using KNX-Ultimate (at bottom of the README page).<br/>
</p>
<p>
<b>Version 1.2.11</b> - February 2021<br/>
- NEW: Gateway Simulation node. Put "EMULATE" instead of IP Address in the gateway node. The gateway will not write to the KNX BUS. Useful for simulation and classroom's lessons.<br/>
- NEW: Online node-red public test website... coming soon.
</p>
<p>
<p>
<b>Version 1.2.10</b> - February 2021<br/>
- Global Context Node: fixed translation issues and added a warning in the config window.
</p>
<p>
<b>Version 1.2.9</b> - February 2021<br/>
- NEW: LOBAL CONTEXT node: https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/SampleGlobalContextNode), exposes the group addresses to a Global Context variable, to be used in function nodes.<br/>
- NEW: Datapoint 19.001 DateTime<br/>
- Added sample in the config window of Datapoint 19.001 and updated the sample page in the wiki.
</p>
<p>
<b>Version 1.2.8</b> - January 2021<br/>
- NEW: you can now change the node configuration my input message. https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample-setConfig<br/>
- Added msg.setConfig sample and updated the rest of the WIKI.
</p>
<p>
<b>Version 1.2.7</b> - January 2021<br/>
- NEW: Datapoint 237 DALI diags. https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample---DPT237<br/>
- Added sample DPT 237.x in the Wiki
</p>
<p>
<b>Version 1.2.6</b> - January 2021<br/>
- NEW: Datapoint 213.x has been added.<br/>
- Added sample DPT 213.x in the Wiki
</p>
<p>
<b>Version 1.2.5</b> - January 2021<br/>
- FIX: nodes wasn't emitting a msg to the flow, when they've been set to respond to READ requests while the they haven't already received a value either from BUS or flow.<br/>
- NEW: you can now update the node's payload without sending the KNX Telegram to the bus. See the node input messages in the wiki and the Virtual Device sample.<br/>
- Updated the Help in various parts of the wiki.<br/>
- Updated Virtual Device sample, in the samples section.<br/>
</p>
<p>
<b>Version 1.2.4</b> - January 2021<br/>
- REMOVED: removed compatibility with KNX Virtual because it brokes some dockerized/pluginized node-red KNX connections.<br/>
</p>
<p>
<b>Version 1.2.3</b> - 31 December 2020<br/>
- FIX: last 2 bytes of 249.600 were swapped.<br/>
- FIX: last 2 bytes of 242.600 were swapped.<br/>
</p>
<p>
<b>Version 1.2.2</b> - 31 December 2020<br/>
- NEW: Datapoint 249.600 added msg.payload={transitionTime:100, colourTemperature:1000, absoluteBrightness:80, isTimePeriodValid:true, isAbsoluteColourTemperatureValid:true, isAbsoluteBrightnessValid:true};
- FIX: validities bits of 242.600, that returns everytime true.<br/>
</p>
<p>
<b>Version 1.2.1</b> - December 2020<br/>
- FIX: fixed RBE filter not working for Datapoint 242.600<br/>
- Change: payload 242.600 must now be passed with color and brighness valididy booleans: msg.payload={x:500, y:500, brightness:80, isColorValid:true, isBrightnessValid:true};
</p>
<p>
<b>Version 1.2.0</b> - December 2020<br/>
- NEW: added compatibility with ETS KNX VIRTUAL.<br/>
- NEW: added node protection help in the german wiki.<br/>
- Updated the circular reference protection to be more intelligent thus more tollerant. Thanks @Christian for raising the request.<br/>
- Updated the circular reference sample in the wiki.<br/>
- Updated the msg input help in the wiki for all languages..<br/>
</p>
<p>
<b>Version 1.1.99</b> - December 2020<br/>
- FIX: RBE filter (from BUS and from flow) doesn't work if the payload is an object.<br/>
- Removed an unwanted debug log in dPT 242.600<br/>
</p>
<p>
<b>Version 1.1.98</b> - December 2020<br/>
- NEW: added Datapoint 242.600 Color xyY.<br/>
</p>
<p>
<b>Version 1.1.97</b> - December 2020<br/>
- NEW: added help links directly into the config windows and upon selection of datapoint as well.<br/>
- Cleaning of UI.<br/>
</p>
<p>
<b>Version 1.1.95</b> - December 2020<br/>
- Enhancement: you can now send a raw buffer directly to the KNX bus. See the Wiki, "message to the node" page.<br/>
- Updated the wiki accordingly.<br/>
</p>
<p>
<b>Version 1.1.93</b> - December 2020<br/>
- Enhancement: Check if the gateway's IP is a valid one, otherwise it avoids connection. Thanks @heleon for signaling this issue.<br/>
- Replaced some deprecated buffer calls.<br/>
</p>
<p>
<b>Version 1.1.92</b> - October 2020<br/>
- BUGFIX: RGB Color wasn't working. Now it's fixed.<br/>
</p>
<p>
<b>Version 1.1.91</b> - October 2020<br/>
- NEW: Datapoint 22.201 RCHH Status (for example, for MDT actuators)<br/>
- Added sample for Datapoint 22.x (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample---DPT22)<br/>
- Added sample for Datapoint 20.x<br/>
</p>
<p>
<b>Version 1.1.90</b> - October 2020<br/>
- Connection and queue handling optimization for big installations where knxd is used and where there is a near maximum (allowed by knx standards) of datagram per seconds traffic on the BUS. Thanks @Songzh<br/>
- FIX sample message not showing in the config window of knx-ultimate device, if the device is already presento on the flow. <br/>
- Added sample for Datapoint 2.*, 1 bit with priority. <br/>
- Added sample for Datapoint 6.x, value -128 to 127%. <br/>
- Added sample for Datapoint 7.x. <br/>
- Added sample for Datapoint 8.x. <br/>
- Added sample for Datapoint 9.x. <br/>
- Added sample for Datapoint 12.x. <br/>
- Added sample for Datapoint 13.x. <br/>
- Added sample for Datapoint 14.x. <br/>
- Added sample for switching on/off a POE port of Unifi Switch (https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample---UnifiPOE)
</p>
<p>
<b>Version 1.1.89</b> - September 2020<br/>
- Fix an issue, where the node stops connecting to the bus if you're using knxd, in some particular scenario. Thanks @Songzh<br/>
</p>
<p>
<b>Version 1.1.88</b> - September 2020<br/>
- FIX: Scene Controller. If disabled, it outputs now the correct values of recallscene and savescene properties (before, both was sentout as false, even if true). See here at bottom: https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/SceneController-MSG-to-the-node<br/>
</p>
<p>
<b>Version 1.1.86</b> - September 2020<br/>
- NEW: Scene Controller, added the ability to disable the scene controller via msg.disabled = true. See here at bottom: https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/SceneController-MSG-to-the-node<br/>
</p>
<p>
<b>Version 1.1.85</b> - September 2020<br/>
- FIX: The buffer of the ETS Logger is now cleared after every sendout. Thanks @Mil.<br/>
</p>
<p>
<b>Version 1.1.84</b> - September 2020<br/>
- The knx API is now part of knx-ultimate. External dependency has been removed. This allow to a more tight integration between KNX Bus and node-red.<br/>
- Update: Rewrite of all datapoint names, to adhere to ETS naming convenction. Updated some deprecated buffer initialization.<br/>
- NEW: Added Datapoint 6.020 Status with mode.<br/>
- NEW: Added Datapoint 8.012 Length in meter.<br/>
- NEW: Added Datapoint 9.029 Wind speed (km/h).<br/>
- NEW: Added Datapoint 9.030 Concentration (ug/m3).<br/>
- NEW: many people simply don't care about WIKI in Github, so i need to find a simpler and more direct way to access the huge documentation, without being flooded by questions about samples, that are already in the WIKI. Now KNX-Ultimate node displays a text box with sample on how to format input payload and a link to the relative help page, directly in the config window.<br/> 
</p>
<p>
<b>Version 1.1.83</b> - September 2020<br/>
- Update API to 2.3.24: Added Datapoint 222.100 and 222.201.<br/>
- NEW: Added Sample DPT 222 (See in the Wiki).<br/> 
</p>
<p>
<b>Version 1.1.82</b> - August 2020<br/>
- Update API to 2.3.23: Fixed a very old/why this?/odd issue with log in datapoints code, that instantiate a new instance of the logger instead of using the proper one. Thanks @heleon19 .<br/> 
</p>
<p>
<b>Version 1.1.81</b> - August 2020<br/>
- Update API to 2.3.22: Changed the log datetime from ISO to Local UTC. Added the prefix "KnUltimate-API to the log, to better undestand form where the log comes.<br/> 
- NEW: ADDED Datapoint 5.100 Fan Stage
</p>
<p>
<b>Version 1.1.80</b> - August 2020<br/>
- Update API to 2.3.21: changing the debug level now is applied immediately without restarting node-red. 
</p>
<p>
<b>Version 1.1.79</b> - August 2020<br/>
- NEW: The scene controller node can now save the current group address value via a msg input. See here: https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/SceneController-MSG-to-the-node and the sample in the wiki as well..
</p>
<p>
<b>Version 1.1.76</b> - August 2020<br/>
- Fixed the ETS XML logger. Sometimes the files could contains an invalid CEMI telegram that was not properly discarded and that prevent ETS to load the log. Thanks @Namakemono93.<br/>
- Fixed a visual glitch in the KNX-Node config window (Telegram value format) for nodered 1.1.0 and above.
</p>
<p>
<b>Version 1.1.75</b> - June 2020<br/>
- NEW: Added Datapont 7.xxx with 7.600 as well.<br/>
- Adjusted italian node translation on "OUTPUT (invio datagrammi sul bus KNX)" selection properties. Adjusted the documentation consequently.<br/>
</p>
<p>
<b>Version 1.1.73</b> - Mai 2020<br/>
- FIX: fixed an issue in importing ETS file, preventing import if you have an improperly set knx-ultimate node, having no gateway selected. Thanks @enzensbs.<br/>
</p>
<p>
<b>Version 1.1.72</b> - Mai 2020<br/>
- Update knx api to 2.3.19<br/>
- FIX: fixed a problem when issuing a gateway ip change to a watchdog node, if you've a tunneling KNX Interface and node-red v. 0.20 or below.<br/>
- FIX: above related with connection status request if tunneling mode, sometime giving "timed out waiting for CONNECTIONSTATE_RESPONSE" errors.<br/>
</p>
<p>
<b>Version 1.1.71</b> - Mai 2020<br/>
- Update knx api to 2.3.18<br/>
- NEW: added Datapoint 251.600 RGBW<br/>
- State request to the BUS is now sent every 60 seconds instead of 10, for lowering the BUS traffic (see changelog for Version 1.1.68)<br/>
- More relaxed handling of errors coming from an query to a KNX/IP interface not always reponding to connection status (in case, for example, of some implementations of knxd)<br/>
- Watchdog: on "basic Ethernet check", switched to ping mode detection. With the introduction of "echo local telegrams" in unicast mode, since some versions ago, the watchdog must yet check for the KNX Interface using Ping, otherwise, the lost of connection is never trapped. Other than that, the "basic Ethernet check" works only with KNX Interfaces, because the router uses multicast and multicast is connectionless.<br/>
</p>
<p>
<b>Version 1.1.70</b> - Mai 2020<br/>
- NEW: Added the option to select the delay between each telegram and further delay multiplicator between only the **read** telegrams<br/>
</p>
<p>
<b>Version 1.1.69</b> - Mai 2020<br/>
- Update: knxultimate-api to 2.3.17.<br/>
- NEW: Added Datapoint 12.001 and 12.1201.<br/>
</p>
<p>
<b>Version 1.1.68</b> - April 2020<br/>
- Update: knxultimate-api to 2.3.16.<br/>
- FIX: fixed disconnection in tunneling mode by strictly adhere to KNX standard (sending state request to the BUS every 10 seconds). Thanks to Matthias of Timberwolf Server.<br/>
- Introduced some internal changes in preparation to the introduction of the new dashboard compatible visualization nodeset "visu-ultimate".<br/>
</p>
<p>
<b>Version 1.1.67</b> - April 2020<br/>
- Re-introduced selectable option for local echo if tunneling.<br/>
- Smarter restart maneuvering in case of Ethernet issues, while on tunneling connections.<br/>
</p>
<p>
<b>Version 1.1.65</b> - April 2020<br/>
- FIX: If the imported ETS file, contains a device name with a # character, strange things happens. Fixed.<br/>
- Forced local Echo for IP interfaces.<br/>
</p>
<p>
<b>Version 1.1.64</b> - April 2020<br/>
- NEW: Added output type "Read", to issue a read by simply pass a payload to the node. Thanks @waldbaer for the suggestion.<br/>
</p>
<p>
<b>Version 1.1.63</b> - April 2020<br/>
- Informational nitification when datapoint RGB is selected, on how to pass into the payload.<br/>
- Removal selection of echoing the sent payload on all node, if the gateway is unicast. Now the echo is active everytime.<br/>
</p>
<p>
<b>Version 1.1.62</b> - April 2020 in Italy, we're crying our dead people.<br/>
- Better decriptive Multicast/Unicast gateway auto discovery.<br/>
- Definitive use of heavily modified knx-ultimate.js API instead of knx.js.<br/>
</p>
<p>
<b>Version 1.1.61</b> - April 2020 in Italy, deaths are increasing to 600 pro day.<br/>
- Fix error in ESF file import, if you set more than one Group Address in a single device property.<br/>
</p>
<p>
<b>Version 1.1.60</b> - April 2020 in Italy, deaths are decresing to 500 pro day.<br/>
- Fix error in gateway node translation, that disappeared.<br/>
</p>
<p>
<b>Version 1.1.59</b> - April 2020 in Italy, deaths are decresing to 500 pro day.<br/>
- Adjusted translations.<br/>
- NEW: added Datapoint 10 Bytes.<br/>
</p>
<p>
<b>Version 1.1.58</b> - April 2020 in Italy, continue lock down Coronavirus.<br/>
- Adjusted translations.<br/>
- Small bugfixes.<br/>
- Removed the deprecated setGatewayConfig from knx-ultimate. Use Watchdog node instead.<br/>
</p>
<p>
<b>Version 1.1.57</b> - April 2020 in Italy, continue lock down Coronavirus, but situation is better now.<br/>
- Datapoint 18.001 added. Now this datapoint for Scene is fully supported.<br/>
- Sample controlling datapoint 18.001.<br/>
- Scene node and knx-ultimate device node changed accordnlgy.<br/>
</p>
<p>
<b>Version 1.1.55</b> - March 2020 in Italy, continue lock down Coronavirus, but situation is better now.<br/>
- NEW: Added option to skip the import of the group address from the ETS file, if the datapoint is not set.<br/>
</p>
<p>
<b>Version 1.1.54</b> - March 2020 in Italy, continue lock down Coronavirus, but situation is better now.<br/>
- FIX: fixed status display of date/time. Yet if you uncheck the option not do display the date/time, it works.<br/>
- ENHANCEMENT: search for all words in the group address fields. You can now search, for example, for "licht wohnzimmer".<br/>
- Changed palette order to better view the service nodes, like Logger and Watchdog.<br/>
- Ongoning Deutch translation.<br/>
</p>
<p>
<b>Version 1.1.53</b> - March 2020 in Italy, continue lock down Coronavirus.<br/>
- NEW: msg passthrough option.<br/>
</p>
<p>
<b>Version 1.1.52</b> - March 2020 in Italy, continue lock down Coronavirus.<br/>
- FIX: import ETS csv and ESF files may had problem with languages other that english. Fixed.<br/>
- FIX: Scene Controller, fix trigger suggestion if datapoint trigger is set to DIM.<br/>
- FIX: WatchDog, fix autostart timer if no Group Address monitor is selected.<br/>
- NEW: Logger Node, a new node to hear all telegrams and to output an ETS bus monitor compatible file.<br/>
- Update underlying KNX api to 2.3.10, to extract CEMI telegram for the Logger Node.<br/>
- Minor bugfixes.<br/>
- Other translation work has been done.<br/>
</p>
<p>
<b>Version 1.1.50</b> - March 2020 in Italy, continue lock down Coronavirus. Cases 25.000<br/>
- FIX: Scene controller, the "save scene" datapoint was override by "recall scene" datapoint on each open of the config window.<br/>
- FIX: Scene Controller, without imported ETS file, the scene controller recall/save worked only with boolean values. Now it works correctly. Thanks @mthauth.<br/>
- FIX: Scene Controller, correct handling of dim commands (example {decr_incr:1,data:5}).<br/>
- Scene Controller now is called via javascript Promise to leverage the main thread.<br/>
</p>
<p>
<b>Version 1.1.48</b> - March 2020 in Italy, continue lock down Coronavirus. Milan index down 8%, Down Jons as well. Panic selling everywhere.<br/>
- FIX: When you copy/paste knx-ultimate or scene controller node, autofill of device names doesn't work.<br/>
- Scene Controller devices cosmetics adjustments.<br/>
</p>
<p>
<b>Version 1.1.47</b> - March 2020 in Italy, continue lock down. More people involved in Coronavirus<br/>
- FIX: In gateway config-node, fixed the "List of your nodes in all flows" (under Advanced Options) list, sometime not populated.<br/>
- ENHANCEMENT: Now knx-ultimate and scene controller display device list names for newly added nodes in the flow. Prior, you had to save the node first, to get the knx device list into the Group Address fields.<br/>
</p>
<p>
<b>Version 1.1.45</b> - March 2020 in Italy, we're locked down for Coronavirus<br/>
- Update knxultimate-api. Yet the nodes connected to an IP Interface, behaves like the nodes connected to an IP Router. See option <b>Echo sent message to all node with same Group Address</b> in the Gateway configuration wiki.<br/>
- I'm internationalizing the node <b>(Deutsch, Italiano, English)</b> with the help of <b>@svenflender</b>, so please be patient if some parts are still only in english. Internationalization is working with node-red version 1.0.3 and above. Versions below, does have issues in the i18n module, so knx-ultimate falls back to english. Please upgrade node-red.<br/>
</p>
<p>
<b>Version 1.1.43</b> - March 2020 in the middle of Coronavirus emergency in Italy<br/>
- NEW: Scene Controller node (see the Wiki).<br/>
</p>
<p>
<b>Version 1.1.40</b> - March 2020<br/>
- Better handling of telegrams, giving priority to the "write" and "response" telegram in the queue. Thanks @heleon19 for the suggestion.<br/>
</p>
<p>
<b>Version 1.1.39</b> - March 2020<br/>
- Fix a very low priority issue: a possible crash if you set the knx-ultimate node's output as "respond", while passing an object as payload to the input.<br/>
</p>
<p>
<b>Version 1.1.38</b> - March 2020<br/>
- Yet, if you import an ETS CSV file without datapoints, a fake datapoint 1.001 will be used (if you selected to force import the group address)<br/>
- Update help and wiki to reflect the change<br/>
</p>
<p>
<b>Version 1.1.37</b> - Feb 2020<br/>
- Fixed an issue where new knx-ultimate nodes, without a gateway config node, doesn't open the configuration window. Thanks @svenflender<br/>
</p>
<p>
<b>Version 1.1.36</b> - Feb 2020<br/>
- You can now import ESF group address format, beside CSV.<br/>
- Updated the Wiki.<br/>
</p>
<p>
<b>Version 1.1.34</b> - Feb 2020<br/>
- Fix an issue with RGB values.<br/>
- Added RGB sample in the Wiki.<br/>
</p>
<p>
<b>Version 1.1.33</b> - Feb 2020<br/>
- New: the Watchdog node now outputs a msg to the flow if you issued a setGatewayConfig<br/>
- Patched and switched to knxultimate-api (v. 2.3.8) underlying API. This should fix a very rare issue causing node-red to crash giving ERR_SOCKET_DGRAM_NOT_RUNNING error.<br/>
</p>
<p>
<b>Version 1.1.32</b> - Feb 2020<br/>
- New: in the knx-ultimate, added the option to <a href="https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/2.-Node-Configuration" target="_blank">format the msg.payload value</a>, if it's numeric.<br/>
- Switched to knx.js API 2.3.7<br/>
- Refractoring of some internal code to speed up things, whenever the node sends a "Read" request to the BUS.<br/>
- Fix a message warning in the config page, if you not imported the ETS csv file.<br/>
- Fix the "Universal Mode" setting wrongly reverting to false on newly added nodes, if you've not imported the ETS csv.<br/>
- Devicename msg property is now populated with the node name, if the node is in Universal Mode and the ETS CSV file has not been imported (previoulsy was set to empty string).<br/>
- Update the Wiki and node help, with the new "payload format" options.<br/>
</p>
<p>
<b>Version 1.1.31</b> - Feb 2020<br/>
- Rewritten the "Send a GrpValue read once on connection/reconnect" using the telegram queue.<br/>
- New: new underlying API set to knxultimate-api (v. 2.3.7) and patched with last API fixes. From now onwards, knx-ultimate node will switch between underlying <b>knx.js</b> API and his own <b>knxultimate-api</b>, to allow a quicker fix of possible problems with the API.<br/>
- Relocate nodes in a specific folder.<br/>
</p>
<p>
<b>Version 1.1.30</b> - Feb 2020<br/>
- New: the Watchdog node now signals if a knx-ultimate node throws errors as well. <a href="https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/8.-WatchDog-Messages-from-the-node" target="_blank">See here output message properties.</a><br/>
</p>
<p>
<b>Version 1.1.29</b> - Feb 2020<br/>
- Changed Node KNX Icon, logo and colors, thanks @svenflender <br/>
- New in config-node: copy/paste friendly text block, with a list of all KNX Nodes (for using, for example, in KNX Router line/zone filters).<br/>
- New: added subtype decoded value **payloadsubtypevalue** ( for exampe, On/Off, Ramp/NoRamp, Start/Stop, Alarm/NoAlarm ). <a href="https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Sample---Subtype" target="_blank">See here an example</a><br/>
</p>
<p>
<b>Version 1.1.28</b> - Jan 2020<br/>
- New: Added topic property<br/>
- New: added page to wiki, explaining the node protection. <a href="https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/-Protections" target="_blank">Node Protections</a>.<br/>
- Updated Wiki to reflect the new changes.<br/>
</p>
<p>
<b>Version 1.1.27</b> - Jan 2020<br/>
- New: added payloadmeasureunit to the node's msg output (for example "W" or "%"), based on Datapoint type.<br/>
- New: added knx.dptdesc to the node's msg output (for example "Power" or "Humidity").<br/>
- New: added Loglevel option in config-node, for debugging pourpose only. Thanks Heleon19.<br/>
</p>
<p>
<b>Version 1.1.26</b> - Jan 2020<br/>
- New: Watchdog Node added. Please <a href="https://github.com/Supergiovane/node-red-contrib-knx-ultimate/wiki/7.-WatchDog-Configuration" target="_blank">consult the Wiki</a>.<br/>
- Changed category (the node's list on left panel of node-red) to "KnxUltimate", to accomodate the Watchdog node.<br/>
</p>
<p>
<b>Version 1.1.25</b> - Jan 2020<br/>
- New: ability to programmatically change the KNX/IP interface or router's IP, Port, Physical Address and reset local ETH Interface Binding.<br/>
</p>
<p>
<b>Version 1.1.24</b> - Jan 2020<br/>
- FIX: If the message has no payload and no readstatus, throw an error. If you requests a readstatus, there's no need to pass a payload. Previously, the node has gone in stop mode if the payload was null, thus having readstatus.<br/>
- Added Read Request sample in the Wiki.<br/>
</p>
<p>
<b>Version 1.1.22</b><br/>
- Added msg.previouspayload that stores the previous node value<br/>
- Update Wiki accordlingy.<br/>
</p>
<p>
<b>Version 1.1.21</b><br/>
- Fixed a possible crash if the payload is an object and the node is set to send a "response" telegram instead of a "write" telegram.<br/>
- Added an explanation about meaning of status colors, in the node info on the right panel and in the wiki.<br/>
- Updated node info and wiki to reflect the new UI changes.<br/>
</p>
<p>
<b>Version 1.1.20</b><br/>
- Config node UI cleanup.<br/>
- During the ETS CSV file import, if a datapoint is not set, you can now select whether to abort the import or to skip the affected group address and continue.<br/>
- Added Homekit, Alexa and Google Assistant samples in the wiki.<br/>
</p>
<p>
<b>Version 1.1.19</b><br/>
- More UI cleanup.
</p>
<p>
<b>Version 1.1.18</b><br/>
- Removed the handling of the telegram queue's delay buffer from underlying KNX.js API, because it doesn't respect the telegram queue order.<br/>
- Added own message queue buffer with delay of 50 millisecs. Now the telegrams order is respected.<br/>
- In the node's configuration, added an advanced tab, that hides or shows the advanced options; now the configuration is much more clean. Advanced Options opens up automatically if the values have been changed from defaults.<br/>
</p>
<p>
<p>
<b>Version 1.1.17</b><br/>
- Fixed autorespond to a read request.<br/>
</p>
<p>
<b>Version 1.1.16</b><br/>
- Added a minimum delay of 60milliseconds between telegrams, when the node sends telegrams to the BUS, to avoid flooding the KNX BUS, causing a loss of telegrams. The KNX.org specs allows max 50 telegrams per seconds (max 1 telegram each 20milliseconds), but in real life, this is too much.<br/>
</p>
<p>
<b>Version 1.1.15</b><br/>
- Updated underlying API to 2.3.6 with some bugfixes.<br/>
- Added FAQ and troubleshoot in the Wiki.<br/>
</p>
<p>
<b>Version 1.1.14</b><br/>
- Fix issue with RBE Output due to code cleanup.<br/>
</p>
<p>
<b>Version 1.1.13</b><br/>
- Code cleanup thanks @SystemKeeper<br/>
</p>
<p>
<b>Version 1.1.12</b><br/>
- Universal mode optimizations<br/>
- Fix abnormal log iw universal mode receiver cannot find a suitable datapoint<br/>
- Added automatic discover for datapoint 14.056<br/>
- Added automatic discover for datapoint 16.001<br/>
</p>
<p>
<b>Version 1.1.12</b><br/>
- Fixed a little issue where the status message is not displayed if the node has not well wrote group address (for example 1/5 instead of 1/5/1). Thanks @arsiesis.<br/>
- Cleaned up the layout of config window.<br/>
- Changed option <b>Listen to all Group Addresses</b> to a more comprensible <b>Universal mode (listen to all Group Addresses)</b>.<br/>
- The node can now be used as universal KNX sender/receiver without the need of the ETS CSV File.<br/>
</p>
<p>
<b>Version 1.1.10</b><br/>
- Auto send node value as response to the KNX Bus. It works in conjunction with React to event GroupValue read. When checked, whenever the node receives a read request from bus, it sends a response to the KNX Bus with the stored payload value.<br/>
- Fixed an issue where if you have a node set to Universal mode (listen to all Group Addresses) (with ETS CSV File set) and you create a new node having a Group Addr. not in the ETS CSV file, an exception is raised but not caught and the nodes may not receive the values from KNX BUS.<br/>
</p>
<p>
<b>Version 1.1.9</b><br/>
- Fixed visual glitch when create a new freshly Config Node.<br/>
- Added 3 options in the config-node to select what to display in the node status, for a cleaner flow or for a clearer flow.<br/>
- Fixed issue with IP Interfaces. On each deploy, the node doesn't lock tunnels anymore.<br/>
</p>
<p>
<b>Version 1.1.8</b><br/>
- For new nodes, the rbe output filter is enabled by default. You can always turn it off in the options. This helps novice users avoiding loops.<br/>
- Fixed an issue where if the connection is in tunnel mode and the connection to the IP Interface or KNX Bus is lost, the node trows an unhandled exception. Thanks to User Maarten200.<br/>
- Added the word "knxUltimate" before any log, to identify that the log comes from the knx-ultimate node.<br/>
</p>
<p>
<b>Version 1.1.7</b><br/>
- Fixed bind to ethernet. Now you can manually input the ethernet name as well. Thanks to user rotorman.<br/>
</p>
<p>
<b>Version 1.1.6</b><br/>
- Fixed inport CSV from ETS where there is return carriages and parenthesis in the Group Address description. Thanks to user xrk.<br/>
</p>
<p>
<b>Version 1.1.4</b><br/>
- Last changed status date/time shortened out<br/>
</p>
<p>
<b>Version 1.1.3</b><br/>
- In node status, added the last changed status date/time.<br/>
</p>
<p>
<b>Version 1.1.2</b><br/>
- When you asks for a read on a node having Listen All Group Addresses set to true, due to a low delay between each KNX telegram, some telegrams are discarded. Increased the delay between telegram to avoid that.<br/>
- Added RBE filter for the INPUT from KNX bus as well.<br/>
- Added the option to bind to local ethernet interface, in case you have more than one, for example, ethernet and wifi.<br/>
- Fixed option suppress_ack_ldatareq not retain after restart.<br/>
- In-Line help update to reflect new changes.<br/>
</p>
<p>
<b>Version 1.1.1</b><br/>
- Disambigued misinterpretation of the "disconnect" status.<br/>
- In the autocomplete box of KNX device names, when you type in the group address or the device's name, it shows the main and subgroup name as well<br/>
- Cosmetic adjustment<br/>
- In-Line help additions<br/>
</p>
<p>
<b>Version 1.1.0 LTS (Long term stable)</b><br/>
- Once disabled for loop or circular reference protection, the node can be re-enabled by simply click on deploy "modified nodes"<br/>
- When "Universal mode (listen to all Group Addresses)" is selected, the RBE filter is disabled.<br/>
- Cosmetic adjustment<br/>
</p>
<p>
<b>Version 1.0.19</b><br/>
- Automatic loop protection<br/>
</p>
<p>
<b>Version 1.0.18</b><br/>
- Added gateway options:<br/>
    KNX Physical Address<br/>
    Suppress ACK request<br/>
    This option help compatibility with old Siemens SWG1 148-1AB22 IP Interface <br/>
- Added RBE option to the input (Report by Exception node - only passes on data if the payload has changed)<br/>
</p>
<p>
<b>Version 1.0.16</b><br/>
- Input message format has been CHANGED! please see the wiki!!!.<br/>
- Circular reference protection (when 2 nodes with same group address are link toghether, the protection avoids loops.).<br/>
</p>
<p>
<b>Version 1.0.15</b><br/>
- Device Node outputs the name when ETS csv is not set too.<br/>
</p>
<p>
<b>Version 1.0.14</b><br/>
- Fixed knx dependency<br/>
</p>
<p>
<b>Version 1.0.7</b><br/>
- Check for invalid node's Group Addr.<br/>
</p>
<p>
<b>Version 1.0.5</b><br/>
- Fixed the fix for the typo error causing a mess<br/>
</p>
<p>
<b>Version 1.0.5</b><br/>
- Fixed a typo error causing a mess<br/>
</p>
<p>
<b>Version 1.0.4</b><br/>
- Fixed possible issue with the csv ETS endpoint<br/>
</p>
<p>
<b>Version 1.0.3</b><br/>
- If ETS csv file is set, when typing a group address in the node, a list of KNX devices will be shown and when selected, it set the Datapoint and the Devicename automatically.<br/>
</p>
<p>
<b>Version 1.0.2</b><br/>
- Fixed minor glitches in node config ui<br/>
</p>
<p>
<b>Version 1.0.1 FIRST PUBLIC RELEASE</b><br/>
- Fixed minor glitches<br/>
- Ended extensive testing<br/>
- Enhanced Wiki and Youtube Video about ETS CSV File
</p>
<p>
<b>Version 0.0.6 BETA</b><br/>
- Fixed Output Type unable to be set<br/>
- Added node status for response (blue) and read (grey)<br/>
</p>
<p>
<b>Version 0.0.5 BETA</b><br/>
- Integration of Help documentation<br/>
- Readstatus fix<br/>
</p>
<p>
<b>Version 0.0.3 BETA</b><br/>
- Added Help documentation<br/>
- Added samples on the Readme.md<br/>
- Better user's notifications handling of the ETS csv file checks.<br/>
</p>
<p>
<b>Version 0.0.2 BETA</b><br/>
- Added BETA warnings.<br/>
</p>
<p>
<b>Version 0.0.1 BETA</b><br/>
- Initial release<br/>
</p>
