---
title: Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public
description: Lorsqu'une approbation ou un contrat sous forme d'une commande fournisseur n'est pas nécessaire, vous pouvez créer une facture pour un nouveau fournisseur avec vous n'entretenez pas de relation régulière, tout en créant un enregistrement pour le fournisseur.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendImportOneTimeVendFileUpload_PSN
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 650215df59018d6a930e432483f5bc3d73fef692
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "370783"
---
# <a name="import-and-create-multiple-one-time-vendors-and-invoices-in-the-public-sector"></a>Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public

[!include [task guide banner](../../includes/task-guide-banner.md)]

Lorsqu'une approbation ou un contrat sous forme d'une commande fournisseur n'est pas nécessaire, vous pouvez créer une facture pour un nouveau fournisseur avec vous n'entretenez pas de relation régulière, tout en créant un enregistrement pour le fournisseur. Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à Comptabilité fournisseur > Tâches périodiques > Importer des fournisseurs occasionnels et des factures.
2. Recherchez et sélectionnez le fichier CSV contenant les informations fournisseur.
3. Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Cliquez sur OK.
    * Les informations du fournisseur et de facturation sont importées. S'il existe des erreurs, un état est imprimé, et vous devez corriger les entrées répertoriées dans le fichier d'importation puis réimporter le fichier.  
6. Accédez à Comptabilité fournisseur > Tâches périodiques > Traiter les fournisseurs occasionnels et les factures.
    * Les noms de fournisseur ou les ID de taxe fédérale en double feront l'objet d'une recherche.  Important :si vous choisissez de ne pas traiter les fournisseurs en double, les factures associées ne seront pas traitées non plus. Vous pouvez créer manuellement une facture à l'aide des informations du fichier csv.    
7. Cliquez sur OK.

