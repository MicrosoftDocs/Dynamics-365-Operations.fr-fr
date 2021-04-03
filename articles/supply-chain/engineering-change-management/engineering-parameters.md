---
title: Paramètres de gestion des modifications d’ingénierie
description: Cette rubrique explique comment configurer des fonctionnalités de gestion des modifications d’ingénierie pour Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d5cf6826aa44e27fae989c73d87d2d3687e0cd0c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262283"
---
# <a name="engineering-change-management-parameters"></a>Paramètres de gestion des modifications d’ingénierie

[!include [banner](../includes/banner.md)]

La page **Paramètres de gestion des modifications techniques** contient les paramètres de configuration qui modifient le comportement par défaut lié à la structure du produit de lancement et aux processus de gestion des modifications techniques.

## <a name="open-the-engineering-change-management-parameters-page"></a>Ouvrez la page des paramètres de gestion des modifications d’ingénierie

Pour ouvrir la page **Paramètres de gestion des modifications techniques**, allez à **Gestion du changement d’ingénierie \> Configurer \> Paramètres de gestion des modifications techniques**. Vous pouvez ensuite définir les champs comme décrit dans les sections restantes de cette rubrique.

## <a name="release-control-tab"></a>Onglet Contrôle de lancement

Le tableau suivant décrit les champs disponibles sur l’onglet **Contrôle de lancement** de la page **Paramètres de gestion des modifications techniques**. Ces champs affectent le processus de structure de produit de lancement.

| Champ | Description |
|---|---|
| Règle de numérotation d’article | Sélectionnez la manière dont le numéro d’article doit être défini lorsque le produit est remis à une entité juridique. Sélectionnez *Numéro de produit d’ingénierie* si le numéro de produit de l’entité juridique destinataire doit correspondre au numéro de produit de la société d’ingénierie. Sélectionnez *Séquence de numéros d’articles locaux* si le produit doit prendre le numéro suivant dans la séquence de numéros pour les numéros de produit dans l’entité juridique destinataire. |
| Règle de nom de nomenclature | Sélectionnez la manière dont le nom de la nomenclature (BOM) est défini lorsque le produit est reçu (lancé) dans une entité juridique. Sélectionnez soit *Nom de l’ingénierie* ou *Numéro d’article à la réception*. |
| Règle de nom de gamme | Sélectionnez la manière dont le nom de gamme est défini lorsque la gamme d’un produit est reçue (lancée) dans une entité juridique. Sélectionnez soit *Nom de l’ingénierie* ou *Numéro d’article à la réception*. |
| Exécuter la vérification de la nomenclature | Indiquez si une vérification de nomenclature sera exécutée lorsque le produit est reçu (lancé) dans une entité juridique. |
| Comportement de lancement de nomenclature inactive | Indiquez si un produit peut être lancé s’il a une nomenclature inactive. Sélectionnez *Accepter*, *Avertissement seulement*, ou *Non autorisé*. |
| Comportement de lancement de gamme inactive | Indiquez si un produit peut être lancé s’il a une gamme inactive. Sélectionnez *Accepter*, *Avertissement seulement*, ou *Non autorisé*.|
| Acceptation du produit | Indiquez si une étape supplémentaire d’acceptation est requise avant que le produit puisse être lancé dans l’entité juridique. Sélectionnez *Manuel* pour ajouter l’étape d’acceptation. Dans ce cas, la page **Versions des produits ouverts** affichera les produits. Sélectionnez *Automatique* pour montrer le produit directement sur la page **Produits lancés** dans l’entité juridique cible immédiatement après la publication du produit avec sa structure de produit de lancement. |

## <a name="engineering-change-management-tab"></a>Onglet Gestion du changement technologique

Le tableau suivant décrit les champs disponibles sur l’onglet **gestion des modifications techniques** de la page **Paramètres de gestion des modifications techniques**. Ces paramètres affectent le processus de gestion des modifications techniques.

| Champ | Description |
|---|---|
| Catégorie | La catégorie par défaut qui sera utilisée lors de la création d’une demande de modification technique. |
| Priorité | La priorité par défaut qui sera utilisée lors de la création d’une demande de modification technique. |
| Règle de gravité | Sélectionnez la manière dont la gravité d’un ordre de modification technique doit être établie. Sélectionnez *Manuel* si l’utilisateur doit entrer une valeur dans le champ **Gravité**. Sélectionnez *Calculer* pour que le système calcule la valeur du champ **Gravité** lorsque vous sélectionnez **Calculer la gravité** dans le volet Actions de la demande de modification technique. Dans ce cas, le système utilisera les règles de gravité définies sur la page **Ensemble de règles de gravité**. Sélectionnez *Calculer automatiquement* pour avoir la valeur du champ **Gravité** automatiquement calculé et rempli en fonction des ensembles de règles de gravité. |
| Relancer les produits impactés | Ce champ s’applique lorsque vous lancez des produits via un ordre de modification technique. Vous pouvez choisir si tous les produits ou uniquement les produits concernés doivent être proposés dans la boite de dialogue **Versions**. |
| Niveaux de nomenclature à lancer | La profondeur du niveau de nomenclature à lancer. Si la nomenclature a plus de niveaux (c’est-à-dire si elle est plus profonde) que la valeur spécifiée ici, seuls les niveaux supérieurs à la valeur spécifiée seront libérés. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]