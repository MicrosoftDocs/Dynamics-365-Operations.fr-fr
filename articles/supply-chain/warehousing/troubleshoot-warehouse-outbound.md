---
title: Résoudre les problèmes des opérations d’entrepôt sortantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts sortantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 491803c5f9394f47a996c4e4c7fb8925e9464e644c99e5c1ab434706af6ad74e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756653"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Résoudre les problèmes des opérations d’entrepôt sortantes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts sortantes dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Je reçois le message d’erreur suivant : "La commande client n’a pas pu être lancée".

### <a name="issue-description"></a>Description du problème

Ce problème peut se produire pour plusieurs raisons. Par exemple, la commande est en attente de gestion du crédit et aucune livraison ne peut être créée tant qu’une adresse postale valide n’est pas saisie pour toutes les lignes de vente associées à une commande client. Il existe également un blocage de commande qui doit être traité avant que la commande puisse être validée vers l’entrepôt. Ce blocage peut être lié à la commande ou au compte client.

### <a name="issue-resolution"></a>Résolution du problème

Ajoutez ou mettez à jour l’adresse sur la commande client et les lignes de commande, puis validez la commande vers l’entrepôt. Les commandes ne peuvent être validées dans l’entrepôt que si elles ont une adresse de livraison valide (selon le format d’adresse configuré dans le module **Administration de l’organisation**).

Examinez le blocage de la commande et résolvez les problèmes. Supprimez ensuite le blocage de la commande ou du client et transférez la commande à l’entrepôt.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Je reçois le message suivant : "L’expédition pour chargement 1% a été confirmée. » Cependant, aucune ligne n’est publiée.

### <a name="issue-description"></a>Description du problème

Un envoi sur un chargement a été confirmé, mais aucun autre enregistrement n’a eu lieu.

### <a name="issue-resolution"></a>Résolution du problème

La confirmation d’expédition n’affecte pas la publication. Elle met simplement à jour le statut de l’expédition et du chargement. La publication doit avoir lieu dans un processus distinct.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Je reçois le message d’erreur suivant : "La livraison directe ne peut pas être traitée pour l’entrepôt 1% car la gestion d’entrepôt est activée. Spécifiez un autre entrepôt qui n’est pas activé pour la gestion de l’entrepôt. »

### <a name="issue-description"></a>Description du problème

Un article est ajouté à une ligne de vente pour une livraison directe à partir d’un entrepôt activé pour la gestion des entrepôts (WMS). Vous recevez ce message d’erreur lorsque la ligne de vente est mise à jour. 

### <a name="issue-resolution"></a>Résolution du problème

Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Actuellement, WMS ne prend pas en charge la livraison directe. Par conséquent, pour utiliser la livraison directe, vous devez sélectionner un article et un entrepôt non WMS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]