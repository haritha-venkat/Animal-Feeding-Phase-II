# Animal-Feeding-Phase-II

# Aim:

To develop a animal feeding game-Phase-2 using unity.

# Algorithm:
## Random Animal Stampede
### Step 1: In the Hierarchy, create an Empty object called “SpawnManager”
### Step 2: Create a new script called “SpawnManager”, drag the script and attach it to the Spawn Manager in the hierarchy , and open it
### Step 3: Declare new public GameObject[ ] animalPrefabs;
### Step 4: In the inspector assign the size as 3 , for each element drag the animals from prefabs folder into the array

## Collision Decisions
### Step 1: Double-click on one of the animal prefabs, then Add Component > Box Collider
### Step 2: Click Edit Collider, then drag the collider handles to encompass the object
### Step 3: Check the “Is Trigger” checkbox
### Step 4: Repeat this process for each of the animals and the projectile
### Step 5: Add a RigidBody component to the (pizza)projectile and uncheck “use gravity”.
### Step 6: Create a new DetectCollisions.cs script, then drag the scripts and add it to each animal prefab and pizza, then open it and check it.
### Step 7: For all the animal prefabs and food in th inspector (below the  layer ) drop down the override option and choose apply all.

# Program:

## Spawm Manager:
```python
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpamManager : MonoBehaviour
{
    public GameObject[] animalPrefabs;
    private float spamRangeX = 20;
    private float spamPosZ = 20;
    private float startDelay = 2;
    private float spamInterval = 1.5f;
    // Start is called before the first frame update
    void Start()
    {
        InvokeRepeating("SpamRandomAnimal", startDelay, spamInterval);
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    void SpamRandomAnimal()
    {
        int animalIndex = Random.Range(0, animalPrefabs.Length);
        Vector3 spamPos = new Vector3(Random.Range(-spamRangeX, spamRangeX), 0, spamPosZ);
        Instantiate(animalPrefabs[animalIndex], spamPos, animalPrefabs[animalIndex].transform.rotation);
    }
}
```

## Detectcollider:
```python
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DetectCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {

    }
    private void OnTriggerEnter(Collider other)
    {
        Destroy(gameObject);
        Destroy(other.gameObject);
    }
}
```


## Output:

![image](https://github.com/haritha-venkat/Animal-Feeding-Phase-II/assets/121285701/1280e3d1-fb8a-4b59-b7c2-aed839359794)

## Result:

Animal feeding game-Phase-2 using unity is developed successfully.



