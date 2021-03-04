---
title: Vérifier que la double écriture est configurée dans les applications Finance and Operations et Dataverse
description: Cette rubrique explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f389bcf133cc7e6a086167d5e26c1b8795d0fa30
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685537"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-dataverse"></a>Vérifier que la double écriture est configurée dans les applications Finance and Operations et Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse. Notamment, elle explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Vérifier que la double écriture est configurée dans une application Finance and Operations

Pour déterminer si les erreurs que vous voyez lorsque vous essayez d’enregistrer des lignes pour la mise à jour proviennent de la double écriture, vérifiez d’abord que la double écriture est configurée.

+ Si vous avez des privilèges d’administrateur dans l’application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**. Si les détails des environnements liés et la liste des cartes de tables en cours d’exécution sont affichés, la double écriture est configurée.

    ![Vérification de la connexion à l’application Finance and Operations lorsque vous disposez de privilèges d’administrateur](media/verify_fin_ops_1.png)

+ Si vous ne disposez pas des privilèges d’administrateur, vous recevrez un message d’erreur, *Impossible d’écrire des données dans l’entité \<entity name\>*. Dans l’exemple de l’illustration suivante, vous ne pouvez pas créer une ligne client dans l’application Finance and Operations, car la double écriture est configurée, mais les données de référence du groupe de clients et des conditions de paiement n’existent pas dans Dataverse.

    ![Vérification de la connexion à l’application Finance and Operations lorsque vous ne disposez pas de privilèges d’administrateur](media/verify_fin_ops_2.png)

Pour plus d’informations sur la résolution des problèmes lors de la création de données dans les applications Finance and Operations, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Vérifier que la double écriture est configurée dans Dataverse

Lorsque vous créez des données, si vous voyez le champ **Société** sur les pages dans Dataverse, la double écriture est configurée.

![Vérification de la connexion Dataverse](media/verify_cds.png)

Pour plus d’informations sur la résolution des problèmes lors de la création de données dans Dataverse, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

Pour plus d’informations sur la façon d’afficher les détails des erreurs si vous rencontrez des erreurs lors de la création de données dans Dataverse, voir [Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]