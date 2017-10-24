---
title: "Ajouter des dimensions financières à l'espace de travail CFO"
description: "Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail CFO, afin qu'elles puissent être utilisées pour les états comptables et budgétaires."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e674948f642ab7525f96092a9a1f3adaae66974
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Ajouter des dimensions financières à l'espace de travail CFO

[!include[banner](../includes/banner.md)]

Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail Directeur financier, afin qu'elles puissent être utilisées pour les états comptables et budgétaires. L'espace de travail CFO contient un onglet **Vue d'ensemble** et un onglet **Rapport financier**. Les états de ces deux onglets sont soutenus par deux mesures : LedgerActivityMeasure et BudgetActivityMeasure. Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017), il existe une relation entre ces deux mesures et l'entité DimensionCombinationEntity. Par conséquent, vous pouvez sélectionner des dimensions.

1. Dans Finance and Operations, dans la page **Magasin des entités**, mettez à jour les mesures **LedgerActivityMeasure** et **BudgetActivityMeasure**.
2. Dans Microsoft Visual Studio, ouvrez l'Explorateur d'application et recherchez **LedgerCFO**.
3. Sous **Ressources**, ouvrez **LedgerCFOWorkspacePBIX**.
4. Lorsque la ressource s'ouvre dans Microsoft Power BI Desktop, sélectionnez **Obtenir des données**, **Base de données SQL Server**, puis **Connecter**.
5. Entrez le nom du serveur, puis **AxDW** comme base de données. Sélectionnez **DirectQuery**, puis **OK**.
6. Recherchez et sélectionnez **LedgerActivityMeasure\_DimensionCombination**, puis sélectionnez **Charger**.

    > [!TIP]
    > Dans la liste **Champs**, renommez la table **Dimensions financières** pour l'identifier facilement.

7. Sélectionnez **Gérer les relations**, puis **Nouveau**.
8. Dans le premier champ, sélectionnez **Activités liées à la comptabilité**, puis **LedgerDimension**.
9. Dans le deuxième champ, sélectionnez **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensions financières** si vous avez renommé la table). Sélectionnez l'en-tête **DimensionCombinationRECID**.
10. Dans le champ **Cardinalité**, sélectionnez **Plusieurs à un**.
11. Définissez la valeur **Direction de filtre croisé** sur **Unique**.
12. Sélectionnez **Rendre cette relation active** et **Supposer l'intégrité référentielle**, sélectionnez **OK**, puis sélectionnez **Fermer**.

    [![Créer une relation](./media/Create-relationship.png)](./media/Create-relationship.png)

13. Dans la liste **Champs**, la table et les dimensions financières disponibles doivent s'afficher. Faites glisser les dimensions financières souhaitées vers les filtres au niveau de l'état.
14. Enregistrez vos modifications.
15. Dans l'arbre d'objets d'application (AOT), cliquez avec le bouton droit sur votre projet, puis sélectionnez **Synchroniser**.
16. Générez votre projet, puis ouvrez l'application pour afficher les résultats.

    [![Espace de travail terminé](./media/workspace.png)](./media/workspace.png)

