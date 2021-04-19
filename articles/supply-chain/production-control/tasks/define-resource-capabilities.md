---
title: Définir des capacités de ressources
description: Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 072991e7b3844ad3583b7d0c575d426299f74e9f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828704"
---
# <a name="define-resource-capabilities"></a>Définir des capacités de ressources

[!include [banner](../../includes/banner.md)]

Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer. Lors de la planification, les exigences de chaque tâche et opération sont mises en correspondance avec les capacités des ressources disponibles. Ce guide des tâches vous aidera à créer une capacité et à l’affecter à une ressource. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.


## <a name="create-a-resource-capability"></a>Créer une capacité de ressource
1. Allez dans Capacités de ressources.
2. Cliquez sur Nouveau.
3. Dans le champ Capacité, entrez l’ID de la capacité de la ressource.
    * Pour une opération donnée, vous devez utiliser l’ID de capacité pour spécifier que les ressources doivent avoir cette possibilité d’exécuter l’opération.  
4. Dans le champ Description, entrez la description de la capacité.

## <a name="assign-capability-to-a-resource"></a>Affecter la capacité à une ressource
1. Cliquez sur Ajouter.
2. Dans le champ Ressource, entrez l’ID de la capacité de la ressource.
    * Une capacité de la ressource peut être affectée à une ou plusieurs ressources.  
3. Dans le champ Expiration, entrer une date et une heure.
    * Vous pouvez utiliser ce champ pour spécifier qu’une ressource a la capacité pour une durée limitée uniquement.  
4. Dans le champ Priorité, entrer un numéro.
    * Lorsque vous planifiez des tâches et des opérations, vous pouvez spécifier si les ressources doivent être sélectionnées par priorité ou non. Si vous choisissez de le faire et que plusieurs ressources peuvent exécuter la tâche ou l’opération pour la date demandée, la ressource ayant la priorité la plus faible par rapport à la capacité nécessaire est sélectionnée.  
5. Dans le champ Niveau, entrez un nombre.
    * Si vous spécifiez qu’une tâche ou une opération nécessite une capacité particulière, vous pouvez également spécifier le niveau minimal requis. Utilisez le niveau de la capacité pour différencier les ressources capables d’effectuer la même tâche, mais à des vitesses, des forces, des tailles, etc. différentes.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]