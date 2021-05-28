---
title: Vous ne pouvez pas appliquer un modèle à un produit lancé
description: Vous ne pouvez pas appliquer un modèle à un produit lancé.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026500"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Vous ne pouvez pas appliquer un modèle pour créer un produit lancé

Numéro de la base de connaissances : 4612097

## <a name="symptoms"></a>Symptômes

Lorsque vous créez un nouveau produit lancé en utilisant la boîte de dialogue **Nouveau produit lancé**, vous pouvez sélectionner un modèle. Le modèle doit fournir des paramètres par défaut pour de nombreux champs du nouveau produit lancé. Cependant, certains ou tous les champs ne sont pas définis une fois que vous avez sélectionné le modèle.

## <a name="cause"></a>Cause

De nombreuses pages dans Microsoft Dynamics 365 Supply Chain Management vous permettent de créer un modèle qui établit les paramètres initiaux pour les enregistrements affichés sur ces pages. Vous pouvez créer l'un de ces modèles en sélectionnant **Enregistrer les informations** dans l'onglet **Options** du volet Actions. Cependant, les produits lancés sont beaucoup plus complexes que la plupart des autres types d'enregistrements. Bien que vous puissiez sélectionner **Enregistrer les informations** dans la page **Produits lancés** pour créer un modèle, et bien que vous puissiez sélectionner ce modèle lorsque vous créez un produit lancé, le modèle ne fournira pas les valeurs de champ attendues pour le nouveau produit lancé. Par conséquent, vous ne pouvez pas utiliser de modèles "informations d'enregistrement" pour les produits lancés. Au lieu de cela, vous devez créer des modèles de produits dédiés.

## <a name="resolution"></a>Résolution

Pour créer un modèle de produit, utilisez le menu **Modèle** dans l'onglet **Produit** du volet Actions, pas le bouton **Enregistrer les informations** dans l'onglet **Options**.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans le volet Actions, dans l'onglet **Produit** au sein du groupe **Nouveau**, sélectionnez **Modèle**, puis sélectionnez soit **Créer un modèle personnel**, soit **Créer un modèle partagé**, le cas échéant.
