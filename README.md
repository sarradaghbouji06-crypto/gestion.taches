taches = []


def ajouter_tache():
    titre = input("Titre de la tâche : ")
    if titre.strip() == "":
        print("Erreur : le titre ne peut pas être vide.")
    else:
        taches.append(titre)
        print("Tâche ajoutée avec succès.")


def afficher_taches():
    if len(taches) == 0:
        print("Aucune tâche dans la liste.")
    else:
        for i in range(len(taches)):
            print(i + 1, "-", taches[i])


def rechercher_tache():
    mot = input("Mot-clé à rechercher : ")
    trouve = False
    for i in range(len(taches)):
        if mot.lower() in taches[i].lower():
            print(i + 1, "-", taches[i])
            trouve = True
    if not trouve:
        print("Aucune tâche trouvée.")


choix = ""
while choix != "0":
    print("\n=== GESTION DES TÂCHES ===")
    print("1. Ajouter une tâche   2. Afficher   3. Rechercher   0. Quitter")
    choix = input("Votre choix : ")

    if choix == "1":
        ajouter_tache()
    elif choix == "2":
        afficher_taches()
    elif choix == "3":
        rechercher_tache()
    elif choix == "0":
        print("Au revoir !")
    else:
        print("Erreur : choix invalide.")