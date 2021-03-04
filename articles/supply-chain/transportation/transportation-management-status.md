---
title: Statuts sur la gestion du transport
description: Cette rubrique explique comment créer un statut de transport et mapper ce statut sur un statut de transporteur.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4428351"
---
# <a name="transportation-management-statuses"></a>Statuts sur la gestion du transport

[!include [banner](../includes/banner.md)]

Paramétrez les codes données principales pour les statuts de transport afin d'interpréter les codes fournis par vos transporteurs. Cela vous permet de vous intégrer aux transporteurs pour fournir un statut. Le statut de transport que vous fournissez un pour code données principales de statut de transport peut vous aider à suivre le statut d'une charge, d'une expédition, ou d'un conteneur. Le statut de transport spécifique d'un chargement, d'une expédition ou d'un conteneur ne peut être mis à jour que par le biais de l'intégration des données et non manuellement par le biais de l'interface utilisateur.

## <a name="create-a-transportation-status"></a>Créer un statut de transport

Pour créer un statut de transport, procédez comme suit :

1. Accédez à **Gestion du transport \> Configurer \> Données principales du statut du transport**.
1. Cliquez sur **Nouveau** pour créer les données principales de statut de transport.
1. Dans le champ **Données principales de statut de transport**, entrez un code unique pour le statut de transport.
1. Dans le champ **Type de transport**, sélectionnez *Transporteur* ou *Hub* comme type de transport.
1. Entrez un nom et un statut de transport.
1. Fermez la page.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Mapper un statut de transport à un statut de transporteur

Pour mapper un statut de transport à un statut de transporteur, procédez comme suit :

1. Accédez à **Gestion du transport \> Configurer \> Transporteurs \> Statut du transporteur**.
1. Cliquez sur **Nouveau** pour mettre en correspondance un transporteur et un code données principales de statut de transport.
1. Sélectionnez l'ID unique pour le transporteur et le service de transporteur.
1. Sélectionnez le code statut de transport que vous souhaitez mettre en correspondance avec le code du transporteur sélectionné.
1. Entrez le code externe utilisé par le transporteur.
1. Fermez la page.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]