---
title: Paramètres fournisseur ajoutés pour le coût au débarquement
description: Cet article décrit les nouveaux champs qui sont ajoutés à la page Fournisseurs existante lorsque vous activez le module Coût au débarquement. Vous utilisez ces champs pour configurer les fournisseurs que vous utiliserez avec les fonctionnalités de coût au débarquement.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 84d1dee0815b036a3d411eabff49d8a08249bed3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882574"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Paramètres fournisseur ajoutés pour le coût au débarquement

[!include [banner](../../includes/banner.md)]

Lorsque vous activez le module **Coût au débarquement**, plusieurs nouveaux champs sont ajoutés à la page **Fournisseurs** existante. Vous utilisez ces champs pour configurer les fournisseurs que vous utiliserez avec les fonctionnalités de coût au débarquement.

Pour définir les champs pertinents, accédez à **Approvisionnement \> Fournisseurs \> Tous les fournisseurs**. Ouvrez un fournisseur existant ou créez un fournisseur, puis sélectionnez le raccourci **Détails divers**. Tous les nouveaux champs que le module **Coût au débarquement** ajoute apparaissent sous l’en-tête **Voyages**. Le tableau suivant décrit ces champs.

| Champ | Description |
|---|---|
| Type d’expédition | <p>Sélectionnez le rôle du fournisseur par rapport au coût au débarquement :</p><ul><li>**Aucun** – Le fournisseur n’a pas de rôle spécifique lié au coût au débarquement. Cette valeur est le paramètre par défaut, car la plupart des fournisseurs n’auront probablement pas de rôle spécifique.</li><li>**Transporteur** – Le fournisseur est une compagnie maritime. Les fournisseurs qui ont ce type d’expédition peuvent être sélectionnés dans le champ **Transporteur** sur la page **Voyages**.</li><li>**Courtier en douane** – Le fournisseur est un courtier en douane. Les fournisseurs qui ont ce type d’expédition peuvent être sélectionnés dans le champ **Courtier en douane** sur la page **Folios**.</li><li>**Agent** – Le vendeur est un agent. Les fournisseurs qui ont ce type d’expédition peuvent être sélectionnés dans le champ **Agent** sur les pages **Fournisseurs** et **Commandes fournisseur**.</li></ul> |
| Groupe de types de coût | Affectez le fournisseur à un groupe de types de coûts afin de sélectionner les [coûts automatiques](auto-cost-setup.md). |
| Port de départ | Sélectionnez le port d’origine du voyage. |
| Agent | L’agent par défaut lorsque les achats sont effectués auprès du fournisseur. |
| Importer le fournisseur d’évaluation des coûts | <p>Indiquez si le fournisseur est un fournisseur à coût fixe.</p><p>**Conseil :** Vous pouvez utiliser ce champ avec la sécurité au niveau de l’enregistrement pour limiter les commandes fournisseur affichés lors de la création d’un voyage.</p> |
| Société d’expédition | Sélectionnez la société de transport par défaut utilisée lors de la création des commandes fournisseur pour le fournisseur. |
| Fournisseur de services | Indiquez si le fournisseur est un fournisseur de services. |
| Groupe de tolérance excédentaire/incomplet | Sélectionnez le groupe de tolérance supérieur / inférieur par défaut pour le fournisseur. |
