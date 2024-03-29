---
title: Configurer les paramètres de l’espace de travail de contrôle des coûts
description: Cette procédure permet de configurer l’espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d’une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits.
author: kfend
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c38b6f2664426513ea46b16b4cd54d69d71d1399
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710555"
---
# <a name="configure-cost-control-workspace-parameters"></a>Configurer les paramètres de l’espace de travail de contrôle des coûts

[!include [banner](../../includes/banner.md)]

Cette procédure permet de configurer l’espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d’une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits. La société fictive USP2 a été utilisée pour créer cet enregistrement.

1. Accédez à Contrôle de gestion > Paramétrage > Configuration de l’espace de travail de contrôle des coûts.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez Oui dans le champ Publié.
    * Si vous définissez cette option sur Oui, les utilisateurs affectés à l’un des rôles suivants peuvent afficher l’état dans l’espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable, commis contrôleur de gestion ou contrôleur d’objet de coût. Si vous définissez cette option sur Non, seuls les utilisateurs affectés à l’un des rôles suivants peuvent afficher l’état dans l’espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable ou commis contrôleur de gestion.  
6. Développez la section Filtrage des données.
7. Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.
8. Dans le champ Version originale du budget, entrez ou sélectionnez une valeur.
9. Dans le champ Hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.
10. Dans le champ Hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
11. Développez la section Affecter les enregistrements de calcul.
12. Cliquez sur Nouveau.
13. Dans la liste, marquer la ligne sélectionnée.
14. Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.
15. Dans le champ Version réelle, entrez ou sélectionnez une valeur.
16. Développez la section Périodes fiscales par colonne.
17. Sélectionnez Oui dans le champ Période actuelle.
18. Développez la section Colonnes à afficher pour les coûts.
19. Sélectionnez Oui dans le champ Coût fixe.
20. Sélectionnez Oui dans le champ Coût variable.
21. Sélectionnez Oui dans le champ Coût total.
22. Cliquez sur Enregistrer.
23. Fermez la page.
24. Accédez à Contrôle de gestion > Espaces de travail > Contrôle des coûts.
25. Sélectionnez un relevé pour afficher les coûts fixes, variables, totaux et non classés pour les périodes fiscales sélectionnées.
26. Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.
27. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Après avoir sélectionné une hiérarchie Dimension d’objet de coût, développez la hiérarchie Dimension d’élément de coût pour afficher les valeurs de coût souhaitées. Par exemple, vous pouvez développer la hiérarchie des frais généraux de fabrication pour afficher la valeur.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
