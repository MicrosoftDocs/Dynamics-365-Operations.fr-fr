---
title: Application de visibilité des stocks
description: Cet article décrit comment utiliser l’application de visibilité des stocks.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 9886ddbf0b072283cffd73d4bfdc20835ccb3b7c
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762698"
---
# <a name="use-the-inventory-visibility-app"></a>Utiliser l’application Inventory Visibility

[!include [banner](../includes/banner.md)]

Cet article décrit comment utiliser l’application de visibilité des stocks.

La visibilité des stocks fournit une application pilotée par modèle pour la visualisation. Cette application contient trois pages : **Configuration**, **Visibilité opérationnelle** et **Récapitulatif des stocks**. Elle présente les fonctionnalités suivantes :

- Elle fournit une interface utilisateur (IU) pour la configuration du stock disponible et la configuration de la réservation provisoire.
- Elle prend en charge les requêtes de stock disponible en temps réel sur diverses combinaisons de dimensions.
- Elle fournit une IU pour la validation des requêtes de réservation.
- Elle fournit une vue des stocks disponibles pour les produits avec toutes les dimensions.
- Elle fournit une vue d’une liste des stocks disponibles pour les produits avec les dimensions pré-définies. La vue de la liste des stocks disponibles peut être soit un résumé complet, soit un résultat préchargé d’une requête disponible.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, installez et configurez le complément de visibilité des stocks comme décrit dans [Installer et configurer la visibilité des stocks](inventory-visibility-setup.md).

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a>Ouvrir et authentifier l’application Inventory Visibility

Pour ouvrir et authentifier l’application Inventory Visibility, procédez comme suit.

1. Connectez-vous à votre environnement Power Apps.
1. Ouvrir l’application **Inventory Visibility**.
1. Ouvrez la page **Visibilité opérationnelle** dans le volet de gauche.
1. Cliquez sur le bouton **Paramètres** (symbole de l’engrenage) en haut de la page.
1. Dans la boîte de dialogue **Paramètres**, entrez les valeurs **ID client**, **ID locataire** et **Clé secrète client** que vous avez notées lorsque vous avez [installé et configuré Inventory Visibility](inventory-visibility-setup.md).
1. Cliquez sur le bouton **Actualiser** en regard du champ **Jeton du porteur**. Le système génère un nouveau jeton du porteur, basé sur les informations que vous avez saisies.

    ![Paramètres de la requête de stock disponible.](media/inventory-visibility-query-settings.png "Paramètres de requête de stock disponible")

1. Lorsque vous recevez un jeton du porteur valide, fermez la boîte de dialogue. Le jeton du porteur expire au bout d’un certain temps. Vous devez donc l’actualiser de temps en temps lorsque vous devez mettre à jour la configuration, valider ou interroger les données.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a>Configurer l’application Inventory Visibility

La page **Configuration** de l’application Inventory Visibility permet de définir la configuration générale de la gestion des données et la configuration des fonctionnalités. Une fois le complément installé, la configuration par défaut inclut un paramétrage par défaut pour Microsoft Dynamics 365 Supply Chain Management (la source de données `fno`). Vous pouvez examiner le paramètre par défaut. Ensuite, en fonction des besoins de votre entreprise et des exigences de validation de stock du système externe, vous pouvez modifier la configuration pour standardiser la manière dont les modifications de stock peuvent être validées, organisées et interrogées sur les différents systèmes.

