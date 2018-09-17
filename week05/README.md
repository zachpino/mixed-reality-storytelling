### Week 5 · Up and Running in Unity for VR

-----

![unity](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Unity_Technologies_logo.svg/600px-Unity_Technologies_logo.svg.png)

Let's spend the week digging in to Unity 3D, which is an amazing tool for creating interactive experiences. Unity3D is a combination drag-and-drop UI and coding environment, and can be very confusing. We'll take it slow this week, and cover the basics for creating interactive VR software for the Google Cardboard platform.

-----

##### Agenda 

- [Download Unity3D](#download-unity)
- [Download Google VR SDK](#download-google-vr-sdk)
- [Learn Unity VR Basics with the Google Cardboard SDK](#unity-vr-basics)
- [References](#references)
- [Homework](#homework)

-----

##### Download Unity

First – let's get a **big** download out of the way. Visit the following link to download Unity3D, the preeminent software package for videogame and interactive narrative development. 

[Unity3D](https://unity3d.com)

Sign-up first, and then download and *install* the *installer* for Unity Personal your platform. You will then need to run the installer, which will pull down lots of bits over your internet connection (probably around 10GB). You can choose to install various additional platform SDKs and compilers, though they will take up lots of hard drive space! We need to install **Android Build Support**.

-----

#### Download Google VR SDK

Download this Unity Package so we can use all of the cool things Google has already created for VR experimenters. Place it in a findable place on your machine. 

[Google VR Unity Package](https://github.com/googlevr/gvr-unity-sdk/releases)

-----

#### Unity VR Basics

We will review [this tutorial](https://docs.google.com/document/d/1zYE5O9LUL2WcxZShAwSQxk7dETCcptKSN-K1ihCeE2s/edit#) as a class today. Note that a few things are outdated (sigh...), so take notes!

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ReticleTest : MonoBehaviour {

    public void randomMove()
    {
         gameObject.transform.position = new Vector3(
             GetRandomCoordinate(), Random.Range(0.5f, 2), GetRandomCoordinate()
         );

        GetComponent<Renderer>().material.color = new Color(Random.Range(0.0f,1.0f), Random.Range(0.0f, 1.0f), Random.Range(0.0f, 1.0f));
    }

    private float GetRandomCoordinate()
    {

        var coordinate = Random.Range(-7, 7);
        while (coordinate > -1.5 && coordinate < 1.5)
        {
            coordinate = Random.Range(-5, 5);
        }
        return coordinate;
    }
}

```

-----

##### References

- [Unity Scripting API](https://docs.unity3d.com/ScriptReference/Transform.html)
- [Cardboard Developer Homepage](https://vr.google.com/cardboard/developers/)
- [Google Functional Design Guidelines](https://designguidelines.withgoogle.com/cardboard/) 

-----

##### Homework

Complete the [Roll-a-Ball](https://unity3d.com/learn/tutorials/s/roll-ball-tutorial) tutorial series on the Unity website.

If you want an additional challenge, try out this [twitter visualization tutorial](https://www.sitepoint.com/visualizing-a-twitter-stream-in-vr-with-three-js-and-node/).