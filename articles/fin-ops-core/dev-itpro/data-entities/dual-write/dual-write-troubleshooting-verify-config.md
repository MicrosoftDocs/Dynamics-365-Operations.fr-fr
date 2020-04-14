---
title: Vérifier que la double écriture est configurée dans les applications Finance and Operations et Common Data Service
description: Cette rubrique explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172643"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Vérifier que la double écriture est configurée dans les applications Finance and Operations et Common Data Service

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service. Notamment, elle explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Vérifier que la double écriture est configurée dans une application Finance and Operations

Pour déterminer si les erreurs que vous voyez lorsque vous essayez de sauvegarder des enregistrements pour la mise à jour proviennent de la double écriture, vérifiez d'abord que la double écriture est configurée.

+ Si vous avez des privilèges d'administrateur dans l'application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**. Si les détails des environnements liés et la liste des cartes d'entités en cours d'exécution sont affichés, la double écriture est configurée.

    ![Vérification de la connexion à l'application Finance and Operations lorsque vous disposez de privilèges d'administrateur](media/verify_fin_ops_1.png)

+ Si vous ne disposez pas des privilèges d'administrateur, vous recevrez un message d'erreur, *Impossible d'écrire des données dans l'entité \<nom d'entité\>*. Dans l'exemple de l'illustration suivante, vous ne pouvez pas créer un enregistrement client dans l'application Finance and Operations, car la double écriture est configurée, mais les données de référence du groupe de clients et des conditions de paiement n'existent pas dans Common Data Service.

    ![Vérification de la connexion à l'application Finance and Operations lorsque vous ne disposez pas de privilèges d'administrateur](media/verify_fin_ops_2.png)

Pour plus d'informations sur la résolution des problèmes lors de la création de données dans les applications Finance and Operations, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Vérifier que la double écriture est configurée dans Common Data Service

Lorsque vous créez des données, si vous voyez le champ **Société** sur les pages dans Common Data Service, la double écriture est configurée.

![Vérification de la connexion Common Data Service](media/verify_cds.png)

Pour plus d'informations sur la résolution des problèmes lors de la création de données dans Common Data Service, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

Pour plus d'informations sur la façon d'afficher les détails des erreurs si vous rencontrez des erreurs lors de la création de données dans Common Data Service, voir [Activer et afficher le journal de suivi des plug-ins dans Common Data Service pour afficher les détails de l'erreur](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
