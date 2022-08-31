---
title: Statut de l'emplacement de l'entrepôt
description: Cet article fournit une vue d’ensemble de la fonctionnalité de statut de l’emplacement de l’entrepôt.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 9b12a7d6a7ce388c8fd049c4aef79ea57c82ae60
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336093"
---
# <a name="warehouse-location-status"></a>Statut de l’emplacement de l’entrepôt

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management comprend plusieurs champs d’emplacement qui vous offrent de la flexibilité lorsque vous travaillez avec des emplacements et que vous les gérez. Vous pouvez inclure des statuts d’emplacement dans la requête de directive d’emplacement pour fournir un meilleur contrôle sur le flux de l’entrepôt.

Les quatre champs suivants de la page **Emplacements** effectuent le suivi des informations sur le statut actuel d’un emplacement. Ces champs permettent aux responsables d’entrepôt d’avoir un aperçu du statut des emplacements d’entrepôt. Ils permettent également de générer des rapports et un filtrage avancés.

- **Numéro d’article** - Article qui se trouve actuellement à l’emplacement. Si l’emplacement contient plusieurs articles, ce champ est vide.
- **Date et heure de la dernière activité** - Horodatage de la dernière transaction d’entrepôt effectuée à l’emplacement.
- **Date âgée** - Date à laquelle le stock de l’emplacement a été introduit dans l’entrepôt. Cette valeur est calculée en fonction de la date âgée du contenant. Elle est précise pour les emplacements dont le contenant fait l’objet d’un suivi, mais elle peut ne pas être précise pour les emplacements qui ne font pas l’objet d’un suivi par contenant.
- **Statut de l’emplacement** - Statut de l’emplacement. Quatre valeurs sont possibles :

    - **Indéterminé** - Le profil d’emplacement ne peut pas effectuer le suivi du statut. Par conséquent, le statut actuel est inconnu.
    - **Vide** - Il n’y a actuellement aucun stock à l’emplacement.
    - **Prélèvement** - Les transactions sortantes ont été effectuées à l’emplacement depuis qu’il a été vide pour la dernière fois.
    - **Stockage** - Seules les transactions sortantes ont été effectuées à l’emplacement depuis que l’emplacement a été vide pour la dernière fois.

## <a name="turn-the-warehouse-location-status-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité de statut de l’emplacement de Warehouse

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Statut d'emplacement de Warehouse* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-warehouse-location-status"></a>Configurer le statut de l’emplacement dans l’entrepôt

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Préparer les exemples de données requis pour l’exemple de scénario

Avant de commencer à travailler sur le scénario, vous devez activer des exemples de données et configurer la fonctionnalité comme décrit dans cette section. Pour terminer l’exemple de scénario, vous devez utiliser l’application mobile Gestion des entrepôts ou l’émulateur basé sur un navigateur. La procédure fournie ici est basée sur l’application mobile Gestion des entrepôts. La procédure de l’émulateur basé sur un navigateur est similaire.

#### <a name="use-the-usmf-legal-entity"></a>Utiliser l’entité juridique USMF

Pour utiliser l’exemple de scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

#### <a name="set-up-location-profiles"></a>Définir des profils d’emplacement

L’exemple de scénario nécessite que vous prépariez deux profils d’emplacement.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.
1. Sélectionnez **Modifier** pour afficher la page en mode d’édition.
1. Sélectionnez le profil **VRAC-06**.
1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Activer l’article à l’emplacement :** Définissez cette option sur _Oui_.
    - **Activer la date et l’heure de l’activité de l’emplacement :** Définissez cette option sur _Oui_.
    - **Activer le statut de l’emplacement :** Définissez cette option sur _Oui_.

    Ces options contrôlent si les champs de référence sur l’emplacement sont actifs.

1. Répétez les étapes 3 et 4 pour le profil **PRÉLEVER-06**.

