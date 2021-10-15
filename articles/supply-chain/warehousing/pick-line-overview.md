---
title: Configurer un élément de menu d’appareil mobile pour fournir un aperçu de la ligne de prélèvement
description: Cette rubrique explique comment définir quand une liste de toutes les lignes de travail sera affichée aux magasiniers qui traitent le travail d’entrepôt sur un appareil mobile. Cette fonctionnalité peut être utile pour les magasiniers qui ont souvent besoin d’une vue d’ensemble des lignes de prélèvement dans un ordre de travail afin d’optimiser leur séquence de prélèvement.
author: MarkusFogelberg
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8bb5a7851987b71d5a1df1d37054547f28ecf9a4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580046"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Configurer un élément de menu d’appareil mobile pour fournir un aperçu de la ligne de prélèvement

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer les options liées à la vue d’ensemble de la ligne de prélèvement pour les éléments de menu d’appareil mobile utilisés pour traiter le travail de prélèvement. La vue d’ensemble des lignes de prélèvement permet aux magasiniers de visualiser et de faire une sélection dans une liste de toutes les lignes de travail liées à leur tâche actuelle. Cette fonction peut aider les travailleurs à optimiser leur séquence de prélèvement. La fonction fournit des options qui remplacent le bouton standard **Ignorer** qui permet aux travailleurs de parcourir les lignes une par une, dans un ordre fixe. (Cependant, l’option permettant d’utiliser ce bouton est toujours disponible.)

Les administrateurs peuvent configurer chaque élément de menu individuellement pour contrôler comment, quand et où l’application mobile Gestion des entrepôts présente la vue d’ensemble de la ligne de prélèvement.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Activer la fonctionnalité Vue d’ensemble de la ligne de prélèvement du travail

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** _Gestion des entrepôts_
- **Nom de la fonctionnalité :** _Vue d’ensemble de la ligne de prélèvement du travail_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Configurer les éléments de menu pour afficher une liste de toutes les lignes de travail

Pour configurer un élément de menu d’appareil mobile pour fournir un aperçu de la ligne de prélèvement, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez ou créez un élément de menu lié au travail de prélèvement et définissez les valeurs suivantes :

    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*
    - **Dirigé par :** *Dirigé par l’utilisateur* ou *Dirigé par le système*

    Pour plus d’informations sur la création d’éléments de menu et l’utilisation des différents paramètres disponibles sur la page **Éléments de menu de l’appareil mobile** page, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).

1. Sur le raccourci **Général**, configurez la fonctionnalité en définissant le champ **Afficher la liste des lignes de travail** sur l’une des valeurs suivantes :

    - **Afficher uniquement sur demande** – les travailleurs peuvent choisir d’afficher la liste des lignes de prélèvement en sélectionnant le bouton **Ignorer** dans l’application mobile Gestion des entrepôts.
    - **Afficher au début de chaque prélèvement** – les travailleurs voient la liste à chaque fois qu’ils commencent ou terminent une ligne de prélèvement. Ils peuvent également afficher à nouveau la liste en sélectionnant le bouton **Ignorer** dans l’application mobile Gestion des entrepôts.
    - **Afficher uniquement au début du premier prélèvement** – les collaborateurs voient la liste chaque fois qu’ils commencent un nouveau travail de prélèvement, mais pas après chaque ligne. Ils peuvent également afficher à nouveau la liste en sélectionnant le bouton **Ignorer** dans l’application mobile Gestion des entrepôts.
    - **Ne jamais afficher** – le bouton standard **Ignorer** apparaît dans l’application mobile Gestion des entrepôts et l’affichage de la liste des lignes de travail est désactivé. Le bouton **Ignorer** permet aux travailleurs de parcourir les lignes une par une, dans un ordre fixe. Ils peuvent également parcourir la liste autant de fois qu’ils le souhaitent, jusqu’à ce que toutes les lignes aient été traitées.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

    Si vous définissez le champ **Afficher la liste des lignes de travail** sur n’importe quelle valeur sauf *Ne jamais afficher*, le bouton **Liste de champs** du volet Actions devient disponible.

1. Dans le volet Actions, sélectionnez **Liste de champs**.
1. Sur la page **Liste de champs**, configurez les informations affichées par l’application mobile Gestion des entrepôts pour chaque ligne de la liste.

    - Le champ **Contrôle principal** est toujours défini sur *LineNum*. Par conséquent, chaque ligne de la liste commence par un numéro de ligne.
    - Utilisez les champs restants de **Champ d’affichage** pour ajouter jusqu’à sept champs d’affichage supplémentaires, selon vos besoins. Dans chaque champ de **Champ d’affichage**, sélectionnez le nom d’un champ de ligne de travail. Chaque ligne affichera alors une valeur pour ce champ. Les valeurs seront affichées dans l’ordre que vous sélectionnez ici. Vous pouvez laisser certains des champs de **Champ d’affichage** vides si vous n’avez pas besoin des sept valeurs.

1. Dans le volet Actions, sélectionnez **Enregistrer**, puis fermez la page **Liste de champs**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]