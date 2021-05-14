---
title: Commandes des clients en point de vente (PDV)
description: Cette rubrique fournit des informations sur les commandes client dans le point de vente (PDV). Les commandes client sont également appelées commandes spéciales. La rubrique inclut une discussion sur les paramètres associés et les flux de transaction.
author: josaw1
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e495ac4f3cc55503cc8b15d4d4640d3468ab7cd2
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936728"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Commandes des clients en point de vente (PDV)

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur la création et la gestion des commandes client dans le point de vente (PDV). Les commandes client peuvent être utilisées pour capturer les ventes pour lesquelles les acheteurs souhaitent récupérer des produits à une date ultérieure, récupérer des produits à un autre endroit ou se faire expédier des articles. 

Dans le monde de Commerce dans plusieurs canaux, de nombreux détaillants offrent la possibilité que les commandes client ou les commandes spéciales répondent à diverses exigences de produit et de traitement. Voici quelques scénarios classiques :

- Un client souhaite que les produits soient livrés à une adresse spécifique à une date spécifique.
- Un client souhaite prélever les produits dans un magasin ou un emplacement qui diffère du magasin ou de l’emplacement où il a acheté ces produits.
- Un client dans un magasin souhaite commander des produits aujourd’hui et les récupérer au même magasin à une date ultérieure.

Les détaillants peuvent utiliser les commandes client pour réduire les ventes perdues que les pénuries de stock peuvent causer, car les marchandises peuvent être livrées ou prélevées à un autre moment ou emplacement.

## <a name="set-up-customer-orders"></a>Paramétrer les commandes client
Avant d’essayer d’utiliser la fonctionnalité de commande client dans le PDV, assurez-vous que vous avez terminé toutes les configurations requises au siège de Commerce.

### <a name="configure-modes-of-delivery"></a>Configurer les modes de livraison

