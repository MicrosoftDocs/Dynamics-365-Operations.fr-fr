---
title: Paramétrer les grilles de rémunération
description: Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe.
author: twheeloc
ms.date: 01/03/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51b98320eac539e49787d352f32683efadc11f41
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071447"
---
# <a name="set-up-compensation-grids"></a>Paramétrer les grilles de rémunération


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe. Les grilles de rémunération peuvent être partagées entre plusieurs régimes ou être copiées lors de la création d’un régime de rémunération.  Avant de créer une grille de rémunération, vous devez configurer les niveaux et les points de référence. Cet exemple crée un type de catégorie de grille de rémunération en utilisant des données de démonstration pour les niveaux et les points de référence. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Paramétrer les informations sur la grille de rémunération
1. Accédez à **Ressources humaines** > **Rémunération** > **Rémunération fixe** > **Grilles de rémunération**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Grille**, tapez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez une option dans le champ **Type**.
6. Dans le champ Paramétrage de **référence**, saisissez ou sélectionnez une valeur.
7. Saisissez ou sélectionnez une valeur dans le champ **Devise**.
8. Entrez une date dans le champ **Date d’effet**.

## <a name="add-levels-to-the-compensation-structure"></a>Ajouter des niveaux à la structure de rémunération
1. Cliquez sur **Structure des rémunérations**.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ **Niveau**, saisissez ou sélectionnez une valeur.
4. Cliquez sur **Nouveau**.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ **Niveau**, saisissez ou sélectionnez une valeur.
7. Cliquez sur **Nouveau**.
8. Dans la liste, marquez la ligne sélectionnée.
9. Dans le champ **Niveau**, saisissez ou sélectionnez une valeur.
10. Cliquez sur **Nouveau**.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ **Niveau**, saisissez ou sélectionnez une valeur.
13. Cliquez sur **Nouveau**.
14. Dans la liste, marquez la ligne sélectionnée.
15. Dans le champ **Niveau**, saisissez ou sélectionnez une valeur.

## <a name="fill-in-the-compensation-structure-with-values"></a>Renseigner la structure de rémunération avec des valeurs
1. Dans la liste, marquez la ligne sélectionnée.
    * À ce stade, vous pouvez saisir les valeurs de rémunération manuellement dans chaque champ de la table, ou utiliser la fonctionnalité de modification en masse pour renseigner facilement plusieurs champs et effectuer des calculs de base.  
2. Cliquez sur **Modification en masse**.
    * Pour cette grille, nous appliquerons d’abord la valeur médiane du premier niveau à tous les champs de la table. Cela servira de base à la matrice de rémunération.  
3. Dans le champ **Type d’ajustement**, sélectionnez une option.
4. Entrez un nombre dans le champ **Montant d’ajustement**.
5. Dans la liste, cochez ou décochez toutes les lignes.
6. Cliquez sur **Appliquer à la grille**.
    * Nous emploierons maintenant la fonction de modification en masse pour incrémenter les montants dans chaque niveau suivant par un certain pourcentage ou montant. Dans cet exemple, chaque niveau aura un écart de 12,5 % entre ses valeurs médianes.  
7. Dans le champ **Type d’ajustement**, sélectionnez une option.
8. Entrez un nombre dans le champ **Montant d’ajustement**.
9. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
10. Cliquez sur **Appliquer à la grille**.
    * Nous emploierons maintenant la fonction de modification en masse pour ajuster les points de référence minimum et maximum pour chaque niveau. Cet exemple utilise un écart de 50 %. Le point de référence minimum sera ajusté de -20 % et le point maximum de +20 %.  
11. Entrez un nombre dans le champ **Montant d’ajustement**.
12. Dans le champ **Point de référence**, saisissez ou sélectionnez une valeur.
13. Dans la liste, cochez ou décochez toutes les lignes.
14. Cliquez sur **Appliquer à la grille**.
15. Entrez un nombre dans le champ **Montant d’ajustement**.
16. Dans le champ **Point de référence**, saisissez ou sélectionnez une valeur.
17. Dans la liste, cochez ou décochez toutes les lignes.
18. Cliquez sur **Appliquer à la grille**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
