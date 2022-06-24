---
title: Application de visibilité des stocks
description: Cet article décrit comment utiliser l’application de visibilité des stocks.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: db158e3b6ae76f69149db04096f99d3dc4251146
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895755"
---
# <a name="use-the-inventory-visibility-app"></a>Utiliser l’application Inventory Visibility

[!include [banner](../includes/banner.md)]


Cet article décrit comment utiliser l’application de visibilité des stocks.

La visibilité des stocks fournit une application pilotée par modèle pour la visualisation. Cette application contient trois pages : **Configuration**, **Visibilité opérationnelle** et **Récapitulatif des stocks**. Elle présente les fonctionnalités suivantes :

- Elle fournit une interface utilisateur (IU) pour la configuration du stock disponible et la configuration de la réservation provisoire.
- Elle prend en charge les requêtes de stock disponible en temps réel sur diverses combinaisons de dimensions.
- Elle fournit une IU pour la validation des requêtes de réservation.
- Elle fournit une vue personnalisée des stocks disponibles pour les produits avec toutes les dimensions.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, installez et configurez le complément de visibilité des stocks comme décrit dans [Installer et configurer la visibilité des stocks](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Ouvrir l’application Visibilité des stocks

Pour ouvrir l’application Visibilité des stocks, connectez-vous à votre environnement Power Apps et ouvrez **Visibilité des stocks**.

## <a name="configuration"></a><a name="configuration"></a>Configuration

La page **Configuration** de l’application Visibilité des stocks vous permet de définir la configuration du stock disponible et la configuration des réservations provisoires. Une fois le complément installé, la configuration par défaut inclut un paramétrage par défaut pour Microsoft Dynamics 365 Supply Chain Management (la source de données `fno`). Vous pouvez examiner le paramètre par défaut. Désormais, en fonction des besoins de votre entreprise et des exigences de validation de stock de votre système externe, vous pouvez modifier la configuration pour standardiser la manière dont les modifications de stock peuvent être validées, organisées et interrogées sur les multiples systèmes.

Pour plus de détails sur la configuration de la solution, consultez [Configurer la visibilité des stocks](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilité opérationnelle

La page **Visibilité opérationnelle** fournit les résultats d’une requête de stock disponible en temps réel, basée sur diverses combinaisons de dimensions. Quand la fonctionnalité *OnHandReservation* est activée, vous pouvez également valider des requêtes de réservation à partir de la page **Visibilité opérationnelle**.

### <a name="on-hand-query"></a>Requête de stock disponible

L’onglet **Requête de stock disponible** affiche les résultats d’une requête de stock disponible en temps réel.

Lorsque vous sélectionnez l’onglet **Requête de stock disponible**, le système demande vos informations d’identification afin d’obtenir le jeton du porteur requis pour interroger le service de visibilité des stocks. Vous pouvez simplement coller le jeton du porteur dans le champ **BearerToken** et fermer la boîte de dialogue. Vous pouvez ensuite valider une requête de stock disponible.

Si le jeton du porteur n’est pas valide, ou s’il a expiré, vous devez en coller un nouveau dans le champ **BearerToken**. Entrez le valeurs appropriées pour **ID client**, **ID de locataire**, **Clé secrète client**, puis sélectionnez **Actualiser**. Le système obtiendra automatiquement un nouveau jeton du porteur valide.

Pour valider une requête de stock disponible, saisissez la requête dans le corps de la demande. Utilisez le modèle décrit dans [Interroger en utilisant la méthode post](inventory-visibility-api.md#query-with-post-method).

![Paramètres de requête de stock disponible](media/inventory-visibility-query-settings.png "Paramètres de requête de stock disponible")

### <a name="reservation-posting"></a>Validation de réservation

Utilisez l’onglet **Validation de la réservation** pour valider une requête de réservation. Avant de pouvoir valider une requête de réservation, vous devez activer la fonctionnalité *OnHandReservation*. Pour plus d’informations sur cette fonctionnalité, consultez [Réservations de visibilité des stocks](inventory-visibility-reservations.md).

Pour valider une requête de réservation, vous devez saisir une valeur dans le corps de la demande. Utilisez le modèle décrit dans [Créer un événement de réservation](inventory-visibility-api.md#create-one-reservation-event). Sélectionnez ensuite **Valider**. Pour afficher les détails de la réponse à la requête, sélectionnez **Afficher les détails**. Vous pouvez également obtenir la valeur `reservationId` à partir des détails de la réponse.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Récapitulatif du stock

**Récapitulatif du stock** est une vue personnalisée de l’entité *Somme de stock disponible*. Elle fournit un récapitulatif du stock pour les produits avec toutes les dimensions. Les données récapitulatives du stock seront périodiquement synchronisées à partir de la visibilité des stocks toutes les 15 minutes. Pour voir les données sur l’onglet **Récapitulatif du stock**, vous devez activer la fonction *OnHandMostSpecificContexteService* sur l’onglet **Gestion des fonctionnalités**, puis sélectionnez **Mettre à jour la configuration**.

> [!NOTE]
> La fonctionnalité *OnHandMostSpecificBackgroundService* suit uniquement les modifications du produit en stock qui se sont produites après l'activation de la fonctionnalité. Les données des produits qui n'ont pas changé depuis que vous avez activé la fonctionnalité ne seront pas synchronisées du cache du service d'inventaire vers l'environnement Dataverse. Si votre page **Récapitulatif du stock** n'affiche pas toutes les informations disponibles que vous attendez, accédez à **Gestion des stocks > Tâches périodiques > Intégration de la visibilité des stocks**, désactivez le traitement par lots et réactivez-le. Cela fera la poussée initiale, et toutes les données seront synchronisées avec l'entité *Somme d'inventaire disponible* dans les 15 prochaines minutes. Si vous souhaitez utiliser cette fonctionnalité, nous vous recommandons de l'activer avant de créer des modifications en cours et d'activer le traitement par lots **Intégration de la Visibilité des stocks**.

En utilisant le **Filtre avancé** fourni par Dataverse, vous pouvez créer une vue personnelle qui affiche les lignes qui sont importantes pour vous. Les options de filtrage avancées vous permettent de créer un large éventail de vues, des plus simples aux plus complexes. Elles vous permettent également d’ajouter des conditions groupées et imbriquées aux filtres. Pour en savoir plus sur l’utilisation du **Filtre avancé**, voir [Modifier ou créer des vues personnelles à l’aide de filtres de grille avancés](/powerapps/user/grid-filters-advanced).

La partie supérieure de la vue personnalisée fournit trois champs : **Dimension par défaut**, **Dimension personnalisée** et **Mesure**. Vous pouvez utiliser ces champs pour contrôler les colonnes visibles.

Vous pouvez sélectionner l’en-tête de colonne pour filtrer ou trier le résultat actuel.

Le bas de la vue personnalisée affiche des informations telles que « 50 enregistrements (29 sélectionnés) » ou « 50 enregistrements ». Ces informations se réfèrent aux enregistrements actuellement chargés à partir du résultat **Filtre avancé**. Le texte « 29 sélectionnés » fait référence au nombre d’enregistrements qui ont été sélectionnés à l’aide du filtre d’en-tête de colonne pour les enregistrements chargés.

Au bas de la vue se trouve un bouton **Charger plus** que vous pouvez utiliser pour charger des enregistrements supplémentaires à partir de Dataverse. Le nombre par défaut d’enregistrements chargés est de 50. Lorsque vous sélectionnez **Charger plus**, les 1 000 enregistrements disponibles suivants sont chargés dans la vue. Le nombre affiché sur le bouton **Charger plus** indique les enregistrements actuellement chargés et le nombre total d’enregistrements pour le résultat **Filtre avancé**.

![Récapitulatif du stock](media/inventory-visibility-onhand-list.png "Récapitulatif du stock")
