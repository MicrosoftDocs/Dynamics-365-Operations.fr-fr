---
title: Amortissement des immobilisations
description: Cet article fournit une vue d’ensemble de l’amortissement dans Immobilisations.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.form: AssetBonus, AssetBookTable
ms.openlocfilehash: 9761fc9846324d1c165274b72033e195bf4ea3e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275293"
---
# <a name="fixed-asset-depreciation"></a>Amortissement des immobilisations

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article fournit une vue d’ensemble de l’amortissement dans Immobilisations.

L’amortissement est une transaction périodique qui réduit généralement la valeur des immobilisations dans le bilan et est facturé comme une dépense dans le compte de résultat. Par conséquent, un compte principal est généralement utilisé pour créditer l’amortissement périodique dans le bilan. Un compte de contrepartie est un compte dans la partie résultat du plan de comptes.

À partir de la version 10.0.24, l’option de configuration du registre des immobilisations **Calculer l’amortissement positif** de la page **Registres** permet à l’amortissement de débiter une immobilisation acquise avec une valeur comptable négative (crédit).

## <a name="depreciation-adjustment"></a>Ajustement de l’amortissement
En règle générale, seule la correction d’une transaction d’amortissement déjà validée peut être validée en tant qu’ajustement d’amortissement. Par conséquent, le compte principal et le compte de contrepartie sont paramétrés de la même manière que les comptes d’amortissement. Un ajustement de l’amortissement peut correspondre à un montant positif ou négatif mais la fonctionnalité du compte principal (en tant que compte de bilan) et de la fonctionnalité du compte de contrepartie (généralement en tant que compte de résultat) reste la même.

## <a name="extraordinary-depreciation"></a>Amortissement exceptionnel
L’amortissement exceptionnel fonctionne comme un amortissement de base. Par conséquent, un compte principal est utilisé pour créditer le montant de l’amortissement sur le bilan et réduire la valeur de l’immobilisation. Un compte de contrepartie est un compte de résultat dans lequel l’amortissement calculé pour la période fiscale est facturé comme dépense. 

Un amortissement exceptionnel fonctionne indépendamment de l’amortissement de base. En définissant l’amortissement exceptionnel en tant que type de transaction distinct, vous pouvez valider et de déclarer l’amortissement exceptionnel indépendamment de l’amortissement ordinaire, de base.

## <a name="special-depreciation-allowance"></a>Provision spéciale pour amortissement
Vous pouvez utiliser des provisions spéciales pour l’amortissement pour prendre des montants d’amortissement exceptionnels durant la première année de mise en service et d’amortissement d’une immobilisation. Les provisions spéciales pour amortissement doivent être prises avant tout autre calcul d’amortissement. Comme les provisions spéciales pour amortissement sont souvent inconnues jusqu’à ultérieurement dans la vie de l’immobilisation, il est recommandé d’utiliser ce type d’amortissement avec un registre qui ne valide pas dans la comptabilité. Vous pouvez utiliser la fonctionnalité périodique Supprimer les transactions non validées dans la comptabilité pour supprimer l’historique des transactions pour ces registres. Vous pouvez ensuite supprimer l’historique d’amortissement pour le registre des immobilisations, valider la provision spéciale pour amortissement lorsqu’elle est connue, puis valider les transactions d’amortissement restantes pour l’année. 

Vous pouvez créer un nombre illimité d’enregistrements de provision spéciale pour amortissement. Une fois que vous affectez ces enregistrements à un registre de groupe d’immobilisations, ils sont appliqués au registre des immobilisations. 

Une provision spéciale pour amortissement est entrée comme pourcentage ou montant fixe. Lorsque vous validez des propositions d’amortissement, les transactions de provision spéciale pour amortissement sont validées dans le registre comme transactions distinctes des transactions d’amortissement.

## <a name="depreciation-calendars"></a>Calendriers d’amortissement
Chaque registre possède un calendrier utilisé lorsque vous amortissez des immobilisations. Par défaut, si vous n’indiquez pas le calendrier sur le registre, celui-ci utilise le calendrier fiscal. Vous devez sélectionner un calendrier fiscal pour un registre lorsque le profil d’amortissement associé au registre utilise une année d’amortissement fiscal. 

Vous pouvez créer des calendriers partagés à l’aide de la page **Calendriers fiscaux** dans Comptabilité.

Pour plus d’informations, voir [Méthodes et conventions d’amortissement](depreciation-methods-conventions.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
