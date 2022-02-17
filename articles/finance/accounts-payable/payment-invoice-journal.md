---
title: Appliquer un échéancier de paiement au journal des factures
description: Cette rubrique décrit comment ajouter un paiement au journal des factures fournisseur.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: bd288ac48ef59d8e2a4e0922aa652276dddb666d
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075586"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Appliquer un échéancier de paiement au journal des factures

[!include [banner](../includes/preview-banner.md)]

Dans Microsoft Dynamics 365 Finance version 10.0.25, un échéancier de paiement est désormais pris en charge sur le journal des factures fournisseur.

Pour utiliser cette fonctionnalité, vous devez activer la fonctionnalité **Appliquer l’échéancier de paiement au journal des factures** dans la gestion des fonctionnalités.

Une fois la fonctionnalité activée, un nouveau champ **Calendrier de paiement** est ajouté à la page **Journal des factures**. Lorsque vous créez une ligne journal des factures, si les conditions de paiement sont gérées pour le fournisseur et que les conditions de paiement sont sélectionnées sur l’échéancier de paiement, le champ **Calendrier de paiement** est mis à jour sur la page **Journal des factures**.

Vous pouvez modifier l’échéancier de paiement utilisé en fonction des besoins de votre entreprise. Lors de la validation du journal des factures fournisseur, les transactions fournisseur en cours seront créées en fonction de l’échéancier de paiement.

Pour consulter plusieurs transactions fournisseur en cours générées à partir de l’échéancier de paiement, accédez à **Comptes à payer \> Factures \> Ouvrir les factures fournisseur**, et entrez le numéro de facture ou le compte fournisseur.

Pour consulter ou configurer le calendrier des paiements, accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Échéancier de paiement**.

Pour configurer les conditions de paiement et attribuer un échéancier de paiement, accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Conditions de paiement**.

Pour gérer les conditions de paiement d’un fournisseur, accédez à **Comptabilité fournisseur \> Tous les fournisseurs**, sélectionnez le compte fournisseur, puis, sur l’onglet **Paiement**, définissez le champ **Conditions de paiement**.

La fonction d’échéancier de paiement est également disponible dans le processus **Registre des factures fournisseur**. Si un échéancier de paiement est sélectionné dans le journal du registre des factures, plusieurs lignes de paiement fournisseur ne seront **pas** générées lors de la validation du registre des factures. Les lignes de paiement fournisseur seront générées lorsque la facture sera approuvée.

## <a name="limitation"></a>Limitation

Pour une facture fournisseur en attente, si l’échéancier de paiement figure sur l’en-tête de la facture, une page avancée permet aux utilisateurs de modifier les lignes de paiement. (Par exemple, les utilisateurs peuvent modifier la date d’échéance et la valeur de chaque ligne de paiement.) Les lignes de paiement générées à partir du journal des factures auront la valeur de l’échéancier de paiement.

Cette fonctionnalité sera disponible pour le journal des factures fournisseur et les factures en attente dans une prochaine version.
