---
title: Demandes de coût au débarquement
description: Cette rubrique décrit comment rechercher et utiliser les différents types de demandes disponibles pour le module Coût au débarquement.
author: sherry-zheng
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 10f5948b4e3df089aef982269143254d9ac1e8a9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500354"
---
# <a name="landed-cost-inquiries"></a>Demandes de coût au débarquement

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="voyage-line-inquiries"></a>Demandes de renseignements sur la ligne de voyage

La demande **Lignes de voyage** montre toutes les lignes de voyage en ce qui concerne l’inventaire. Cette demande peut être utilisée comme filtre pour vous aider à trouver un article, une commande fournisseur ou toute autre information utile. Il peut également être utilisé pour identifier la date de livraison prévue d’un article qui pourrait être sur un ou plusieurs voyages. De cette façon, il peut vous aider à gérer la réception prévue de l’inventaire.

Pour ouvrir cette enquête, accédez à **Prix au débarquement \> Demandes de renseignements \> Lignes de voyage**.

### <a name="overview-tab"></a>Onglet Vue d’ensemble

L’onglet **Aperçu** de la page de demande **Lignes de voyage** comprend une grille qui affiche des informations de base sur chaque ligne de voyage pertinente. Le tableau suivant décrit les colonnes de la grille.

| Colonne | Description |
|---|---|
| **numéro d’article** | Article de la ligne de voyage. |
| **Référence** | Le type de commande (commande fournisseur ou ordre de transfert). |
| **Nombre** | Numéro de commande fournisseur ou numéro d’ordre de transfert. |
| **Folio** | Folio associé à la ligne de voyage. |
| **Conteneur d’expédition** | Le conteneur d’expédition associé à la ligne de voyage. |
| **Voyage** | Voyage associé à la ligne de voyage. |
| **Quantité** | Quantité de l’article de la ligne de voyage. |
| (Autres dimensions) | Vous pouvez afficher des colonnes pour des dimensions supplémentaires selon vos besoins. Ces dimensions incluent le numéro de traitement par lots, le statut du stock et l’entrepôt. Dans le volet Actions, sélectionnez **Stock \> Afficher les dimensions** pour ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions à inclure. |

### <a name="general-tab"></a>Onglet Général

Sélectionnez l’onglet **Général** pour afficher plus d’informations sur la ligne actuellement sélectionnée sur l’onglet **Aperçu**.

### <a name="dimensions-tab"></a>Onglet Dimensions

Sélectionnez l’onglet **Dimensions** pour afficher les valeurs de toutes les dimensions disponibles pour la ligne sélectionnée actuellement sur l’onglet **Aperçu**, quelles que soient les dimensions que vous avez sélectionnées sur cet onglet.

## <a name="cost-estimate-inquiries"></a>Demandes d’estimation de coût

