---
title: Spécifier le taux croisé
description: Cet article fournit des informations générales sur les taux croisés dans Microsoft Dynamics 365 Finance.
author: abruer
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efb01948af2bcba9ca740e8bd0e12584cf021fce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889959"
---
# <a name="specify-the-cross-rate"></a>Spécifier le taux croisé

[!include [banner](../includes/banner.md)]

Cet article décrit l’objectif d’un taux croisé, et comment spécifier le taux croisé lorsque vous réglez un paiement avec une facture. Utilisez un taux croisé lorsque tous les critères suivants s’appliquent : 
-   Vous réglez un paiement avec une facture. 
-   La ligne de paiement et la ligne de facture utilisent des devises différentes. 
-   Aucune de ces devises n’est la devise comptable. 

Le taux croisé n’est pas utilisé pour calculer la conversion de la devise de la transaction de paiement en devise comptable de paiement. À la place, les taux de change des tables de taux de change sont extraits pour calculer la valeur du montant en devise de transaction de paiement et du montant en devise comptable de paiement. 

Par exemple, la devise comptable est USD, la devise de facturation est CAD, et la devise de paiement est EUR. Le taux croisé vous permet d’entrer un taux de change pour convertir directement les dollars canadiens en euros et ne pas passer par les dollars américains. Lorsque vous sélectionnez une facture et un paiement principal, vous pouvez entrer un taux croisé pour la ligne de facture. Le taux croisé est le taux de change entre les devises pour ces transactions jusqu’à la date de règlement.

1.  Accédez à l’une des pages suivantes :
- **Comptabilité client > Commun > Clients > Tous les clients** 
- **Comptabilité fournisseur > Commun > Fournisseurs > Tous les fournisseurs** 
- **Approvisionnements > Commun > Fournisseurs > Tous les fournisseurs**
2.  Sélectionnez le client ou le fournisseur dont vous réglez les transactions en cours. 
3.  Pour un client, dans la page de liste **Tous les clients**, accédez à **Collecter > Régler les transactions en cours**. Pour un fournisseur, dans la page de liste **Tous les fournisseurs**, accédez à **Facture > Régler les transactions en cours**. 
4.  Sélectionnez la transaction qui est le paiement principal, puis cliquez sur **Marquer le paiement**. La case à cocher dans la colonne **Marquer** est activée et une icône d’information s’affiche dans la colonne **Paiement principal**. 
5.  Dans le champ **Taux croisé**, entrez le taux de change entre la devise de la facture et la devise de paiement, à compter de la date de règlement. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
