---
title: Contrats de garantie
description: Cette rubrique explique les contrats de garantie dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: da60d098aff96780ca1e40832db34e3c9cc835e7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569683"
---
# <a name="warranty-agreements"></a>Contrats de garantie

[!include [banner](../../includes/banner.md)]

 


Dans le module Gestion des actifs, vous pouvez configurer les conditions de la garantie à associer à un actif ou à un type d'actif. Les conditions de garantie sont créées pour une période spécifique. La garantie peut être configurée pour offrir une couverture totale ou partielle et vous pouvez configurer les conditions associées aux heures, dépenses et articles.

La première étape consiste à créer des contrats de garantie fournisseur que vous avez pour votre équipement. Ensuite, vous joignez les contrats de garantie aux actifs ou types d'actif. Les contrats de garantie fournisseur sont utilisés uniquement à titre informatif. Si la garantie fournisseur est configurée sur un actif, vous pouvez voir la période de couverture de garantie sur l'actif.

## <a name="create-a-warranty-agreement"></a>Créer un contrat de garantie

Un contrat de garantie peut inclure plusieurs lignes de contrat pour couvrir la garantie pour les heures ouvrées, les dépenses et les articles.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Garantie**.
2. Sélectionnez **Nouveau** pour créer un produit.
3. Dans le champ **Garantie**, entrez un ID de garantie.
4. Dans le champ **Nom**, entrez une description.

    Dans l'organisateur **Détails**, le champ **Actifs** présente le nombre d'actifs actifs qui utilisent le contrat de garantie.

5. Dans les organisateurs **Garantie des heures** et **Garantie des articles**, procédez comme suit pour ajouter les lignes à inclure dans un contrat de garantie qui concerne les heures ou les articles :

    1. Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle condition à la garantie. Un numéro de ligne séquentiel est automatiquement entrée dans le champ **Ligne** .
    2. Dans le champ **Période**, sélectionnez le type de période de garantie.
    3. Entrez un nombre dans le champ **Intervalle**. Ce champ définit le nombre de périodes pour lesquelles la garantie doit être valide.
    4. Dans le champ **Pourcentage**, entrez le pourcentage de couverture pour la ligne de garantie. Le pourcentage indique l'étendue de la couverture par votre entreprise.

![Page de garantie](media/01-warranty.png)
