---
title: Activer plusieurs modes de livraison de retrait pour les commandes des clients
description: Cette rubrique explique les fonctionnalités de Microsoft Dynamics 365 Commerce qui vous permettent de créer des commandes client pour le retrait en magasin.
author: hhainesms
manager: annbe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 768b20ecc8d15353258c9b3af69b897957d3de60
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594962"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Activer plusieurs modes de livraison de retrait pour les commandes des clients

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Dans Microsoft Dynamics 365 Commerce version 10.0.16 et ultérieure, les organisations peuvent définir plusieurs modes de livraison parmi lesquels les acheteurs ou les vendeurs peuvent choisir lorsqu'ils créent une commande qui sera retirée en magasin. De cette façon, les organisations peuvent offrir plusieurs options de retrait à leurs acheteurs. Par exemple, de nombreux détaillants offrent maintenant aux acheteurs le choix entre le retrait en magasin ou le retrait à des points relais pour leurs commandes. Commerce prend en charge la configuration de ces différents modes de livraison de retrait. Les utilisateurs peuvent ensuite en profiter lorsqu'ils créent des commandes client dans n'importe quel canal de commerce pris en charge (e-commerce, centre d'appels ou magasin).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Activer et configurer des modes de livraison de retrait

Pour utiliser cette fonctionnalité, activez la fonctionnalité **Prise en charge de plusieurs modes de livraison de retrait** dans l'espace de travail **Gestion des fonctionnalités** du siège Commerce. Une fois la fonctionnalité activée, une configuration supplémentaire est requise.

Dans Commerce version 10.0.15 et versions antérieures, les organisations ne peuvent définir qu'un seul mode de livraison comme mode de livraison de retrait désigné. Cette définition se fait sur la page **Paramètres de Commerce**. Dans les versions 10.0.16 et ultérieures, lorsque vous activez la fonctionnalité **Prise en charge de plusieurs modes de livraison de retrait**, le mode de livraison qui était précédemment défini comme le mode de livraison de retrait sur la page **Paramètres de Commerce** est automatiquement copiée dans la nouvelle configuration pour les modes de livraison de retrait.

![Modes de livraison de retrait sur la page Paramètres de Commerce](media/multiplepickupparameter.png)

Après avoir activé la fonctionnalité **Prise en charge de plusieurs modes de livraison de retrait**, vous pouvez définir plusieurs modes de livraison de retrait dans la grille **Mode de retrait de livraison** sur le raccourci **Modes de livraison** sur l'onglet **Commandes clients** de la page **Paramètres de Commerce**.

Les champs **Effectuer le mode de livraison** et **Mode de livraison électronique** et l'option **Afficher uniquement les options du mode transporteur pour les ordres d'expédition**, ont été déplacés vers ce raccourci.

Avant de configurer des modes de livraison de retrait supplémentaires, vous devez définir les modes de livraison. Sur la page **Modes de livraison** du siège de Commerce, ajoutez les modes de livraison qui doivent être considérés comme des modes de livraison en retrait. Assurez-vous que toute la configuration est terminée. Par exemple, assurez-vous que le mode de livraison est lié aux canaux et aux articles appropriés. Lorsque vous avez terminé, exécutez la tâche **Traiter les modes de livraison** pour créer les relations entre le mode de livraison, les canaux et les articles. Une fois la tâche terminée, ouvrez la page **Calendrier de distribution** du siège de Commerce et exécutez la tâche de distribution **1120** pour garantir que les bases de données pertinentes du canal Commerce sont mises à jour avec votre nouvelle configuration de mode de livraison.

![Exemple de configuration de mode de livraison en retrait à un point-relais](media/pickupmodes.png)

Après avoir défini les modes de livraison en retrait supplémentaires, ajoutez-les à la grille **Mode de livraison en retrait** sur la page **Paramètres de Commerce**. Exécutez ensuite les tâches de distribution appropriées pour mettre à jour les bases de données de canal de Commerce pertinentes avec la modification de configuration.

> [!NOTE]
> En dehors du mode de livraison en retrait existant qui est copié dans la grille **Mode de livraison en retrait** lorsque vous activez la **Prise en charge de plusieurs modes de livraison en retrait**, pour chaque configuration de mode de livraison en retrait supplémentaire que vous créez, vous devez configurer de nouveaux modes de livraison. Lorsque vous ajoutez des modes de livraison à al grille **Mode de livraison en retrait**, Commerce vérifie si des lignes de vente ouvertes actives les utilisent déjà. Si des lignes de vente ouvertes sont trouvées, vous recevez un message d'erreur. Les modes de livraison ne sont pas considérés comme des modes de livraison en retrait tant que toutes les lignes de vente ouvertes qui les utilisent n'ont pas été fermées (facturées ou annulées).

