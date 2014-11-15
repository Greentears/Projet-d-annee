Projet-d-annee
==============
def inputdata():
    informedPeople = [False]
    nom_pers = []
    network = []
    nbr_pers_res = int(input("Veuillez entrer le nombre de personnes : "))
    for pers in range(1,nbr_pers_res+1):
        if pers == 1:
            nom_pers.append(input("Veuillez entrer le nom de la première" + \
            " personne : "))
        else:
            nom_pers.append(input("Veuillez entrer le nom de la " + \
            str(pers) + " ième personne : "))
            informedPeople.append('False')
    for ami in range(nbr_pers_res-1):
        for pote in range(1,nbr_pers_res):
            if nom_pers[ami] != nom_pers[pote] and pote >= ami:
                copain = (int(input(nom_pers[ami] + " et " + \
                nom_pers[pote] + " sont-ils amis" +  \
                "(1 pour oui et 0 pour non) ? : ")))
                if copain == 0:
                    network[ami][pote] = 'False'
                    network[pote][ami] = 'False'
                elif copain == 1:
                    network[ami][pote] = 'True'
                    network[pote][ami] = 'True'
    print(network)
print(inputdata())
