---
title: Prélèvement de groupement dirigé par le système
description: Cette rubrique fournit une vue d’ensemble du prélèvement de groupement dirigé par le système dans Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: dca006ca00e7ff5aa3681daac713f1e93187cd9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239190"
---
# <a name="system-directed-cluster-picking"></a>Prélèvement de groupement dirigé par le système

[!include [banner](../includes/banner.md)]

Le prélèvement de groupement est un processus de prélèvement de pièces qui vous permet de sélectionner des articles pour plusieurs commandes en même temps en les regroupant en groupements de prélèvements. Vous devez ensuite visiter le lieu de prélèvement une seule fois. En règle générale, cette fonctionnalité est utilisée avec la préparation de petites commandes ou des quantités inférieures aux quantités de dossiers.

Lorsque le prélèvement de groupement dirigé par le système est configuré, vous pouvez sélectionner des tâches de prélèvement de groupement, en fonction d’un prélèvement généré par le système. Les prélèvements de groupement système sélectionne les commandes jusqu’au nombre de postes spécifié dans le profil de groupement. Par conséquent, vous pouvez prélever plusieurs commandes en même temps sans avoir à créer manuellement un groupement.

Le prélèvement de groupement dirigé par le système offre une alternative à la création manuelle de groupement, où un profil de groupement est utilisé pour créer un groupement. Plusieurs lignes liées à la configuration doivent être définies dans le profil de groupement avant son utilisation :

- Le **Nombre de postes** correspond au nombre de commandes qui seront placées sur un groupement. Il correspond donc au nombre de chariots.
- **Rompre le groupement** détermine quand le groupement doit être rompu.
- **Générer un ID de groupement** contrôle si l’ID groupement sera généré par le système ou saisi par l’utilisateur.
- **Trier le type de vérification** détermine si la vérification de poste est requise.

Un nouvel élément de menu d’appareil mobile est utilisé pour le prélèvement de groupement dirigé par le système. L’**ID profil de groupement** doit être spécifié pour l’option **Dirigé par**. En outre, les requêtes de séquence de travail dirigées par le système peuvent regrouper les ordres en fonction de critères spécifiques à l’entreprise. Par conséquent, vous pouvez optimiser davantage l’affectation des ordres de travail en spécifiant des critères de tri personnalisés à l’aide des requêtes de séquence de travail dirigées par le système.

Lorsque le prélèvement de groupement dirigé par le système est activé, les collaborateurs de l’entrepôt se voient présenter un groupement dans lequel les ordres de prélèvement ont été préaffectés aux postes du groupement. Par conséquent, les employés peuvent commencer à prélever un article pour plusieurs ordres de travail en visitant le lieu de prélèvement une seule fois. Le processus de prélèvement pour le prélèvement de groupement dirigé par le système est le même que le processus de prélèvement de groupement dirigé par l’utilisateur.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Activer la fonction de prélèvement de groupement dirigé par le système

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de la page de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. La fonctionnalité est répertoriée comme suit :

- **Module** - Gestion des entrepôts
- **Nom de la fonctionnalité** - Prélèvement de groupement dirigé par le système

Cette fonctionnalité nécessite également d’activer une fonctionnalité dépendante. La fonctionnalité dépendante est :

- **Module** - Gestion des entrepôts
- **Nom de la fonctionnalité** - Séquençage du travail dirigé par le système à l’échelle de l’organisation

## <a name="set-up-system-directed-cluster-picking"></a>Paramétrage du prélèvement de groupement dirigé par le système

### <a name="create-cluster-profiles"></a>Création de profils de groupement

