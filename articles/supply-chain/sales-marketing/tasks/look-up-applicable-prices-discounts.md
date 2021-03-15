---
title: Rechercher les prix et remises applicables
description: Cette procédure décrit comment rechercher le prix ou la remise pour un produit qui est actuellement valide pour un client spécifique, sans créer de commande client.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bd85d9cd2d7273ad6e05d794a96e4d6a8d7c526
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010770"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Rechercher les prix et remises applicables

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment rechercher le prix ou la remise pour un produit qui est actuellement valide pour un client spécifique, sans créer de commande client. La procédure décrit un exemple spécifique et vous devez suivre l'exemple à l'aide de la société de démonstration USMF afin de sélectionner les valeurs nécessaires.


## <a name="find-the-applicable-price"></a>Rechercher le prix applicable
1. Accédez à Ventes et marketing > Prix et remises > Rechercher des prix.
2. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez le client US-001.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Entrez « T0004 » dans le champ Numéro d'article.
    * Par défaut, le champ Quantité est défini sur 1. Toutefois, si vous connaissez la taille de la commande que le client a l'intention de passer pour le produit en question, entrez cette valeur à la place. Ces informations sont pertinentes si les accords commerciaux avec le client sont soumis à la quantité (en d'autres termes, que le prix du produit dépend de la quantité minimale achetée).  
6. Dans le champ Date, entrez la date à laquelle le client compte passer une commande. 
    * La date peut être celle d'aujourd'hui ou n'importe quelle date ultérieure.  
    * Le système renvoie désormais le prix qui est valide pour le produit sélectionné une fois acheté par le client sélectionné à la date sélectionnée avec une quantité spécifiée. Dans cet exemple, si le client US-001 achetait 1 unités du produit T0004 aujourd'hui, il paierait 350 CAD l'unité. Ce prix provient d'un accord commercial existant et actif passé avec le client.      D'autres champs de la page fournissent plus de détails sur le prix et le coût du produit (si le paramétrage a été effectué sur le produit générique), ainsi que sur la rentabilité calculée.  
    * Si l'option Afficher les variantes de produits associées est activée, cela signifie qu'il existe des accords commerciaux supplémentaires pour les variantes du produit.  
7. Cliquez sur la case à cocher Afficher les variantes de produits associées.
    * La liste des variantes de produit s'affiche, avec des informations sur les dimensions.  
8. Dans la liste, marquez la ligne représentant la couleur Blanc.
    * Notez que le prix du produit est désormais différent de celui précédemment affiché lorsqu'il n'était pas spécifié par dimension.  
9. Cliquez sur Afficher les prix de vente.
    * La page Prix (ventes) affiche tous les accords commerciaux applicables au produit, y compris ses variantes.  
10. Fermez la page.

## <a name="find-the-applicable-discount"></a>Rechercher la remise applicable
Vérifiez que le champ Compte client contient le numéro de client US-001   
1. Entrez « T0012 » dans le champ Numéro d'article.
    * Veillez à ce que le champ Quantité soit défini sur 1.  
    * Les informations suivantes de tarification indiqués pour le produit T0012 proviennent d'un ou plusieurs accords commerciaux : le prix unitaire est de 1 000 CAD et le pourcentage de remise est de 5.  
2. Définir la Quantité sur « 20 ».
    * La quantité de commande augmentée entraîne le passage de la remises ligne offerte au client de 5 à 7 %.  
    * Le Montant net est calculé sur le prix unitaire, la remise et la quantité totale.  
3. Cliquez sur Afficher la remise ligne.
    * Il existe deux accords de remise de ligne pour le produit T0012, spécifiant une remise de 5 % pour une quantité de ligne de commande de 1 à 10 et de 7 % pour les quantités de commande au-dessus de 10. Notez que les remises sont appliquées à un groupe de produits, dans cet exemple, le code du groupe 01 auquel le produit T0012 appartient.  
4. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]