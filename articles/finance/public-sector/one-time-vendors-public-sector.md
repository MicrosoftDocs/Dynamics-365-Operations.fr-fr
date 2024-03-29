---
title: Fournisseurs occasionnels dans le secteur public
description: Cet article fournit des informations sur la création d’un fournisseur occasionnel et d’une facture, et sur l’importation et la création de plusieurs fournisseurs occasionnels et factures.
author: TaylorVH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: TaylorVH
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 19801
ms.assetid: 403857a3-bebb-4ff7-b1b5-c88f41fc18ae
ms.search.industry: Public sector
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
ms.openlocfilehash: cf3726f6f17924ec250f2e540869d98bb72f32a5
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573068"
---
# <a name="one-time-vendors-in-the-public-sector"></a>Fournisseurs occasionnels dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la création d’un fournisseur occasionnel et d’une facture, et sur l’importation et la création de plusieurs fournisseurs occasionnels et factures. 

Il peut arriver que vous deviez créer une facture pour un nouveau fournisseur avec qui vous n’avez pas de relation régulière. Dans Dynamics 365 Finance, si une approbation ou un contrat sous la forme d’une commande fournisseur n’est pas nécessaire, vous pouvez rapidement créer une facture tout en créant un enregistrement pour le fournisseur. Par exemple, vous devez payer des référents ou effectuer des remboursements, mais il n’existe pas d’enregistrement pour le fournisseur. Vous pouvez toujours créer plusieurs factures pour de nouveaux fournisseurs avec qui vous n’avez pas de relation régulière. Si ni une approbation ni une commande fournisseur ne sont nécessaires, vous pouvez rapidement créer des factures en même temps que vous créez des enregistrements pour les fournisseurs. Par exemple, vous souhaitez peut-être prendre en charge les paiements fournisseur à des fins juridiques, de paiement d’enregistrement et de remboursement de clients ou pour d’autres paiements pour lesquels il n’existe pas d’enregistrements fournisseur principaux. Pour plus d’informations, voir [Plan pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).

## <a name="how-do-i-create-a-onetime-vendor-and-invoice"></a>Comment créer un fournisseur occasionnel et une facture ?
L’enregistrement fournisseur utilise les valeurs du compte fournisseur occasionnel par défaut, sauf si de nouvelles valeurs sont spécifiées. Ce compte est spécifié dans la section **Général** de la page **Paramètres de la comptabilité fournisseur**. Pour afficher les détails du compte, accédez à la page **Tous les fournisseurs**, puis double-cliquez sur le numéro de compte du fournisseur occasionnel par défaut.

## <a name="how-do-i-import-and-create-multiple-onetime-vendors-and-invoices"></a>Comment importer et créer plusieurs fournisseurs occasionnels et factures ?
Pour créer plusieurs fournisseurs et factures occasionnels, commencez par créer un fichier contenant les informations du fournisseur et de facturation, puis importez le fichier dans une table intermédiaire. Traitez ensuite le fichier importé et générez les factures. Pour plus d’informations sur la manière de créer le fichier, voir [Plan pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
