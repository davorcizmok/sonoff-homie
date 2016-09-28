[Homie](https://github.com/marvinroger/homie) based firmware for Sonoff wifi relay

## Features:
* ON/OFF relay
* Timer based relay
* Configurable default (on boot) relay state - (MQTT independent)
* Local button on/off
* All Homie buildin features (OTA,configuration)

## MQTT messages

<table>
<tr>
  <th>Property</th>
  <th>Message format</th>
  <th>Direction</th>
  <th>Description</th>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/relay01/relayState</td>
  <td><code>(ON|OFF)</code></td>
  <td>Device → Controller</td>
  <td>Current state of relay</td>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/relay01/relayState/set</td>
  <td><code>(ON|OFF)</code></td>
  <td>Controller → Device</td>
  <td>Change relay state</td>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/relay01/relayInitMode</td>
  <td><code>(0|1)</code></td>
  <td>Device → Controller</td>
  <td>Current boot mode <code>1</code> - relay ON, <code>0</code> - relay OFF</td>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/relay01/relayInitMode/set</td>
  <td><code>(0|1)</code></td>
  <td>Controller → Device</td>
  <td>Set Boot mode <code>1</code> - relay ON, <code>0</code> - relay OFF</td>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/relay01/relayTimer/set</td>
  <td><code>\d+</code></td>
  <td>Controller → Device</td>
  <td>Turn on relay for specific no. of seconds</td>
</tr>
<tr>
  <td>_HOMIE_PREFIX_/_node-id_/$online</td>
  <td><code>(true|false)</code></td>
  <td>Device → Controller</td>
  <td><code>/true</code> when the device is online, <code>false</code> when the device is offline (through LWT)</td>
</tr>
</table>
