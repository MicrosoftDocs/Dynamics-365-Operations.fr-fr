---
title: Immobilisations dans le secteur public
description: Cet article décrit la fonctionnalité des immobilisations disponible pour les entités du secteur public.
author: v-kiarnd
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTransfer
audience: Application User
ms.reviewer: twheeloc
ms.custom: 20891
ms.assetid: 552c7969-f044-4774-82ec-080aeae8cf3f
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbda7bcbc9da828101c9b8de77e55caaa8cb621c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888839"
---
# <a name="fixed-assets-in-the-public-sector"></a>Immobilisations dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article décrit la fonctionnalité des immobilisations disponible pour les entités du secteur public. 

## <a name="what-do-i-need-to-know-about-disposing-of-fixed-assets"></a>Que dois-je savoir à propos de la cession des immobilisations ?

Les organisations du secteur public peuvent utiliser les propositions de rebut et de vente pour céder plus d’une immobilisation à la fois.

## <a name="why-do-i-have-to-enter-transfer-from-and-transfer-to-accounts-when-i-transfer-fixed-assets-between-funds"></a>Pourquoi dois-je entrer des comptes d’origine et de destination du transfert lorsque je transfère des immobilisations entre les fonds ?
Les organisations du secteur public ont généralement besoin des écritures équilibrées pour la dimension financière utilisée pour désigner les fonds. Lorsque vous transférez des immobilisations entre les fonds, si la dimension de fonds exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination de la page des transferts d’immobilisation. 

> [!NOTE] 
> Il ne s’agit pas d’une propriété des immobilisations ni des fonds. En revanche, il s’agit d’une propriété de la dimension financière. Lorsque vous transférez une immobilisation, si une dimension financière associée à l’immobilisation exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination. 

Les comptes d’origine et de destination ne sont pas les comptes dans lesquels la valeur nette de l’immobilisation est conservée. En revanche, Les comptes d’origine et de destination sont les comptes principaux utilisés pour équilibrer les écritures dans les dimensions financières. Ils sont utilisés uniquement lorsqu’une dimension financière pour l’immobilisation exige un équilibrage. Le compte Prov. transfert présentera une entrée de débit, et le compte Dest. transfert présentera une entrée de crédit.

Pour plus d’informations, voir [Fonds dans le secteur public](funds-public-sector.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
