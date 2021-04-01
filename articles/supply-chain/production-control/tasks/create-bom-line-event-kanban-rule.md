---
title: Créer une règle de kanban d’événement de ligne de nomenclature
description: Cette tâche se concentre sur le paramétrage nécessaire pour créer une règle de kanban d’événement pour vérifier l’approvisionnement des lignes de nomenclature de production dans un environnement de fabrication en mode mixte et classique.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6df9632d6e2798fad2b3462055a9495394583f6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255275"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>Créer une règle de kanban d’événement de ligne de nomenclature

[!include [banner](../../includes/banner.md)]

Cette tâche se concentre sur le paramétrage nécessaire pour créer une règle de kanban d’événement pour vérifier l’approvisionnement des lignes de nomenclature de production dans un environnement de fabrication en mode mixte et classique. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d’un produit nouveau ou modifié.


## <a name="create-a-new-kanban-rule"></a>Créer une règle de kanban
1. Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Règles de kanban.
2. Cliquez sur Nouveau.
3. Sélectionnez Prélèvement dans le champ Type.
    * Le type de prélèvement permet de créer des kanbans de transfert.  
4. Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».
    * La stratégie d’événement est activée pour créer le transfert des kanbans selon un événement. Plus loin dans le guide de tâche, nous le déclencherons en estimant un ordre de fabrication.  
5. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Entrez ou sélectionnez ReplenishSpeakerComponents. Cette activité de transfert a l’entrepôt de sortie et l’emplacement 12, ce qui signifie que les matériaux sont déplacés vers l’emplacement 12 dans l’entrepôt 12.  
6. Développez la section Détails.
7. Dans le champ Produit, saisissez ou sélectionnez M0001.
8. Développez la section Événements.
9. Dans le champ Événement de ligne de nomenclature, sélectionnez « Automatique ».
    * Si le champ Événement de ligne de nomenclature est défini sur Automatique, le kanban est créé pour répondre aux besoins en matériaux pour les lignes de nomenclature de l’ordre de fabrication.  
10. Fermez la page.

## <a name="create-and-modify-a-new-production-order"></a>Créer et modifier un nouvel ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
2. Cliquez sur Nouvel ordre de fabrication.
3. Entrez ou sélectionnez une valeur dans le champ Numéro d’article.
    * Entrez ou sélectionnez L0001. Nous utilisons l’article L0001 car l’article M0001 est inclus dans la nomenclature pour l’article L0001.  
4. Cliquez sur Créer.
5. Dans la liste, cliquez sur le lien dans la ligne pour L0001.
6. Cliquez sur Nomenclature.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur Modifier.
9. Sélectionnez Approvisionnement invariable dans le champ Type de ligne.
    * L’approvisionnement invariable est sélectionné pour déclencher la création d’approvisionnement d’un kanban.  
10. Sélectionnez Non dans le champ Consommation de ressource.
    * Si vous décochez la case à cocher Consommation de ressource cela permet de modifier l’entrepôt.  
11. Développez la section Dimensions de stock.
12. Dans le champ Entrepôt, tapez « 12 ».
    * L’entrepôt est défini sur 12 car il s’agit de l’entrepôt de sortie pour l’activité de prélèvement.  
13. Tapez « 12 » dans le champ Emplacement.
    * L’emplacement est défini sur 12 car il s’agit de l’emplacement de sortie pour l’activité de prélèvement.  
14. Fermez la page.
15. Fermez la page.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Estimer l’ordre de fabrication et afficher le kanban créé
1. Cliquez sur Estimer.
    * L’estimation de l’ordre de fabrication déclenche la création du kanban associé pour fournir l’article M0001.  
2. Cliquez sur OK.
3. Fermez la page.
4. Fermez la page.
5. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la règle de kanban d’événement créée pour l’article M0001.  
7. Développer la section Kanbans.
8. Dans la liste, marquez la ligne sélectionnée.
    * Notez le kanban créé pour fournir M0001 pour l’ordre de fabrication estimé.  
    * Il s’agit de la dernière étape.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]