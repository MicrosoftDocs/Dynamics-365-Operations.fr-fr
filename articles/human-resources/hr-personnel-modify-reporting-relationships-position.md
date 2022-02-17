---
title: Modifier les relations hiérarchiques d’un poste
description: Cette procédure illustre comment modifier la relation hiérarchique pour un employé.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7996733575c2d3a23971d08eb101962c1f6bbd9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066623"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modifier les relations hiérarchiques d’un poste


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cette procédure illustre comment modifier la relation hiérarchique pour un employé. La relation hiérarchique peut être utilisée pour acheminer des documents dans le workflow. La procédure illustre également la manière d’affecter l’employé à des hiérarchies supplémentaires. Par exemple, un employé peut faire partie d’une équipe de projet avec une relation hiérarchique informelle envers un superviseur du projet. Les relations hiérarchiques supplémentaires peuvent être définies par rapport au poste afin de convenir à divers scénarios de projet ou de matrice. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à **Ressources humaines** \> **Postes** \> **Postes**.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **000091** pour le champ **Poste**.
3. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
4. Développez la section **Poste de référence**.
5. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue déroulante.
6. Dans le champ **Référence**, saisissez ou sélectionnez une valeur.
7. Cliquez sur **Créer**.
8. Développez ou réduisez la section **Relations**.
9. Sélectionnez **Ajouter**.
10. Cochez la case située à gauche de la grille.
11. Dans le champ **Nom de la hiérarchie**, saisissez ou sélectionnez une valeur (par exemple **Projet**).
12. Dans le champ **Poste de référence**, saisissez ou sélectionnez une valeur (par exemple, **000437**).
13. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
