---
title: Fractionnement du travail
description: Cette rubrique fournit des informations sur la fonctionnalité de fractionnement du travail. Cette fonctionnalité vous permet de diviser les ordres de travail volumineux en plusieurs ordres de travail plus petits que vous pouvez ensuite affecter à plusieurs magasiniers. De cette manière, le même travail peut être prélevé simultanément par plusieurs magasiniers.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8a530f3887c3c66295177d480a8c486dd0984153
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965525"
---
# <a name="work-split"></a>Fractionnement du travail

La fonctionnalité de fractionnement du travail vous permet de diviser les ID d'ordres de travail volumineux (c'est-à-dire les ordres de travail avec plusieurs lignes) en plusieurs ID d'ordres de travail plus petits que vous pouvez ensuite affecter à plusieurs magasiniers. De cette manière, le même nombre de création de travail peut être prélevé simultanément par plusieurs magasiniers.

> [!IMPORTANT]
> Vous ne pouvez fractionner que les ordres de travail dont le statut est *Ouvert* ou *En cours*.

## <a name="turn-on-the-work-split-functionality"></a>Activer la fonctionnalité de répartition du travail

Avant de pouvoir utiliser la fonctionnalité de répartition du travail, vous devez activer la fonctionnalité et sa fonctionnalité prérequise dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut des fonctionnalités et les activer si nécessaire.

Tout d'abord, activez la fonctionnalité *Blocage du travail à l'échelle de l'organisation* prérequise si elle n'est pas déjà activée. Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Blocage du travail l'échelle de l'organisation*

> [!NOTE]
> Lorsque cette fonctionnalité est activée, une mise à niveau des données est automatiquement appliquée une fois la fonctionnalité activée dans toutes les entités juridiques.

Ensuite, activez la fonctionnalité *Fractionnement du travail*, qui est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Fractionnement du travail*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Améliorations des pages Détails du travail et Tout le travail

La fonctionnalité *Fractionnement du travail* ajoute les deux boutons suivants à l'onglet **Travail** sur le volet Actions des pages **Détails du travail** et **Tout le travail** :

- **Fractionnement du travail** – Fractionnez l'ID de travail actuel en plusieurs petits ID de travail qui peuvent être traités par des collaborateurs distincts.
- **Annuler la session de fractionnement de travail** - Annulez la session de fractionnement du travail et rendez le travail disponible pour traitement.

![Boutons Fractionnement du travail et Annulation de session de fractionnement du travail](media/Work_split_buttons.png "Boutons Fractionnement du travail et Annulation de session de fractionnement du travail")

> [!IMPORTANT]
> Le bouton **Travail fractionné** ne sera pas disponible si l'une des conditions suivantes est remplie :
>
> - Le statut de travail est autre que *Ouvert* ou *En cours*.
> - Un ID de conteneur est associé à l'ID de travail. (Un conteneur ne peut pas être systématiquement fractionné, car il nécessite des actions physiques.)
> - Le travail est associé à un cluster.
> - Le type d'ordre de travail est autre chose que l'un des types suivants :
>
>    - Commandes client
>    - Prélèvement de matières premières
>    - Sortie de transfert
>
> - Le travail est actuellement fractionné par un autre utilisateur. Si vous essayez d'ouvrir la page de fractionnement pour le travail déjà fractionné par un autre utilisateur, vous recevez le message d'erreur suivant : « Le travail avec l'ID \#\#\#\# est actuellement en cours de fractionnement. Réessayez dans quelques minutes. Si vous continuez à recevoir ce message, contactez un superviseur. »

Une nouvelle raison de blocage du travail, *Travail fractionné*, indique quand l'ID de travail est en cours de fractionnement. Il est montré à la fois sur la page **Travail fractionné** et dans l'application d'entrepôt si un utilisateur tente d'exécuter le travail. Lorsque des motifs de blocage sont utilisés, le nom du champ **Vague bloquée** de l'ID de travail est remplacé par **Bloqué**.

## <a name="initiate-a-work-split"></a>Initier un fractionnement de travail

La fonctionnalité ajoute une page **Travail fractionné** qui permet aux utilisateurs de fractionnement les lignes de travail de l'ID de travail. Lorsque la page est ouverte pour la première fois, elle affiche les lignes dont le statut de travail est *Ouvert* et qui sont disponibles pour être divisés. Dans le volet Actions, sélectionnez **Travail fractionné** pour traiter le travail sélectionné.

Pour fractionner le travail, procédez comme suit.

1. Ouvrez l'une des pages de travail suivantes :

    - **Détails du travail** (**Gestion des entrepôts \> Travail \> Détails du travail**)
    - **Tout le travail** (**Gestion des entrepôts \> Travail \> Tout le travail**)

1. Dans la grille, sélectionnez un ID de travail à fractionner. Le champ **Type d'ordre de travail** doit être défini sur l'une des valeurs suivantes :

    - Commandes client
    - Prélèvement de matières premières
    - Sortie de transfert

1. Dans le volet Actions, sous l'onglet **Travail**, dans le groupe **Travail**, sélectionnez **Travail fractionné**.

    La page **Travail fractionné** apparaît et affiche les lignes de travail ouvertes et disponibles pour être fractionnées. Par défaut, seules les lignes de travail disponibles sont affichées. Pour afficher toutes les lignes de l'ID de travail (par exemple, les lignes qui ont un type de travail de *Rangement*), cochez la case **Afficher toutes les lignes** au-dessus de la grille.

    Le message suivant s'affiche : « Les utilisateurs ne peuvent pas traiter les lignes du travail tant que vous n'avez pas terminé de fractionner et fermer cette page. »

    Le champ **Motif de blocage de travail** du travail en cours sera défini sur *Travail fractionné*, et le travail sera bloqué.

    ![Motif de blocage](media/Blocking_reason.png "Motif de blocage")