Pour utiliser les commandes client, vous devez configurer les modes de livraison que le canal de magasin peut utiliser. Vous devez définir au moins un mode de livraison qui peut être utilisé lorsque des lignes de commande sont expédiées à un client depuis un magasin. Vous devez également définir au moins un mode de retrait qui peut être utilisé lorsque des lignes de commande sont récupérées dans le magasin. Les modes de livraison sont définis sur la page **Modes de livraison** au siège de Commerce. Pour plus d’informations sur la configuration des modes de livraison pour les canaux de Commerce, voir [Définir les modes de livraison](./configure-call-center-delivery.md#define-delivery-modes).

![Page Modes de livraison](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Paramétrer les Groupes d’exécution

Certains emplacements de magasins ou d’entrepôt peuvent ne pas être en mesure de traiter les commandes client. En configurant des groupes d’exécution, une organisation peut spécifier quels emplacements de magasins et d’entrepôt sont affichés comme options pour les utilisateurs qui créent des commandes client dans le PDV. Les groupes d’exécution sont configurés sur la page **Groupes d’exécution**. Les organisations peuvent créer autant de groupes d’exécution qu’elles le souhaitent. Une fois qu’un groupe d’exécution est défini, vous devez le lier à un magasin en cliquant sur le bouton **Affectation du groupe d’exécution** de l’onglet **Paramétrage** du volet Actions sur la page **Magasins**.

Dans Commerce version 10.0.12 et versions ultérieures, les organisations peuvent définir si l’entrepôt ou les combinaisons d’entrepôt/magasin définies dans les groupes d’exécution peuvent être utilisés pour l’expédition, pour le retrait ou pour l’expédition et le retrait. Cela permet à l’entreprise d’avoir plus de flexibilité pour déterminer les entrepôts qui peuvent être sélectionnés lors de la création d’une commande client pour les articles à expédier et les magasins qui peuvent être sélectionnés lors de la création d’une commande client pour les articles à retirer. Pour utiliser ces options de configuration, vous devez activer la fonctionnalité **Possibilité de spécifier des emplacements comme « Expédition » ou « Retrait » activée dans le groupe d’exécution**. Si un entrepôt lié à un groupe d’exécution n’est pas un magasin, il ne peut être configuré qu’en tant que lieu d’expédition. Il ne peut pas être utilisé lorsque les commandes avec retrait sont configurées dans le PDV.

![Page Groupes d’exécution](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Configurer les paramètres de canal

Lorsque vous travaillez avec des commandes client dans le PDV, vous devez prendre en compte certains des paramètres du canal de magasin. Ces paramètres se trouvent sur la page **Magasins** au siège de Commerce.

- **Entrepôt** : ce champ indique l’entrepôt qui sera utilisé lors de la réduction des stocks pour les commandes de retrait et de prélèvement client liées à ce magasin. Nous recommandons d’employer un entrepôt unique pour chaque canal de magasin afin d’éviter les problèmes de conflits de logique métier entre les magasins.
- **Entrepôt d’expédition** : ce champ indique l’entrepôt qui sera utilisé lors de la réduction des stocks pour les commandes client à expédier depuis le magasin sélectionné. Si la fonctionnalité **Possibilité de spécifier des emplacements comme « Expédition » ou « Retrait » activés dans le groupe d’exécution** a été activée dans votre environnement, les utilisateurs des PDV peuvent choisir un entrepôt spécifique à partir duquel expédier dans le PDV, au lieu de choisir un magasin à partir duquel expédier. Par conséquent, lorsque cette fonctionnalité est activée, l’entrepôt d’expédition n’est plus utilisé, car l’utilisateur choisira l’entrepôt particulier à partir duquel expédier la commande lors de la création de la commande.
- **Affectation au groupe d’exécution** – Cliquez sur ce bouton (sur l’onglet **Configurer** dans le volet Actions) pour lier les groupes d’exécution référencés pour afficher les options des lieux de retrait ou les origines d’expédition lorsque les commandes client sont créées dans le PDV.
- **Utiliser la taxe basée sur la destination** – Cette option indique si l’adresse de livraison est utilisée pour déterminer le groupe de taxe appliqué aux lignes de commande expédiées à l’adresse du client.
- **Utiliser la taxe basée sur le client** – Cette option indique si le groupe de taxe défini pour l’adresse de livraison du client est utilisé pour taxer les commandes client créées dans le PDV pour l’expédition au domicile du client.

![Enregistrer la configuration de canal sur la page Magasins](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Définir les paramètres de la commande client

Avant d’essayer de créer des commandes client dans le PDV, vous devez configurer les paramètres appropriés dans le siège de Commerce. Ces paramètres se trouvent sur l’onglet **Commandes client** de la page **Paramètres Commerce**.

- **Type de commande par défaut** – Vous pouvez spécifier le type de commande affecté par défaut aux commandes client créées dans le PDV. Ces commandes client peuvent être des commandes client ou des commandes de devis. Quel que soit le type de commande par défaut, les utilisateurs peuvent toujours créer à la fois des commandes client et des commandes des clients à partir du PDV.
- **Pourcentage de dépôt par défaut** – Spécifiez le pourcentage du montant total de la commande que le client doit payer comme dépôt avant qu’une commande puisse être confirmée. En fonction de leurs privilèges, les associés du magasin peuvent être en mesure de remplacer le montant en utilisant l’opération **Remplacement de dépôt** dans le PDV, si cette opération est configurée pour la disposition de l’écran de transaction.
- **Mode de retrait de livraison** – Spécifiez le mode de livraison à appliquer aux lignes de commande client configurées pour le retrait dans le PDV.
- **Exécuter le mode de livraison** – Spécifiez le mode de livraison qui doit être appliqué aux lignes de commande client qui sont considérées comme des lignes de commande à exécuter lors de la création d’un panier mixte, où certaines lignes seront récupérées ou expédiées, et d’autres lignes seront exécutées par le client immédiatement.
- **Pourcentage de frais d’annulation** – Si des frais doivent être appliqués lorsqu’une commande client est annulée, spécifiez le montant de ces frais.
- **Code de frais d’annulation** – Spécifiez le code frais de la Comptabilité client à utiliser lorsque des frais d’annulation sont appliqués aux commandes client annulées via le PDV. Le code frais définit la logique de validation financière pour les frais d’annulation.
- **Code frais d’expédition** – Si l’option **Utiliser les frais automatiques avancés** est définie sur **Oui**, ce paramètre n’a aucun effet. Si cette option est définie sur **Non**, les utilisateurs seront invités à saisir manuellement des frais d’expédition lorsqu’ils créeront des commandes client dans le PDV. Utilisez ce paramètre pour mapper un code frais de Comptabilité client qui sera appliqué aux commandes lorsque les utilisateurs saisiront des frais d’expédition. Le code frais définit la logique de validation financière pour les frais d’expédition.
- **Utiliser les frais automatiques avancés** – Définissez cette option sur **Oui** pour utiliser les frais automatiques calculés par le système lorsque les commandes client sont créées dans le PDV. Ces frais automatiques peuvent être utilisés pour calculer les frais d’expédition ou d’autres frais spécifiques à la commande ou à l’article. Pour plus d’informations sur la configuration et l’utilisation de frais automatiques avancés, consultez [Frais automatiques avancés omnicanaux](./omni-auto-charges.md).

![Onglet Commandes client sur la page des paramètres de Commerce](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Mettre à jour les dispositions de l’écran des transactions dans le PDV

Assurez-vous que la [disposition de l’écran](./pos-screen-layouts.md) du PDV est configuré pour prendre en charge la création et la gestion des commandes client, et que toutes les opérations de PDV requises sont configurées. Voici quelques-unes des opérations de PDV recommandées pour prendre en charge correctement la création et la gestion des commandes client :
- **Expédier tous les produits** – Cette opération permet de spécifier que toutes les lignes du panier de transaction seront expédiées vers une destination.
- **Expédier des produits sélectionnés** – Cette opération permet de spécifier que les lignes sélectionnées dans le panier de transaction seront expédiées vers une destination.
- **Récupérer tous les produits** – Cette opération permet de spécifier que toutes les lignes du panier de transaction seront retirées à un emplacement de magasin sélectionné.
- **Récupérer tous les produits sélectionnés** – Cette opération permet de spécifier que les lignes sélectionnées dans le panier de transaction seront retirées à un emplacement de magasin sélectionné.
- **Exécuter tous les produits** – Cette opération permet de spécifier que toutes les lignes du panier de transaction seront exécutées. Si cette opération est utilisée dans le PDV, la commande client sera convertie en une transaction au comptant sans livraison.
- **Exécuter des produits sélectionnés** – Cette opération permet de spécifier que les lignes sélectionnées dans le panier de transaction sont exécutées par le client au moment de l’achat. Cette opération n’est utile que dans un scénario de [commande hybride](./hybrid-customer-orders.md).
- **Rappeler une commande** – Cette opération est utilisée pour rechercher et récupérer les commandes client afin que les utilisateurs du PDV puissent les modifier, les annuler ou effectuer des opérations liées à leur exécution selon les besoins.
- **Changer de mode de livraison** – Cette opération permet de changer rapidement le mode de livraison des lignes déjà configurées pour l’expédition, sans exiger que les utilisateurs passent à nouveau par le flux « Expédier tous les produits » ou « Expédier les produits sélectionnés ».
- **Remplacement de dépôt** – Cette opération permet de modifier le montant du dépôt que le client paiera pour la commande client sélectionnée.

![Opérations sur l’écran de transaction du PDV](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Utiliser des commandes client dans le PDV

> [!NOTE]
> La fonctionnalité de reconnaissance des revenus n’est actuellement pas prise en charge pour une utilisation dans les canaux de Commerce (commerce électronique, PDV, centre d’appels). Les articles configurés avec la reconnaissance des revenus ne doivent pas être ajoutés aux commandes créées dans les canaux de Commerce. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Créer une commande client pour les produits qui seront expédiés au client

1. Sur l’écran de transaction du PDV, ajoutez un client à la transaction.
2. Ajoutez des produits dans le chariot.
3. Sélectionnez **Expédier sélectionné** ou **Expédier tout** pour expédier les produits à une adresse du compte client.
4. Sélectionnez l’option pour créer une commande client.
5. Confirmez ou modifiez l’emplacement d’« expédition », confirmez ou modifiez l’adresse de livraison et sélectionnez un mode de livraison.
6. Saisissez la date d’expédition de la commande souhaitée par le client.
7. Utilisez les fonctions de paiement pour payer les montants calculés qui sont dus ou utilisez l’opération **Remplacement de dépôt** pour modifier les montants dus, puis appliquer le paiement.
8. Si le montant total de la commande n’a pas été payé, saisissez une carte de crédit qui sera capturée pour le solde dû sur la commande lors de sa facturation.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Créer une commande client pour les produits que le client viendra retirer

1. Sur l’écran de transaction du PDV, ajoutez un client à la transaction.
2. Ajoutez des produits dans le chariot.
3. Sélectionnez **Retrait sélectionné** ou **Récupérer tout** pour lancer la configuration du retrait des commandes.
4. Sélectionnez l’emplacement du magasin où le client viendra retirer les produits sélectionnés.
5. Sélectionnez la date à laquelle l’article sera retiré.
6. Utilisez les fonctions de paiement pour payer les montants calculés qui sont dus ou utilisez l’opération **Remplacement de dépôt** pour modifier les montants dus, puis appliquer le paiement.
7. Si le montant total de la commande n’a pas été réglé, indiquez si le client effectuera le paiement plus tard (lors du retrait) ou si une carte de crédit sera marquée sous forme de jeton maintenant, puis utilisée et capturée au moment du retrait.

### <a name="edit-an-existing-customer-order"></a>Modifier une commande client existante

Les commandes de vente au détail créées dans le canal en ligne ou en magasin peuvent être rappelées et modifiées via le PDV selon les besoins.

> [!IMPORTANT]
> Toutes les commandes de produits ne peuvent pas être modifiées via l’application PDV. Les commandes créées dans un canal de centre d’appels ne peuvent pas être modifiées par le biais du PDV si le paramètre [Activer la finalisation de la commande](./set-up-order-processing-options.md#enable-order-completion) est activé pour le canal du centre d’appels. Pour garantir un traitement correct des paiements, les commandes provenant d’un canal de centre d’appels et qui utilisent la fonctionnalité Activer l’achèvement de commande doivent être modifiées par le biais de l’application du centre d’appels du siège de Commerce.

Dans les versions 10.0.17 et ultérieures, les utilisateurs peuvent modifier les commandes éligibles via l’application PDV, même si la commande est partiellement traitée. Cependant, les commandes entièrement facturées ne peuvent toujours pas être modifiées par le biais du PDV. Pour activer cette fonctionnalité, activez la fonctionnalité **Modifier les commandes partiellement exécutées dans le point de vente** dans l’espace de travail **Gestion des fonctionnalités**. Si cette fonctionnalité n’est pas activée, ou si vous utilisez la version 10.0.16 ou antérieure, les utilisateurs ne pourront modifier les commandes client dans le PDV que si la commande est complètement ouverte. De plus, si la fonctionnalité est activée, vous pouvez limiter le nombre de magasins qui peuvent modifier les commandes partiellement traitées. L’option permettant de désactiver cette fonctionnalité pour des magasins spécifiques peut être configurée via le **Profil de la fonctionnalité** sous le raccourci **Général**.


1. Sélectionnez **Rappeler la commande**.
2. Utilisez **Rechercher** pour entrer des filtres pour trouver la commande, puis sélectionnez **Appliquer**.
3. Sélectionnez la commande dans la liste des résultats, puis sélectionnez **Modifier**. Si le bouton **Modifier** n’est pas disponible, la commande est dans un état où elle ne peut pas être modifiée.
4. À partir du panier de transaction, apportez les modifications nécessaires à la commande client. Certaines modifications peuvent être interdites lors de la modification.
5. Terminez le processus de modification en sélectionnant une opération de paiement.
6. Pour quitter le processus de modification sans enregistrer les modifications, vous pouvez utiliser l’opération **Annuler la transaction**.



### <a name="cancel-a-customer-order"></a>Annuler une commande client

1. Sélectionnez **Rappeler la commande**.
2. Utilisez **Rechercher** pour entrer des filtres pour trouver la commande, puis sélectionnez **Appliquer**.
3. Sélectionnez la commande dans la liste des résultats, puis sélectionnez **Annuler**. Si le bouton **Annuler** n’est pas disponible, la commande est dans un état où elle ne peut plus être annulée.
4. Si des frais d’annulation sont configurés, confirmez-les. Vous pouvez ajuster les frais d’annulation avant de les confirmer, au besoin. 
5. À partir du panier de transaction, terminez le processus d’annulation en sélectionnant une opération de paiement. Si les dépôts payés dépassent les frais d’annulation, des remboursements peuvent être dus.
6. Pour quitter le processus d’annulation sans enregistrer les modifications, vous pouvez utiliser l’opération **Annuler la transaction**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Finalisation de l’expédition de la commande client ou le retrait au PDV

Une fois la commande créée, les articles seront retirés par le client dans un magasin ou expédiés, selon la configuration de la commande. Pour plus d’informations sur ce processus, consultez la documentation sur [l’exécution des commandes en magasin](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flux de transaction asynchrone pour les commandes client

Les commandes client peuvent être créées dans le PDV en mode synchrone ou asynchrone. Si vous remarquez des problèmes de performances ou des retards utilisateur lorsque vous créez des commandes client dans le PDV, envisagez d’activer la création de commande asynchrone.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Activer les commandes client à créer en mode asynchrone

1. Au siège de Commerce, sur la page **Profils de fonctionnalité**, sélectionnez le profil de fonctionnalité correspondant au magasin que vous souhaitez configurer.
2. Dans l’organisateur **Général**, définissez l’option **Créer une commande client en mode asynchrone** sur **Oui**.

Lorsque l’option **Créer une commande client en mode asynchrone** est définie sur **Oui**, les commandes client sont toujours créées en mode asynchrone, même si Retail Transaction Service (RTS) est disponible. Si vous définissez cette option sur **Non**, les commandes client sont toujours créées en mode synchrone à l’aide de RTS. Lorsque les commandes client sont créées en mode asynchrone, elles sont extraites et créées en tant que transactions de vente au détail au siège de Commerce à partir des tâches d’extraction Commerce (P). Les commandes client correspondantes pour les transactions de vente au détail sont créées lorsque l’option **Synchroniser les commandes** est exécutée manuellement ou via un processus de traitement par lots.

## <a name="additional-resources"></a>Ressources supplémentaires

[Commandes client hybrides](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]