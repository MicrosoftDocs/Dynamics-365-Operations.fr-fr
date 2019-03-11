---
title: Spécification du taux croisé
description: Cette rubrique fournit des informations générales sur les taux croisés dans Microsoft Dynamics 365 for Finance and Operations.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320234"
---
# <a name="specify-the-cross-rate"></a>Spécification du taux croisé

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l'objectif d'un taux croisé, et comment spécifier le taux croisé lorsque vous réglez un paiement avec une facture. Utilisez un taux croisé lorsque tous les critères suivants s'appliquent : 
-   Vous réglez un paiement avec une facture. 
-   La ligne de paiement et la ligne de facture utilisent des devises différentes. 
-   Aucune de ces devises n'est la devise comptable. 

Le taux croisé n'est pas utilisé pour calculer la conversion de la devise de la transaction de paiement en devise comptable de paiement. À la place, les taux de change des tables de taux de change sont extraits pour calculer la valeur du montant en devise de transaction de paiement et du montant en devise comptable de paiement. 

Par exemple, la devise comptable est USD, la devise de facturation est CAD, et la devise de paiement est EUR. Le taux croisé vous permet d'entrer un taux de change pour convertir directement les dollars canadiens en euros et ne pas passer par les dollars américains. Lorsque vous sélectionnez une facture et un paiement principal, vous pouvez entrer un taux croisé pour la ligne de facture. Le taux croisé est le taux de change entre les devises pour ces transactions jusqu'à la date de règlement.

1.  Accédez à l'une des pages suivantes :
- **Comptabilité client > Commun > Clients > Tous les clients** 
- **Comptabilité fournisseur > Commun > Fournisseurs > Tous les fournisseurs** 
- **Approvisionnements > Commun > Fournisseurs > Tous les fournisseurs**
2.  Sélectionnez le client ou le fournisseur dont vous réglez les transactions en cours. 
3.  Pour un client, dans la page de liste **Tous les clients**, accédez à **Collecter > Régler les transactions en cours**. Pour un fournisseur, dans la page de liste **Tous les fournisseurs**, accédez à **Facture > Régler les transactions en cours**. 
4.  Sélectionnez la transaction qui est le paiement principal, puis cliquez sur **Marquer le paiement**. La case à cocher dans la colonne **Marquer** est activée et une icône d'information s'affiche dans la colonne **Paiement principal**. 
5.  Dans le champ **Taux croisé**, entrez le taux de change entre la devise de la facture et la devise de paiement, à compter de la date de règlement. 
