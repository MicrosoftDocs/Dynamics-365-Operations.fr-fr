---
title: Actifs entrants et sortants
description: Cette rubrique explique comment enregistrer des actifs entrants et sortants dans Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb318c24424c291f08ba7527b2258c0da4cba9a8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571666"
---
# <a name="inbound-and-outbound-assets"></a>Actifs entrants et sortants

[!include [banner](../../includes/banner.md)]

 

Si votre société effectue des tâches de réparation ou de maintenance sur les actifs reçus d'autres emplacements ou clients, Gestion des actifs peut suivre les actifs entrants vers votre société et les actifs sortants qui sont retournées.

> [!NOTE]
> Si vous souhaitez utiliser des états du cycle de vie entrant et sortant pour gérer les actifs entrants et étant retournés, vous devez paramétrer des états de cycle de vie de demande de maintenance et des modèles de cycle de vie pour prendre en charge ces actions. Pour plus d'informations, voir [Paramétrage des demandes de maintenance](../setup-for-maintenance-requests/requests.md).

Le paramétrage de Gestion des actifs détermine si vous pouvez utiliser les actifs entrants et sortants.

## <a name="register-assets-as-inbound"></a>Enregistrer les actifs comme entrants

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.
2. Sélectionnez la demande de maintenance.
3. Sélectionnez **Mettre à jour l'état de la demande de maintenance**.
4. Sélectionnez **Entrant** (ou un autre état du cycle de vie créé pour les actifs entrants), puis **OK**.

![Enregistrer les actifs comme entrants](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Enregistrer les actifs entrants comme reçus

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Entrant/sortant** \> **Actifs entrants**.
2. Sélectionnez l'actif ou la demande de maintenance.
3. Sélectionnez **Recevoir des actifs**.
4. Dans le champ **Reçu**, entrez de date et l'heure. Puis sélectionnez **OK**. L'enregistrement est supprimé de la page de liste **Actifs entrants**.

![Enregistrer les actifs entrants comme reçus](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Enregistrer les actifs comme sortants

Lorsque vous avez terminé la tâche de maintenance ou de réparation, vous pouvez enregistrer l'actif comme retourné.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Demandes de maintenance actives**.
2. Sélectionnez la demande de maintenance.
3. Sélectionnez **Mettre à jour l'état de la demande de maintenance**.
4. Sélectionnez **Sortant** (ou un autre état du cycle de vie créé pour les actifs sortants), puis **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Enregistrer les actifs sortants comme livrés

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Entrant/sortant** \> **Actifs sortants**.
2. Sélectionnez l'actif ou la demande de maintenance.
3. Sélectionnez **Livrer les actifs**.
4. Dans le champ **Livré**, entrez de date et l'heure. Puis sélectionnez **OK**. L'enregistrement est supprimé de la page de liste **Actifs sortants**.