Les profils de groupement contrôlent la façon dont le système crée chaque groupement. Si différents groupements sont requis, un profil de groupement différent doit être créé pour chaque élément de menu de l’appareil mobile.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **ID de profil de groupement**, entrez **2 Poste**.
4. Dans le champ **Nom**, entrez **2 Poste**.
5. Dans le raccourci **Général**, entrez les informations suivantes :

    - **Générer un ID de cluster** - Sélectionnez **Oui**. Cette option détermine si l’ID de groupement est créé automatiquement par le système ou si l’utilisateur le créera au début du prélèvement. 
    - **Activer les postes** - Sélectionnez **Oui**. Cette option détermine si les noms de poste sont générés automatiquement en fonction de la configuration du nom de poste. Si cette option est définie sur **Non**, l’ID contenant du poste est utilisé.
    - **Nombre de postes** - Sélectionnez **2**. Ce champ détermine le nombre maximal de postes que le groupement peut avoir (c’est-à-dire le nombre maximal de boîtes, de chariots, etc.).
    - **Nom du poste** - Sélectionnez **Numérique**, afin que les postes soient nommés à l’aide de nombres continus. Si vous sélectionnez **Alphabétique**, les postes sont nommés par ordre alphabétique.
    - **Rompre le groupement à** - Sélectionnez **Placer**. Ce champ détermine le moment où le groupement est rompu. 
    - **Trier le type de vérification** - Sélectionnez **Analyse de position**. Ce champ détermine si l’étape de mise en position est vérifiée.
        
6. Sur l’organisateur **Tri de groupement**, vous pouvez définir des critères de tri en créant une ligne et en entrant les informations suivantes :

    - **Numéro de séquence** - Sélectionnez **1**. Ce champ détermine la séquence de tri du système. Une valeur est entrée automatiquement, mais vous pouvez la modifier si nécessaire.
    - **Nom du champ** - Saisissez **WMSLocationId**. Ce champ détermine le champ que la ligne utilise pour les critères de tri.
    - **Tri** - Sélectionnez **Ascendant**. Ce champ définit si le tri est effectué par ordre croissant ou décroissant.

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d’appareil mobile

Pour créer un élément de menu d’appareil mobile pour le prélèvement de groupement dirigé par le système et lier l’ID de profil de groupement à l’élément de menu d’appareil mobile, procédez comme suit.

1. Accédez à **Gestion des entrepôts > Paramétrage > Appareil mobile > Options de menu d’appareil mobile**.
1. Sélectionnez **Nouveau**.
1. Dans la section d’en-tête, entrez les informations suivantes :
    - **Nom de l’option de menu** - Groupement SD
    - **Titre** - Groupement SD
    - **Mode** - Travail
    - **Utiliser un travail existant** - Oui

1. Dans le raccourci **Général**, entrez les informations suivantes :
    - **Dirigé par** - Prélèvement de groupement dirigé par le système
    - **Générer un contenant** - Oui
    - **ID de profil de groupement** - 2 postes

1. Sur l’organisateur **Classes de travail**, configurez la classe de travail valide pour cet élément de menu d’appareil mobile en définissant les champs suivants :
    - **ID classe de travail** - Vente
    - **Type d’ordre de travail** - Commandes client

1. Dans le volet d’action **Options de menu d’appareil mobile**, sélectionnez **Requêtes de séquence de travail dirigées par le système** et suivez ces étapes pour spécifier une nouvelle requête de séquence de travail dirigée par le système :
    - Dans le volet Actions, sélectionnez **Nouveau**.
    - **Numéro de séquence** - 1
    - **Description** - Priorité du travail – ID du travail

1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Sélectionnez l’onglet **Tri**.
1. Sélectionnez **Ajouter** pour ajouter une nouvelle ligne, puis entrez les informations suivantes :
    - **Table** - Travail
    - **Table dérivée** - Travail
    - **Champ** - Priorité du travail
    - **Direction de recherche** - Ascendant
1. Sélectionnez **Ajouter** pour ajouter une deuxième ligne, puis entrez les informations suivantes :
    - **Table** - Travail
    - **Table dérivée** - Travail
    - **Champ** - ID du travail
    - **Direction de recherche** - Ascendant

1. Le système va maintenant trier les ID travail dans le groupement, d’abord par priorité de travail, puis par ID travail.

