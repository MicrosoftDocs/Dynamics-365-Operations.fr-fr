---
title: Comptes de validation de cession d’immobilisations
description: Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité afin de céder des immobilisations.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c82cb8b82f2cc8424675f76c68613a2b5aa76745
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675516"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Comptes de validation de cession d’immobilisations

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité lorsque vous cédez des immobilisations.

Pour configurer les comptes de validation de la comptabilité à utiliser lors de la cession d’une immobilisation, sélectionnez **Cession – Vente** et **Cession - Mise au rebut** dans le raccourci **Comptes généraux** de la page **Profils de validation d’immobilisation**.

Pour les deux types de transactions (cession d’une immobilisation par vente ou mise au rebut), le compte général est crédité de la valeur de cession de l’immobilisation. Le débit est validé dans un compte de contrepartie, par exemple un compte bancaire. Si des immobilisations sont vendues à un client, le compte client est utilisé à la place du compte de contrepartie. Pour plus d’informations, voir [Céder des immobilisations en tant que rebut](dispose-of-a-fixed-asset-as-scrap.md).

Cliquez sur **Cession**, puis sur **Vente** ou **Mise au rebut**, puis paramétrez les comptes détaillés pour contrepasser la valeur nette de l’immobilisation. Vous pouvez également entrer des informations dans les champs **Valeur d’acquisition** et **Type de prix de vente** dans la page **Paramètres de cession**. 

La transaction de cession d’une immobilisation dans un regroupement de faible valeur réduit la valeur nette de ce regroupement du montant vendu uniquement. Toutefois, si la vente d’une immobilisation est supérieure à la valeur nette du regroupement de faible valeur, la valeur nette est réduite à zéro.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