Pour plus de détails sur la configuration de la solution, consultez [Configurer la visibilité des stocks](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilité opérationnelle

La page **Visibilité opérationnelle** fournit les résultats d’une requête de stock disponible en temps réel, la validation des réservations et la répartition en fonction de différentes combinaisons de dimensions. Quand la fonctionnalité *OnHandReservation* est [activée](inventory-visibility-configuration.md), vous pouvez également valider les requêtes de réservation à partir de la page **Visibilité opérationnelle**.

### <a name="on-hand-query"></a>Requête de stock disponible

L’onglet **Requête de stock disponible** de la page **Visibilité opérationnelle** affiche les résultats d’une requête de stock disponible en temps réel. Procédez comme suit pour configurer et exécuter une requête.

1. Ouvrir l’application **Inventory Visibility**.
1. Ouvrez la page **Visibilité opérationnelle** dans le volet de gauche.
1. Dans l’onglet **Requête de stock disponible**, entrez les valeurs **ID organisation**, **ID site** et **ID emplacement** que vous souhaitez interroger.
1. Dans le champ **ID produit**, entrez un ou plusieurs ID produit pour obtenir une correspondance exacte pour votre requête. Si vous laissez le champ **ID produit** vide, les résultats incluent tous les produits du site et de l’emplacement spécifiés.
1. Pour obtenir un résultat plus précis (par exemple, une vue par valeurs de dimension telles que la couleur et la taille), sélectionnez les dimensions de regroupement dans le champ **Regrouper le résultat par**.
1. Pour rechercher des éléments ayant une valeur de dimension spécifique (couleur = rouge, par exemple), sélectionnez la dimension dans le champ **Filtrer les dimensions**, puis entrez une valeur de dimension.
1. Sélectionnez **Requête**. Vous recevez soit un message de réussite (vert), soit un message d’échec (rouge). Si la requête échoue, vérifiez vos critères de requête et assurez-vous que votre [jeton du porteur](#open-authenticate) n’a pas expiré.

Une autre façon d’effectuer une requête de stock disponible consiste à lancer des requêtes API directes. Vous pouvez utiliser soit `/api/environment/{environmentId}/onhand/indexquery`, soit `/api/environment/{environmentId}/onhand`. Pour plus d’informations, voir [API publiques de la Inventory Visibility](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Validation de réservation

Utilisez l’onglet **Validation de la réservation** de la page **Visibilité opérationnelle** pour valider une requête de réservation. Avant de pouvoir valider une requête de réservation, vous devez activer la fonctionnalité *OnHandReservation*. Pour plus d’informations sur cette fonctionnalité et comment l’activer, consultez [Réservations de visibilité des stocks](inventory-visibility-reservations.md).

> [!NOTE]
> La possibilité d’effectuer une réservation provisoire par l’interface utilisateur permet de tester la fonctionnalité. Chaque demande de réservation provisoire doit être associée à un changement de ligne d’ordre de transaction (création, modification, suppression, etc.). Ainsi, nous vous recommandons de n’effectuer que des réservations provisoires liées à une commande principale. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md).

Suivez ces étapes pour valider une demande de réservation provisoire en utilisant l’interface utilisateur.

1. Ouvrir l’application **Inventory Visibility**.
1. Ouvrez la page **Visibilité opérationnelle** dans le volet de gauche.
1. Dans l’onglet **Validation de la réservation**, dans le champ **Quantité**, précisez la quantité que vous souhaitez réserver provisoirement.
1. Cochez la case **Activer le stock négatif pour prendre en charge la survente** pour éviter que le stock ne soit survendu ou surréservé.
1. Dans le champ **Opérateur**, sélectionnez la source de données et la mesure physique qui s’appliquent à la quantité réservée provisoirement.
1. Entrez les valeurs **ID organisation**, **ID site**, **ID emplacement** et **ID produit** que vous souhaitez interroger.
1. Pour obtenir un résultat plus précis, sélectionnez une source de données, des dimensions et des valeurs de dimension.

Une autre façon de valider une réservation provisoire consiste à effectuer des requêtes API directes. Utilisez le modèle décrit dans [Créer un événement de réservation](inventory-visibility-api.md#create-one-reservation-event). Sélectionnez ensuite **Valider**. Pour afficher les détails de la réponse à la requête, sélectionnez **Afficher les détails**. Vous pouvez également obtenir la valeur `reservationId` à partir des détails de la réponse.

### <a name="allocation"></a>Répartition

Pour des informations sur la gestion des répartitions à partir de l’interface utilisateur et des API, voir [Répartition des stocks d’Inventory Visibility](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Récapitulatif du stock

La page de **récapitulatif d’inventaire** fournit un récapitulatif d’inventaire pour les produits, avec toutes les dimensions. C’est une vue personnalisée de l’entité *Somme d’inventaire disponible*. Les données récapitulatives d’inventaire seront périodiquement synchronisées à partir de Inventory Visibility.

Pour activer la page de **récapitulatif d’inventaire** et définir la fréquence de synchronisation, suivez ces étapes :

1. Ouvrez la page **Configuration**.
1. Ouvrez l’onglet **Gestion des fonctionnalités et Paramètres**.
1. Réglez l’interrupteur à bascule pour la fonctionnalité **OnHandMostSpecificBackgroundService** sur *Oui*.
1. Lorsque la fonction est activée, la section de **Paramétrage des services** devient disponible et comprend une ligne pour configurer la fonctionnalité **OnHandMostSpecificBackgroundService**. Ce paramètre vous permet de choisir la fréquence à laquelle les données récapitulatives de l’inventaire sont synchronisées. Utilisez les boutons **Haut** et **Bas** dans la collone **Valeur** pour modifier le temps entre les synchronisations (qui peut être aussi bas que 5 minutes). Sélectionnez ensuite **Enregistrer**.

    ![Paramètre OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "Paramètre OnHandMostSpecificBackgroundService")

1. Sélectionnez **Mettre à jour la configuration** pour enregistrer toutes les modifications.

> [!NOTE]
> La fonctionnalité *OnHandMostSpecificBackgroundService* suit uniquement les modifications du produit en stock qui se sont produites après l’activation de la fonctionnalité. Les données des produits qui n’ont pas changé depuis que vous avez activé la fonctionnalité ne seront pas synchronisées du cache du service d’inventaire vers l’environnement Dataverse. Si votre page **Récapitulatif des stocks** n’affiche pas toutes les informations disponibles que vous attendez, ouvrez Supply Chain Management, accédez à **Gestion des stocks > Tâches périodiques > Intégration de la visibilité des stocks**, désactivez le traitement par lots et réactivez-le. Cela fera la poussée initiale, et toutes les données seront synchronisées avec l’entité *Somme de stock disponible* dans les 15 prochaines minutes. Si vous souhaitez utiliser la fonctionnalité *OnHandMostSpecificBackgroundService*, nous vous recommandons de l’activer avant de créer des modifications en cours et d’activer le traitement par lots **Intégration de la Inventory Visibility**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a>Précharger une requête des stocks disponibles simplifiée

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Supply Chain Management stocke une grande quantité d’informations sur votre stock disponible actuel et les rend disponibles à des fins très diverses. Cependant, de nombreuses opérations quotidiennes et intégrations tierces ne nécessitent qu’un petit sous-ensemble de ces détails, et interroger le système pour chacun d’entre eux peut entraîner de grands ensembles de données qui prennent du temps à assembler et à transférer. Par conséquent, le service Inventory Visibility peut périodiquement récupérer et stocker un ensemble simplifié de données d’inventaire disponibles pour rendre ces informations optimisées disponibles en permanence. Les détails de l’inventaire disponible stocké sont filtrés en fonction de critères commerciaux configurables pour garantir que seules les informations les plus pertinentes sont incluses. Étant donné que les listes d’inventaire disponibles filtrées sont stockées localement dans le service Inventory Visibility et sont régulièrement mises à jour, elles prennent en charge un accès rapide, des exportations de données à la demande et une intégration simplifiée avec des systèmes externes.

La page **Précharger le récapitulatif de visibilité des stocks** fournit une vue pour l’entité *Résultats de préchargement de requête d’index disponibles*. Contrairement à l’entité *Récapitulatif des stocks*, l’entité *Résultats de préchargement de requête d’index disponibles* fournit une liste des stocks disponibles pour les produits avec les dimensions sélectionnées. La Inventory Visibility synchronise les données récapitulatives préchargées toutes les 15 minutes.

Pour voir les données sur l’onglet **Précharger le récapitulatif de la visibilité des stocks**, vous devez activer la fonctionnalité *OnHandIndexQueryPreloadBackgroundService* sur l’onglet **Gestion des fonctionnalités** de la page **Configuration**, puis sélectionnez **Mettre à jour la configuration** (voir également [Configurer la visibilité des stocks](inventory-visibility-configuration.md)).

> [!NOTE]
> Comme avec la fonctionnalité *OnhandMostSpecificBackgroudService*, la fonctionnalité *OnHandIndexQueryPreloadBackgroundService* suit uniquement les modifications de stock disponibles qui se sont produites après l’activation de la fonctionnalité. Les données des produits qui n’ont pas changé depuis que vous avez activé la fonctionnalité ne seront pas synchronisées du cache du service d’inventaire vers l’environnement Dataverse. Si votre page **Récapitulatif du stock** n’affiche pas toutes les informations disponibles que vous attendez, accédez à **Gestion des stocks > Tâches périodiques > Intégration de la visibilité des stocks**, désactivez le traitement par lots et réactivez-le. Cela fera la poussée initiale, et toutes les données seront synchronisées avec l’entité *Résultats du préchargement de requête d’index disponibles* dans les 15 prochaines minutes. Si vous souhaitez utiliser cette fonctionnalité, nous vous recommandons de l’activer avant de créer des modifications en cours et d’activer le traitement par lots **Intégration de la Inventory Visibility**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtrer et parcourir les récapitulatifs de stocks

En utilisant le **Filtre avancé** fourni par Dataverse, vous pouvez créer une vue personnelle qui affiche les lignes qui sont importantes pour vous. Les options de filtrage avancées vous permettent de créer un large éventail de vues, des plus simples aux plus complexes. Elles vous permettent également d’ajouter des conditions groupées et imbriquées aux filtres. Pour en savoir plus sur l’utilisation du filtre avancé, voir [Modifier ou créer des vues personnelles à l’aide de filtres de grille avancés](/powerapps/user/grid-filters-advanced).

La page **Récapitulatif des stocks** offre trois champs au-dessus de la grille (**Dimension par défaut**, **Dimension personnalisée** et **Mesure**) que vous pouvez utiliser pour contrôler quelles colonnes sont visibles. Vous pouvez également sélectionner tout en-tête de colonne pour filtrer ou trier le résultat actuel selon cette colonne. La capture d’écran suivante met en évidence les champs de dimension, de filtrage, de nombre de résultats et « charger plus » disponibles sur la page **Récapitulatif des stocks**.

![La page de récapitulatif des stocks.](media/inventory-visibility-onhand-list.png "La page de récapitulatif des stocks")

Étant donné que vous aurez prédéfini les dimensions utilisées pour charger les données de synthèse, la page **Précharger la synthèse d’Inventory Visibility** affiche les colonnes liées aux dimensions. *Les dimensions ne sont pas personnalisables&mdash;le système ne prend en charge que les dimensions de site et d’emplacement pour les listes disponibles préchargées.* La page **Précharger le récapitulatif de la visibilité des stocks** fournit des filtres similaires à ceux de la page **Récapitulatif des stocks**, sauf que les dimensions sont déjà sélectionnées. La capture d’écran suivante met en évidence les champs de dimension, de filtrage, de nombre de résultats et « autre chargement » disponibles sur la page **Précharger le récapitulatif de la visibilité des stocks**.

![La page de résumé Précharger la visibilité des stocks.](media/inventory-visibility-preload-onhand-list.png "La page de résumé Précharger la visibilité des stocks")

Au bas des pages **Précharger le récapitulatif de la visibilité des stocks** et **Récapitulatif des stocks**, vous trouverez des informations telles que « 50 enregistrements (29 sélectionnés) » ou « 50 enregistrements ». Ces informations se réfèrent aux enregistrements actuellement chargés à partir du résultat **Filtre avancé**. Le texte « 29 sélectionnés » fait référence au nombre d’enregistrements qui ont été sélectionnés à l’aide du filtre d’en-tête de colonne pour les enregistrements chargés. Notez aussi la présence d’un bouton **Charger plus** pour charger des enregistrements supplémentaires à partir de Dataverse. Le nombre par défaut d’enregistrements chargés est de 50. Lorsque vous sélectionnez **Charger plus**, les 1 000 enregistrements disponibles suivants sont chargés dans la vue. Le nombre affiché sur le bouton **Charger plus** indique les enregistrements actuellement chargés et le nombre total d’enregistrements pour le résultat **Filtre avancé**.