### <a name="set-up-a-mobile-device-menu"></a>Configurer un menu d’appareil mobile

1. Accédez à **Gestion des entrepôts > Paramétrage > Appareil mobile > Menu d’appareil mobile**.
1. Ajoutez l’option de menu **Groupement SD** que vous venez de créer à un menu Appareil mobile.
1. Sélectionnez le menu **Sortant**.
1. Sélectionnez **Modifier** dans le volet Actions.
1. Faites défiler jusqu’à ce que vous trouviez **Groupement SD**.
1. Sélectionnez **Groupement SD**, la flèche pointant vers la **Structure du menu** sera activée.
1. Sélectionnez le bouton en forme de **flèche** pour déplacer l’option de menu **Groupement SD** vers la structure de menu **Sortant**.
1. Sélectionnez **Groupement SD** dans la liste **Structure du menu**, puis sélectionnez les flèches **HAUT** ou **BAS** pour déplacer l’option de menu dans la position souhaitée sur le menu de l’appareil mobile.

## <a name="scenario"></a>Scénario

### <a name="create-picking-work"></a>Création de tâches de prélèvement

Avant de pouvoir configurer le prélèvement de groupement dirigé par le système, vous devez créer un travail sortant éligible. Le profil de groupement créé précédemment spécifie deux positions de groupement. Par conséquent, vous devez créer au moins deux ID travail. Dans ce scénario, vous allez créer deux commandes client, réserver le stock, envoyer les commandes client à l’entrepôt, puis traiter manuellement la vague.

1. Accédez à **Ventes et marketing > Commandes client > Toutes les commandes client**.
1. Sélectionnez **Nouveau** dans le volet Actions pour créer la première commande client.
    - Le menu **Créer une commande client** s’ouvre ; entrez les informations suivantes :
        - Dans le raccourci **Client**, entrez **Compte client** - **US-004**.
        - Dans le raccourci **Général**, entrez **Entrepôt** - **62**.
        - Sélectionnez **OK** pour fermer le menu et créer la commande client.
    - Dans le raccourci **Lignes de commande client**, sélectionnez **Ajouter une ligne** si aucune nouvelle ligne n’est ajoutée automatiquement et entrez les informations suivantes :
        - **Numéro d’article** - A0001
        - **Quantité** - 1
        - Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne.
        - **Numéro d’article** - A0002
        - **Quantité** - 3
    - Réservez le stock pour les deux lignes que vous venez de créer.
        - Sélectionnez **Ligne 1**.
        - Dans le volet Actions **Lignes de commande client**, sélectionnez **Stock**, puis **Réservation** dans la liste.
        - Dans le formulaire **Réservation**, sélectionnez **Réserver un lot** pour réserver le stock.
        - Fermez le formulaire **Réservation** une fois la réservation terminée.
        - Répétez ces étapes pour réserver le stock pour **Ligne 2**.
1. Sélectionnez **Nouveau** dans le volet Actions pour créer la deuxième commande client.
    - Le menu **Créer une commande client** s’ouvre ; entrez les informations suivantes :
        - Dans le raccourci **Client**, entrez **Compte client** - **US-005**.
        - Dans le raccourci **Général**, entrez **Entrepôt** - **62**.
        - Sélectionnez **OK** pour fermer le menu et créer la commande client.
    - Dans le raccourci **Lignes de commande client**, sélectionnez **Ajouter une ligne** si aucune nouvelle ligne n’est ajoutée automatiquement et entrez les informations suivantes :
        - **Numéro d’article** - A0001
        - **Quantité** - 4
        - Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne.
        - **Numéro d’article** - A0002
        - **Quantité** - 2
    - Réservez le stock pour les deux lignes que vous venez de créer.
        - Sélectionnez **Ligne 1**.
        - Dans le volet Actions **Lignes de commande client**, sélectionnez **Stock**, puis **Réservation** dans la liste.
        - Dans le formulaire **Réservation**, sélectionnez **Réserver un lot** pour réserver le stock.
        - Fermez le formulaire **Réservation** une fois la réservation terminée.
        - Répétez ces étapes pour réserver le stock pour **Ligne 2**.
    - Fermez la commande client et revenez sur la page de liste **Toutes les commandes client**.
