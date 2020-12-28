---
title: Remises basées sur le mode de paiement
description: Cette rubrique fournit une vue d'ensemble de la fonctionnalité qui permet aux détaillants de configurer des remises pour les modes de paiement spécifiques.
author: bebeale
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 4be0c9a6f0a32016e07b8e31d0aaff44b4a29623
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412382"
---
# <a name="tender-based-discounts"></a>Remises basées sur le mode de paiement

[!include [banner](includes/banner.md)]


Il s'agit d'une pratique courante entre les détaillants d'émettre des cartes de crédit au nom de leur marque et privées. Les détaillants en tirent profit, car ils obtiennent des taux préférentiels auprès des banques. En outre, car ces cartes de crédits peuvent encourager les clients à visiter le magasin plus souvent, elles permettent d'améliorer le résultat du détaillant. Par conséquent, les détaillants ont une incitation pour augmenter l'utilisation des clients de leur carte de crédit au nom de leur marque. Pour atteindre cet objectif, ils offrent souvent des remises supplémentaires aux clients qui utilisent ces cartes de crédit.

Sinon, les détaillants qui ne fournissent pas de cartes de crédit au nom de leur marque peuvent souhaiter encourager les clients à payer à l'aide d'autres modes de paiement, par exemple les disponibilités, les cartes cadeaux, ou les points de fidélité. Ainsi, ils peuvent permettre de réduire la dépenses des frais de traitement des cartes de crédit. Par conséquent, les détaillants peuvent fournir des remises aux clients qui utilisent ces autres modes de paiement.

Dans Microsoft Dynamics 365 Commerce 365 Retail, les détaillants peuvent configurer un pourcentage de remise appliqué aux lignes qualifiées si le client paie à l'aide du mode de paiement recommandé. Le client peut choisir d'effectuer un paiement partiel ou un paiement complet, et Commerce détermine le montant de remise approprié. Notez que la remise est toujours donnée selon le montant avant taxes des articles qualifiés.

Les remises basées sur le mode de paiement ne concurrencent pas les remises basées sur l'article, telles que les remises exceptionnelles ou manuelles. Elles sont toujours cumulées aux remises d'article. Par conséquent, même si une remise périodique exclusive est appliquée à un article, la remise basée sur le mode de paiement est toujours appliquée sur la remise périodique exclusive. De même, si une remise seuil est appliquée à la transaction, et que la remise basée sur un mode de paiement diminue le total sous le seuil, la remise seuil est toujours appliquée à la transaction.

Bien que les remises basées sur le mode de paiement réduisent le sous-total de la transaction, les frais automatiques qui s'appliquent à la transaction ne sont pas affectés. Par exemple, si les frais de livraison sont calculés à 5 $ car le sous-total est supérieur à 100 $, et que la remise basée sur le mode de paiement réduit le montant afin qu'il soit inférieur à 100 $, les frais de livraison sont toujours de 5 $ pour la commande.


> [!NOTE]
> Les remises basées sur le mode de paiement sont proportionnellement réparties dans les lignes de vente qualifiées et réduisent le montant avant taxes des lignes individuelles. Si plusieurs remises basées sur le mode de paiement sont configurées pour un type de mode de paiement (par exemple, les disponibilités), seule la meilleure remise basée sur le mode de paiement est appliquée.

Les remises basées sur le mode de paiement peuvent être appliquées uniquement aux lignes de vente dont les prix ne sont pas verrouillés. Si de nouvelles lignes de vente sont ajoutées à une commande, la remise basée sur le mode de paiement est appliquée aux nouvelles lignes de vente uniquement lors du paiement. Lorsqu'une commande client pour prélèvement ou expédition est passée, la remise basée sur le mode de paiement est appliquée uniquement au montant du dépôt. Une fois la commande passée, pendant la réalisation, les prix des lignes de vente sont verrouillées. Par conséquent, aucune remise basée sur le mode de paiement n'est appliquée à aucun solde réglé lors du prélèvement ou autorisée lors de l'expédition. La remise basée sur le mode de paiement peut être appliquée au montant entier d'une commande client que si le détaillant collecte la totalité du montant comme dépôt lorsque la commande est passée.

