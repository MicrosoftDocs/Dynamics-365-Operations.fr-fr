---
title: Créer une règle de kanban de retrait
description: Cette procédure permet d’indiquer le paramétrage nécessaire pour créer une règle de kanban de prélèvement pour transférer les matériaux dans un environnement lean.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1e1fc6dff80457cecdcd1659ffa42fd6c9c4447
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263992"
---
# <a name="create-a-withdrawal-kanban-rule"></a>Créer une règle de kanban de retrait

[!include [banner](../../includes/banner.md)]

Cette procédure permet d’indiquer le paramétrage nécessaire pour créer une règle de kanban de prélèvement pour transférer les matériaux dans un environnement lean. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent le réapprovisionnement des matériaux nouveaux ou modifiés.


## <a name="create-new-kanban-rule"></a>Créer une règle de kanban
1. Accédez aux règles de kanban.
2. Cliquez sur Nouveau.
3. Sélectionnez Prélèvement dans le champ Type.
    * Le type Prélèvement est utilisé pour les règles de kanban pour transférer les matériaux ou les marchandises.  
4. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Sélectionnez ReplenishSpeakerComponents.   Cette activité est paramétrée pour déplacer les composants de l’entrepôt 11, emplacement 11 vers l’entrepôt 12 et l’emplacement 12.  
5. Dans le champ Produit, saisissez ou sélectionnez une valeur.
    * Sélectionnez M0007.  
6. Entrez un nombre dans le champ Délai.
    * Par exemple, 60.  
7. Dans le champ Unité de mesure, saisissez ou sélectionnez une valeur.
    * Par exemple, Minutes.  

## <a name="set-quantities-for-kanban"></a>Définir les quantités de kanban
1. Définissez la quantité par défaut sur 5.
    * Il s’agit de la quantité qui sera transférée pour chaque kanban.  
2. Entrez 2 dans le champ Quantité de kanban fixe.
    * Il s’agit de la quantité de kanbans qui doivent être actifs. Dans ce cas, 2 kanbans qui transfèrent 5 unités chacun.  
3. Dans le champ Limite d’alerte minimale, entrez « 1 ».
    * Permet de tenir à jour la quantité minimale de kanbans complets qui doivent être à la destination. Par exemple, cela sert dans la vue d’ensemble de la quantité de kanban.  
4. Dans le champ Limite d’alerte maximale, entrez « 2 ».
    * Permet de tenir à jour la quantité maximale de kanbans complets qui doivent être à la destination. Par exemple, cela sert dans la vue d’ensemble de la quantité de kanban.  

## <a name="create-kanbans"></a>Créer des kanbans
1. Cliquez sur Enregistrer.
    * La règle de kanban doit être enregistrée avant que les kanbans puissent être créés.  
2. Cliquez sur Ajouter.
    * Notez qu’il n’existe aucun kanban actif, parce que le « Nombre suggéré de nouveaux kanbans » est de 2. Cela est égal à la « quantité fixe de kanban ».  
3. Cliquez sur Créer.
    * Cette opération crée deux kanbans.  
    * Notez que 2 kanbans, chacun pour 5 unités, ont été créés pour cette règle de kanban de prélèvement.  Il s’agit de la dernière étape de cette procédure.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]