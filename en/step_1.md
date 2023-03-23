This script changes the material of the ball GameObject to the material on the goal GameObject it collides with.

Add this script to all of the ball:  

--- code ---
---
language: cs
filename: BallMaterial.cs
line_numbers: true
line_number_start: 1
line_highlights:
---
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class BallMaterial : MonoBehaviour
{
    public Material startColour;
    Renderer rend;

    // Start is called before the first frame update
    void Start()
    {
        rend = GetComponent<Renderer>();
        rend.sharedMaterial = startColour;
    }

    void OnCollisionEnter(Collision other){
       if (other.gameObject.tag == "Goal"){
           rend.sharedMaterial = other.gameObject.GetComponent<Renderer>().material;
       	}
	}
}

--- /code ---

When you return to Unity, go to the Inspector for the ball and drag the starting material into the Start Colour.
