---
title: Calcul du prix exact différé et de la remise pour des performances optimales
description: Cette rubrique décrit la fonction de calcul différé du prix disponible dans le point de vente (PDV) et le centre d’appels Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8c4264c3a4c71e6aab0e1ef8d7d8cfffad065a46
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488361"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Calcul du prix exact différé et de la remise pour des performances optimales

[!include [banner](includes/banner.md)]

Cette rubrique décrit la fonction de calcul différé du prix disponible dans le point de vente (PDV) et le centre d’appels Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce prend en charge la création de remises multilignes qui sont appliquées lorsque plusieurs lignes de vente d’une commande client ou d’un devis sont combinées. Ces remises comprennent des remises mixtes, des remises seuil et des remises sur quantité.

Chaque fois qu’une nouvelle ligne est ajoutée à une commande, le moteur de tarification de Commerce évalue l’ensemble du panier pour déterminer si l’une de ces remises multilignes peut être appliquée. En raison de ce recalcul, l’ajout de nouvelles lignes peut affecter les performances à mesure que la commande client augmente.

Cependant, les entreprises interentreprises (B2B) et certaines entreprises interentreprises (B2C) ont souvent des commandes importantes. Par conséquent, il peut être fastidieux d’attendre que le moteur de tarification recalcule après l’ajout de chaque article au panier. De plus, pour les grosses commandes, il n’est généralement pas très important que le prix exact et la remise soient affichés chaque fois qu’un article est ajouté au panier. Il est plus important que les utilisateurs puissent ajouter des éléments rapidement. La possibilité de retarder le calcul exact du prix et de la remise jusqu’à ce qu’un utilisateur le demande ou qu’une commande soit finalisée peut améliorer considérablement les performances. Cela peut également réduire le temps nécessaire pour passer une commande.

La possibilité de retarder le calcul exact du prix et de la remise est disponible depuis longtemps dans les points de vente. Depuis la version Commerce version 10.0.22, elle est également disponible pour les centres d’appels.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Activer le calcul différé du prix et de la remise pour le PDV

Pour activer le calcul différé du prix et de la remise pour le PDV, procédez comme suit.

1. Dans Commerce Headquarters, accédez au profil de fonctionnalité associé au magasin physique.
1. Sur le raccourci **Montant**, activez la configuration **Calculer manuellement les remises sur plusieurs articles**.
1. Ouvrez le concepteur de disposition d’écran pour les registres où le calcul différé doit être activé.
1. Ajoutez un bouton pour l’opération **Calculer le total** à la grille de boutons souhaitée.
1. Exécutez les tâches **1070** et **1090**.

Désormais, lorsque des articles sont ajoutés à une transaction, les remises multilignes ne sont pas calculées à moins que le caissier ne sélectionne le bouton **Calculer le total**. Une fois que l'option **Calculer le total** est sélectionnée pour une transaction, des remises multilignes seront toujours calculées pour celle-ci. Le caissier ne doit pas sélectionner à nouveau le bouton, même si des articles supplémentaires sont ajoutés au panier. Le système ne laisse pas le caissier capturer le paiement tant que l’option **Calculer le total** n’est pas sélectionnée.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Activer le calcul du prix différé et de la remise pour le centre d’appels

Pour activer le calcul du prix différé et de la remise pour le centre d’appels, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Espaces de travail  \> Gestion des fonctionnalités**.
1. Activez la fonctionnalité **Empêcher le calcul de prix involontaire pour les commandes commerciales**. Cette fonctionnalité est une condition préalable à la capacité de calcul du prix différé et de la remise.

    > [!NOTE]
    > Pour les nouveaux déploiements, la fonctionnalité **Empêcher le calcul de prix involontaire pour les commandes commerciales** est activée par défaut.

1. Accédez à **Paramètres commerciaux \> Prix et remises**.
1. Dans la section **Divers**, activez la configuration **Calculer manuellement les prix et les remises multilignes**.

Désormais, lorsqu’une commande client ou un devis est créé ou modifié dans le centre d’appels, le calcul exact du prix et de la remise est différé. Le moteur de tarification ne tient compte que de la ligne de vente qui est ajoutée ou modifiée et ignore toutes les autres lignes de vente. Le montant net d’un article inclut le calcul du prix et les remises simples (pourcentage de remise ou montant de la remise sur un article individuel). Cependant, les remises mixtes, seuil et sur la quantité ne sont pas appliquées. Les utilisateurs du centre d’appels qui souhaitent voir le prix exact, y compris toutes les remises, peuvent sélectionner l’un des trois boutons : **Recalculer**, **Totaux** ou **Terminer**.

> [!NOTE]
> Pour les commandes du centre d’appels, le système affiche un message d’avertissement pour rappeler à l’utilisateur qu’il doit sélectionner le bouton **Recalculer**, **Totaux** ou **Terminer** pour le calcul exact du prix et de la remise à effectuer. Pour les commandes où le bouton **Terminer** est disponible, l’utilisateur du centre d’appels n’a aucun moyen d’omettre le calcul exact du prix et de la remise, car il doit sélectionner **Terminer** pour terminer la saisie de la commande. Pour les commandes où le bouton **Terminer** n’est pas disponible, aucune action n’indique l’achèvement de la capture de la commande. Par conséquent, l’utilisateur du centre d’appels est responsable de sélectionner le bouton **Recalculer** ou **Totaux** avant de terminer la saisie de la commande.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
