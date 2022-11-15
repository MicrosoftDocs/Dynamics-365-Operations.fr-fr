---
title: Affecter des listes de tâches aux magasins ou aux employés
description: Cet article décrit comment affecter des listes de tâches à des magasins ou des employés dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.openlocfilehash: faff772051738f624b86fd23fb6bf29173e909ea
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746192"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Affecter des listes de tâches aux magasins ou aux employés

[!include [banner](includes/banner.md)]

Cet article décrit comment affecter des listes de tâches à des magasins ou des employés dans Microsoft Dynamics 365 Commerce.

La gestion des tâches dans Dynamics 365 Commerce vous permet d’affecter une liste de tâches à plusieurs magasins ou employés, ou à une combinaison de magasins et d’employés. Par exemple, un responsable régional de 20 magasins peut être amené à affecter la liste de tâches **Préparation de la période des fêtes** à tous les 20 magasins.

## <a name="start-the-task-list-assignment-process"></a>Démarrer le processus d’affectation de la liste de tâches

Avant de commencer le processus d’affectation de tâches, assurez-vous d’avoir créé une liste de tâches en suivant les étapes décrites dans l’article [Créer des listes de tâches et ajouter des tâches](task-mgmt-create-lists.md). Pour démarrer le processus d’affectation d’une liste de tâches, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.
1. Sélectionnez la liste de tâches à affecter.
1. Sélectionnez **Démarrer le processus**.
1. Dans la boîte de dialogue **Démarrer le processus**, sous l’onglet **Général**, dans le champ **Nom du processus**, entrez un nom (par exemple, **Magasins de la région Est**).
1. Dans le champ **Date cible**, spécifiez une date.
1. Pour affecter la liste de tâches aux magasins, sous l’onglet **Magasins**, utilisez le filtre **Hiérarchie d’organisation** pour rechercher et sélectionner les magasins.

    Pour affecter la liste de tâches aux employés, sous l’onglet **Collaborateurs**, recherchez et sélectionnez les employés.

1. Sélectionnez **OK** pour démarrer le processus. La liste de tâches est affectée aux magasins ou employés sélectionnés.

L’illustration suivante présente un exemple de recherche et de sélection de magasins dans la boîte de dialogue **Démarrer le processus**.

![Recherche et sélection de magasins dans la boîte de dialogue Démarrer le processus.](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Affecter des listes de tâches de façon récurrente

Les détaillants ont parfois des tâches récurrentes, comme « Liste de contrôle pour la fermeture du jeudi » ou « Liste de contrôle pour le premier jour du mois ». Par conséquent, ils peuvent être amenés à affecter la liste de tâches de façon récurrente.

1. Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.
1. Sélectionnez la liste de tâches à affecter.
1. Sélectionnez **Démarrer le processus**.
1. Dans la boîte de dialogue **Démarrer le processus**, sous l’onglet **Général**, dans le champ **Nom du processus**, entrez un nom.
1. Définissez l’option **Récurrence** sur **Oui**.
1. Dans le champ **Décalage de la date cible de récurrence en jours**, entrez un nombre de jours. Par exemple, si vous entrez **4**, la date cible correspond à la date de récurrence plus quatre jours.
1. Sous l’onglet **Exécuter en arrière-plan**, sélectionnez **Récurrence**.
1. Dans la boîte de dialogue **Définir la récurrence**, entrez les critères de fréquence, puis sélectionnez **OK**.

L’illustration suivante présente un exemple de saisie des critères de fréquence dans la boîte de dialogue **Définir la récurrence**.

![Saisie des critères de fréquence dans la boîte de dialogue Définir la récurrence.](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Suivre le statut de la liste de tâches

Si vous êtes un directeur régional ou un responsable de magasin, vous pouvez être amené à suivre le statut des listes de tâches qui ont été affectées à plusieurs magasins ou employés. Vous pouvez ensuite effectuer le suivi des magasins ou des employés qui n’ont pas terminé les tâches qui leur ont été affectées dans les délais. Le back-office Commerce vous permet d’afficher le statut des listes de tâches, de réaffecter des tâches ou de modifier le statut d’une tâche.

Pour suivre le statut de la liste de tâches pour toutes les tâches, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Gestion des tâches \> Processus de gestion des tâches**.
1. Sélectionnez l’onglet **Toutes les listes de tâches** pour afficher le statut de toutes les listes de tâches affectées à différents magasins.

Pour suivre le statut de la liste de tâches pour toutes les tâches qui vous sont affectées, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Gestion des tâches \> Processus de gestion des tâches**.
1. Sélectionnez l’onglet **Mes tâches** ou **Toutes les tâches** pour afficher ou mettre à jour le statut des tâches qui vous sont affectées.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la gestion des tâches](task-mgmt-overview.md)

[Configurer la gestion des tâches](task-mgmt-configure.md)

[Créer des listes de tâches et ajouter des tâches](task-mgmt-create-lists.md)

[Gestion des tâches dans le PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
