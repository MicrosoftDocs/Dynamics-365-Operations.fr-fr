---
title: Comptes de validation de cession d'immobilisations
description: Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité afin de céder des immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a46125dbe5262ba388e3958ea452975a98243f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187151"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Comptes de validation de cession d'immobilisations

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité afin de céder des immobilisations.

Sur la page Profils de validation des immobilisations, sur l'organisateur Comptes généraux, sélectionnez Cession - Vente et cession - Mise au rebut pour paramétrer les validations de la comptabilité.

Pour les deux types de transactions, le compte général est crédité de la valeur de cession de l'immobilisation. Le débit est validé dans un compte de contrepartie (un compte bancaire, par exemple). Si des immobilisations sont vendues à un client, le compte client est utilisé à la place du compte de contrepartie.

Cliquez sur Cession, puis sur Vente ou Mise au rebut, puis paramétrez les comptes détaillés pour contrepasser la valeur nette de l'immobilisation. Vous pouvez également entrer des informations dans les champs Valeur d'acquisition et Prix de vente dans la page Paramètres de cession. 

La transaction de cession d'une immobilisation dans un regroupement de faible valeur réduit la valeur nette de ce regroupement du montant vendu uniquement. Toutefois, si la vente d'une immobilisation est supérieure à la valeur nette du regroupement de faible valeur, la valeur nette est réduite à zéro.





