---
title: Convertir les clients asynchrones en clients synchrones
description: Cet article explique comment convertir des clients asynchrones en clients synchrones dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b442bfc0685706359771e4d9e2729565d3652a60
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278190"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Convertir les clients asynchrones en clients synchrones

[!include [banner](includes/banner.md)]

Cet article explique comment convertir des clients asynchrones en clients synchrones dans Microsoft Dynamics 365 Commerce.

Procédez comme suit pour convertir des clients asynchrones en clients synchrones.

1. Dans Commerce headquarters, exécutez la **tâche P** pour envoyer les clients asynchrones.
1. Exécutez la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** pour créer des identifiants de compte client. (Cette tâche s’appelait auparavant **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**.)
1. Exécutez la tâche **1010** pour synchroniser les nouveaux identifiants de compte client avec les canaux.

Si une commande fait référence à un client ou à une adresse asynchrone qui n’a pas encore été synchronisée avec Commerce Headquarters, le client ou l’adresse sera synchronisé dans le cadre du traitement par lots **Synchroniser les commandes**. Si une transaction de type cash-and-carry fait référence à un client ou à une adresse asynchrone, le client ou l’adresse sera synchronisé avant la publication de fin de journée (EOD).

## <a name="additional-resources"></a>Ressources supplémentaires

[Gestion des clients en magasin](customer-mgmt-stores.md)

[Mode de création de client asynchrone](async-customer-mode.md)

[Attributs du client](dev-itpro/customer-attributes.md)

[Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
