---
title: Activer plusieurs modes de livraison de retrait pour les commandes des clients
description: Cet article explique les fonctionnalités de Microsoft Dynamics 365 Commerce qui vous permettent de créer des commandes client pour le retrait en magasin.
author: hhainesms
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e4d8883b3dc1c4a0e12bcb00b6441f76d73da92e
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831582"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Activer plusieurs modes de livraison de retrait pour les commandes des clients

[!include [banner](includes/banner.md)]


Dans Microsoft Dynamics 365 Commerce, les organisations peuvent définir plusieurs modes de livraison parmi lesquels les acheteurs ou les vendeurs peuvent choisir lorsqu’ils créent une commande qui sera retirée en magasin. De cette façon, les organisations peuvent offrir plusieurs options de retrait à leurs acheteurs. Par exemple, de nombreux détaillants offrent maintenant aux acheteurs le choix entre le retrait en magasin ou le retrait à des points relais pour leurs commandes. Commerce prend en charge la configuration de ces différents modes de livraison de retrait. Les utilisateurs peuvent ensuite en profiter lorsqu’ils créent des commandes client dans n’importe quel canal de commerce pris en charge (e-commerce, centre d’appels ou magasin).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Activer et configurer des modes de livraison de retrait

La fonctionnalité **Prise en charge de plusieurs modes de livraison de retrait** dans l’espace de travail **Gestion des fonctionnalités** de Commerce Headquarters est rendue obligatoire et doit être activée dans l’environnement.

Si vous avez précédemment défini un mode de livraison avec retrait sur la page **Paramètres Commerce**, ce mode apparaît dans la configuration actuelle des modes de livraison avec retrait.

![Modes de livraison de retrait sur la page Paramètres de Commerce.](media/multiplepickupparameter.png)

Vous pouvez définir plusieurs modes de livraison de retrait sur la grille **Mode de retrait de livraison** dans **Paramètres Commerce** > **onglet Commandes client** > raccourci **Modes de livraison**.  

Les champs **Effectuer le mode de livraison** et **Mode de livraison électronique** et l’option **Afficher uniquement les options du mode transporteur pour les ordres d’expédition**, ont été déplacés vers ce raccourci.

Avant de configurer des modes de livraison de retrait supplémentaires, vous devez définir les modes de livraison. Sur la page **Modes de livraison** de Commerce Headquarters, ajoutez les modes de livraison qui doivent être considérés comme des modes de livraison en retrait. Assurez-vous que toute la configuration est terminée. Par exemple, si vous proposez le retrait en point-relais comme option de livraison pour vos acheteurs en ligne pour certains magasins, vous devez créer un nouveau mode de livraison à cet effet. Vous pouvez créer ce mode de livraison en utilisant « retrait en point-relais » comme description. Vous devrez ensuite vous assurer que le mode de livraison « retrait en point-relais » est mappé sur tous les canaux Commerce qui peuvent l’offrir, y compris les magasins en ligne qui peuvent offrir cette option et les canaux de magasin individuels qui offriront cette méthode d’exécution. Les modes de livraison doivent également être liés aux produits. Dans cet exemple, s’il y a certains produits qui ne peuvent pas être livrés à l’aide du « retrait en point-relais », vous devez vous assurer que ces articles sont exclus. Lorsque vous avez terminé d’ajouter tous les nouveaux modes de livraison, exécutez la tâche **Traiter les modes de livraison** pour créer les relations entre le mode de livraison, les canaux et les articles. Une fois la tâche terminée, ouvrez la page **Calendrier de distribution** de Commerce Headquarters et exécutez la tâche de distribution **1120** pour garantir que les bases de données pertinentes du canal Commerce sont mises à jour avec votre nouvelle configuration de mode de livraison.

![Exemple de configuration de mode de livraison en retrait à un point-relais.](media/pickupmodes.png)

Après avoir défini les modes de livraison en retrait supplémentaires, ajoutez-les à la grille **Mode de livraison en retrait** sur la page **Paramètres de Commerce**. Exécutez ensuite les tâches de distribution appropriées pour mettre à jour les bases de données de canal de Commerce pertinentes avec la modification de configuration.

