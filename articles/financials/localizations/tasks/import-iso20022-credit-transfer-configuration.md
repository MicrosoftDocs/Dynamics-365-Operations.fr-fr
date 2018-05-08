--- 
title: "Importer la configuration du virement ISO20022"
description: "Cette procédure indique comment importer une configuration de génération d'états électroniques pour un paiement fournisseur."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 71c0175178203006e297466c4a37cd3e6319b6ea
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importer la configuration du virement ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment importer une configuration de génération d'états électroniques pour un paiement fournisseur. Le format du virement ISO 20022 allemand est utilisé comme exemple. Cette procédure peut être utilisée pour tout autre format de génération d'états électroniques disponible. 

Cette tâche a été créée à l'aide de la société fictive DEMF, mais vous pouvez utiliser n'importe quelle société fictive pour effectuer cette tâche.

Il s'agit de la première des cinq tâches illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Dans la liste des fournisseurs de configuration disponibles, sélectionnez Microsoft.
3. Cliquez sur Activer.
4. Cliquez sur Référentiels.
5. Cliquez sur Ouvrir.
6. Cliquez sur Afficher les filtres.
7. Appliquez les filtres suivants : entrez la valeur de filtre « Virement ISO20022 (Allemagne) » dans le champ « Nom de la configuration » à l'aide de l'opérateur de filtre « commence par ».
    * Vous pouvez également rechercher la configuration dans la liste, la sélectionner et la déplacer dans la tâche d'importation.  
8. Cliquez sur Importer.
    * Si le bouton Importer n'est pas disponible, cela signifie que la configuration a déjà été importée.  
9. Cliquez sur Oui.


