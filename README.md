# LethalCompanyModDoc

## ILSpy

File > Open > Navigate to "steamapps\common\Lethal Company\Lethal Company_Data\Managed" > Select "Assembly-CSharp.dll" to view the game's code

Right click the types to see where Classes and Methods are used (Analyze feature)

## Asset Bundle

In order to bundle assets in unity, navigate to Window > Package Manager > Top right search bar type in "Asset Bundle Browser" and install. 

After installing, you can navigate to Window > AssetBundle Browser and build your assetbundle there.

See this file for an example on importing asset bundle into code:

https://github.com/JohnPhamDeveloper/GamblingModLethalCompany/blob/main/GamblersMod/Plugin.cs


## Networking

In order to write our own network code from Unity, we need to utilize NetWeaver: https://github.com/EvaisaDev/UnityNetcodeWeaver.

In visual studio code 2022, Right click project solution > Build (left panel) > Advanced... > Set debugging information to "Portable". Failing to do this step will result in the netcode patcher failing.

https://lethal.wiki/advanced-modding/networking#why-netcode-weaver

## Modding Resources

https://lethal.wiki/

Unofficial Lethal Company Discord

## Tools used

Unity 2021.3.15f1 Personal

ILSpy
