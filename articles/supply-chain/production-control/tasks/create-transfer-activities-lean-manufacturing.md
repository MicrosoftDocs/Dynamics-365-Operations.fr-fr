---
title: Créer des activités de transfert pour la lean manufacturing
description: Créez une activité de transfert pour la lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2925833aceba0cffe46b3a44c5d19c87cd3736e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427599"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Créer des activités de transfert pour la lean manufacturing

[!include [banner](../../includes/banner.md)]

Créez une activité de transfert pour la lean manufacturing. 

Conditions préalables : 

1. Un flux de production et une version non actifs doivent être créés.

2. Les emplacements et l'entrepôt d'origine et de destination doivent être créés. Le cas échéant, il convient de créer le réapprovisionnement ou la cellule de travail réapprovisionnée.


## <a name="find-the-production-flow-version"></a>Cherchez la version du flux de production.
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Notez que le flux de production doit avoir une version à l'état de brouillon.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="create-a-new-activity"></a>Créer une nouvelle activité
1. Cliquez sur Activités.
    * Vérifiez que le flux de production sélectionné a une version à l'état de brouillon, et sélectionnez celle-ci.  
2. Cliquez sur Créer une nouvelle activité de plan.
3. Cliquez sur Suivant.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Type d'activité, sélectionnez « Transfert ».
6. Dans le champ Quantité à traiter, entrez un nombre.
7. Cliquez sur Suivant.

## <a name="select-the-work-cells"></a>Sélectionnez les cellules de travail.
1. Dans le champ Réapprovisionnement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Pour utiliser l'emplacement de sortie de la cellule de travail comme emplacement d'origine dans l'activité de transfert, sélectionnez une cellule de travail. Il est possible de faire la même chose avec la cellule de travail réapprovisionnée, ce qui définit l'emplacement cible de l'activité de transfert.  
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="define-the-inventory-updates"></a>Définir les mises à jour de stock
1. Dans le champ Type de produit, sélectionnez une option.
    * Notez qu'un transfert ne modifie pas le type de produit. Vous pouvez transférer des produits finis ou semi-finis (transfert entre deux activités d'un flux de production et éventuellement d'un flux kanban).     Lors du transfert de produits finis, vous pouvez choisir si le prélèvement ou la réception des résultats est une transaction de stock.  

## <a name="define-the-transfer-locations"></a>Définir les emplacements de transfert
1. Cliquez sur Suivant.
2. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Dans le champ Transporté par, sélectionnez « Expéditeur ».
    * Les options sont les suivantes : Expéditeur - l'organisations qui exploite l'entrepôt d'expédition, Destinataire - l'organisation qui exploite l'entrepôt de réception, Transporteur - un fournisseur tiers. Si l'organisation exploitante est un fournisseur, l'activité de transfert nécessite un accord de sous-traitance.  
8. Cliquez sur Suivant.

## <a name="define-the-activity-times"></a>Définir les durées d'activité
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * La définition d'un Délai d'exécution est requise. Le délai d'exécution est utilisé pour calculer les coûts et les délais de débit des tâches de kanban. Les délais d'exécution ne sont pas utilisés pour calculer la charge de la capacité et la consommation, qui sont calculées par durée de cycle, dérivée de la tâche de version du flux de production.  
2. Entrez un nombre dans le champ Durée.
3. Dans le champ Unité, tapez une valeur.
4. Sélectionnez l'Unité de temps.
5. Dans le champ Par quantité, entrez un nombre.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Les temps d'attente sont facultatifs.  
7. Entrez un nombre dans le champ Durée.
8. Dans le champ Unité, tapez une valeur.
9. Sélectionnez l'Unité de temps.
10. Dans le champ Par quantité, entrez un nombre.
11. Cliquez sur Suivant.
12. Cliquez sur Terminer.
13. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]