> [!NOTE]
> Lorsque les paramètres du profil d’emplacement (**Activer l’article dans l’emplacement**, **Activer l’activité d’emplacement**, **Activer le statut de l’emplacement**) sont définis sur *Oui*, le système met immédiatement à jour les emplacements concernés en exécutant la tâche *Vérification de la cohérence du statut des emplacements de l’entrepôt*.

### <a name="scenario"></a>Scénario

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, sur l’organisateur **Fournisseur**, dans le champ **Compte fournisseur**, sélectionnez *104*.
1. Dans l’organisateur **Général**, dans le champ **Entrepôt**, sélectionnez *61*.
1. Cliquez sur **OK**.
1. Votre nouvelle commande fournisseur (CF) est ouverte. Elle comprend une ligne vide dans la grille **Lignes de commande fournisseur**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** _A0002_
    - **Quantité :** _5_

1. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer** pour confirmer la commande fournisseur.
1. Sur l’appareil mobile, accédez à **Entrant \> Réception d’achat**.
1. Sélectionnez le champ **PONUM**, entrez le numéro de la commande fournisseur et confirmez.
1. Sélectionnez le champ **ITEM**, entrez le numéro d’article *A0002* et confirmez.
1. Sur la page **QTY**, entrez *5* comme quantité, et confirmez.

    Vous pouvez entrer la quantité de l’une des manières suivantes :

    - Sélectionnez le signe plus (**+**) ou le signe moins (**–**) pour additionner ou soustraire une valeur numérique.
    - Sélectionnez le champ vide entre le signe plus (**+**) et signe moins (**–**) pour ouvrir le pavé numérique.

1. Confirmez votre sélection du numéro d’article *A0002* et d’une quantité de *5*. Un message « Travail terminé » apparaît en bas de la page.
1. Cliquez sur le bouton Menu (parfois appelé hamburger ou bouton hamburger) dans le coin supérieur droit, puis sélectionnez **Annuler** pour quitter **Réception d’achat** et revenez au menu **Entrant**.
1. Sur la page de la commande fournisseur, sélectionnez **Détails du travail** au dessus de la grille **Lignes de la commande fournisseur**.
1. Sur l’onglet **Général**, notez les valeurs **ID de travail** et **ID de contenant cible** créées.
1. Dans la section **Lignes**, notez les valeurs **Emplacement** pour les types de travail *Prélèvement* et *Rangement*.
1. Sur l’appareil mobile, accédez à **Entrant \> Rangement d’achat**.
1. Sélectionnez le champ **ID**, entrez l’ID de travail et confirmez.
1. Confirmez une fois de plus pour terminer l’entrée *Prélèvement*.
1. Sélectionnez le bouton Menu dans le coin supérieur droit de la page, puis sélectionnez *Terminé* pour terminer le travail de **Prélèvement**.
1. Notez l’emplacement de rangement et confirmez. Un message « Travail terminé » apparaît en bas de la page.
1. Sélectionnez le bouton Menu dans le coin supérieur droit, puis sélectionnez **Annuler** pour quitter **Rangement d’achat** et revenir au menu **Entrant**.
1. Sélectionnez **Précédent** pour revenir au menu principal.
1. Dans, Dynamics 365 Supply Chain Management, accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Filtrez **Emplacement** et entrez l’emplacement de rangement du travail de la commande fournisseur. Les résultats suivants devraient s’afficher :

    - La colonne **Statut de l’emplacement** affiche une valeur de *Stockage*, car la dernière transaction à cet emplacement a été un rangement.
    - La colonne **Numéro d’article** affiche une valeur de *A0002*, car cet article a été reçu et rangé à l’emplacement.
    - La colonne **Date et heure de la dernière activité** indique l’horodatage de la date et de l’heure auxquelles le travail a été terminé à l’emplacement.