1. Sélectionnez les lignes à supprimer de l'ID de travail actuel et ajoutez-les à un nouvel ID de travail. Les événements suivants surviennent :

    - Lorsque vous divisez le travail, la ou les lignes sélectionnées à partir de l'ID de travail d'origine sont annulées, puis copiées vers un nouvel ID de travail.
    - La structure du modèle de travail existant et l'emplacement du rangement (ainsi que les futures paires prélèvement/rangement) sont conservés. Les valeurs des champs d'ID de travail suivants sont copiées du travail d'origine vers le nouveau travail :

        - ID chargement
        - ID expédition
        - Type d'ordre d'exécution
        - Numéro d'ordre
        - Site
        - Entrepôt
        - Priorité du travail
        - ID pool de travail
        - ID vague
        - Numéro de création du travail

    - Les champs suivants ne sont pas copiés dans le nouvel ID de travail :

        - **ID de travail** – Un nouvel ID de travail est généré à partir de la séquence de numéros appropriée.
        - **Statut de travail** – Ce champ est défini sur *Ouvert*.
        - **Verrouillé par** – Ce champ est initialement vide.
        - **ID de contenant cible** – Ce champ est laissé vide.
        - **Date et heure de création** – Ce champ est défini sur la date et l'heure actuelles.
        - **Vague bloquée/gelée** – Ce champ est recalculé pour l'ID de travail d'origine et le nouvel ID de travail.

1. Dans le volet Actions, sélectionnez **Travail fractionné**.

Pendant le fractionnement du travail, le message suivant s'affiche : "Opération de traitement – Travail fractionné". Tant que ce message est visible, vous pouvez annuler l'opération en sélectionnant **Annuler** dans la zone du message.

Si la case à cocher **Afficher toutes les lignes** est désactivée, la ligne qui a été fractionnée et annulée n'apparaîtra plus dans la grille. Si la case est cochée, vous devriez voir que la valeur du champ **Statut de travail** de cette ligne est devenue *Annulé*.

La notification suivante s'affiche pour indiquer que le nouvel ID de travail a été créé : "Le travail \#\#\#\# a été créé en le fractionnant du travail d'origine\#\#\#\# . "

Autres lignes de travail de l'ID de travail d'origine (telles que les lignes *Ranger*) seront ajustées au besoin pour refléter les lignes de travail qui ont été annulées. Par exemple, si l'ID de travail d'origine avait une ligne *Ranger* pour une quantité de 15, et des lignes *Prélever* qui ont une quantité totale de 10 ont été annulées, la nouvelle quantité *Ranger* sur l'ID de travail d'origine sera désormais de 5.

Le nouveau travail ne sera immédiatement attribué à aucun utilisateur. Cependant, vous pouvez l'attribuer à un utilisateur maintenant, si nécessaire, en utilisant la fonctionnalité standard de la page **Détails du travail**.

> [!IMPORTANT]
> Vous ne pouvez fractionner que les ID de travail contenant au moins deux lignes de travail disponibles. Si vous sélectionnez **Fractionner le travail** lorsqu'il n'y a qu'une seule ligne de travail, vous recevrez le message d'erreur suivant : « Au moins une ligne de travail doit rester sur le travail initial ». Dans ce cas, aucun fractionnement ne se produira.

## <a name="finish-a-work-split"></a>Terminer un fractionnement de travail

Pour terminer le travail de fractionnement, la raison de blocage *Travail fractionné* doit être supprimée. Il existe deux manières de terminer cette étape :

- L'utilisateur qui divise le travail ferme la page **Travail fractionné** en cliquant sur le bouton **Fermer** (**X**) dans le coin supérieur droit. Lorsque la page est fermée, la raison de blocage *Travail fractionné* est supprimée. Le statut de ce travail *Bloqué* sera recalculé et, s'il n'y a plus de raisons de blocage pour ce travail, le travail sera débloqué.
- Tout utilisateur ouvre l'ID de travail et clique sur le bouton **Annuler la session de fractionnement du travail** sur le volet Actions. La raison de blocage *Travail fractionné* sera supprimée et le statut de blocage *Bloqué* de ce travail sera recalculé, tout comme lorsque la page **Travail fractionné** est fermée.

Une fois la raison de blocage *Travail fractionné* supprimée, le travail peut être exécuté sur l'appareil mobile, à condition que le statut du travail **Bloqué** est défini sur *Non* sur l'ID de travail.

## <a name="user-blocking-on-the-warehouse-app"></a>Blocage des utilisateurs sur l'application d'entrepôt

Si vous essayez d'utiliser l'application d'entrepôt pour exécuter un travail de prélèvement par rapport à un ID de travail en cours de fractionnement, vous recevez le message d'erreur suivant : « Le travail avec l'ID \#\#\#\# est actuellement en cours de fractionnement. » Si vous recevez ce message, sélectionnez **Annuler**. Vous pouvez ensuite continuer à traiter d'autres travaux.

## <a name="other-blocked-operations"></a>Autres opérations bloquées

Toutes les opérations qui modifient les lignes de travail, les transactions de stock de travail ou les liens de réapprovisionnement liés au travail en cours de fractionnement échoueront et le message d'erreur suivant s'affichera : « Le travail avec l'ID \#\#\#\# est actuellement en cours de fractionnement. »


[!INCLUDE[footer-include](../../includes/footer-banner.md)]