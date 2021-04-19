---
title: Confirmer les échéanciers de paiement par lots de la location d’actifs
description: Cette rubrique explique comment confirmer plusieurs échéanciers de paiement par lot.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9a3bd7293fed4b8df5d7bd76edacbcae253aa1f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816074"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Confirmer les échéanciers de paiement par lots de la location d’actifs

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment confirmer plusieurs échéanciers de paiement par lot. Les échéanciers de paiement sont confirmés sur une base de location-à-location, soit par le biais du processus de confirmation par lot. Une écriture de journal ne peut être validée que pour une location dont l’échéancier de paiement est confirmé. La confirmation de l’échéancier de paiement sert d’approbation finale des informations financières de la location. Toutes les modifications futures des informations financières relatives à la location, telles que les paiements et la durée du bail, constituent un ajustement de la location et doivent être traitées de cette manière.

Pour confirmer plusieurs échéanciers de paiement, procédez comme suit.

1. Aller à **Location d’actifs \> Périodique \> Confirmation par lot**.
2. Sur la page **Confirmation par lot**, sélectionnez **Confirmation par lot**.
3. Dans la boîte de dialogue qui s’affiche, filtrez les registres que vous souhaitez confirmer.

    - Pour confirmer tous les registres d’un groupe de location spécifique, sélectionnez le groupe dans le champ **Groupe de location**.
    - Pour confirmer des registres spécifiques, sélectionnez les registres dans le champ **ID de registre**.
    - Pour confirmer tous les registres, activez le paramètre **Pour tous les registres**.

Les informations relatives aux registres nouvellement confirmés sont affichées sur la page **Registres confirmés**. Une fois les échéanciers de paiement confirmés, les écritures de journal de reconnaissance initiale peuvent être imputées aux locations.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]