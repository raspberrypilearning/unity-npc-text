Ajoute au GameObject PNJ un « Box Collider » dont la case « Is Trigger » est cochée.

Fais un clic droit sur ton GameObject PNJ dans la fenêtre Hierarchy et ajoute un « UI » « Text - TextMeshPro ». Si c'est la première fois que tu utilises TextMeshPro dans ce projet, tu seras invité à ajouter des assets à ton projet.

L'ajout d'un TextMeshPro entraîne également l'ajout d'un Canvas comme conteneur.

Sélectionne le TextMeshPro et ajoute le message que tu veux afficher dans l'Inspector.

Assure-toi que le GameObject Joueur possède le tag « Joueur ».

Ajoute du code à un script sur le GameObject PNJ.

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


Fais glisser le GameObject Canvas de la fenêtre Hierarchy dans la propriété Canvas du script dans l'Inspector pour ton GameObject PNJ.

**Test :** joue ta scène et vérifie que le texte apparaît lorsque le joueur s'approche du PNJ (et déclenche le collider) et disparaît lorsqu'il sort de la zone de collision.

C'est une bonne idée d'ajouter un autre collider plus petit à ton PNJ pour que ton personnage ne puisse pas passer à travers.

**Astuce :** si tu as plusieurs PNJ qui afficheront un message textuel lorsque le joueur entrera en collision avec eux, alors tu peux utiliser le même script pour chacun d'entre eux. Il suffit de faire glisser le script « NPCText » de la vue Project vers les GameObjects PNJ dans les fenêtres Hierarchy ou Inspector. 
