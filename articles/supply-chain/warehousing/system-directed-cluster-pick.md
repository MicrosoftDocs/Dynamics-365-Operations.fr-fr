---
title: Prélèvement de groupement dirigé par le système
description: Cette rubrique fournit une vue d'ensemble du prélèvement de groupement dirigé par le système dans Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 390e0a3379a6482e99a13f4f7835b5264e3747ac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217239"
---
# <a name="system-directed-cluster-picking"></a>Prélèvement de groupement dirigé par le système

[!include [banner](../includes/banner.md)]

Le prélèvement de groupement est un processus de prélèvement de pièces qui vous permet de sélectionner des articles pour plusieurs commandes en même temps en les regroupant en groupements de prélèvements. Vous devez ensuite visiter le lieu de prélèvement une seule fois. En règle générale, cette fonctionnalité est utilisée avec la préparation de petites commandes ou des quantités inférieures aux quantités de dossiers.

Lorsque le prélèvement de groupement dirigé par le système est configuré, vous pouvez sélectionner des tâches de prélèvement de groupement, en fonction d'un prélèvement généré par le système. Les prélèvements de groupement système sélectionne les commandes jusqu'au nombre de postes spécifié dans le profil de groupement. Par conséquent, vous pouvez prélever plusieurs commandes en même temps sans avoir à créer manuellement un groupement.

Le prélèvement de groupement dirigé par le système offre une alternative à la création manuelle de groupement, où un profil de groupement est utilisé pour créer un groupement. Plusieurs lignes liées à la configuration doivent être définies dans le profil de groupement avant son utilisation :

- Le **Nombre de postes** correspond au nombre de commandes qui seront placées sur un groupement. Il correspond donc au nombre de chariots.
- **Rompre le groupement** détermine quand le groupement doit être rompu.
- **Générer un ID de groupement** contrôle si l'ID groupement sera généré par le système ou saisi par l'utilisateur.
- **Trier le type de vérification** détermine si la vérification de poste est requise.

Un nouvel élément de menu d'appareil mobile est utilisé pour le prélèvement de groupement dirigé par le système. L'ID de profil de groupement doit être spécifié pour l'option **Dirigé par**. En outre, l'ordre de requête dirigé par le système peut regrouper les commandes en fonction de critères spécifiques à l'entreprise. Par conséquent, vous pouvez optimiser davantage l'affectation des ordres de travail en spécifiant des critères de tri personnalisés sur l'ordre de requête dirigé par le système.

Lorsque le prélèvement de groupement dirigé par le système est terminé, les employés de l'entrepôt se voient présenter un groupement dans lequel les ordres de prélèvement ont été préaffectés aux postes du groupement. Par conséquent, les employés peuvent commencer à prélever un article pour plusieurs ordres de travail en visitant le lieu de prélèvement une seule fois. Le processus de prélèvement pour le prélèvement de groupement dirigé par le système est le même que le processus de prélèvement de groupement dirigé par l'utilisateur.

## <a name="set-up-system-directed-cluster-picking"></a>Paramétrage du prélèvement de groupement dirigé par le système

### <a name="create-cluster-profiles"></a>Création de profils de groupement