> [!NOTE]
> En dehors du mode de livraison en retrait existant qui est copié dans la grille **Mode de livraison en retrait** lorsque vous activez la **Prise en charge de plusieurs modes de livraison en retrait**, pour chaque configuration de mode de livraison en retrait supplémentaire que vous créez, vous devez configurer de nouveaux modes de livraison. Lorsque vous ajoutez des modes de livraison à al grille **Mode de livraison en retrait**, Commerce vérifie si des lignes de vente ouvertes actives les utilisent déjà. Si des lignes de vente ouvertes sont trouvées, vous recevez un message d’erreur. Les modes de livraison ne sont pas considérés comme des modes de livraison en retrait tant que toutes les lignes de vente ouvertes qui les utilisent n’ont pas été fermées (facturées ou annulées).


### <a name="e-commerce-site-configurations"></a>Configurations du site d’e-commerce

Quand la fonctionnalité **Prise en charge de plusieurs modes de livraison en retrait** est activée, les modules suivants sur les pages d’e-commerce affichent les nouveaux modes de livraison en retrait tels que configurés :

- Zone d’achat
- Sélecteur de magasin
- Chariot
- Informations sur le prélèvement
- Confirmation de commande
- Détails de la commande

Aucune étape supplémentaire n’est requise sur les pages d’e-commerce pour rendre les modes de livraison en retrait disponibles.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Utiliser plusieurs modes de livraison en retrait

Lorsque plusieurs modes de livraison en retrait sont disponibles pour un canal, une expérience améliorée est offerte aux clients lorsqu’ils achètent des produits qui seront retirés. 

- Dans les canaux d’e-commerce, les acheteurs peuvent sélectionner n’importe quel mode de livraison en retrait valide disponible. Par exemple, un détaillant définit deux modes de livraison en retrait (retrait en magasin et retrait en point-relais), tous deux configurés dans la grille **Mode de livraison en retrait**, et les deux sont valables pour le canal de traitement des commandes et le produit qu’un acheteur achète actuellement. Dans ce cas, l’acheteur peut sélectionner son mode de livraison en retrait préféré. Le mode de livraison en retrait sélectionné devient alors le mode de livraison qui est lié à la ligne de commande client lorsque la commande est créée dans Commerce Headquarters.

    ![Sélection d’une option de retrait dans l’e-commerce.](media/pickupecommerce.png)

- Dans les canaux des magasins, si une commande client pour le retrait est créée via l’application de point de vente (PDV), le vendeur est invité à choisir parmi les modes de livraison en retrait disponibles, le cas échéant. Si un seul mode de livraison en retrait valide est disponible pour le canal et l’article, le vendeur n’est pas invité à le sélectionner. Au lieu de cela, le mode de livraison en retrait disponible est automatiquement appliqué aux lignes de commande.

    ![Sélection d’une option de retrait dans l’application PDV.](media/pickuppos.png)

- Dans les canaux du centre d’appels, lorsque les utilisateurs créent des ordres de retrait, ils peuvent sélectionner manuellement tout mode de livraison en retrait défini qui est lié au canal du centre d’appels. Le système valide ensuite que le mode de livraison en retrait sélectionné peut être utilisé lorsque l’article qui y est lié est commandé. Lorsqu’un mode de livraison en retrait est sélectionné dans les canaux du centre d’appels, les lignes de commande client doivent être liées à un entrepôt de magasin valide. Si un entrepôt hors magasin est défini sur une ligne de vente de centre d’appels, un mode de livraison en retrait ne peut pas être défini sur cette ligne de vente.
- Les vendeurs peuvent utiliser l’opération **Rappel de commande** ou **Exécution des commandes** dans l’application PDV pour récupérer une liste de commandes ou de lignes de commande pour le retrait. Si un vendeur utilise un filtre de recherche prédéfini pour afficher toutes les commandes qui seront retirées dans le magasin actuel, les demandes sont modifiées pour garantir que les résultats de la recherche incluent toutes les commandes éligibles qui utilisent un mode de livraison en retrait. Les utilisateurs du PDV peuvent également utiliser des filtres existants pour réduire la liste des commandes à un mode de livraison en retrait spécifique. Par exemple, ils ne peuvent afficher que les commandes en retrait à un point-relais.

    ![Filtre pour les modes de livraison en retrait appliqués à une liste d’ordres de rappel.](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Considérations sur la gestion des commandes distribuées

Les fonctionnalités de [gestion des commandes distribuées](./dom.md) de Commerce ignorent toutes les lignes de vente marquées pour le retrait en magasin. Ces fonctionnalités ont été mises à jour pour garantir que les lignes de vente liées aux modes de livraison en retrait configurés contournent la logique DOM et ne seront pas réaffectées à un nouvel entrepôt d’exécution.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
