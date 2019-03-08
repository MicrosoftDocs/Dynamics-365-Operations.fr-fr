---
title: Définir l'inventaire tournant
description: L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "337300"
---
# <a name="define-cycle-counting"></a>Définir l'inventaire tournant 

[!include [task guide banner](../../includes/task-guide-banner.md)]

L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles. Cet enregistrement de tâche indique comment paramétrer la priorité par défaut du travail d'inventaire, activer une option de menu d'appareil mobile pour traiter à la fois les opérations de prélèvement et d'inventaire, activer un déclencheur de seuil de comptage lorsqu'un emplacement devient vide et activer un plan d'inventaire tournant pour un article spécifique dans un entrepôt particulier. Ces tâches sont généralement effectuées par un gestionnaire d'entrepôt. Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.


## <a name="set-the-priority-of-counting-work"></a>Définir la priorité du travail d'inventaire
1. Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.
2. Cliquez sur l'onglet Inventaire tournant.
3. Dans le champ Priorité de travail d'inventaire tournant par défaut, entrez un nombre.
    * Cette étape modifie la priorité du travail d'inventaire tournant par rapport à d'autres types de travail dans l'entrepôt. Si vous entrez un nombre plus faible que celui pour d'autres types de travail, vous élevez la priorité du travail d'inventaire tournant.  
4. Cliquez sur Enregistrer.
5. Fermez la page.

## <a name="enable-the-mobile-device"></a>Activer l'appareil mobile
1. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Nom de l'option de menu.
4. Tapez une valeur dans le champ Titre.
5. Dans le champ Mode, Sélectionnez « Travail ».
6. Définissez l'option Utiliser un travail existant sur Oui.
    * Lorsque vous définissez cette option sur Oui, le système recherchera les travaux existants lorsque l'option de menu d'appareil mobile est utilisée.  
7. Dans le champ Dirigé par, sélectionnez « Système dirigé ».
    * Lorsque l'option « Dirigé par le système » est sélectionnée, le magasinier sera dirigé vers le travail en cours qui se trouve dans les classes de travail définies. (Nous créerons ces classes de travail par la suite.)  
8. Développez ou réduisez la section Classes de travail.
    * Ensuite, nous créerons deux classes de travail qui seront utilisées avec cette option de menu d'appareil mobile. Lorsque l'option de menu est utilisée, ces classes de travail sont interrogées, et le travail ayant la priorité la plus élevée est affiché à l'utilisateur.  
9. Cliquez sur Nouveau.
10. Dans le champ ID classe de travail, sélectionnez une valeur.
11. Cliquez sur Nouveau.
12. Dans le champ ID classe de travail, sélectionnez une valeur.
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile.
16. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
17. Dans l'arborescence, sélectionnez l'option de menu que vous venez de créer.
18. Cliquez sur Modifier.
19. Cliquez sur la flèche pour ajouter l'option de menu au menu.
20. Cliquez sur Enregistrer.

## <a name="create-a-counting-threshold"></a>Créer un seuil d'inventaire
1. Accédez à Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Seuils d'inventaire tournant.
2. Cliquez sur Nouveau.
3. Dans le champ ID seuil d'inventaire tournant, entrez une valeur.
4. Définissez l'option Traiter immédiatement l'inventaire tournant sur oui.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Enregistrer.
7. Cliquez sur Sélectionner des emplacements.
8. Dans la liste, marquez la ligne sélectionnée.
9. Sélectionnez une valeur dans le champ Critère.
10. Cliquez sur OK.
11. Fermez la page.

## <a name="create-a-cycle-count-plan"></a>Créer un plan d'inventaire tournant
1. Accédez à Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Plans d'inventaire tournant.
2. Cliquez sur Nouveau.
3. Dans le champ ID plan d'inventaire tournant, entrez une valeur.
4. Tapez une valeur dans le champ Description.
5. Dans le champ Nombre maximal d'inventaires tournants, entrez un nombre.
6. Cliquez sur Enregistrer.
7. Cliquez sur Sélectionner des emplacements.
8. Dans la liste, marquez la ligne sélectionnée.
9. Sélectionnez une valeur dans le champ Critère.
10. Cliquez sur OK.
11. Dans le champ Jours entre les inventaires tournants, entrez un nombre.
    * Par exemple, si le champ Jours entre les inventaires tournants est défini sur 5, le travail d'inventaire tournant sera créé tous les cinq jours. Toutefois, si le travail d'inventaire tournant est traité le troisième jour, le travail d'inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le 8ème jour.  
12. Cliquez sur Enregistrer.
13. Cliquez sur Nouveau.
14. Entrez un nombre dans le champ Numéro de souche.
    * Le tri s'effectue du plus petit nombre au plus grand nombre. La valeur doit être supérieure à 0 (zéro).  
15. Dans la liste, marquez la ligne sélectionnée.
16. Dans le champ Description, entrez une valeur.
17. Cliquez sur Enregistrer.
18. Cliquez sur Définir une requête de produit.
19. Dans la liste, marquez la ligne sélectionnée.
20. Dans le champ Critères, saisissez ou sélectionnez une valeur.
21. Cliquez sur OK.
22. Fermez la page.

