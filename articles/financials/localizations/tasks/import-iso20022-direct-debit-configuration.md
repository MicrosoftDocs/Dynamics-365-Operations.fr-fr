---
title: Importer la configuration du débit direct ISO20022
description: Cette procédure montre comment importer une configuration de génération d'états électroniques pour un paiement client.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eee00021f49ac0110d7bde07faba8095348e1b4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852641"
---
# <a name="import-iso20022-direct-debit-configuration"></a>Importer la configuration du débit direct ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment importer une configuration de génération d'états électroniques pour un paiement client. Cette procédure utilise le format de débit direct ISO 20022 comme exemple. 



Cette procédure a été créée à l'aide de la société fictive DEMF, mais vous pouvez utiliser n'importe quelle société fictive à cet effet.



Il s'agit de la première des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Dans la liste des fournisseurs de configuration disponibles, sélectionnez Microsoft.
3. Cliquez sur Activer.
4. Cliquez sur Référentiels.
5. Cliquez sur Ouvrir.
6. Cliquez sur Afficher les filtres.
7. Appliquez les filtres suivants : entrez la valeur de filtre « Débit direct ISO20022 (Allemagne) » dans le champ « Nom de la configuration » à l'aide de l'opérateur de filtre « commence par ».
    * Vous pouvez éventuellement rechercher la configuration dans la liste, la sélectionner et ignorer cette étape.  
8. Cliquez sur Importer.
    * Si le bouton Importer n'est pas disponible, cela signifie que la configuration a déjà été importée.  
9. Cliquez sur Oui.

