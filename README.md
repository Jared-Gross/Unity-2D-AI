# Unity-2D-AI

[Demo AI.rar](https://github.com/JareBear12418/Unity-2D-AI/blob/master/Demo%20AI.rar)

[Demo AI.unitypackage](https://thecodingjsoftware.weebly.com/uploads/1/2/6/9/126914047/ai_demo_scene.unitypackage)

[Showcase Video](https://www.youtube.com/watch?v=DvLCkT96rXA)


This is a free AI for your 2D Unity games!

We know this AI is far from perfect.
We know there are plenty of issues.

But we just want to let you know of some issues that are easy to fix if they ever occur.
    1. If the AI JUMPS REALLY HIGH or doesn't JUMP at all!! Then change your gravity scale on your Rigidbody 2D.
        a. Or check your JUMP HEIGHT on the script
      
Thats really it.
But how does this AI work you may ask. Well this AI works with raycasts. It shoots out raycasts in spesific directions and check if it hits something. These raycasts can all be viewed by pressing DEBUG MODE on the script. You can also custimize the ray casts lenght/height to how ever you want, we reccomend you **dont touch the WALL LENGTH raycasts** as we set it to that magic number so everything works well. Theres really no need to change the raycasts length values, the only ones that you will need to change are the GROUND RAY CASTS and/or your follow/flee/attack ranges.

You might be wondering why we would release this AI, even if its not perfect?

"We noticed an issue in Unity game development, that issue being that theres no open source 2d AI for begginers to get started with, this is what this AI is. A free open source 2d AI for begginers or even experts. We wanted begginers to have an AI for there games, because AI is a huge and scary topic for begginers, so we took it upon our selves to create this AI that is very easy to setup, very little to no setup."

Errors, and how to fix them:
Line 148 in `BotController2D.cs` change from 
```csharp
if (obj.activeInHierarchy == true) 
    distDic.Add (dist, obj);
```

to:
```csharp
if (obj.activeInHierarchy == true && !distDic.ContainsValue (obj)) 
    distDic.Add (dist, obj);
```

That should get rid of this error:
```csharp
ArgumentException: An item with the same key has already been added. Key: 162.1331
System.Collections.Generic.Dictionary2[TKey,TValue].TryInsert (TKey key, TValue value, System.Collections.Generic.InsertionBehavior behavior) (at <599589bf4ce248909b8a14cbe4a2034e>:0)
System.Collections.Generic.Dictionary2[TKey,TValue].Add (TKey key, TValue value) (at <599589bf4ce248909b8a14cbe4a2034e>:0)
```

I am lazy and I didn't feel like updating the project.

Have more questions or bugs that we don't know about?
Join us on [Discord](https://discord.gg/EtrSc4s)
