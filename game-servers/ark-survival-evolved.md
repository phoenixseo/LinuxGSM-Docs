# Ark Survival Evolved

## Config Files

```text
serverfiles/ShooterGame/Saved/Config/LinuxServer/GameUserSettings.ini
serverfiles/ShooterGame/Saved/Config/LinuxServer/Game.ini
```

## Change Map

You can change the map by editing the [instance config](../configuration/linuxgsm-config.md) `lgsm/config-lgsm/arkserver/arkserver.cfg`.

Add the line `defaultmap="MAP_NAME_HERE"`. You can find a official map list right below.

### Official Map Names:

* TheIsland
* TheCenter
* Ragnarok
* ScorchedEarth\_P
* Aberration\_P
* Extinction
* Valguero\_P

## Change maximum players

You can change the number of maximum players by editing the [instance config](../configuration/linuxgsm-config.md) `lgsm/config-lgsm/arkserver/arkserver.cfg`.

Add the line `maxplayers=70`.

## Adding Mods

Add `-automanagedmods` to the [start parameters](../configuration/start-parameters.md).

Next edit `GameUserSettings.ini`, adding the following line under `[ServerSettings]`.

```text
ActiveMods=[workshopID],[workshopID],[workshopID],[workshopID]
```

Next edit `Game.ini` and add the following section. &lt;-- Doing this will auto download mods.

```text
[ModInstaller]
ModIDS=[workshopID]
ModIDS=[workshopID]
ModIDS=[workshopID]
ModIDS=[workshopID]
```

Replace `[workshopID]` with required workshop ID's.

All workshop mods can be found here [http://steamcommunity.com/app/346110/workshop/](http://steamcommunity.com/app/346110/workshop/).

## Collections

Collection Ids won't work directly. You need to have all the ids of the mods you want to use. One tool for getting the ids can be found here: [https://tools.rusty.info/tools/stcolids/](https://tools.rusty.info/tools/stcolids/)

## Clusters

First you need multiple server instances. Please follow [this guide](https://docs.linuxgsm.com/features/multiple-game-servers) if you don't know how:

Follow [this guide](https://survivetheark.com/index.php?/forums/topic/87419-guide-cluster-setup/) to create server clusters:

To change command-line parameters for your server edit your '_/lgsm/config-lgsm/arkserver/YourServerInstance.cfg_' file. Examle:

```text
fn_parms(){
  parms="\"TheIsland?SessionName=MyServerName1?AltSaveDirectoryName=Save1?Port=7777?QueryPort=27015" -NoTransferFromFiltering -clusterid=cluster1\""
}
```

**Additional Notes:** Servers which are running on local networks sometimes have trouble traveling to other arks. A fix I have found for this is adding '?MultiHome=0.0.0.0' to your command-line parameters.