Les profils de groupement contrôlent la façon dont le système crée chaque groupement. Si différents groupements sont requis, un profil de groupement différent doit être créé pour chaque élément de menu de l'appareil mobile.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **ID de profil de groupement**, entrez **2 Poste**.
4. Dans le champ **Nom**, entrez **2 Poste**.
5. Dans l'organisateur **Général**, définissez les champs suivants :

    - **Générer un ID de groupement :** Définissez cette option sur **Oui**. Cette option détermine si l'ID de groupement est créé automatiquement par le système ou si l'utilisateur le créera au début du prélèvement.
    - **Activer les postes :** Définissez cette option sur **Oui**. Cette option détermine si les noms de poste sont générés automatiquement en fonction de la configuration du nom de poste. Si cette option est définie sur **Non**, l'ID contenant du poste est utilisé.
    - **Nombre de postes :** Entrez **2**. Ce champ détermine le nombre maximal de postes que le groupement peut avoir (c'est-à-dire le nombre maximal de boîtes, de chariots, etc.).
    - **Nom du poste :** Sélectionnez **Numérique**, afin que les postes soient nommés à l'aide de nombres continus. Si vous sélectionnez **Alphabétique**, les postes sont nommés par ordre alphabétique.
    - **Rompre le groupement à :** Sélectionnez **Placer**. Ce champ détermine le moment où le groupement est rompu.
    - **Trier le type de vérification :** Sélectionnez **Analyse de position**. Ce champ détermine si l'étape de mise en position est vérifiée.

6. Sur l'organisateur **Tri de groupement**, vous pouvez définir des critères de tri en créant une ligne et en définissant les champs suivants :

    - **Numéro de séquence :** Ce champ détermine la séquence de tri du système. Une valeur est entrée automatiquement, mais vous pouvez la modifier selon vos besoins.
    - **Nom du champ :** Sélectionnez **WMSLocationId**. Ce champ détermine le champ que la ligne utilise pour les critères de tri.
    - **Tri :** Sélectionnez **Ascendant**. Ce champ définit si le tri est effectué par ordre croissant ou décroissant.

### <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile

Pour créer un élément de menu d'appareil mobile pour le prélèvement de groupement dirigé par le système et lier l'ID de profil de groupement à l'élément de menu d'appareil mobile, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom de l'élément de menu**, entrez **Groupement SD**.
4. Dans le champ **Titre**, entrez **Groupement SD**.
5. Dans le champ **Mode**, sélectionnez **Travail**.
6. Définissez l'option **Utiliser un travail existant** sur **Oui**.
7. Dans l'organisateur **Général**, définissez les champs suivants :

    - **Dirigé par :** Sélectionnez **Dirigé par le système**.
    - **Générer un contenant :** Définissez cette option sur **Oui**.
    - **ID de profil de groupement :** Sélectionnez **2 Poste**.

8. Sur l'organisateur **Classes de travail**, configurez la classe de travail valide pour cet élément de menu d'appareil mobile en définissant les champs suivants :

    - **ID classe de travail :** Vérifiez que **Ventes** est saisi.
    - **Type d'ordre de travail :** Vérifiez que **Commandes client** est saisi.

9. Suivez ces étapes pour spécifier une nouvelle requête de séquence de travail dirigée par le système :

    1. Sélectionnez **Nouveau**.
    2. Dans le champ **Souche de N°**, saisissez **1**.
    3. Dans le champ **Description**, sélectionnez **Priorité de travail - ID de travail**.

10. Dans le menu, sélectionnez **Modifier la requête**.
11. Sous l'onglet **Tri**, paramétrez les champs suivants :

    - **Table :** Sélectionnez **Travail**.
    - **Table dérivée :** Sélectionnez **Travail**.
    - **Champ :** Sélectionnez **Priorité du travail**.
    - **Ordre de tri :** Sélectionnez **Ascendant**.
    - **Table :** Sélectionnez **Travail**.
    - **Table dérivée :** Sélectionnez **Travail**.
    - **Champ :** Sélectionnez **ID travail**.
    - **Ordre de tri :** Sélectionnez **Ascendant**.

Le système va maintenant trier les ID travail dans le groupement, d'abord par priorité de travail, puis par ID travail.

### <a name="set-up-a-mobile-device-menu"></a>Configurer un menu d'appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.
2. Ajoutez l'option de menu que vous venez de créer au menu souhaité.

## <a name="example"></a>Exemple

### <a name="create-picking-work"></a>Création de tâches de prélèvement

Avant de pouvoir configurer le prélèvement de groupement dirigé par le système, vous devez créer des travaux sortants éligibles. Le profil de groupement créé précédemment spécifie deux positions de groupement. Par conséquent, vous devez créer au moins deux ID travail.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez **Nouveau** pour créer une commande client.
3. Sélectionnez un client dans le champ **Compte client**.
4. Dans l'organisateur **Général**, dans le champ **Entrepôt**, sélectionnez l'entrepôt **62**.
5. Cliquez sur **OK**.
6. Dans l'organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne**.
7. Dans le champ **Numéro d'article**, sélectionnez **A0001**.
8. Dans le champ **Quantité**, entrez **1**.
9. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne.
10. Dans le champ **Numéro d'article**, sélectionnez **A0002**.
11. Dans le champ **Quantité**, entrez **3**.
12. Répétez les étapes 2 à 6.
13. Dans le champ **Numéro d'article**, sélectionnez **A0001**.
14. Dans le champ **Quantité**, entrez **4**.
15. Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne.
16. Dans le champ **Numéro d'article**, sélectionnez **A0002**.
17. Dans le champ **Quantité**, entrez **2**.

Réservez l'inventaire et remettez-le à l'entrepôt. Deux ID travail différents sont créés. Chaque ID travail a deux lignes de prélèvement.

### <a name="run-the-mobile-device-flow"></a>Exécuter le flux de l'appareil mobile

1. Sur l'appareil mobile, sélectionnez le menu qui inclut la nouvelle option de menu appareil mobile.
2. Sélectionnez l'élément de menu **Groupement SD** et lancez le prélèvement. Un groupement est créé et les deux ID travail créés précédemment lui sont associés. Si vous avez créé plus de deux ID travail, seuls les deux premiers sont ajoutés au groupement. Notez que les ID travail sont ajoutés au groupement par ordre croissant, comme vous l'avez spécifié dans la configuration de la requête.

    > [!NOTE]
    > Le nouveau groupement est automatiquement créé uniquement si suffisamment d'ID travail supplémentaires ont été créés précédemment. Sinon, le message suivant s'affiche : « Le groupement contient un nombre insuffisant de tâches. »

    Après avoir sélectionné le menu, le premier écran de prélèvement apparaît. Le système regroupe toutes les lignes de prélèvement correspondantes à partir des deux ID travail et vous invite à visiter le lieu de prélèvement une fois, afin que vous puissiez satisfaire les deux commandes en utilisant un seul prélèvement. Ce processus est effectué de la même manière que le processus de prélèvement de groupement dirigé par l'utilisateur.

3. Confirmez le premier prélèvement. Vous devez ensuite entrer le nom du poste pour confirmer que les articles ont été placés à la bonne position.
4. Répétez ce processus jusqu'à ce que tous les articles aient été prélevés et placés dans la bonne position.
5. La dernière étape sur l'appareil mobile consiste à placer le groupement à l'emplacement final. Lorsque cette opération de placement est confirmée, le groupement est fermé et rompu, en fonction de la valeur que vous avez définie pour le champ **Rompre le groupement à** dans le profil de groupement. Les ID travail sont également fermés.
6. Un message « Groupement terminé » s'affiche sur l'appareil mobile.
