---
title: Vue d’ensemble du module Gestion des services
description: Utilisez le module Gestion des services pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 108f5b0ed51c1c52a78aa7ca64c983b7e3c24e64
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677728"
---
# <a name="service-management-overview"></a>Vue d’ensemble du module Gestion des services

[!include [banner](../includes/banner.md)]


Utilisez le module **Gestion des services** pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients. Les accords de service permettent de définir les ressources utilisées dans une visite de service classique. Vous pouvez également utiliser les accords de service pour visualiser la façon dont les ressources sont facturées au client. En outre, un accord de service peut inclure un contrat de niveau de service spécifiant les durées de réponse standard et offrant des outils permettant d’enregistrer l’heure réelle.

Vous pouvez créer des commandes de service pour gérer les informations relatives aux visites prévues et non prévues sur un site client par un technicien de service. Les commandes de service incluent notamment les informations suivantes :

1.  le nombre d’heures de travail qu’un technicien de service doit effectuer ;

2.  le type de service ou de réparation ;

3.  l’article à réparer, avec des détails sur les symptômes et le diagnostic ;

4.  les dépenses et les frais associés au service ou à la réparation.

Vous pouvez recevoir, traiter et répartir les demandes de service. Après avoir créé une commande de service, vous pouvez utiliser les stades du service pour surveiller sa progression et spécifier des règles contrôlant les actions mises en œuvre à chaque stade. À la fin d’une commande de service, vous pouvez fermer la session de la commande afin de confirmer qu’elle est terminée, puis la valider afin de lancer le processus de facturation.

Utilisez les outils de génération d’états pour surveiller les marges de commande de service et les transactions d’abonnement, ainsi que pour imprimer les descriptions de travail et les accusés de réception des travaux.

## <a name="business-processes"></a>Processus entreprise

Le schéma suivant présente les processus entreprise généraux associés au module **Gestion des services** et indique à quel niveau les processus de service s’intègrent avec d’autres modules.

[![Diagramme de processus entreprise de gestion des services.](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>Aperçu du module Gestion des services

|Tâches importantes           | Pages principales                         |États courants              |
|--------------------------|---------------------------------------|-----------------------------|
|Réalisation d’accords de service|Accords de service                     |Marge de commande de service         |
|Traitement des demandes des clients |Commandes de service                         |Description du travail             |
|                          |Tableau d’affectation                         |Transaction - Abonnement   |
|                          |                                       |Transactions de frais d’abonnement|


## <a name="integration-of-service-management"></a>Intégration du module Gestion des services

Le module Gestion des services peut être intégré aux modules suivants :

  - [Vue d’ensemble de Ventes et marketing](../sales-marketing/overview-sales-marketing.md)
  - [Ressources humaines](/dynamics365/unified-operations/talent/index)

  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]