---
title: Modes de paiement dans un centre d'appels
description: "Cette rubrique décrit les différentes méthodes de paiement que vous pouvez utiliser dans un centre d’appels de Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 93cff4454139524911a98fc28bccd6aeb5b49d4a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="payment-methods-in-a-call-center"></a>Modes de paiement dans un centre d'appels

[!include[banner](includes/banner.md)]


Cette rubrique décrit les différentes méthodes de paiement que vous pouvez utiliser dans un centre d’appels de Dynamics 365 for Retail.

Les modes de paiement utilisés dans d'autres canaux, tels que les disponibilités, les chèques, les cartes de crédit et les cartes cadeau, peuvent également être utilisés dans les centres d'appels. Une fois un mode de paiement paramétré pour un centre d'appels, il apparaît comme une des options dans la section **Paiements** de la page **Commande client** pour les utilisateurs du centre d'appels. Sinon, vous pouvez configurer des coupons pour offrir des remises aux clients lorsqu'ils passent une commande au centre d'appels de votre organisation. Les coupons peuvent être un montant fixe de remise, ou bien un pourcentage du prix d'un article ou du total de la commande. Par exemple, un coupon de montant peut offrir aux clients une remise de 75,00 si le client dépense 750,00 ou plus. Vous pouvez créer différents types de bons de réduction, paramétrer des bons d’achat parent/enfant et copier ou invalider un bon d’achat. Utilisez les options dans le tableau suivant pour créer des bons.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Attribut**             | Dans le champ **Taux de rachat**, entrez la valeur du taux de rachat prévu pour le coupon en pourcentage, puis indiquez si le coupon est utilisable une seule fois, s'il est automatiquement renouvelé, ou s'il est spécifique à un client.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Valide**                 | Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de validité du coupon.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Inclure/Exclure des règles** | Dans les champs **Catalogues** et **Articles**, indiquez si des catalogues ou des articles sont inclus ou exclus pour le coupon. Si vous sélectionnez **Inclure** ou **Exclure**, cliquez sur **Configurer**, sélectionnez **Inclure/exclure les catalogues** ou **Inclure/exclure les produits** et entrez les informations sur le catalogue ou l’article. Si vous sélectionnez **Aucun** dans ces champs, tous les catalogues ou articles sont inclus dans le coupon.                                                                                                                                                                                                                          |
| **Autre(s)**         | Si ce coupon ne peut être utilisé avec les autres remises, activez la case à cocher **Exclusif**. Puis, dans le champ **Origine**, sélectionnez où le coupon peut être utilisé. Pour ce coupon est un coupon de fabricant, activez la case à cocher **Coupon du fabricant**.                                                                                                                                                                                                                                                                                                                                                                |
| **Coupon futur**         | Si le coupon sera associé à d'autres coupons comme coupon parent, activez la case à cocher **Coupon parent**. Si le coupon est associé à un coupon existant comme coupon enfant, sélectionnez le coupon parent dans le champ **ID coupon parent**. Par exemple, vous pouvez créer un coupon pour le catalogue du printemps prochain. Tous les autres coupons que vous créez pour le catalogue Printemps seront les coupons enfants du coupon du catalogue Printemps. Les coupons enfants peuvent inclure 20 % de remise pour les nouvelles commandes client, 10 % de remise sur un article récemment lancé, ou une réduction de 95,00 sur les commandes de 1 000,00 ou plus. |

Si vous soumettez un paiement par carte de crédit depuis l'écran **Commande client** et recevez un message indiquant que la carte n'a pas été autorisée, vous pouvez traiter l'autorisation manuellement. Vous pouvez autoriser, refuser ou soumettre à nouveau une transaction de carte de crédit à l’aide de la page **Gestion des autorisations**. La page Paramètres du centre d’appel vous permet de configurer les options de traitement des paiements supplémentaires :

-   Les blocages de chèques permettent au personnel financier de traiter les commandes qui ont été placés en attente parce qu’un chèque a été utilisé comme mode de paiement et que le montant du seuil de blocage de chèque a été dépassé. Le blocage peut être lancé manuellement, ou il expire automatiquement à la fin de la période configurée.
-   Vous pouvez définir des seuils au-dessus desquels les remboursements émis par chèques et cartes de crédit doivent être approuvés manuellement. Tout remboursement qui dépasse le seuil est ajouté à la file d'attente d'approbation. Après avoir approuvé le remboursement, la commande client de retour peut être facturée.