1. Recherchez les deux commandes client que vous venez de créer (vous devrez peut-être actualiser la page). Dans le tableau, sélectionnez les deux commandes client à l’aide de la coche de section.
    - Dans le volet Actions **Toutes les commandes client**, sélectionnez l’onglet **Entrepôt**.
    - Dans le groupe **Actions**, sélectionnez **Lancement dans l’entrepôt** pour envoyer les deux commandes client à l’entrepôt.
1. Une fois le processus d’envoi à l’entrepôt terminé, un message d’information s’affiche.
    - Des expéditions seront créées pour chaque commande client.
    - Une vague sera créée et les deux expéditions y seront affectées. Prenez note de l’**ID du travail**.
1. Accédez à **Gestion des entrepôts > Vagues sortantes > Vagues d’expédition > Toutes les vagues**.
    - Dans la liste **Toutes les vagues**, recherchez et sélectionnez l’**ID de vague** que vous avez créé à l’étape précédente.
    - Dans le volet Actions, sélectionnez l’onglet **Vague**.
    - Dans le groupe **Vague**, sélectionnez **Processus** pour traiter la vague et créer le **Travail**.
    - Des messages d’information seront générés une fois le traitement terminé, indiquant que le travail a été créé et que la vague a été publiée.
1. **Facultatif** : accédez à **Gestion d’entrepôt > Travail > Détails du travail** pour voir le travail créé. Deux ID travail différents sont créés. Chaque ID travail a deux lignes de prélèvement.

### <a name="run-the-mobile-device-flow"></a>Exécuter le flux de l’appareil mobile

1. connectez-vous à l’appareil mobile pour un utilisateur dans l’entrepôt **62**.
1. Dans le **Menu principal**, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Groupement SD** pour lancer le prélèvement.
    - Un groupement est créé et les deux ID travail créés précédemment lui sont associés. Si vous avez créé plus de deux ID travail, seuls les deux premiers sont ajoutés au groupement. Notez que les ID travail sont ajoutés au groupement par ordre croissant, comme vous l’avez spécifié dans la configuration de la requête.

    > [!NOTE]
    > Le nouveau groupement est automatiquement créé uniquement si suffisamment d’ID travail supplémentaires ont été créés précédemment. Sinon, le message suivant s’affiche : « Le groupement contient un nombre insuffisant de tâches. »

    - Après avoir sélectionné le menu, le premier écran de prélèvement apparaît. Le système regroupe toutes les lignes de prélèvement correspondantes à partir des deux ID travail et vous invite à visiter le lieu de prélèvement une fois, afin que vous puissiez satisfaire les deux commandes en utilisant un seul prélèvement. Ce processus est effectué de la même manière que le processus de prélèvement de groupement dirigé par l’utilisateur.

1. Confirmez le premier lieu du prélèvement et le premier article en sélectionnant **OK**.
    - La quantité du prélèvement sera le total de l’article affiché sur les commandes client du groupement.
1. Saisissez le nom du poste (numérique ou alphabétique) pour confirmer que la quantité d’articles sélectionnée pour le poste a été placée au bon endroit.
1. Répétez ce processus jusqu’à ce que toutes les quantités d’articles aient été prélevées et placées dans la bonne position.
1. La dernière étape sur l’appareil mobile consiste à **Placer** le groupement à l’emplacement final. Cliquez sur **OK**.
    - Lorsque l’opération de placement est confirmée, le groupement est fermé et rompu, en fonction de la valeur que vous avez définie pour le champ **Rompre le groupement à** dans le profil de groupement. Les ID travail sont également fermés.
1. Un message « Groupement terminé » s’affiche sur l’appareil mobile.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]