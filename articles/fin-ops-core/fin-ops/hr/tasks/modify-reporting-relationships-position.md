---
title: Modifier les relations hiérarchiques d'un poste
description: Cette procédure illustre comment modifier la relation hiérarchique pour un employé.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a1afd2c1cdc2ebaa303030d01b3bbe5fd2af44f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177819"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modifier les relations hiérarchiques d'un poste

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment modifier la relation hiérarchique pour un employé. La relation hiérarchique peut être utilisée pour acheminer des documents dans le workflow. La procédure illustre également la manière d'affecter l'employé à des hiérarchies supplémentaires. Par exemple, un employé peut faire partie d'une équipe de projet avec une relation hiérarchique informelle envers un superviseur du projet. Les relations hiérarchiques supplémentaires peuvent être définies par rapport au poste afin de convenir à divers scénarios de projet ou de matrice. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à Ressources humaines > Postes > Postes.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Poste avec une valeur de « 000091 ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Développez la section Poste de référence.
5. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
6. Dans le champ Référence, saisissez ou sélectionnez une valeur.
7. Cliquez sur Créer.
8. Développez ou réduisez la section Relations.
9. Cliquez sur Ajouter.
10. Cochez la case située à gauche de la grille.
11. Dans le champ Nom de la hiérarchie, saisissez ou sélectionnez une valeur.
    * Exemple : Projet  
12. Dans le champ Poste de référence, saisissez ou sélectionnez une valeur.  Exemple : 000437
13. Cliquez sur Enregistrer.
