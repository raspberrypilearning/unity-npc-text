Voeg een Box Collider met 'Is Trigger' aangevinkt toe aan het NPC GameObject.

Klik met de rechtermuisknop op je NPC GameObject in het Hierarchy venster en voeg een 'UI' 'Text - TextMeshPro' toe. Als dit de eerste keer is dat je TextMeshPro gebruikt in dit project, wordt je gevraagd om assets toe te voegen aan je project.

Als je een TextMeshPro toevoegt, wordt ook een Canvas als container toegevoegd.

Selecteer de TextMeshPro en voeg het bericht toe dat je wil weergeven in de Inspector.

Zorg ervoor dat het Player GameObject de Player-tag heeft.

Voeg code toe aan een script op het NPC GameObject.

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


Sleep het Canvas GameObject vanuit het Hierarchy venster naar de Canvas-eigenschap van het script in de Inspector voor je NPC GameObject.

**Test:** Speel je scène en zorg ervoor dat de tekst verschijnt wanneer de speler in de buurt van de NPC loopt (en de botsingen veroorzaakt) en verdwijnt wanneer deze buiten het botsingsveld beweegt.

Het is een goed idee om nog een kleinere collider aan je NPC toe te voegen, zodat je personage er niet doorheen kan lopen.

**Tip:** Als je meerdere NPC's hebt die een tekstbericht weergeven wanneer de speler met hen botst, dan kun je hetzelfde script gebruiken voor alles. Sleep het 'NPCText'-script van de projectweergave naar de NPC GameObjects in de Hierarchy of Inspector-vensters. 
