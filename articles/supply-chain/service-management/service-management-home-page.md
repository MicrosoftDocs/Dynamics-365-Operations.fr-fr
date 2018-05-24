---
title: Gestion des services
description: "Utilisez le module Gestion des services pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a>Gestion des services 

[!include [banner](../includes/banner.md)]


Utilisez le module **Gestion des services** pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients. Les accords de service permettent de définir les ressources utilisées dans une visite de service classique. Vous pouvez également utiliser les accords de service pour visualiser la façon dont les ressources sont facturées au client. En outre, un accord de service peut inclure un contrat de niveau de service spécifiant les durées de réponse standard et offrant des outils permettant d'enregistrer l'heure réelle.

Vous pouvez créer des commandes de service pour gérer les informations relatives aux visites prévues et non prévues sur un site client par un technicien de service. Les commandes de service incluent notamment les informations suivantes :

1.  le nombre d'heures de travail qu'un technicien de service doit effectuer ;

2.  le type de service ou de réparation ;

3.  l'article à réparer, avec des détails sur les symptômes et le diagnostic ;

4.  les dépenses et les frais associés au service ou à la réparation.

Les clients peuvent envoyer des demandes de service par Internet via Enterprise Portal. Vous pouvez recevoir, traiter et répartir ces demandes. Après avoir créé une commande de service, vous pouvez utiliser les stades du service pour surveiller sa progression et spécifier des règles contrôlant les actions mises en œuvre à chaque stade. À la fin d'une commande de service, vous pouvez fermer la session de la commande afin de confirmer qu'elle est terminée, puis la valider afin de lancer le processus de facturation.

Utilisez les outils de génération d'états pour surveiller les marges de commande de service et les transactions d'abonnement, ainsi que pour imprimer les descriptions de travail et les accusés de réception des travaux.

## <a name="business-processes"></a>Processus entreprise

Le schéma suivant présente les processus entreprise généraux associés au module **Gestion des services**, et indique à quel niveau les processus de service s'intègrent avec d'autres modules dans Microsoft Dynamics 365 for Finance and Operations.

[![Diagramme de processus entreprise de gestion des services](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>Aperçu du module Gestion des services

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tâches importantes</p></th>
<th><p>Écrans principaux</p></th>
<th><p>États courants</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Réalisation d'accords de service</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Accords de service (écran)</a></p></td>
<td><p><strong>Marge de commande de service</strong></p></td>
</tr>
<tr class="even">
<td><p>Traitement des demandes des clients</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Commandes de service (écran)</a></p></td>
<td><p><strong>Description du travail</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Tableau d'affectation (écran)</a></p></td>
<td><p><strong>Transaction - Abonnement</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>Transactions de frais d'abonnement</strong></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a>Intégration du module Gestion des services

Le module Gestion des services peut être intégré aux modules suivants dans Microsoft Dynamics 365 for Finance and Operations :

  - [Ventes et marketing](../sales-marketing/overview-sales-marketing.md)

  - [Ressources humaines](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


