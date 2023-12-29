# LethalCompanyModDoc

## ILSpy

File > Open > Navigate to "steamapps\common\Lethal Company\Lethal Company_Data\Managed" > Select "Assembly-CSharp.dll" to view the game's code

Right click the types to see where Classes and Methods are used (Analyze feature)

## Asset Bundle

In order to bundle assets in unity, navigate to Window > Package Manager > Top right search bar type in "Asset Bundle Browser" and install. 

After installing, you can navigate to Window > AssetBundle Browser and build your assetbundle there.

See this file for an example on importing asset bundle into code:

https://github.com/JohnPhamDeveloper/GamblingModLethalCompany/blob/main/GamblersMod/Plugin.cs

## Rendering Assets In Game

Lethal Company uses HDRP shaders. If your assets do not use HDRP, it will be invisible or gray ingame. I personally use the HDRP/Lit.

You may need to install these shaders. Navigate to Window > Package Manager > Top right search bar type in "High Definition RP" and install.

After installing we'll need to convert our material assets to HDRP. Navigate to Window > Rendering > HDRP Wizard. Make sure all the checkmarks are green in the wizard. 


## Networking

In order to write our own network code from Unity, we need to utilize NetWeaver: https://github.com/EvaisaDev/UnityNetcodeWeaver.

In visual studio code 2022, Right click project solution > Build (left panel) > Advanced... > Set debugging information to "Portable". Failing to do this step will result in the netcode patcher failing. In the unity editor (not in the HDRP Wizard window),
you can highlight/select your materials that you want to convert to HDRP. Once highlighted, switch back to the HDRP wizard window and select "Convert Selected Built-in Materials to HDRP".

https://lethal.wiki/advanced-modding/networking#why-netcode-weaver

## Modding Resources

https://lethal.wiki/

Unofficial Lethal Company Discord

## Tools used

Unity 2021.3.15f1 Personal

ILSpy
