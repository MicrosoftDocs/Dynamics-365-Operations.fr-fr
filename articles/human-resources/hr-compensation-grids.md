---
title: Paramétrer les grilles de rémunération
description: Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13415f68f41555f3e86cbe699cf921e9a2cf6d5c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112456"
---
# <a name="set-up-compensation-grids"></a>Paramétrer les grilles de rémunération

Les grilles de rémunération permettent de définir et de tenir à jour les structures de paie pour les régimes de rémunération fixe. Les grilles de rémunération peuvent être partagées entre plusieurs régimes ou être copiées lors de la création d'un régime de rémunération.  Avant de créer une grille de rémunération, vous devez configurer les niveaux et les points de référence. Cet exemple crée un type de catégorie de grille de rémunération en utilisant des données de démonstration pour les niveaux et les points de référence. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Paramétrer les informations sur la grille de rémunération
1. Accédez à Ressources humaines > Rémunération > Rémunération fixe > Grilles de rémunération.
2. Cliquez sur Nouveau.
3. Dans le champ Grille, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez une option dans le champ Type.
6. Dans le champ Paramétrage de référence, saisissez ou sélectionnez une valeur.
7. Dans le champ Devise, saisissez ou sélectionnez une valeur.
8. Tapez une valeur dans le champ Devise.
9. Entrez une date dans le champ Date d'effet.

## <a name="add-levels-to-the-compensation-structure"></a>Ajouter des niveaux à la structure de rémunération
1. Cliquez sur Structure des rémunérations.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Niveau, saisissez ou sélectionnez une valeur.
4. Cliquez sur Nouveau.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ Niveau, saisissez ou sélectionnez une valeur.
7. Cliquez sur Nouveau.
8. Dans la liste, marquez la ligne sélectionnée.
9. Dans le champ Niveau, saisissez ou sélectionnez une valeur.
10. Cliquez sur Nouveau.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ Niveau, saisissez ou sélectionnez une valeur.
13. Cliquez sur Nouveau.
14. Dans la liste, marquez la ligne sélectionnée.
15. Dans le champ Niveau, saisissez ou sélectionnez une valeur.

## <a name="fill-in-the-compensation-structure-with-values"></a>Renseigner la structure de rémunération avec des valeurs
1. Dans la liste, marquez la ligne sélectionnée.
    * À ce stade, vous pouvez saisir les valeurs de rémunération manuellement dans chaque champ de la table, ou utiliser la fonctionnalité de modification en masse pour renseigner facilement plusieurs champs et effectuer des calculs de base.  
2. Cliquez sur Modification en masse.
    * Pour cette grille, nous appliquerons d'abord la valeur médiane du premier niveau à tous les champs de la table. Cela servira de base à la matrice de rémunération.  
3. Dans le champ Type d'ajustement, sélectionnez une option.
4. Entrez un numéro dans le champ Montant d'ajustement.
5. Dans la liste, cochez ou décochez toutes les lignes.
6. Cliquez sur Appliquer à la grille.
    * Nous emploierons maintenant la fonction de modification en masse pour incrémenter les montants dans chaque niveau suivant par un certain pourcentage ou montant. Dans cet exemple, chaque niveau aura un écart de 12,5 % entre ses valeurs médianes.  
7. Dans le champ Type d'ajustement, sélectionnez une option.
8. Entrez un numéro dans le champ Montant d'ajustement.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
12. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
13. Cliquez sur Appliquer à la grille.
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
17. Cliquez sur Appliquer à la grille.
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
19. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
20. Cliquez sur Appliquer à la grille.
21. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
22. Cliquez sur Appliquer à la grille.
    * Nous emploierons maintenant la fonction de modification en masse pour ajuster les points de référence minimum et maximum pour chaque niveau. Cet exemple utilise un écart de 50 %. Le point de référence minimum sera ajusté de -20 % et le point maximum de +20 %.  
23. Entrez un numéro dans le champ Montant d'ajustement.
24. Dans le champ Point de référence, saisissez ou sélectionnez une valeur.
25. Dans la liste, cochez ou décochez toutes les lignes.
26. Cliquez sur Appliquer à la grille.
27. Entrez un numéro dans le champ Montant d'ajustement.
28. Dans le champ Point de référence, saisissez ou sélectionnez une valeur.
29. Dans la liste, cochez ou décochez toutes les lignes.
30. Cliquez sur Appliquer à la grille.



[!INCLUDE[footer-include](../includes/footer-banner.md)]