---
title: Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public
description: Cette rubrique fournit des informations sur la création simultanée d’une facture et d’un enregistrement pour un nouveau fournisseur lorsqu’aucune commande d’achat n’est requise.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendImportOneTimeVendFileUpload_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56814317a430f7dd456f0f2c7833c69185ad6bb3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811203"
---
# <a name="import-and-create-multiple-one-time-vendors-and-invoices-in-the-public-sector"></a>Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public

[!include [banner](../../includes/banner.md)]

Lorsqu’une approbation ou un contrat sous forme d’une commande fournisseur n’est pas nécessaire, vous pouvez créer une facture pour un nouveau fournisseur avec vous n’entretenez pas de relation régulière, tout en créant un enregistrement pour le fournisseur. Cette procédure a été créée à l’aide des données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à Comptabilité fournisseur > Tâches périodiques > Importer des fournisseurs occasionnels et des factures.
2. Recherchez et sélectionnez le fichier CSV contenant les informations fournisseur.
3. Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Cliquez sur OK.
    * Les informations du fournisseur et de facturation sont importées. S’il existe des erreurs, un état est imprimé, et vous devez corriger les entrées répertoriées dans le fichier d’importation puis réimporter le fichier.  
6. Accédez à Comptabilité fournisseur > Tâches périodiques > Traiter les fournisseurs occasionnels et les factures.
    * Les noms de fournisseur ou les ID de taxe fédérale en double feront l’objet d’une recherche.  Important : si vous choisissez de ne pas traiter les fournisseurs en double, les factures associées ne seront pas traitées non plus. Vous pouvez créer manuellement une facture à l’aide des informations du fichier csv.    
7. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]