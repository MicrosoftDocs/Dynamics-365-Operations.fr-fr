---
title: Actifs entrants et sortants
description: Cet article explique comment enregistrer des actifs entrants et sortants dans Gestion des actifs.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd7482cfe943347840e9fb070151d66fbe5ef9ca
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016534"
---
# <a name="inbound-and-outbound-assets"></a>Actifs entrants et sortants

[!include [banner](../../includes/banner.md)]

 

Si votre société effectue des tâches de réparation ou de maintenance sur les actifs reçus d’autres emplacements ou clients, Gestion des actifs peut suivre les actifs entrants vers votre société et les actifs sortants qui sont retournées.

> [!NOTE]
> Si vous souhaitez utiliser des états du cycle de vie entrant et sortant pour gérer les actifs entrants et étant retournés, vous devez paramétrer des états de cycle de vie de demande de maintenance et des modèles de cycle de vie pour prendre en charge ces actions. Pour plus d’informations, voir [Demandes de maintenance](/d365F-O/supply-chain/asset-management/manage-maintenance-requests/../manage-maintenance-requests/maintenance-request-overview).

Le paramétrage de Gestion des actifs détermine si vous pouvez utiliser les actifs entrants et sortants.

## <a name="register-assets-as-inbound"></a>Enregistrer les actifs comme entrants

1. Sélectionnez **Gestion des actifs** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.
2. Sélectionnez la demande de maintenance.
3. Sélectionnez **Mettre à jour l’état de la demande de maintenance**.
4. Sélectionnez **Entrant** (ou un autre état du cycle de vie créé pour les actifs entrants), puis **OK**.

![Enregistrer les actifs comme entrants.](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Enregistrer les actifs entrants comme reçus

1. Sélectionnez **Gestion des actifs** \> **Entrant/sortant** \> **Actifs entrants**.
2. Sélectionnez l’actif ou la demande de maintenance.
3. Sélectionnez **Recevoir des actifs**.
4. Dans le champ **Reçu**, entrez de date et l’heure. Puis sélectionnez **OK**. L’enregistrement est supprimé de la page de liste **Actifs entrants**.

![Enregistrer les actifs entrants comme reçus.](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Enregistrer les actifs comme sortants

Lorsque vous avez terminé la tâche de maintenance ou de réparation, vous pouvez enregistrer l’actif comme retourné.

1. Sélectionnez **Gestion des actifs** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.
2. Sélectionnez la demande de maintenance.
3. Sélectionnez **Mettre à jour l’état de la demande de maintenance**.
4. Sélectionnez **Sortant** (ou un autre état du cycle de vie créé pour les actifs sortants), puis **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Enregistrer les actifs sortants comme livrés

1. Sélectionnez **Gestion des actifs** \> **Entrant/sortant** \> **Actifs sortrants**.
2. Sélectionnez l’actif ou la demande de maintenance.
3. Sélectionnez **Livrer les actifs**.
4. Dans le champ **Livré**, entrez de date et l’heure. Puis sélectionnez **OK**. L’enregistrement est supprimé de la page de liste **Actifs sortants**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]