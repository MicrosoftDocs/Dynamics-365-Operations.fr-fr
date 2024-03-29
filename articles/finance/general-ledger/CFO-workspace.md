---
title: Ajouter des dimensions financières à l’espace de travail CFO
description: Cet article explique comment ajouter des dimensions financières à l’espace de travail CFO, afin qu’elles puissent être utilisées pour les états comptables et budgétaires.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ea453eed826dec2e97371ec559e91b94933bdce6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853378"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Ajouter des dimensions financières à l’espace de travail CFO

[!include [banner](../includes/banner.md)]

Cet article explique comment ajouter des dimensions financières à l’espace de travail Directeur financier, afin qu’elles puissent être utilisées pour les états comptables et budgétaires. L’espace de travail CFO contient un onglet **Vue d’ensemble** et un onglet **Rapport financier**. Les états de ces deux onglets sont soutenus par deux mesures : LedgerActivityMeasure et BudgetActivityMeasure. Là, il existe une relation entre ces deux mesures et l’entité DimensionCombinationEntity. Par conséquent, vous pouvez sélectionner des dimensions.

1. Dans Finance, sur la page **Magasin des entités**, mettez à jour les mesures **LedgerActivityMeasure** et **BudgetActivityMeasure**.
2. Dans Microsoft Visual Studio, ouvrez l’Explorateur d’application et recherchez **LedgerCFO**.
3. Sous **Ressources**, ouvrez **LedgerCFOWorkspacePBIX**.
4. Lorsque la ressource s’ouvre dans Microsoft Power BI desktop, sélectionnez **Obtenir des données**, **Base de données SQL Server**, puis **Connecter**.
5. Entrez le nom du serveur, puis **AxDW** comme base de données. Sélectionnez **DirectQuery**, puis **OK**.
6. Recherchez et sélectionnez **LedgerActivityMeasure\_DimensionCombination**, puis sélectionnez **Charger**.

    > [!TIP]
    > Dans la liste **Champs**, renommez la table **Dimensions financières** pour l’identifier facilement.

7. Sélectionnez **Gérer les relations**, puis **Nouveau**.
8. Dans le premier champ, sélectionnez **Activités liées à la comptabilité**, puis **LedgerDimension**.
9. Dans le deuxième champ, sélectionnez **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensions financières** si vous avez renommé la table). Sélectionnez l’en-tête **DimensionCombinationRECID**.
10. Dans le champ **Cardinalité**, sélectionnez **Plusieurs à un**.
11. Définissez la valeur **Direction de filtre croisé** sur **Unique**.
12. Sélectionnez **Rendre cette relation active** et **Supposer l’intégrité référentielle**, sélectionnez **OK**, puis sélectionnez **Fermer**.

    [![Créer une relation.](./media/Create-relationship.png)](./media/Create-relationship.png)

13. Dans la liste **Champs**, la table et les dimensions financières disponibles doivent s’afficher. Faites glisser les dimensions financières souhaitées vers les filtres au niveau de l’état.
14. Enregistrez vos modifications.
15. Dans l’arbre d’objets d’application (AOT), cliquez avec le bouton droit sur votre projet, puis sélectionnez **Synchroniser**.
16. Générez votre projet, puis ouvrez l’application pour afficher les résultats.

    [![Espace de travail terminé.](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
