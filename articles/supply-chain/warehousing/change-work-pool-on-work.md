---
title: Modifier le pool de travail sur le travail
description: Cette rubrique explique comment utiliser le bouton Modifier le pool de travail pour les éléments de travail afin de modifier le pool de travail du travail existant.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 66d110c3235e8a87b64bf160bdad8524fad6abe5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001147"
---
# <a name="change-work-pool-on-work"></a>Modifier le pool de travail sur le travail

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser des pools de travail pour organiser le travail en groupes. Par exemple, vous pouvez créer un pool de travail pour classer le travail qui se produit dans un emplacement d'entrepôt spécifique.

La fonction *Modifier le pool de travail sur le travail* ajoute un bouton **Changer de pool de travail** sur le volet Actions pour les éléments de travail. Par conséquent, les directeurs d'entrepôt peuvent facilement modifier le pool de travail du travail existant. Cette fonctionnalité permet aux responsables de réagir rapidement aux changements dans l'entrepôt et contribue à améliorer leur capacité à s'adapter aux situations changeantes et au besoin de transférer du travail vers un autre pool de travail.

## <a name="turn-on-the-change-work-pool-on-work-feature"></a>Activer la fonctionnalité Modifier le pool de travail sur le travail

Avant de commencer à configurer ou à utiliser cette fonction, vous devez vous assurer qu'elle est disponible dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Modifier le pool de travail sur le travail*

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Configurer la fonctionnalité Modifier le pool de travail sur le travail

Pour utiliser cette fonctionnalité, vous devez avoir configuré des pools de travail. Vous pouvez également configurer vos modèles de travail pour qu'ils attribuent automatiquement un pool. Si vous souhaitez exécuter l'exemple de scénario fourni plus loin dans cette rubrique, configurez votre système comme décrit dans cette section.

### <a name="set-up-work-pools"></a>Paramétrer des pools de travail

Les pools de travail vous permettent d'organiser les éléments de travail par type. Pour utiliser la fonctionnalité *Modifier le pool de travail sur le travail*, vous devez avoir au moins deux pools de travail disponibles. Pour afficher et ajouter des pools de travail, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Pools de travail**.
1. Si vous travaillez avec des données de démonstration de la société **USMF** et étudierez l'exemple de scénario fourni plus loin dans cette rubrique, ajoutez deux pools de travail ayant les paramètres suivants :

    - Pool de travail 1 :

        - **ID du pool de travail :** *Webshop*
        - **Description :** *Boutique en ligne*

    - Pool de travail 2 :

        - **ID du pool de travail :** *CallCenter*
        - **Description :** *Centre d'appel*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-work-templates"></a>Définir des modèles de travail

Pour chacun de vos modèles de travail, vous pouvez définir un pool de travail par défaut, selon vos besoins. Pour chaque modèle pertinent, vous attribuez un pool de travail dans la colonne **ID du pool de travail**. Dans ce cas, tous les éléments de travail générés à l'aide d'un modèle donné héritent automatiquement du pool de travail attribué. Si vous travaillez avec les données de démonstration de la société **USMF** et étudierez l'exemple de scénario fourni plus loin dans cette rubrique, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans le volet Actions, sélectionnez **Modifier** pour afficher la page en mode d'édition.
1. Modifiez le modèle en définissant les valeurs suivantes :

    - **Modèle de travail :** *62 Prélever pour emballage*
    - **ID du pool de travail :** *Webshop*

1. Sélectionnez **Enregistrer**.

## <a name="example-scenario"></a>Exemple de scénario

Ce scénario montre comment modifier le flux de traitement d'un élément de travail existant en modifiant son pool de travail. Il utilise les données de démonstration de la société **USMF** et les paramètres suggérés précédemment dans cette rubrique.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Créer une commande client et la lancer dans l'entrepôt

1. Confirmez qu'il y a suffisamment de stock disponible pour les articles *A0001* et *A0002* dans l'entrepôt *62*. Accédez à **Gestion des stocks \> Recherches et états \> Liste disponible**, et modifiez les filtres comme indiqué ici :

    - La valeur **Entrepôt** commence par *62*.
    - La valeur du **Numéro d'article** est *A001* ou *A002*.

    Les données de démonstration doivent avoir une quantité de 10 chacune.

    Ensuite, vous devez créer une commande client.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-007*
    - **Entrepôt :** *62*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle doit inclure une nouvelle ligne vide dans la grille de l'organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *2*

1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
1. Fermez la page.
1. Dans l'organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour ajouter une autre ligne à votre commande client. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *2*

1. Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
1. Fermez la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.
1. Vous recevez des messages d’information indiquant l’ID de vague et les ID d’expédition créés à partir du lancement. Prenez note de l'ID de vague.

### <a name="review-the-outbound-wave"></a>Examiner la vague sortante

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Dans la grille, cherchez l'ID de vague qui a été créé à partir du lancement de la commande client.
1. Sélectionnez l'ID de vague pour afficher les détails.
1. Dans l'organisateur **Lignes de vague**, assurez-vous qu'un ID d'expédition est affiché pour la commande client.

    > [!TIP]
    > Si l'option **Traiter la vague à la libération dans l’entrepôt** est *Non* dans la configuration du modèle de vague d'expédition, vous devez traiter manuellement la vague en sélectionnant **Traiter** dans l'onglet **Vague** du volet Actions pour créer un travail.

1. Assurez-vous que la vague a été traitée. Ce traitement crée le travail requis.

### <a name="view-work-details-and-change-the-work-pool"></a>Afficher les détails du travail et modifier le pool de travail

Vous pouvez utiliser la page **Détails du travail** pour afficher le travail créé et gérer le pool de travail.

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Sélectionnez la ligne du travail qui vient d'être créé. La colonne **Numéro de commande** affiche le numéro de la commande client.

    Le champ **ID du pool de travail** est défini sur l'ID du pool de travail qui a été configuré dans le modèle de travail.

    > [!TIP]
    > Si vous ne voyez pas le champ **ID du pool de travail**, ajoutez la colonne à la grille, puis actualisez la page.

1. Pour modifier le pool de travail associé à l'ID de travail, dans le volet Actions, dans l'onglet **Travail**, sélectionnez **Changer de pool de travail**.
1. Dans la boîte de dialogue **Changer de pool de travail**, dans l'organisateur **Paramètres**, dans le champ **ID du pool de travail**, sélectionnez *Centre d'appel*.
1. Sélectionner **OK** pour appliquer les modifications.
1. Notez que la valeur du champ **ID du pool de travail** a maintenant été changée en *CallCenter*.

> [!IMPORTANT]
> Quand la boîte de dialogue **Changer de pool de travail** s'affiche, le champ **ID du pool de travail** peut être vide par défaut. Si le champ est vide lorsque vous sélectionnez **OK** pour appliquer les modifications, vous supprimerez complètement le pool de travail du travail.
>
> En plus de changer de pool de travail, vous pouvez utiliser cette procédure pour ajouter un pool de travail à tout élément de travail qui n'en a pas, ou pour supprimer un pool de travail de tout élément de travail qui en a.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]