> [!IMPORTANT]
> Après avoir défini plus d'un mode de livraison en retrait sur la page **Paramètres de Commerce**, la fonctionnalité **Prise en charge de plusieurs modes de livraison en retrait** devient obligatoire et ne peut plus être désactivée. Si vous devez désactiver la fonctionnalité, supprimez tous les modes de livraison en retrait sauf un de la grille **Mode de livraison en retrait**. Lorsqu'un seul mode de livraison en retrait est défini, la fonction n'est plus considérée comme obligatoire et peut être désactivée.

### <a name="e-commerce-site-configurations"></a>Configurations du site d'e-commerce

Quand la fonctionnalité **Prise en charge de plusieurs modes de livraison en retrait** est activée, les modules suivants sur les pages d'e-commerce affichent les nouveaux modes de livraison en retrait tels que configurés :

- Zone d’achat
- Sélecteur de magasin
- Chariot
- Informations sur le prélèvement
- Confirmation de commande
- Détails de la commande

Aucune étape supplémentaire n'est requise sur les pages d'e-commerce pour rendre les modes de livraison en retrait disponibles.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Utiliser plusieurs modes de livraison en retrait

Lorsque plusieurs modes de livraison en retrait sont disponibles pour un canal, une expérience améliorée est offerte aux clients lorsqu'ils achètent des produits qui seront retirés. 

- Dans les canaux d'e-commerce, les acheteurs peuvent sélectionner n'importe quel mode de livraison en retrait valide disponible. Par exemple, un détaillant définit deux modes de livraison en retrait (retrait en magasin et retrait en point-relais), tous deux configurés dans la grille **Mode de livraison en retrait**, et les deux sont valables pour le canal de traitement des commandes et le produit qu'un acheteur achète actuellement. Dans ce cas, l'acheteur peut sélectionner son mode de livraison en retrait préféré. Le mode de livraison en retrait sélectionné devient alors le mode de livraison qui est lié à la ligne de commande client lorsque la commande est créée au siège de Commerce.

    ![Sélection d'une option de retrait dans l'e-commerce](media/pickupecommerce.png)

- Dans les canaux des magasins, si une commande client pour le retrait est créée via l'application de point de vente (PDV), le vendeur est invité à choisir parmi les modes de livraison en retrait disponibles, le cas échéant. Si un seul mode de livraison en retrait valide est disponible pour le canal et l'article, le vendeur n'est pas invité à le sélectionner. Au lieu de cela, le mode de livraison en retrait disponible est automatiquement appliqué aux lignes de commande.

    ![Sélection d'une option de retrait dans l'application PDV](media/pickuppos.png)

- Dans les canaux du centre d'appels, lorsque les utilisateurs créent des ordres de retrait, ils peuvent sélectionner manuellement tout mode de livraison en retrait défini qui est lié au canal du centre d'appels. Le système valide ensuite que le mode de livraison en retrait sélectionné peut être utilisé lorsque l'article qui y est lié est commandé. Lorsqu'un mode de livraison en retrait est sélectionné dans les canaux du centre d'appels, les lignes de commande client doivent être liées à un entrepôt de magasin valide. Si un entrepôt hors magasin est défini sur une ligne de vente de centre d'appels, un mode de livraison en retrait ne peut pas être défini sur cette ligne de vente.
- Les vendeurs peuvent utiliser l'opération **Rappel de commande** ou **Exécution des commandes** dans l'application PDV pour récupérer une liste de commandes ou de lignes de commande pour le retrait. Si un vendeur utilise un filtre de recherche prédéfini pour afficher toutes les commandes qui seront retirées dans le magasin actuel, les demandes sont modifiées pour garantir que les résultats de la recherche incluent toutes les commandes éligibles qui utilisent un mode de livraison en retrait. Les utilisateurs du PDV peuvent également utiliser des filtres existants pour réduire la liste des commandes à un mode de livraison en retrait spécifique. Par exemple, ils ne peuvent afficher que les commandes en retrait à un point-relais.

    ![Filtre pour les modes de livraison en retrait appliqués à une liste d'ordres de rappel](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Considérations sur la gestion des commandes distribuées

Les fonctionnalités de [gestion des commandes distribuées](https://docs.microsoft.com/dynamics365/commerce/dom) de Commerce ignorent toutes les lignes de vente marquées pour le retrait en magasin. Ces fonctionnalités ont été mises à jour pour garantir que les lignes de vente liées aux modes de livraison en retrait configurés contournent la logique DOM et ne seront pas réaffectées à un nouvel entrepôt d'exécution.


[!INCLUDE[footer-include](../includes/footer-banner.md)]