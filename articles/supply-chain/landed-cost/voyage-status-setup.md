---
title: Configuration du statut du voyage
description: Cette rubrique décrit comment établir les valeurs de statut que les utilisateurs peuvent attribuer aux voyages.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500884"
---
# <a name="voyage-status-setup"></a>Configuration du statut du voyage

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Sur la page **Statuts de voyage**, vous définissez l’ensemble des valeurs de statut que les utilisateurs peuvent attribuer aux voyages. Les utilisateurs peuvent attribuer des valeurs de statut de voyage à tous les niveaux d’un voyage : voyage, conteneur d’expédition, folio, commande fournisseur et article (lignes d’achat et lignes d’ordre de transfert). Ils sont utilisés à deux fins :

- Informez l’utilisateur du statut du voyage, du conteneur d’expédition, du folio, de la commande fournisseur ou de l’article (lignes d’achat et lignes d’ordre de transfert).
- Limitez l’utilisation de la zone de coûts en empêchant la modification ou la suppression.

Pour configurer vos statuts de voyage, accédez à **Coût au débarquement \> Installer \> Statuts de voyage**. Vous pouvez ajouter, supprimer et modifier des statuts avec les boutons du volet Actions.

Chaque zone de coût a son propre ensemble et sa propre hiérarchie de statuts de voyage. Par conséquent, sur la page **Statuts de voyage**, dans la **Zone de coût**, vous devez d’abord sélectionner la zone de coûts pour laquelle vous souhaitez afficher ou créer des statuts de voyage. Ensuite, pour chaque statut de voyage, définissez les champs décrits dans le tableau suivant, selon les besoins. Notez que le statut d’un voyage peut également être automatiquement modifié par des événements système, tels que des règles qui ont été établies à l’aide du centre de contrôle de suivi.

| Champ | Description |
|---|---|
| Statut du voyage | Entrez le nom du statut de voyage. |
| Description | Entrez une description du statut de voyage. |
| Modifier | Cochez cette case si les utilisateurs sont autorisés à modifier les voyages qui ont ce statut. |
| Retirer | Cochez cette case si les utilisateurs sont autorisés à supprimer les voyages qui ont ce statut. |
| Obligatoire | Cochez cette case pour rendre le statut du voyage obligatoire, afin qu’il ne puisse pas être ignoré. |
| Parent | Utilisez ce champ pour établir une hiérarchie entre les valeurs de statut. Les statuts de voyage peuvent être modifiés (manuellement ou automatiquement) uniquement vers le bas dans la hiérarchie, d’un statut parent à l’un de ses statuts enfants.

> [!NOTE]
> Vous devez configurer uniquement les statuts de voyage spécifiques utilisés par votre organisation. Les statuts de voyage typiques incluent *Confirmé*, *Marchandises en transit*, *Reçu*, *Prêt pour l’évaluation des coûts*, et *Évaluer les coûts*. Cependant, d’autres statuts peuvent être présents.