> [!IMPORTANT]
> Dans Commerce, les remises basées sur le mode de paiement sont actuellement limitées à deux types de paiement : cartes de crédit et disponibilités.

## <a name="pos-user-experience"></a>Expérience utilisateur PDV

Si la remise basée sur le mode de paiement est paramétrée pour les disponibilités, et le caissier du point de vente (PDV) sélectionne un bouton qui est mappé à l'opération Paiement en espèces, la remise basée sur le mode de paiement s'applique automatiquement à la transaction. Le montant réduit ensuite affiché comme solde. Toutefois, si le caissier sélectionne le bouton **Précédent** sur l'écran des paiements, la remise est supprimée, et le montant d'origine est affiché sur l'écran de transaction. La remise basée sur le mode de paiement est supprimée si la ligne de paiement est annulée.

Pour les paiements par carte, les détaillants peuvent définir la remise basée sur le mode de paiement sur un ou plusieurs types de cartes de crédit. Toutefois, le système ne peut pas vérifier le type de carte de crédit utilisé à moins que la carte soit autorisée. Si la remise est appliquée après autorisation, l'autorisation de paiement sera pour un montant supérieur, mais la capture du paiement sera pour un montant inférieur.

Pour empêcher cette situation, si un client paie avec une carte de crédit, le caissier voit une boîte de dialogue qui répertorie les cartes de crédit qui offriront au client des économies supplémentaires. Le caissier peut ensuite demander si le client veut utiliser l'une des cartes recommandées pour obtenir une remise supplémentaire. Si le caissier utilise une carte recommandée, la remise basée sur le mode de paiement est appliquée à la transaction, et le montant réduit s'affiche sur l'écran de paiement. L'autorisation sera pour le montant réduit. Si le client insère une carte différente de la carte que le caissier a sélectionné, un message d'erreur s'affiche, et de l'autorisation est annulée.


## <a name="call-center-user-experience"></a>Expérience utilisateur du centre d'appels

Lorsque l'utilisateur sélectionne **Terminé** au cours d'une commande au centre d'appels, l'écran **Totaux** s'affiche. Au début, les totaux sur cet écran ne comprennent pas les remises basées sur le mode de paiement, car le mode de paiement n'a pas encore été sélectionné. Sur l'écran **Ajouter un paiement**, si l'utilisateur sélectionne le mode de paiement pour lequel la remise basée sur le mode de paiement est configurée, le montant du paiement est ajusté automatiquement afin de refléter le montant déduit. Comme le client au PDV, le client du centre d'appels peut choisir d'effectuer le paiement partiellement ou complètement. Selon le montant payé, la remise basée sur le mode de paiement est appliquée à la commande client.

> [!NOTE]
> La validation de la carte n'est pas effectuée pour les commandes au centre d'appels. Par exemple, si l'utilisateur du centre d'appels sélectionne Visa comme carte de crédit, mais que le client utilise Mastercard, le système applique toujours la remise.

## <a name="exclude-items-from-discounts"></a>Exclure des articles des remises

Les détaillants choisissent souvent d'exclure certaines produits, tels que les nouveaux articles ou des articles en demande, des remises. Toutefois, ils peuvent toujours souhaitez appliquer des remises basées sur le mode de paiement. Par exemple, un détaillant configure Commerce afin qu'il n'autorise pas les remises basées sur l'article ou les remises manuelles. Toutefois, si le client paie à l'aide du mode de paiement recommandé, Commerce applique toujours la remise basée sur le mode de paiement. Pour configurer Commerce de cette manière, les détaillants doivent accéder à **Gestion des informations sur les produits > Produits > Produits lancés**, sélectionner l'article, puis dans l'organisateur **Commerce**, définir les options **Empêcher toutes les remises** et **Empêcher les remises basées sur le mode de paiement** sur **Non**, et les options **Empêcher les remises sur la vente au détail** et **Empêcher les remises manuelles** sur **Oui**.

> [!NOTE]
> Lorsque la configuration **Empêcher toutes les remises** est définie sur **Oui**, aucune remise n'est appliquée au produit. Même les remises basées sur le mode de paiement ne sont pas appliquées.
