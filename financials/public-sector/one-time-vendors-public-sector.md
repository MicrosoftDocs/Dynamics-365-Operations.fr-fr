---
title: Fournisseurs occasionnels dans le secteur public
description: "Cet article fournit des informations sur la création d&quot;un fournisseur occasionnel et d&quot;une facture, et sur l&quot;importation et la création de plusieurs fournisseurs occasionnels et factures."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19801
ms.assetid: 403857a3-bebb-4ff7-b1b5-c88f41fc18ae
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: d64f9228c538a08a2fc938bc6ff4ce11278b6fed
ms.openlocfilehash: a0f4051ec32891396dc4ebf6bd5d19b8ba7cc3ec
ms.lasthandoff: 03/31/2017


---

# <a name="one-time-vendors-in-the-public-sector"></a>Fournisseurs occasionnels dans le secteur public

Cet article fournit des informations sur la création d'un fournisseur occasionnel et d'une facture, et sur l'importation et la création de plusieurs fournisseurs occasionnels et factures. 

Il peut arriver que vous deviez créer une facture pour un nouveau fournisseur avec qui vous n'avez pas de relation régulière. Dans Microsoft Dynamics 365 pour les opérations, si l'approbation ou un contrat sous forme de commande fournisseur n'est pas nécessaire, vous pouvez créer rapidement une facture lorsque vous créez un enregistrement pour le fournisseur. Par exemple, vous devez payer des référents ou effectuer des remboursements, mais il n'existe pas d'enregistrement pour le fournisseur. Vous pouvez toujours créer plusieurs factures pour de nouveaux fournisseurs avec qui vous n'avez pas de relation régulière. Si ni une approbation ni une commande fournisseur ne sont nécessaires, vous pouvez rapidement créer des factures en même temps que vous créez des enregistrements pour les fournisseurs. Par exemple, vous souhaitez peut-être prendre en charge les paiements fournisseur à des fins juridiques, de paiement d'enregistrement et de remboursement de clients ou pour d'autres paiements pour lesquels il n'existe pas d'enregistrements fournisseur principaux. Pour plus d'informations, voir [planification pour les fournisseurs occasionnels dans le du secteur public] (plan-one-time-vendors-public-sector.md).

## <a name="how-do-i-create-a-onetime-vendor-and-invoice"></a>Comment crée un fournisseur ci-devant et facture ?
L'enregistrement fournisseur utilise les valeurs du compte fournisseur occasionnel par défaut, sauf si de nouvelles valeurs sont spécifiées. Ce compte est spécifié dans la section **Général** de la page **Paramètres de la comptabilité fournisseur**. Pour afficher les détails du compte, accédez à la page **Tous les fournisseurs**, puis double-cliquez sur le numéro de compte du fournisseur occasionnel par défaut.

## <a name="how-do-i-import-and-create-multiple-onetime-vendors-and-invoices"></a>Comment importe et crée des fournisseurs et des factures ci-devant plusieurs ?
Pour créer les fournisseurs occasionnels et plusieurs factures, commencez par créer un fichier qui contient le fournisseur et les informations de facturation, et d'après le fichier dans une table intermédiaire dans Microsoft Dynamics 365 pour les opérations. Traitez ensuite le fichier importé et générez les factures. Pour plus d'informations sur la manière de créer le fichier, voir [Planification pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).  


