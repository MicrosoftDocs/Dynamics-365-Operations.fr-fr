---
title: Confirmer les échéanciers de paiement par lots de la location d’actifs
description: Cet article explique comment confirmer plusieurs échéanciers de paiement par lot.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd75e22f6407d6bc25a78c1dfeacf70022238e94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895049"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Confirmer les échéanciers de paiement par lots de la location d’actifs

[!include [banner](../includes/banner.md)]

Cet article explique comment confirmer plusieurs échéanciers de paiement par lot. Les échéanciers de paiement sont confirmés sur une base de location-à-location, soit par le biais du processus de confirmation par lot. Une écriture de journal ne peut être validée que pour une location dont l’échéancier de paiement est confirmé. La confirmation de l’échéancier de paiement sert d’approbation finale des informations financières de la location. Toutes les modifications futures des informations financières relatives à la location, telles que les paiements et la durée du bail, constituent un ajustement de la location et doivent être traitées de cette manière.

Pour confirmer plusieurs échéanciers de paiement, procédez comme suit.

1. Aller à **Location d’actifs \> Périodique \> Confirmation par lot**.
2. Sur la page **Confirmation par lot**, sélectionnez **Confirmation par lot**.
3. Dans la boîte de dialogue qui s’affiche, filtrez les registres que vous souhaitez confirmer.

    - Pour confirmer tous les registres d’un groupe de location spécifique, sélectionnez le groupe dans le champ **Groupe de location**.
    - Pour confirmer des registres spécifiques, sélectionnez les registres dans le champ **ID de registre**.
    - Pour confirmer tous les registres, activez le paramètre **Pour tous les registres**.

Les informations relatives aux registres nouvellement confirmés sont affichées sur la page **Registres confirmés**. Une fois les échéanciers de paiement confirmés, les écritures de journal de reconnaissance initiale peuvent être imputées aux locations.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