1. Sur l’appareil mobile, accédez à **Qualité \> Mouvement**.
1. Sélectionnez le champ **LOC/LP** et entrez l’emplacement que vous avez noté lors des étapes précédentes.
1. Confirmez les informations affichées. Notez le numéro de contenant généré.
1. Sur l’écran **Informations sur la destination**, sélectionnez **LOC/LP** et entrez *06A07R2S1B* comme emplacement vers lequel déplacer l’article.
1. Sur l’écran **Informations sur la destination**, confirmez la valeur **LP** (l’ID du contenant cible), qui est générée automatiquement. Un message « Travail terminé » apparaît en bas de la page.
1. Sélectionnez le bouton Menu dans le coin supérieur droit, puis sélectionnez **Annuler** pour quitter **Mouvement** et revenir au menu **Gestion de la qualité**.
1. Sélectionnez **Précédent** pour revenir au menu principal.
1. Dans, Dynamics 365 Supply Chain Management, accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Actualisez la page **Emplacements** et affichez à nouveau l’emplacement de rangement d’origine. Notez que le champ **Statut de l’emplacement** est désormais défini sur *Vide*, et que la colonne **Numéro d’article** est vide.
1. Affichez l’enregistrement pour l’emplacement *06A07R2S1B* et notez que la valeur **Statut** est devenue *Stockage*, et que les champs **Numéro d’article** et **Date et heure de la dernière activité** ont été mis à jour.
1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez *US-002*.
1. Dans le champ **Entrepôt**, sélectionnez *61*.
1. Cliquez sur **OK**.
1. Votre nouvelle commande client est ouverte. Elle comprend une ligne vide dans la grille **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** _A0002_
    - **Quantité :** _1_

1. Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la ligne de commande. Cliquez ensuite sur le bouton **Fermer** (**X**) dans le coin supérieur droit pour fermer la page.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Dans la section **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails du travail**.
1. Copiez la valeur de l’**ID de travail** créée.
1. Sur l’appareil mobile, accédez à **Sortant \> Prélèvement des ventes**.
1. Sélectionnez le champ **ID**, entrez l’ID de travail copié précédemment et confirmez.
1. Sur la page **Commandes client : prélèvement**, le champ **LOC** indique l’emplacement de prélèvement comme emplacement de rangement créé précédemment. Notez l’emplacement.
1. Sélectionnez le champ **LOC**, entrez l’emplacement et confirmez.
1. Sélectionnez le champ **LP**, entrez le numéro de contenant dont vous avez pris note lors de l’activité de mouvement et confirmez.
1. Sélectionnez le champ **Article**, entrez le numéro d’article *A0002* et confirmez.
1. Sur la page **QTY**, entrez *1* comme quantité, et confirmez.

    Vous pouvez entrer la quantité de l’une des manières suivantes :

    - Sélectionnez le signe plus (**+**) ou le signe moins (**–**) pour additionner ou soustraire une valeur numérique.
    - Sélectionnez le champ vide entre le signe plus (**+**) et signe moins (**–**) pour ouvrir le pavé numérique.

1. Sélectionnez le champ **TARGET LP**, entrez un ID de contenant cible défini par l’utilisateur et confirmez.
1. Confirmez une fois de plus pour terminer le travail de prélèvement. Un message « Travail terminé » apparaît en bas de la page.
1. Sélectionnez le bouton Menu dans le coin supérieur droit, puis sélectionnez **Annuler** pour terminer l’activité de prélèvement et revenez au menu **Sortant**.
1. Dans, Dynamics 365 Supply Chain Management, accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Filtrez **Emplacement** et entrez l’emplacement de prélèvement du travail de la commande client.
1. Notez que le champ **Statut de l’emplacement** de l’emplacement auquel le travail de commande client est prélevé est désormais défini sur *Prélèvement*, et que le champ **Date et heure de la dernière activité** a été mis à jour.

> [!NOTE]
> Les champs d’emplacement sont mis à jour uniquement par les transactions d’entrepôt. Si vous déplacez le stock à l’aide d’un journal ou d’autres processus non WMS, les champs ne seront pas mis à jour.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]