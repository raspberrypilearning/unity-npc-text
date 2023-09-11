Add a Box Collider with 'Is Trigger' checked to the NPC GameObject.

Right-click on your NPC GameObject in the Hierarchy window and add a 'UI' 'Text - TextMeshPro'. If this is the first time you are using TextMeshPro in this project, you will be prompted to add assets to your project.

Adding a TextMeshPro will also add a Canvas as a container.

Select the TextMeshPro and add the message you want to display in the Inspector.

Make sure the Player GameObject has the Player tag.

Add code to a script on the NPC GameObject.

--- code ---
---
language: cs
---

    public GameObject canvas;
    
    void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Player"))
        {
            canvas.SetActive(true);
        }
    }
    
    void OnTriggerExit(Collider other)
    {
        if (other.CompareTag("Player"))
        {
            canvas.SetActive(false);
        }
    }
--- /code ---


Drag the Canvas GameObject from the Hierarchy window into the Canvas property of the script in the Inspector for your NPC GameObject.

**Test:** Play your scene and make sure the text appears when the Player walks close to the NPC (and triggers the collider) and disappears when it moves outside the collision box.

It's a good idea to add another smaller collider to your NPC so your character can't walk through them.

**Tip:** If you have multiple NPCs that will display a text message when the Player collides with them, then you can use the same script for all of them. Just drag the 'NPCText' script from the Project view to the NPC GameObjects in the Hierarchy or Inspector windows. 
