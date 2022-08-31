---
title: Remises basées sur le mode de paiement
description: Cet article décrit la fonctionnalité des remises basées sur les offres qui permet aux détaillants de configurer des remises pour des types d'offres spécifiques dans Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: 3c28297e62e5b2880a7a39381702d5a1448c91ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336673"
---
# <a name="tender-based-discount"></a>Remises basées sur l'offre

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cet article décrit la fonctionnalité des remises basées sur les offres qui permet aux détaillants de configurer des remises pour des types d'offres spécifiques dans Microsoft Dynamics 365 Commerce.

Il s’agit d’une pratique courante entre les détaillants d’émettre des cartes de crédit au nom de leur marque et privées. Les détaillants en tirent profit, car ils obtiennent des taux préférentiels auprès des banques. En outre, car ces cartes de crédits peuvent encourager les clients à visiter le magasin plus souvent, elles permettent d’améliorer le résultat du détaillant. Par conséquent, les détaillants ont une incitation pour augmenter l’utilisation des clients de leur carte de crédit au nom de leur marque. Pour atteindre cet objectif, ils offrent souvent des remises supplémentaires aux clients qui utilisent ces cartes de crédit.

Sinon, les détaillants qui ne fournissent pas de cartes de crédit au nom de leur marque peuvent souhaiter encourager les clients à payer à l’aide d’autres modes de paiement, par exemple les disponibilités, les cartes cadeaux, ou les points de fidélité. Ainsi, ils peuvent permettre de réduire la dépenses des frais de traitement des cartes de crédit. Par conséquent, les détaillants peuvent fournir des remises aux clients qui utilisent ces autres modes de paiement.

## <a name="tender-based-discount"></a>Remises basées sur l'offre

Commerce prend en charge une *remise basée sur l’offre* qui permet aux détaillants de configurer un pourcentage de remise qui est appliqué à une transaction si le total de la transaction dépasse un montant spécifique et que le client paie en utilisant le type de paiement préféré. La remise basée sur l’offre est basée sur le niveau, de sorte que différents pourcentages de remise peuvent être associés à différents seuils de montant. Le client peut choisir d’effectuer un paiement partiel ou un paiement complet, et le moteur de tarification détermine le montant de remise approprié. La remise sur l’offre est toujours accordée sur le montant HT des lignes de vente.

Les remises basées sur l'offre ne peuvent être appliquées qu'aux lignes de vente où les prix ne sont pas fixes et elles sont proportionnellement réparties sur les lignes de vente qualifiées. Si de nouvelles lignes de vente sont ajoutées à une commande, la remise basée sur l'offre n'est appliquée qu'aux nouvelles lignes de vente lors du paiement. Lorsqu’une commande client pour enlèvement ou expédition est passée, la remise basée sur l'offre est appliquée uniquement au montant du dépôt. Une fois la commande passée, pendant la réalisation, les prix des lignes de vente sont verrouillées. Aucune remise basée sur l'offre n’est appliquée à aucun solde réglé lors de l'enlèvement ou autorisée lors de l’expédition. La remise basée sur le mode de paiement peut être appliquée au montant entier d’une commande client que si le détaillant collecte la totalité du montant comme dépôt lorsque la commande est passée.

Les remises basées sur l’offre ne sont pas en concurrence avec les remises basées sur les articles telles que les remises simples, les remises sur quantité, les remises de seuil, les remises sur les assortiments et les remises manuelles. Les remises basées sur l’offre sont toujours cumulées sur les remises basées sur les articles. Par conséquent, même si une remise exclusive est appliquée à un article, la remise basée sur l'offre est toujours appliquée sur la remise exclusive. De même, si une remise seuil est appliquée à la transaction, et que la remise basée sur un mode de paiement diminue le total sous le seuil, la remise seuil est toujours appliquée à la transaction.

Bien que les remises basées sur l'offre réduisent le sous-total de la transaction, les frais automatiques qui s’appliquent à la transaction ne sont pas affectés. Par exemple, si les frais de livraison sont calculés à 5 $ car le sous-total est supérieur à 100 $, et que la remise basée sur l'offre réduit le montant afin qu’il soit inférieur à 100 $, les frais de livraison sont toujours de 5 $ pour la commande.

Les remises basées sur l'offre sont actuellement limitées à deux types de paiement : cartes de crédit et espèces. Si plusieurs remises basées sur le mode de paiement sont configurées pour un type de mode de paiement, seule la meilleure remise basée sur l'offre est appliquée.

## <a name="pos-user-experience"></a>Expérience utilisateur PDV

Si la remise basée sur l'offre est paramétrée pour les espèces, et le caissier du point de vente (PDV) sélectionne le bouton **Payer en espèce** pour régler une transaction en espèces, la remise basée sur l'offre s’applique automatiquement à la transaction. Le montant réduit ensuite affiché comme solde. Toutefois, si le caissier sélectionne le bouton **Précédent** sur l’écran des paiements, la remise est supprimée, et le montant d’origine est affiché sur l’écran de transaction. La remise basée sur le mode de paiement est supprimée si la ligne de paiement est annulée.

Pour les paiements par carte, les détaillants peuvent définir la remise basée sur l'offre sur un ou plusieurs types de cartes de crédit. Toutefois, le système ne peut pas vérifier le type de carte de crédit utilisé à moins que la carte soit autorisée. Si la remise est appliquée après autorisation, l’autorisation de paiement sera pour un montant supérieur, mais la capture du paiement sera pour un montant inférieur. Pour empêcher cette situation, si un client paie avec une carte de crédit, le caissier voit une boîte de dialogue qui répertorie les cartes de crédit qui offriront au client des remises supplémentaires. Le caissier peut ensuite demander si le client veut utiliser l’une des cartes recommandées pour obtenir une remise supplémentaire. Si le caissier sélectionne une carte recommandée, la remise basée sur l'offre est appliquée à la transaction, et le montant réduit s’affiche sur l’écran de paiement. L’autorisation sera pour le montant réduit. Si le client insère une carte différente de la carte que le caissier a sélectionné, un message d’erreur s’affiche, et de l’autorisation est annulée.

## <a name="call-center-user-experience"></a>Expérience utilisateur du centre d’appels

Si l’utilisateur d'un centre d'appel sélectionne **Terminé** au cours d’une commande au centre d’appels, l’écran **Totaux** s’affiche. Au début, les totaux sur cet écran ne comprennent pas les remises basées sur le mode de paiement, car le mode de paiement n’a pas encore été sélectionné. Sur l’écran **Ajouter un paiement**, si l’utilisateur sélectionne le mode de paiement pour lequel la remise basée sur le mode de paiement est configurée, le montant du paiement est ajusté automatiquement afin de refléter le montant déduit. Comme un client au PDV, le client du centre d’appels peut choisir d’effectuer le paiement partiellement ou complètement. Selon le montant payé, la remise basée sur le mode de paiement est appliquée à la commande client.

> [!NOTE]
> La validation de la carte n’est pas effectuée pour les commandes au centre d’appels. Par exemple, si l’utilisateur du centre d’appels sélectionne Visa comme carte de crédit, mais que le client utilise Mastercard, le système applique toujours la remise.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
