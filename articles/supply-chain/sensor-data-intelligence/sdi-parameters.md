---
title: Paramètres de Sensor Data Intelligence
description: Cet article fournit des informations sur les paramètres de configuration disponibles sur la page des paramètres Sensor Data Intelligence.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5240537e3a6526ceb35253b9e68f46b1753c6a37
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689371"
---
# <a name="sensor-data-intelligence-parameters"></a>Paramètres de Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

La page **Paramètres de Sensor Data Intelligence** fournit quelques paramètres que vous pouvez utiliser pour configurer la fonctionnalité. Ces paramètres incluent les paramètres de connexion Azure et un paramètre pour la durée de vie des messages d’alerte qui sont envoyés aux utilisateurs en réponse aux mesures des capteurs.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Lire et modifier les détails de connexion pour votre solution Azure IoT

En règle générale, vous configurerez votre solution Azure IoT et la connecterez à Microsoft Dynamics 365 Supply Chain Management depuis la page **Déployer et connecter des ressources Azure** qui vous guidera à travers les deux procédures. (Pour plus d’informations, voir [Déployer une solution IoT sur Azure](sdi-deploy-iot-solution-on-azure.md).) Vous pouvez également afficher et modifier les détails de connexion à tout moment dans Supply Chain Management en suivant ces étapes.

1. Accédez à **Administration système \> Configurer \> Sensor Data Intelligence \> Paramètres de Sensor Data Intelligence**.
1. Sur l’onglet **Algorithme**, dans le champ **Chaîne de connexion au magasin métrique de l’instruction Redis**, saisissez la valeur **Chaîne de connexion principale (StackExchange.Redis)** pour la solution Azure IoT à laquelle vous souhaitez vous connecter. Pour plus d’informations sur la façon de trouver cette valeur, voir [Déployer une solution IoT sur Azure](sdi-deploy-iot-solution-on-azure.md).
1. Sur l’onglet **Intégrations**, dans le champ **ID client d’application Azure AD**, saisissez la valeur **ID client** pour la solution Azure IoT à laquelle vous souhaitez vous connecter. Pour plus d’informations sur la façon de trouver cette valeur, voir [Déployer une solution IoT sur Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Définir la durée de vie des messages d’alerte

Chaque fois que Sensor Data Intelligence détecte une situation nécessitant l’attention de l’utilisateur, il envoie une notification à l’utilisateur concerné. Pour éviter que ces notifications ne s’accumulent dans le système, vous devez les configurer pour qu’elles expirent après quelques jours.

1. Accédez à **Administration système \> Configurer \> Sensor Data Intelligence \> Paramètres de Sensor Data Intelligence**.
1. Sur l’onglet **Notifications**, dans le champ **Jours de notification dynamiques**, entrez le nombre de jours pendant lesquels conserver une notification. Une fois le délai spécifié écoulé, la notification sera supprimée.
