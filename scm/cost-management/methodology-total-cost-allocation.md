---
title: "Méthode de répartition des coûts totaux"
description: "Cet article fournit des instructions pour utiliser la répartition des coûts totaux (RCT). La RCT est une méthode de calcul du coût entre l&quot;élément de formule principal pour un lot de commandes et des coproduits définis pour la formule."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c26dcc5a8caa461bce90f931bb5c584f1816526b
ms.lasthandoff: 03/31/2017


---

# <a name="total-cost-allocation-method"></a>Méthode de répartition des coûts totaux

Cet article fournit des instructions pour utiliser la répartition des coûts totaux (RCT). La RCT est une méthode de calcul du coût entre l'élément de formule principal pour un lot de commandes et des coproduits définis pour la formule.

La Méthode de répartition des coûts totaux (RCT) est une méthode de calcul du coût entre l'élément de formule principal pour un lot de commandes et des coproduits définis pour la formule. Cette méthode est dynamique. Elle permet de calculer le coût en tant que moyenne pondérée entre les quantités déclarées comme terminées pour l'élément de formule et les coproduits. Lorsque la RCT est utilisée, vous ne devez pas examiner les répartitions des coûts pour chaque lot de commandes. Si la RCT n'est pas utilisée, le calcul de la formule utilise la fonctionnalité existante.

## <a name="using-tca-for-coproducts"></a>Utiliser la RCT pour des coproduits
Voici des instructions pour utiliser la RCT pour des coproduits :

-   Si vous définissez le curseur **Répartition des coûts totaux** sur **Oui** pour une version de formule, les coproduits doivent posséder un prix de revient supérieur à 0 (zéro). La valeur peut être extraite de la version de coût actif pour le même site ou pour le premier site pour une formule qui n'est pas propre aux sites. Cette condition est validée lorsque la formule est approuvée.
-   Si vous définissez le curseur **Répartition des coûts totaux** sur **Oui** pour la version de formule et si les conditions suivantes sont remplies, la méthode de répartition des coûts est **RCT**, et le pourcentage de répartition des coûts est inchangé :
    -   Vous avez ajouté des coproduits.
    -   Vous avez utilisé une autre méthode de répartition des coûts pour les coproduits.
-   Si vous définissez le curseur **Répartition des coûts totaux** sur **Non** pour la version de formule et si les conditions suivantes sont remplies, la méthode de répartition des coûts est changée en **Manuel**, et le pourcentage de répartition des coûts est inchangé :
    -   Vous avez ajouté des coproduits.
    -   Le pourcentage de répartition du coût de l'article est supérieur à 0 (zéro).
-   Avant de pouvoir correctement effectuer un calcul de formule, vous devez estimer les pourcentages de répartition des coûts. Vous pouvez réaliser cette étape manuellement ou à l'aide de l'option **Estimer les coûts** dans la page **Coproduits**. **Remarque :** L'option **Estimer les coûts** n'est disponible que si le curseur **Répartition des coûts totaux** est défini sur **Oui** pour la version de formule. Vous pouvez afficher la répartition prévue si les quantités de lot de commandes déclarées comme terminées correspondent aux quantités qui figurent sur la formule.
-   Lorsqu'un lot de commandes est créé manuellement ou qu'un lot de commandes prévisionnel est confirmé, le curseur **Répartition des coûts totaux** de la formule de version est copié dans le lot de commandes. Toutefois, vous pouvez modifier ce paramètre dans le lot de commandes. Si le curseur **Répartition des coûts totaux** est défini sur **Non** pour la formule de version puis modifié en **Oui** pour le lot de commandes, la méthode de répartition des coûts pour chaque ligne qui était définie sur **Manuel** est modifiée sur **RCT**. Une répartition des coûts de **Aucun** est inchangée. Si le curseur **Répartition des coûts totaux** est défini sur **Oui** pour la version de formule puis modifié en **Non** pour le lot de commandes, la méthode de répartition des coûts pour chaque coproduit du type **Production** est modifiée sur **Manuel**. Tout pourcentage estimé de répartition des coûts est inchangé.
-   La page **Répartition des coûts des coproduits** affiche le pourcentage calculé de répartition des coûts. Ouvrez cette page depuis la page **Lot de commandes**. Ces informations sont utiles lorsque les produits et les quantités qui sont déclarés diffèrent des quantités prévues ou commencées dans le lot de commandes. Lorsque le coût est terminé, ces nouvelles répartitions de pourcentage de RCT sont indiquées dans la page **Répartition des coûts des coproduits**.

## <a name="calculating-the-burden-for-byproducts"></a>Calculer de la charge des sous-produits
Le champ **Répartition des coûts de sous-produit** dans la page **Coproduits** est un énumérateur utilisé uniquement pour des sous-produits. Pour des coproduits, la valeur de ce champ est toujours **Aucun**. Pour les lignes de sous-produit, ce champ détermine la manière dont le coût pour la ligne de sous-produit est ajouté au coût total de la production. Les options suivantes sont disponibles :

-   **Aucun** ─ Aucun montant n'est ajouté au prix total de la production pour cette ligne de sous-produit.
-   **Pourcentage** ─ Le montant du coût est calculé comme un pourcentage du coût total des matières premières consommées dans la production. Le pourcentage utilisé pour le calcul est entré dans le champ.
-   **Quantité de base** ─ Le montant du coût calculé équivaut à un montant par taille de lot standard de l'ordre de fabrication. Ce montant est indépendant de la quantité déclarée dans la production. Le montant utilisé pour le calcul est entré dans le champ.
-   **Par quantité** ─ Le montant du coût est calculé comme un montant par quantité déclarée de l'élément de formule dans la production. Le montant utilisé pour le calcul est entré dans le champ.



