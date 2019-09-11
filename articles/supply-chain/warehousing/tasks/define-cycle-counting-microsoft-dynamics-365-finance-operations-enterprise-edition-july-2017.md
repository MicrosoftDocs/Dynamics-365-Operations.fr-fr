---
title: Définir l'inventaire tournant
description: L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/12/2019
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
ms.openlocfilehash: 24c4c27745a15f013d20b52efc6e36de848a0251
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916781"
---
# <a name="define-cycle-counting"></a>Définir l'inventaire tournant 

[!include [task guide banner](../../includes/task-guide-banner.md)]

L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles. Cet enregistrement de tâche indique comment paramétrer la priorité par défaut du travail d'inventaire, activer une option de menu d'appareil mobile pour traiter à la fois les opérations de prélèvement et d'inventaire, activer un déclencheur de seuil de comptage lorsqu'un emplacement devient vide et activer un plan d'inventaire tournant pour un article spécifique dans un entrepôt particulier. Ces tâches sont généralement effectuées par un gestionnaire d'entrepôt. Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.


## <a name="set-the-priority-of-counting-work"></a>Définir la priorité du travail d'inventaire
1. Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.
2. Cliquez sur l'onglet **Inventaire tournant**.
3. Entrez un nombre dans le champ **Priorité de travail d'inventaire tournant par défaut**. Cette étape modifie la priorité du travail d'inventaire tournant par rapport à d'autres types de travail dans l'entrepôt. Si vous entrez un nombre plus faible que celui pour d'autres types de travail, vous élevez la priorité du travail d'inventaire tournant.  
4. Cliquez sur **Enregistrer**.
5. Fermez la page.

## <a name="enable-the-mobile-device"></a>Activer l'appareil mobile
1. Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom de l'option de menu**, saisissez une valeur.
4. Dans le champ **Titre**, saisissez une valeur.
5. Dans le champ **Mode**, sélectionnez « Travail ».
6. Définissez l'option **Utiliser un travail existant** sur Oui. Lorsque vous définissez cette option sur Oui, le système recherchera les travaux existants lorsque l'option de menu d'appareil mobile est utilisée.  
7. Dans le champ **Dirigé par**, sélectionnez « Système dirigé ». Lorsque l'option « Dirigé par le système » est sélectionnée, le magasinier sera dirigé vers le travail en cours qui se trouve dans les classes de travail définies. (Nous créerons ces classes de travail par la suite.)  
8. Développez le raccourci **Classes de travail**. Ensuite, nous créerons deux classes de travail qui seront utilisées avec cette option de menu d'appareil mobile. Lorsque l'option de menu est utilisée, ces classes de travail sont interrogées, et le travail ayant la priorité la plus élevée est affiché à l'utilisateur.  
9. Cliquez sur **Nouveau**.
10. Sélectionnez une valeur dans le champ **ID classe de travail**.
11. Cliquez sur **Nouveau**.
12. Sélectionnez une valeur dans le champ **ID classe de travail**.
13. Dans le **volet Actions**, cliquez sur **Enregistrer**.
14. Fermez la page.
15. Dans le **Volet de navigation**, allez dans **Modules > Gestion des entrepôts > Configuration > Appareil mobile > menu d'appareil mobile**.
16. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
17. Dans l'arborescence, sélectionnez l'option de menu que vous venez de créer.
18. Cliquez sur **Modifier**.
19. Cliquez sur la flèche pour ajouter l'option de menu au menu.
20. Cliquez sur **Enregistrer**.

## <a name="create-a-counting-threshold"></a>Créer un seuil d'inventaire
1. Dans le **Volet de navigation**, allez dans **Modules > Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Seuils d'inventaire tournant**.
2. Cliquez sur **Nouveau**.
3. Entrez une valeur dans le champ **ID seuil d'inventaire tournant**.
4. Définissez l'option **Traiter immédiatement l'inventaire tournant** sur Oui.
5. Tapez une valeur dans le champ **Description**.
6. Cliquez sur **Enregistrer**.
7. Cliquez sur **Sélectionner des emplacements**.
8. Dans la liste, marquez la ligne sélectionnée.
9. Sélectionnez une valeur dans le champ **Critère**.
10. Cliquez sur **OK**.
11. Fermez la page.

## <a name="create-a-cycle-count-plan"></a>Créer un plan d'inventaire tournant
1. Dans le **Volet de navigation**, allez dans **Modules > Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Plans d'inventaire tournant**.
2. Cliquez sur **Nouveau**.
3. Entrez une valeur dans le champ **ID plan d'inventaire tournant**.
4. Tapez une valeur dans le champ **Description**.
5. Entrez un nombre dans le champ **Nombre maximal d'inventaires tournants**.
6. Cliquez sur **Enregistrer**.
7. Cliquez sur **Sélectionner des emplacements**.
8. Dans la liste, marquez la ligne sélectionnée.
9. Sélectionnez une valeur dans le champ **Critère**.
10. Cliquez sur **OK**.
11. Entrez un nombre dans le champ **Jours entre les inventaires tournants**. Par exemple, si le champ **Jours entre les inventaires tournants** est défini sur 5, le travail d'inventaire tournant sera créé tous les cinq jours. Toutefois, si le travail d'inventaire tournant est traité le troisième jour, le travail d'inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le 8ème jour.  
12. Cliquez sur **Enregistrer**.
13. Cliquez sur **Nouveau**.
14. Entrez un nombre dans le champ **Numéro de souche**. Le tri s'effectue du plus petit nombre au plus grand nombre. La valeur doit être supérieure à 0 (zéro).  
15. Dans la liste, marquez la ligne sélectionnée.
16. Tapez une valeur dans le champ **Description**.
17. Cliquez sur **Enregistrer**.
18. Cliquez sur **Définir le produit**.
19. Dans la liste, marquez la ligne sélectionnée.
20. Dans le champ **Critères**, saisissez ou sélectionnez une valeur.
21. Cliquez sur **OK**.
22. Fermez la page.

