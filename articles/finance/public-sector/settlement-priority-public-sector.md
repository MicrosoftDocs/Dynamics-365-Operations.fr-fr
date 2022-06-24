---
title: Priorité de règlement (Secteur public)
description: Cet article fournit des informations sur la manière dont le secteur public peut hiérarchiser automatiquement ou manuellement les règlements à l’aide des classifications de facturation.
author: v-kiarnd
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustBillingClassification, CustBillingCode, CustParameters, CustSettlementPrioritySetup, LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 19551
ms.assetid: b6f96e12-5614-4edf-9f67-47bf011b6ee7
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f64266b03b3a5b156907e079f27b1e8e8e67598
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946292"
---
# <a name="settlement-priority-in-the-public-sector"></a>Priorité de règlement (Secteur public)

[!include [banner](../includes/banner.md)]

Dans Dynamics 365 Finance, vous pouvez sélectionner manuellement les transactions à régler, ou vous pouvez utiliser la fonctionnalité de règlement automatique. Les organisations du secteur public ont des options supplémentaires pour classer les règlements à l’aide des classifications de facturation. Ces options peuvent être utilisées avec le règlement automatique ou manuel.

## <a name="how-to-set-the-general-ledger-parameters-and-accounts-receivable-parameters-for-settlement-priority"></a>Comment définir les paramètres de comptabilité et les paramètres de la comptabilité client pour la priorité de règlement

Pour utiliser les classifications de facturation afin de contrôler les priorités de règlement, vous devez définir à la fois un paramètre de taxe dans l’application Comptabilité et les paramètres de règlement dans l’application Comptabilité client. 

> [!NOTE]
> Vous devez paramétrer et activer complètement vos classifications de facturation avant de définir ces paramètres. Dès que vous activez les classifications de facturation, le champ Classification de facturation devient obligatoire sur la facture financière. 

Pour plus d’informations sur les classifications de facturation, notamment la manière de les activer, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).

-   Sur la page **Paramètres de comptabilité**, dans la section **Taxe**, dans l’organisateur **Options de taxe**, sélectionnez l’option **Taxe par ligne de facture**.
-   Sur la page **Paramètres de la comptabilité client**, dans la section **Règlement**, procédez comme suit :
    -   Sélectionnez l’option permettant de marquer des lignes sur des factures financières et des notes d’intérêts.
    -   Sélectionnez l’option permettant de définir un ordre de priorité au règlement.
    -   Cliquez sur **Gérer la priorité**, puis modifiez la page pour activer l’attribut **Facturation** et définir la priorité de la ligne de facture et les paramètres associés. L’attribut **Facturation** n’est pas disponible tant que les classifications de facturation sont activées.

Trois options sont disponibles pour la priorité de la ligne de facture : **Aucun(e)**, **Code facturation** et **Ventilation**.

-   Si vous sélectionnez **Aucun(e)** pour la priorité de facture, la priorité est octroyée au règlement par les classifications de facturation. Lorsque vous effectuez cela, les paiements sont appliqués d’abord aux transactions dotées de la priorité de classification de facturation la plus élevée. Tout paiement restant est appliqué à la classification de facturation dotée de la priorité la plus élevée suivante, et ainsi de suite jusqu’à ce que tous les paiements soient effectués.
-   Si vous sélectionnez **Code facturation**, la priorité est octroyée au règlement par les classifications de facturation et les codes facturation sont utilisés pour affiner plus avant la priorité de règlement. Lorsque vous effectuez cela, vous pouvez choisir d’étendre les codes facturation à toutes les factures. Par exemple, supposons que vous ayez trois factures doté de la classification de facturation Parcs. Ces trois factures comportent quatre lignes, et chacune de ces lignes sont dotées de codes facturation.
    -   Si vous étendez les codes facturation à toutes les factures, le processus de règlement examine chacune des 12 lignes et règle le paiement en fonction de la priorité du code facturation. Par conséquent, toutes les lignes dotées du code facturation à la priorité la plus élevée sont réglées avant toute ligne dotée d’une priorité de code facturation inférieure.
    -   Si vous n’étendez pas les codes facturation à toutes les factures, le processus de règlement examine les lignes de chaque facture séparément. Toutes les lignes de la première facture sont réglées en fonction de la priorité du code facturation avant que toute ligne de la facture suivante soit réglée.
-   Si vous sélectionnez **Ventilation**, la priorité est octroyée au règlement par les classifications de facturation et la ventilation est utilisée pour affiner la priorité de règlement dans le cadre des classifications de facturation. Lorsque vous procédez ainsi, vous pouvez choisir d’utiliser la ventilation égale ou proportionnelle. Dans un cas comme dans l’autre, toutes les lignes d’une facture doivent être réglées avant que toute ligne de la facture suivante soit réglée. Par exemple, supposons que vous ayez trois factures doté de la classification de facturation Parcs. Chaque facture a quatre lignes, pour 200 €, 400 €, 600 € et 800 €. Un paiement de 2 500 € a été reçu.
    -   Si vous utilisez la ventilation égale, un montant de paiement qui ne paie pas une facture entièrement est divisé en quatre parties égales. Une partie est appliquée à chaque ligne. Le résultat pour l’exemple serait le suivant :
        -   La première facture est complètement réglée, et il reste 500 € à appliquer à la facture suivante.
        -   Les 500 € restants sont divisés en quatre parties égales de 125 € et appliqués à chaque ligne de facture de la deuxième facture.
        -   Rien n’est appliqué aux lignes de la troisième facture.
    -   Si vous utilisez la ventilation proportionnelle, un montant de paiement qui ne paie pas une facture entièrement est divisé en montants proportionnels et appliqué à chaque ligne de facture. La proportion est basée sur le montant de ligne par rapport au montant total de la facture. Le résultat pour l’exemple serait le suivant :
        -   La première facture est complètement réglée, et il reste 500 € à appliquer à la facture suivante.
        -   Les 500 € restants sont divisés en quatre quantités proportionnelles de 50 €, 100 €, 150 € et 200 €, puis appliqués aux lignes correspondantes de la deuxième facture.
        -   Rien n’est appliqué aux lignes de la troisième facture.

## <a name="how-to-set-the-settlement-priority-of-billing-codes-billing-classifications-and-settlement-attributes"></a>Comment définir la priorité de règlement des codes facturation, des classifications de facturation, et des attributs de règlement
Lors du processus de règlement, les attributs de règlement sont considérés en premier, puis les classifications de facturation, et enfin les codes facturation.

-   Après avoir ajouté des codes facturation à une classification de facturation, utilisez les boutons **Haut** et **Bas** de l’organisateur **Codes facturation** pour organiser les codes facturation par ordre de priorité. (Cela est uniquement nécessaire si vous envisagez d’utiliser **Code facturation** comme votre priorité de ligne de facture.)
-   Après avoir créé toutes les classifications de facturation pour votre organisation, utilisez les boutons **Haut** et **Bas** situés en haut de la page **Classifications de facturation** pour organiser les classifications de facturation par ordre de priorité.
-   Après avoir activé l’attribut **Facturation** sur la page **Priorité de règlement**, utilisez les boutons **Haut** et **Bas** situés en haut de la page pour organiser les attributs actifs de règlement par ordre de priorité.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
