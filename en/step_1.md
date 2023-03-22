This script changes the material of the ball GameObject to the material on the GameObject it collides with.

Add the script to all of the GameObjects that should change material when the player collides with them.  

--- code ---
---
language: cs
filename: MaterialController.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MaterialController : MonoBehaviour
{
  Material start;
  Renderer rend;

  // Start is called before the first frame update
  void Start()
  {
      rend = GetComponent<Renderer>();
      start = rend.sharedMaterial;
  }

  void OnCollisionEnter(Collision collision)
  {
      if (collision.gameObject.tag == "Player"){
          rend.sharedMaterial = collision.gameObject.GetComponent<Renderer>().sharedMaterial;
      }
  }