Chaque fois que vous générez une estimation des coûts, l’estimation est ajoutée à la page de demande **Estimations de coût**. Pour plus d’informations sur la génération, l’affichage et l’utilisation d’estimations de coûts (y compris les estimations sur la page de demande), voir [Estimer et gérer les coûts au débarquement](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Suivi des articles

Utilisez la page **Suivi des articles** pour afficher les lignes de commandes fournisseur ouvertes et leur statut actuel. Les lignes n’ont pas besoin d’être associées à un voyage pour apparaître ici. Cependant, si un article est associé à un voyage, la ligne d’enregistrement de suivi d’article affiche l’ID du voyage.

Pour ouvrir cette page, accédez à **Prix au débarquement \> Demandes de renseignements \> Suivi \> Suivi des articles**.

Étant donné que votre système contient probablement un très grand nombre de lignes de commande fournisseur, la page **Suivi des articles** n’affiche initialement aucun enregistrement. Commencez par utiliser les champs de filtre en haut de la page pour définir l’ensemble de lignes de commande fournisseur que vous recherchez. Puis sélectionnez **Mettre à jour** dans le volet Actions pour générer la liste. Vous pouvez utiliser un astérisque (\*) comme caractère générique dans l’un des champs de filtre. Par exemple, pour rechercher toutes les lignes de commande fournisseur pour les articles qui incluent le mot "DVD" dans leur nom, définissez le champ **Type** sur **Nom du produit**, et entrez *\*DVD\** dans le champ **Valeur du champ**.

> [!NOTE]
> Actuellement, les commandes en souffrance ne comprennent que les commandes client. Les devis ne sont pas affichés ou considérés comme des commandes en souffrance.

Le tableau suivant décrit les colonnes de la grille sur la page **Suivi des articles**.

| Colonne | Description |
|---|---|
| **Port d’arrivée** | La destination finale. |
| **Confirmée** | Date confirmée de ligne de commande fournisseur. |
| **Date de livraison** | Date de livraison de ligne de commande fournisseur. |
| **Voyage** | Si la ligne est associée à un voyage, l’ID du voyage. |
| **Conteneur d’expédition** | Si la ligne est attachée à un conteneur d’expédition, l’ID du conteneur. |
| **Port d’expédition** | Le port actuel, basé sur la première étape du formulaire de suivi où aucune date réelle n’est définie pour le conteneur d’expédition associé à la ligne de commande fournisseur. |
| **Activité** | L’activité actuelle, basée sur la première étape du formulaire de suivi où aucune date réelle n’est définie pour le conteneur d’expédition associé à la ligne de commande fournisseur. |
| **Date de fin estimée** | La date à laquelle le voyage devrait être reçu à l’entrepôt de destination. |
| **Nom** | Nom du fournisseur. |
| **Statut du voyage** | Le statut de l’expédition associée à la ligne de commande fournisseur. |
| **numéro d’article** | Numéro d’article de la ligne de commande fournisseur. |
| **Externe** | Nom de l’article fournisseur. |
| **Nom du produit** | Nom de l’article de la ligne de la commande fournisseur. |
| **Quantité** | Quantité de ligne de commande fournisseur de la ligne de la commande fournisseur. |
| **Unité** | L’unité de mesure de la ligne de commande fournisseur. |
| **Référence** | Le type de commande (commande fournisseur ou ordre de transfert) |
| **Numéro de référence** | Numéro de commande fournisseur ou numéro d’ordre de transfert. |
| **Commande en souffrance** | Un symbole indique qu’il y a des commandes en souffrance pour l’article. |
| (Autres dimensions) | Vous pouvez afficher des colonnes pour des dimensions supplémentaires selon vos besoins. Ces dimensions incluent le numéro de traitement par lots, le statut du stock et l’entrepôt. Dans le volet Actions, sélectionnez **Afficher les dimensions** pour ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions à inclure. |

### <a name="related-information-about-backorders"></a>Informations connexes sur les commandes en souffrance

Pour afficher plus d’informations sur les commandes en souffrance, sélectionnez l’onglet **Information connexe** sur le côté droit de la page, puis sélectionnez **Commandes en souffrance**. Pour afficher encore plus d’informations sur une commande en souffrance spécifique, sélectionnez la ligne correspondante, puis sélectionnez le lien **Suite**.

## <a name="individual-shipping-container-tracking"></a>Suivi du conteneur d’expédition individuel

La demande **Suivi individuel des conteneurs d’expédition** fournit un filtre qui vous permet de trouver un conteneur d’expédition, puis d’identifier toutes les lignes de voyage dans ce conteneur.

Pour ouvrir cette demande, accédez à **Prix au débarquement \> Demandes de renseignements \> Suivi \> Suivi individuel des conteneurs d’expédition**.

## <a name="multiple-shipping-container-tracking"></a>Suivi du conteneur d’expédition multiple

La demande **Suivi de plusieurs conteneurs d’expédition** fournit un filtre qui vous permet de trouver un ensemble de conteneurs d’expédition, puis d’identifier toutes les lignes de voyage de ces conteneurs.

Pour ouvrir cette demande, accédez à **Prix au débarquement \> Demandes de renseignements \> Suivi \> Suivi de plusieurs conteneurs d’expédition**.
