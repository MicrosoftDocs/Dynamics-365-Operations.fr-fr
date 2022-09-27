---
title: Utiliser des codes disposition de lot pour marquer les lots comme disponibles ou non disponibles
description: Cet article décrit comment configurer et utiliser des codes disposition de lot pour marquer des lots comme disponibles ou non disponibles à des fins de planification générale, réservation, prélèvement et/ou d’expédition.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542469"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Utiliser des codes disposition de lot pour marquer les lots comme disponibles ou non disponibles

Cet article explique comment configurer et utiliser les *codes disposition de lot*. Chaque code disposition de lot peut avoir un statut défini sur *Disponible* ou *Non disponible*. Vous affectez des codes disposition de lot aux traitements par lots du stock pour indiquer si chaque lot est disponible pour la planification générale, la réservation, le prélèvement et/ou l’expédition.

Pour utiliser des codes disposition de lot, vous devez paramétrer les codes et les affecter aux lots que vous souhaitez gérer.

## <a name="set-up-batch-disposition-codes"></a>Paramétrer les codes disposition de lot

Vous devez configurer chaque code disposition de lot que vous souhaitez utiliser dans votre système. Vous pouvez créer autant de codes que vous le souhaitez. (Par exemple, vous pouvez créer des codes pour identifier les différentes raisons pour lesquelles un lot peut être disponible ou non disponible). Cependant, vous n’aurez souvent que deux codes : un pour *disponible* et un pour *indisponible*. Vous pouvez également créer des codes personnalisés qui permettent d’utiliser un lot pour certaines opérations, mais pas pour d’autres.

Procédez comme suit pour paramétrer des codes disposition de lot.

1. Accédez à **Gestion des stocks \> Configuration \> Lot \> Données principales de disposition de lot**.
1. La page **Données principales de disposition de lot** répertorie vos codes disposition de lot actuels et vous permet de les créer, de les supprimer et de les modifier. Utilisez l’une des procédures suivantes :

    - Pour modifier un code existant, sélectionnez-le dans le volet de liste.
    - Pour créer un code, sélectionnez **Nouveau** dans le volet Action.

1. Définissez les champs suivants sur l’en-tête du nouveau code ou du code sélectionné :

    - **Code disposition de lot** : saisissez le nom complet du code.
    - **Description** : permet de décrire la façon dont le code doit être utilisé.
    - **Statut de disposition du lot** : sélectionnez le statut qui s’applique aux traitements par lots auxquels le code est attribué :

        - *Indisponible* : les lots ne peuvent pas être utilisés pour la planification générale, la réservation, le prélèvement ou l’expédition. Lorsque vous sélectionnez cette valeur, toutes les options **Bloquer** du raccourci **Installer** sont définis sur *Oui*, et toutes les options **Disponible à la vente** sont définies sur *Non*. Cependant, vous pouvez modifier certains de ces paramètres pour ajouter des exceptions.
        - *Disponible* : les lots ne peuvent pas être utilisés pour la planification générale, la réservation, le prélèvement et/ou l’expédition. Lorsque vous sélectionnez cette valeur, toutes les options **Bloquer** du raccourci **Installer** sont définis sur *Non*, et toutes les options **Disponible à la vente** sont définies sur *Oui*. Ces paramètres seront en lecture seule pendant que le champ **Statut de disposition du lot** est défini sur *Disponible*.

1. Si vous définissez le champ **Statut de disposition du lot** sur *Indisponible*, vous pouvez personnaliser le statut de blocage de chaque opération (réserver, prélever et expédier) pour chaque type de commande (vente, transfert et production). Pour les ordres de fabrication, vous pouvez choisir de bloquer ou de débloquer le journal de prélèvement de production. Vous pouvez également choisir de bloquer ou de débloquer la planification générale. Utilisez les options sur le raccourci **Configurer** pour bloquer ou débloquer chaque opération selon vos besoins. Définissez l’option **Disponible à la vente** sur *Oui* pour activer la planification générale ou définissez-la sur *Non* pour bloquer la planification générale.

## <a name="assign-batch-disposition-codes-to-batches"></a>Attribuer des codes disposition de lot aux traitements par lots

Après avoir défini les codes disposition de lot dont vous avez besoin, suivez ces étapes pour les affecter aux traitements par lots.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Traitements par lots**.
1. Sélectionnez un ou plusieurs lots auxquels attribuer un code disposition de lot.
1. Sur le volet Actions, sous l’onglet **Réinitialiser**, sélectionnez **Réinitialiser le code disposition de lot**.
1. Dans la boîte de dialogue **Modifier les restrictions du lot de stock**, définissez le champ **Nouveau code disposition de lot** sur le nom du code que vous souhaitez attribuer.
1. Sélectionnez **OK** pour appliquer le nouveau paramètre et enregistrez vos modifications.

    Sur la page **Traitements par lots**, les valeurs des colonnes **Code disposition de lot** et **Statut de disposition du lot** sont mises à jour afin de refléter les nouveaux paramètres des lots sélectionnés.

## <a name="master-planning-example"></a>Exemple de planification générale

Cet exemple montre comment les codes disposition de lot peuvent affecter la planification générale.

Pour cet exemple, les codes disposition de lot sont configurés de la manière suivante :

- *P-Disponible :*

    - **Statut de disposition de lot :** *Disponible*
    - **Disponible à la vente :** *Oui*

- *P-Non disponible :*

    - **Statut de disposition de lot :** *Indisponible*
    - **Disponible à la vente :** *Non*

Il existe un produit (*Produit-1*) qui a deux lots : *Lot-A* et *Lot-B*. Ces lots sont configurés de la manière suivante :

- *Lot-A :*

    - **Code disposition de lot :** *P-Disponible*
    - **Quantité disponible :** 1

- *Lot-B :*

    - **Code disposition de lot :** *P-Indisponible*
    - **Quantité disponible :** 1

Il y a une commande client (*SO1*) pour une quantité de 2 du produit *Produit-1*. La date de livraison est de trois jours à compter d’aujourd’hui.

Vous exécutez la planification générale et définissez les valeurs suivantes qui sont pertinentes pour cet exemple :

- **Commande prévisionnelle :** *Commande fournisseur*
- **Stratégie de réapprovisionnement :** *Exigence*
- **Délai :** *0*

Suite à la planification, le système utilise le lot disponible (*Lot-A*) pour couvrir une quantité de 1 de produit *Produit-1* pour la commande client *SO1*. Cependant, il ne peut pas utiliser le lot *Lot-B*, car ce lot est marqué comme non disponible pour la planification. Par conséquent, pour couvrir la quantité restante, le système crée une commande fournisseur prévisionnelle (*PPO1*) pour un nouveau lot de produit *Produit-1*.

L’illustration suivante présente une chronologie pour le résultat de planification.

![Exemple qui montre comment les codes disposition de lot peuvent affecter la planification générale.](media/batch-codes-planning-example.png "Exemple qui montre comment les codes disposition de lot peuvent affecter la planification générale")
