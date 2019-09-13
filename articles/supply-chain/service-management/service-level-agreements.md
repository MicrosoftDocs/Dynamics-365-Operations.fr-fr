---
title: Vue d'ensemble des contrats de niveau de service
description: Dans le cadre d'un contrat de niveau de service, le client accepte un temps de réponse minimal (de l'enregistrement du problème par la société de service jusqu'à la résolution du problème).
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90915502100c6165838f7eb2ebc620c7b15e6ec8
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865919"
---
# <a name="service-level-agreements-overview"></a>Vue d'ensemble des contrats de niveau de service       

[!include [banner](../includes/banner.md)]


Un contrat de niveau de service (SLA) est un contrat conclu entre une société de service et un client de service. Dans le cadre d'un contrat SLA, le client accepte un temps de réponse minimal (de l'enregistrement du problème par la société de service jusqu'à la résolution du problème).

Un contrat SLA applique un niveau de service standard offert aux clients et indique de façon transparente la date d'exécution d'une tâche de service pour une société de service.

Plusieurs contrats SLA peuvent être créés pour offrir aux clients de service différents niveaux de service.

## <a name="create-a-service-level-agreement"></a>Création d'un contrat de niveau de service

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Accords de service** \> **Contrats de niveau de service**.

2.  Tapez un nom pour le contrat de niveau de service dans le champ **Contrat de niveau de service**.

3.  Entrez le temps que vous souhaitez accorder pour l'achèvement des appels de service associés au contrat de niveau de service. Sélectionnez ensuite un calendrier si vous souhaitez baser le contrat de niveau de service sur un calendrier spécifique.

## <a name="apply-a-service-level-agreement"></a>Application d'un contrat de niveau de service

Le contrat SLA est appliqué directement à un accord de service.

Les commandes de service créées manuellement et associées à un accord de service avec un contrat SLA sont évaluées par rapport à ce contrat.

Les commandes de service créées automatiquement ne sont pas associées à un contrat SLA.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Application du contrat de niveau de service à l'accord de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**. Sélectionnez le contrat de service auquel appliquer le contrat SLA, puis cliquez sur **Modifier** dans le volet **Actions**.

2.  Dans le champ **Contrat de niveau de service**, sélectionnez le contrat SLA à affecter.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>Application du contrat de niveau de service à un groupe d'accords de service

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Accords de service** \> **Groupes d'accords de service**.

2.  Dans le champ **Contrat de niveau de service**, sélectionnez le contrat SLA à affecter.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Suivi de la durée dans une commande de service par rapport à un contrat SLA

Lorsque vous créez une commande de service pour un accord de service auquel le contrat SLA est affecté, l'intervalle pour la fourniture de service est initialisé, et le système commence à suivre le délai de livraison. Vous pouvez également définir les options suivantes :

  - démarrage et arrêt de l'enregistrement de l'heure dans la commande de service pour enregistrer la durée totale passée sur les commandes de service ;

  - Vous pouvez contrôler la conformité avec le délai défini dans le contrat de niveau de service.

  - Vous pouvez définir des codes motif si le délai du contrat de niveau de service est dépassé.

## <a name="see-also"></a>Voir également :

[Affichage de la conformité avec les contrats SLA](view-compliance-with-service-level-agreements.md)

  


