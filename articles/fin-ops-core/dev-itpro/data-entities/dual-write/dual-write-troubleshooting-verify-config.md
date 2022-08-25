---
title: Vérifier la configuration en double écriture dans les applications de finances et d’opérations et Dataverse
description: Cet article explique comment déterminer si la double écriture est configurée dans les applications de finances et d’opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 4ff7821fce661f174f57fb45667d4ceb3cfcede9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289388"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Vérifier la configuration en double écriture dans les applications de finances et d’opérations et Dataverse

[!include [banner](../../includes/banner.md)]





Cet article fournit des informations sur le dépannage de l’intégration de la double-écriture entre les applications de finances et d’opérations et Dataverse. Notamment, elle explique comment déterminer si la double écriture est configurée dans les applications de finances et d’opérations et Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Vérifier que la configuration en double écriture est configurée dans l’application de finances et d’opérations

Pour déterminer si les erreurs que vous voyez lorsque vous essayez d’enregistrer des lignes pour la mise à jour proviennent de la double écriture, vérifiez d’abord que la double écriture est configurée.

+ Si vous avez des privilèges d’administrateur dans l’application de finances et d’opérations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**. Si les détails des environnements liés et la liste des cartes de tables en cours d’exécution sont affichés, la double écriture est configurée.

    ![Vérification de la connexion à l’application de finances et d’opérations lorsque vous avez les privilèges d’administrateur.](media/verify_fin_ops_1.png)

+ Si vous ne disposez pas des privilèges d’administrateur, vous recevrez un message d’erreur, *Impossible d’écrire des données dans l’entité \<entity name\>*. Dans l’exemple de l’illustration suivante, vous ne pouvez pas créer une ligne client dans l’application de finances et d’opérations, car la double écriture est configurée, mais les données de référence du groupe de clients et des conditions de paiement n’existent pas dans Dataverse.

    ![Vérification de la connexion à l’application de finances et d’opérations lorsque vous n’avez pas les privilèges d’administrateur.](media/verify_fin_ops_2.png)

Pour plus d’informations sur la résolution des problèmes lors de la création de données dans les applications de finances et d’opérations, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Vérifier que la double écriture est configurée dans Dataverse

Lorsque vous créez des données, si vous voyez la colonne **Société** sur les pages dans Dataverse, la double écriture est configurée.

![Vérification de la connexion Dataverse.](media/verify_cds.png)

Pour plus d’informations sur la résolution des problèmes lors de la création de données dans Dataverse, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).

Pour plus d’informations sur la façon d’afficher les détails des erreurs si vous rencontrez des erreurs lors de la création de données dans Dataverse, voir [Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
