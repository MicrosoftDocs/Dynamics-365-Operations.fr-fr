---
title: Factures financières dans le secteur public
description: Cette rubrique décrit la fonctionnalité de facture financière disponible pour les entités du secteur public et répond aux questions courantes sur l’utilisation des classifications de facturation et des codes de facturation avec les factures financières.
author: v-kiarnd
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustBillingClassification, CustBillingCode, CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 25821
ms.assetid: 483e2726-ec48-4d1f-82f5-bffddea301ce
ms.search.region: Global
ms.search.industry: Public sector
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a044d332ef8208e808d2d7a3230e1f445131423d
ms.sourcegitcommit: 52a6b038d42ab28092bb942c61f5196330db3a7b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2021
ms.locfileid: "7817720"
---
# <a name="free-text-invoices-in-the-public-sector"></a>Factures financières dans le secteur public

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité de facture financière disponible pour les entités du secteur public et répond aux questions courantes sur l’utilisation des classifications de facturation et des codes de facturation avec les factures financières.

## <a name="do-i-have-to-select-a-billing-classification-for-every-free-text-invoice"></a>Dois-je sélectionner une classification de facturation pour chaque facture financière ?

Oui, lorsque les classifications de facturation sont activées, vous devez entrer une classification de facturation pour chaque facture financière. La classification de facturation contrôle quels codes facturation vous pouvez entrer sur la facture. Elle régit également les conditions générales de paiement, les souches de numéros et le traitement de la facture. Pour plus d’informations sur les classifications de facturation, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).

## <a name="what-happens-if-ive-already-created-free-text-invoices-when-i-enable-billing-classifications"></a>Que se passe-t-il si j’ai déjà créé des factures financières lorsque j’active les classifications de facturation ?
Si une facture n’était pas encore validée lorsque vous avez activé les classifications de facturation, vous devez affecter une classification de facturation à la facture avant de pouvoir la valider. Lorsque vous ouvrez la page pour afficher la facture, vous obtenez un message indiquant que la classification de facturation est requise.

## <a name="why-should-i-use-billing-codes-when-i-create-free-text-invoices"></a>Pourquoi utiliser les codes facturation lorsque je crée des factures financières ?
Lorsque vous sélectionnez un code facturation, les valeurs par défaut sont automatiquement entrées dans de nombreux champs de la ligne de facture. Cela rend la saisie de données plus rapide et plus exacte. Les codes facturation sont également utilisés avec les définitions de validation pour contrôler la façon dont les transactions de comptabilité client sont validées dans la comptabilité.

## <a name="im-creating-a-free-text-invoice-and-the-billing-code-that-i-want-to-use-isnt-available-what-should-i-do"></a>Je crée une facture financière, et le code facturation que je souhaite utiliser n’est pas disponible. Que dois-je faire ?
Assurez-vous d’abord que la facture utilise la bonne classification de facturation. Seuls certains codes facturation peuvent être utilisés avec chaque classification de facturation. Si la classification de facturation est correcte, vous devez alors sélectionner l’un des codes facturation disponibles pour la facture financière que vous créez.

## <a name="i-can-change-some-of-the-fields-on-my-free-text-invoices-all-of-the-time-and-i-can-change-all-of-the-fields-some-of-the-time-but-some-of-the-fields-i-can-only-change-some-of-the-time-whats-up-with-that"></a>Je peux modifier certains champs de mes factures financières à tout moment, et je peux modifier tous les champs une partie du temps. Mais je peux uniquement modifier certains champs une partie du temps. Qu’est-ce que cela signifie ?
Les paramètres du code facturation contrôlent si vous pouvez modifier certains champs.

-   Si le code facturation sur une ligne de facture financière n’autorise pas les modifications de taux sur la facture, vous ne pouvez pas modifier le montant, le prix unitaire ni les détails du montant sur la ligne. 

> [!TIP] 
> Si le champ **Le code facturation détermine** est défini à « prix unitaire », vous ne pouvez pas modifier le prix unitaire, mais vous pouvez modifier le montant indirectement en modifiant la quantité.

-   Si le code facturation sur une ligne de facture financière n’autorise pas les modifications aux comptes généraux, vous ne pouvez pas modifier les répartitions comptables sur la ligne. Vous pouvez modifier le compte principal qui s’affiche sur la ligne de facture financière, mais cette modification a un impact uniquement sur ce qui s’affiche. Modifier le compte principal n’affecte pas les répartitions.
-   Lorsqu’un projet est associé à la ligne de facture, le code facturation contrôle si vous pouvez modifier l’ID projet, la catégorie et le compte général. 

> [!TIP] 
> Pour modifier le compte général pour les lignes de facture associées à des projets, les modifications doivent être autorisées à la fois sur le code facturation lui-même et dans la section Projets de la page Paramètres de la comptabilité client.

Pour plus d’informations sur les codes facturation, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).

## <a name="where-does-the-interest-code-on-a-free-text-invoice-come-from"></a>D’où vient le code intérêt sur une facture financière ?
Le code intérêt peut être défini sur le code facturation, la classification de facturation ou le profil de validation.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
