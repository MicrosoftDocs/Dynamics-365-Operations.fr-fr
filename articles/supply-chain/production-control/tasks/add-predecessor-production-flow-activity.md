---
title: Ajouter un prédécesseur à une activité de flux de production
description: Dans une version de flux de production, toutes les activités doivent être séquencées.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc1aa742013faeeb545d746f9715c639a5b66b9b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575073"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Ajouter un prédécesseur à une activité de flux de production

[!include [banner](../../includes/banner.md)]

Dans une version de flux de production, toutes les activités doivent être séquencées. Une activité peut avoir un ou plusieurs prédécesseurs ou successeurs. 

Cette procédure indique comment associer un prédécesseur à une activité. 

Pour exécuter cette tâche, vous devez disposer d’un flux de production en version brouillon avec au moins deux activités pouvant être connectées. 

Pour en savoir plus, lisez le livre blanc « Production flows and activities in lean manufacturing (Flux et activités de production liés au lean manufacturing) ».


## <a name="find-the-production-flow-and-version"></a>Rechercher la version et le flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Cliquez sur Activités.

## <a name="select-an-activity-and-add-a-predecessor"></a>Sélectionner une activité et ajouter un prédécesseur
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
2. Cliquez sur Ajouter un prédécesseur.
3. Dans le champ Activité, entrez ou sélectionnez une valeur.
4. Entrez un nombre dans le champ Ratio de durée de cycle.
    * Le ratio de durée de cycle par défaut d’une relation d’activité est 1. Cela suppose que les deux activités s’exécutent au même rythme ou takt time. Si un prédécesseur s’exécute à un rythme plus élevé (takt time inférieur), le ratio peut être inférieur à 1, si le prédécesseur s’exécute à un rythme plus lent (takt time supérieur), le ratio de durée de cycle est supérieur à 1.  
5. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]