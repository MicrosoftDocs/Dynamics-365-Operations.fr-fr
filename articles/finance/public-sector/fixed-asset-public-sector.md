---
title: Immobilisations dans le secteur public
description: Cet article décrit la fonctionnalité des immobilisations disponible pour le secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTransfer
audience: Application User
ms.reviewer: roschlom
ms.custom: 20891
ms.assetid: 552c7969-f044-4774-82ec-080aeae8cf3f
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c1d227689fd96a296ee1b0f06a94153647ab87d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971167"
---
# <a name="fixed-assets-in-the-public-sector"></a>Immobilisations dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article décrit la fonctionnalité des immobilisations disponible pour le secteur public. 

<a name="what-do-i-need-to-know-about-disposing-of-fixed-assets"></a>Que dois-je savoir à propos de la cession des immobilisations ?
-------------------------------------------------------

Les organisations du secteur public peuvent utiliser les propositions de rebut et de vente pour céder plus d’une immobilisation à la fois.

## <a name="why-do-i-have-to-enter-transfer-from-and-transfer-to-accounts-when-i-transfer-fixed-assets-between-funds"></a>Pourquoi dois-je entrer des comptes d’origine et de destination du transfert lorsque je transfère des immobilisations entre les fonds ?
Les organisations du secteur public ont généralement besoin des écritures équilibrées pour la dimension financière utilisée pour désigner les fonds. Lorsque vous transférez des immobilisations entre les fonds, si la dimension de fonds exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination de la page des transferts d’immobilisation. 

> [!NOTE] 
> Il ne s’agit pas d’une propriété des immobilisations ni des fonds. En revanche, il s’agit d’une propriété de la dimension financière. Lorsque vous transférez une immobilisation, si une dimension financière associée à l’immobilisation exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination. 

Les comptes d’origine et de destination ne sont pas les comptes dans lesquels la valeur nette de l’immobilisation est conservée. En revanche, Les comptes d’origine et de destination sont les comptes principaux utilisés pour équilibrer les écritures dans les dimensions financières. Ils sont utilisés uniquement lorsqu’une dimension financière pour l’immobilisation exige un équilibrage. Le compte Prov. transfert présentera une entrée de débit, et le compte Dest. transfert présentera une entrée de crédit.

Pour plus d’informations, voir [Fonds dans le secteur public](funds-public-sector.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]