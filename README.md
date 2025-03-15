# LethalCompanyModDoc

## ILSpy

File > Open > Navigate to "steamapps\common\Lethal Company\Lethal Company_Data\Managed" > Select "Assembly-CSharp.dll" to view the game's code

Right click the types to see where Classes and Methods are used (Analyze feature)

## Asset Bundle

In order to bundle assets in unity: 
  - Navigate to Window > Package Manager
  - Click the + (Add) button at the top, left corner of the window.
  - Choose Add package from git URL…
  - Enter https://github.com/Unity-Technologies/AssetBundles-Browser.git as the URL
  - Click Add.

After installing, you can navigate to Window > AssetBundle Browser and build your assetbundle there.

See this file for an example on importing asset bundle into code:

https://github.com/JohnPhamDeveloper/GamblingModLethalCompany/blob/main/GamblersMod/Plugin.cs

## Rendering Assets In Game

Lethal Company uses HDRP shaders. If your assets do not use HDRP, it will be invisible or gray ingame. I personally use the HDRP/Lit.

You may need to install these shaders. Navigate to Window > Package Manager > Top right search bar type in "High Definition RP" and install.

After installing we'll need to convert our material assets to HDRP. Navigate to Window > Rendering > HDRP Wizard. Make sure all the checkmarks are green in the wizard.
In the unity editor (not in the HDRP Wizard window), you can highlight/select your materials that you want to convert to HDRP. Once highlighted, switch back to the HDRP wizard window and select "Convert Selected Built-in Materials to HDRP".

## Networking

In order to write our own network code from Unity, we need to utilize a NetWeaver patcher: https://github.com/EvaisaDev/UnityNetcodeWeaver.

In visual studio code 2022, Right click project solution > Properties > Build (left panel) > Advanced... > Set debugging information to "Portable". Failing to do this step will result in the netcode patcher failing.

https://lethal.wiki/advanced-modding/networking#why-netcode-weaver

## Using RuntimeUnityEditor

Download here: https://github.com/ManlyMarco/RuntimeUnityEditor
If no UI shows up ingame, open BepInEx.cfg and set HideManagerGameObject = true

## Modding Resources

https://lethal.wiki/

Unofficial Lethal Company Discord

## Tools used

Unity 2021.3.15f1 Personal

ILSpy

https://github.com/ManlyMarco/RuntimeUnityEditor

## Functions
Contains code for the tool tip pop up on hovering an item
```
SetHoverTipAndCurrentInteractTrigger
```
## Issues

### My ClientRPC code is being called on the host but not on the client
You need to use the NetWeaver patcher. Visit that section [here](#Networking)

### Seeing an error "NetworkObjectReference can only be created from spawned NetworkObjects" or "Networkvariable is written to but doesn't know its networkbehaviour"
Make sure to add your prefab to the Network manager: 
```
NetworkManager.Singleton.AddNetworkPrefab(Plugin.GamblingMachine)
```

In addition, After you instantiate the game object, it MUST be spawned in the server and not the client. After instantiating, spawn it using:
```
GetComponent<NetworkObject>().Spawn();
```




