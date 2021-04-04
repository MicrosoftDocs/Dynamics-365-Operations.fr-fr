---
title: Réévaluer les paiements de location liés à un taux d’indexation
description: Cette rubrique décrit l’ajustement effectué pour louer le passif d’un droit d’utilisation de l’actif lorsque les paiements de location variables changent en raison d’une modification du taux d’indexation.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 79e8922a6118693db941ec259a2a1004e3522954
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241368"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Réévaluer les paiements de location liés à un taux d’indexation

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l’ajustement effectué sur le passif locatif d’un droit d’utilisation de l’actif lorsque les paiements de location variables changent en raison d’une modification du taux d’indexation. Le passif locatif et le droit d’utilisation de l’actif seront ajustés pour tenir compte des nouveaux montants du paiement. Selon la codification des normes comptables 842 (ASC 842), qui est la norme des principes comptables généralement reconnus aux États-Unis (US GAAP), seuls les paiements variables changent lorsque les paiements augmentent ou diminuent en raison d’un changement du taux d’indexation, sauf s’il y a modifications supplémentaires des flux de trésorerie. Ces modifications supplémentaires peuvent inclure une modification des conditions de location liée aux taux d’intérêt. Pour plus d’informations, voir ASC 842-10-55-225 et le paragraphe 42 (b) de la norme internationale d’information financière 16 (IFRS 16).

## <a name="adjust-lease-payments"></a>Ajuster des paiements de location

Procédez comme suit pour réévaluer les paiements de location liés à un taux d’indexation.

1. Pour exécuter le processus de réévaluation de l’index de location, accédez à **Location d’actifs \> Périodique \> Réévaluation du taux d’indexation**.

    La page **Réévaluation du taux d’indexation** apparaît et affiche tous les précédents processus de réévaluation de l’indice de location qui ont été exécutés. Les informations sur cette page comprennent l’ID de processus généré à partir de la configuration de la souche de N°, l’entité juridique, le nombre de registres de location qui ont été ajustés, l’ajustement total du passif pour les contrats de location IFRS 16 et le total des paiements variables qui ont été ajustés pour les baux ASC 842.

2. Pour exécuter la réévaluation, dans le volet Actions, sélectionnez **Réévaluation de l’indice de location**.

    La boîte de dialogue **Paramètres de réévaluation de l’indice** apparaît. Ici, vous pouvez filtrer et sélectionner les baux, groupes de baux ou autres critères à utiliser lorsque vous sélectionnez les baux à réévaluer. De plus, sur l’onglet **Exécuter en arrière-plan**, vous pouvez configurer le processus de réévaluation de l’index pour qu’il s’exécute dans un lot.

4. Sélectionnez les filtres pour sélectionner les baux à inclure dans le traitement en arrière-plan, puis sélectionnez **OK**.

    La boîte de dialogue **Version préliminaire de la réévaluation du taux d’indexation** apparaît et affiche les baux qui seront réévalués. Il montre également les ajustements d’actif et de passif ou les ajustements de paiement variable.
    
5. Pour empêcher la réévaluation des baux, sélectionnez les baux qui **devraient** être réévalués. Si vous ne sélectionnez aucun bail, tous les baux seront réévalués. Lorsque vous avez terminé, sélectionnez **OK** pour réévaluer les paiements de location.
6. Pour afficher les transactions qui ont été créées pour un processus de réévaluation d’index spécifique, sélectionnez l’ID de processus, puis sélectionnez **Transactions**.

    Une boîte de dialogue apparaît et affiche les détails des transactions créées lors du traitement.

> [!NOTE]
> Seuls les contrats de location dont la date de réévaluation est égale ou antérieure à la date système peuvent être réévalués. Le système ignore automatiquement tous les contrats de location dont la date de réévaluation est postérieure à la date système.

## <a name="asc-842-leases--index-revaluation"></a>Baux ASC 842 – Réévaluation de l’indice

Pour afficher les effets du processus de réévaluation des baux sur les baux ASC 842, ouvrez l’échéancier de paiement d’un bail. La page affiche uniquement les paiements variables qui ont été effectués le ou après la date de réévaluation a été modifiée en raison de la réévaluation de l’indice. Les plans d’amortissement restent inchangés. Lorsque vous créez une facture avec un paiement variable, le paiement variable est débité du compte de comptabilisation des paiements variables. Le montant du paiement variable est également ajouté à l’écriture de crédit qui est imputée directement au fournisseur, ou imputée au compte de paiement Notes, en fonction de la configuration du registre de location.

Les lignes d’échéancier de paiement sur la page des détails du bail sont automatiquement mises à jour avec une nouvelle ligne qui indique le nouveau taux d’indexation. En outre, une colonne indique si la ligne a été créée manuellement ou via le processus de réévaluation de l’indice.

## <a name="ifrs-16-leases--index-revaluation"></a>Baux IFRS 16 – Réévaluation de l’indice

Pour afficher les effets du processus de réévaluation des baux sur les baux IFRS 16, ouvrez les détails du bail pour un bail ajusté. Les champs **Durée du bail** et **Durée de vie utile des actifs** ont été mis à jour pour refléter le passage du temps entre la date de début ou la date de modification et la date de réévaluation. En outre, les lignes d’échéancier de paiement ont été mises à jour pour refléter les nouveaux paiements sur le contrat de location, le nouveau taux d’indexation et la façon dont la ligne a été créée.

Vous pouvez afficher l’échéancier de paiement nouvellement généré qui commence à la date de réévaluation et afficher le montant total du règlement mis à jour. Un nouveau calendrier d’amortissement du passif locatif et un calendrier d’amortissement des actifs ont également été créés pour refléter l’échéancier de paiement ajusté.

L’écriture de journal a automatiquement enregistré l’écriture de journal d’ajustement dans le compte pour la modification des paiements de location liée à la réévaluation de l’indice.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]