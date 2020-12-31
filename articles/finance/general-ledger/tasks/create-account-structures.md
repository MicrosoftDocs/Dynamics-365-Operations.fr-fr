---
title: Créer des structures de compte
description: Ce guide accompagne l’utilisateur le long de la création d’une structure de compte.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b75ee76a1fb874652415a2174441f629955d763a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443250"
---
# <a name="create-account-structures"></a>Créer des structures de compte

[!include [banner](../../includes/banner.md)]

Ce guide accompagne l’utilisateur le long de la création d’une structure de compte. La société fictive USMF est citée en exemple dans les étapes.

1. Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Configurer les structures de compte**.
2. Dans le volet **Actions**, cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
3. Dans le champ **Structure de compte**, entrez un nom pour décrire l’objectif de la structure de compte.
4. Dans le champ **Description**, entrez une description pour préciser l’objectif de la structure de compte.
5. Cliquez sur **Créer**.
6. Dans **Segments et valeurs autorisées**, cliquez sur **Ajouter un segment**.
7. Dans la liste des dimensions, sélectionnez la dimension à ajouter à la structure de compte.
8. À la fin de la liste, cliquez sur **Ajouter un segment**.
9. Répétez les étapes 6 à 9 si nécessaire.
10. Dans la section **Détails des valeurs autorisées**, sélectionnez le segment pour modifier les valeurs autorisées.
    Par exemple, cliquez dans le **compte principal**.  
11. Dans le champ **Opérateur**, sélectionnez une option, comme Est compris entre et Comprend.
12. Tapez une valeur dans le champ **Valeur**. Par exemple, 600000.  
13. Dans le champ **À**, tapez une valeur. Par exemple, 699999.  
14. Dans la section **Détails de valeur autorisées**, cliquez sur **Appliquer**.
15. Répétez les étapes 10 à 15 si nécessaire.  
16. Dans la section **Détails de valeur autorisées**, cliquez sur **Ajouter de nouveaux critères**.
17. Dans le champ Opérateur, sélectionnez une option, comme Est compris entre et Comprend.
18. Tapez une valeur dans le champ **Valeur**. Par exemple, 033.  
19. Dans le champ **À**, tapez une valeur. Par exemple, 034.  
20. Cliquez sur **Appliquer**.
21. Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées. Par exemple, Centre de coût.  
22. Dans le champ **Centre de coût**, tapez une valeur. Par exemple, 007..021.  
23. Dans **Segments et valeurs autorisées**, cliquez sur **Ajouter**.
24. Tapez une valeur dans le champ **Compte principal**. Par exemple, 600000..699999  
25. Dans la grille, sélectionnez le segment pour modifier les valeurs autorisées. Par exemple, Département.  
26. Dans le champ Département, tapez une valeur. Par exemple, 032.  
27. Dans le champ Centre de coût, tapez une valeur. Par exemple, 086.  
28. Dans le volet **Actions**, cliquez sur **Valider**.
29. Dans le volet **Actions**, cliquez sur **Activer**.
30. Cliquez sur **Activer**.

