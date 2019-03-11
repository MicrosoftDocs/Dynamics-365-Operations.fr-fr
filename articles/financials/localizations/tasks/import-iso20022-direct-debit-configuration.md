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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1757a1477e46f71e327bb70cf4780767b7509e55
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "333068"
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

