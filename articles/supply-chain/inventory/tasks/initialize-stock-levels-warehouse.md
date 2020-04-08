---
title: Initialiser les niveaux des stocks dans l'entrepôt
description: Cette procédure décrit la manière dont vous obtenez le stock disponible mis à jour manuellement à l'aide du journal des mouvements de stock.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f922620c7aeeafd8560316239875c1ec5486191
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145684"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Initialiser les niveaux des stocks dans l'entrepôt

[!include [banner](../../includes/banner.md)]

Cette procédure décrit la manière dont vous obtenez le stock disponible mis à jour manuellement à l'aide du journal des mouvements de stock. (Il est également possible de mettre à jour le stock disponible en important les transactions dans des entités de données.) Vous pouvez exécuter ce guide avec les données de démonstration de la société USMF dans lesquelles toutes les conditions préalables, comme le nom de journal, le paramétrage des articles, les profils de validation et les comptes sont disponibles. Le guide propose des valeurs spécifiques pour l'article et les dimensions utilisés. Si vous sélectionnez un article différent, vous devrez peut-être entrer des valeurs pour des dimensions différentes.

1. Accédez à Gestion des stocks > Entrées de journal > Articles > Mouvement.
2. Cliquez sur Nouveau.
3. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez IMov.
    * Il est judicieux d'utiliser différents modèles de nom de journal pour les différents objectifs de l'activité.  
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Spécifiez les valeurs '140200' dans le champ Compte de contrepartie.
    * Il s'agit du compte de contrepartie qui sera le compte par défaut dans les lignes de journal. Il est possible de remplacer la valeur par défaut pour affecter différents comptes de contrepartie par ligne.  
7. Cliquez sur OK.
8. Cliquez sur Nouveau.
9. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Sélectionner l'article A0001.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Cliquez sur l'onglet Dimensions de stock.
13. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
14. Sélectionner le site 1.
15. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Sélectionner l'entrepôt 13.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Sélectionner l'emplacement 13.
20. Dans le champ Quantité, entrer un numéro.
21. Cliquez sur Enregistrer.
22. Cliquez sur Valider.
23. Activez ou désactivez la case à cocher Transférer toutes les erreurs de validation vers un nouveau journal.
    * Si vous activez cette option, toutes les lignes non validées seront copiées dans un nouveau journal. Vous pouvez utiliser les informations contenues dans le journal pour corriger les problèmes puis revalider les lignes.  
24. Cliquez sur OK.
25. Fermez la page.
26. Fermez la page.

