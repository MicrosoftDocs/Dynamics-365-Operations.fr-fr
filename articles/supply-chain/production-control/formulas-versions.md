---
title: Formules et versions de formule
description: Cette rubrique fournit des informations sur les formules et les versions de formule. Une formule définit les matières, les ingrédients et les résultats d'un processus spécifique du traitement de la production. Les formules sont utilisées pour planifier et générer des produits dans le traitement de la production.
author: cvocph
manager: tfehr
ms.date: 09/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule, EcoResProductProdTypeFormulaNoActiveFormulaFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7fb37483412fdd09fe3734ddb148b050ec02951
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986972"
---
# <a name="formulas-and-formula-versions"></a>Formules et versions de formule

[!include [banner](../includes/banner.md)]

Une formule définit les matières, les ingrédients et les résultats d'un processus spécifique du traitement de la production. Avec la gamme correspondante, la formule définit l'ensemble du processus dans le traitement de la production. Les formules sont utilisées pour planifier et générer des produits dans le traitement de la production.

Une formule comprend les ingrédients et les quantités nécessaires pour produire une quantité spécifique d'un élément de formule. Selon la tâche à effectuer, vous pouvez accéder à la fonctionnalité de formule à partir de Gestion des entrepôts et des stocks ou Gestion des informations sur les produits.

## <a name="formulas-and-formula-lines"></a>Formules et lignes de formule
Une formule est composée d'une ou de plusieurs lignes de formule qui identifient les ingrédients ou les articles qui constituent la formule. Une ligne de formule peut contenir des articles de nomenclature, des éléments de formule, des articles de poids variable, des articles achetés, des co-produits ou des sous-produits. De nombreux articles étant exploitables dans plusieurs produits, un article peut être utilisé dans plusieurs formules.

L'exemple d'une formule est la formule d'un biscuit aux pépites de chocolat. Les ingrédients pour cette formule utilisent plusieurs lignes, telles que la farine, le sucre, les œufs, le beurre et les pépites de chocolat. La formule des biscuits aux pépites de chocolat contient les ingrédients qui sont vraisemblablement utilisés dans d'autres formules. Lors de la préparation des biscuits aux pépites de chocolat, il se peut qu'il y ait des restes, comme des miettes, ou que certains biscuits soient trop cuits ou pas assez cuits. Ces articles peuvent être paramétrés comme des co-produits ou sous-produits, selon les opérations de production.

Lorsque vous créez une ligne de formule, utilisez le type de ligne pour indiquer comment le système doit gérer la ligne lorsque vous exécutez la planification principale et que vous créez des lots de commandes. Chaque type de ligne donne un résultat différent. Le tableau suivant décrit les types de ligne que vous pouvez sélectionner. 

| Type de ligne     | Description  |
|---------------|--------------|
| Article          | Sélectionnez **Article** lorsque l'article est une matière première ou un article semi-fini prélevé du stock ou un service. |
| Fantôme       | Sélectionnez le type de ligne **Fantôme** lorsque vous souhaitez éclater les articles de formule de niveau inférieur contenus dans les lignes de formule. Lorsque vous estimez le lot de commandes, et que les éléments de formule sont éclatés, les composants sont répertoriés sous la forme de lignes de formule pour le lot de commandes. En outre, les gammes correspondantes sont ajoutées à la gamme de production. Les articles de formule sont éclatés à l'aide de la configuration actuelle. Lorsque vous utilisez un type de ligne **fantôme**, vous pouvez gérer la configuration de la production et des mesures qui surviennent aux différents niveaux de la formule. Si vous sélectionnez **Fantôme** pour un produit sur l'organisateur **Ingénieur** de la page **Détails des produits lancés**, puis utilisez ce produit dans une formule, le type de ligne de la ligne de formule devient **Fantôme**. Vous ne pouvez pas sélectionner **Fantôme** pour un article de poids variable, ou pour les articles dont le type de production est **Co-produit**, **Sous-produit** ou **Élément de planification**. |
| Approvisionnement invariable | Sélectionnez **Approvisionnement invariable** pour créer un lot de commandes, un ordre de fabrication, un kanban, un ordre de transfert ou une commande fournisseur pour l'ingrédient qui est contenu dans la ligne de formule. L'ordre associé est déterminé selon les paramètres de commande par défaut et le type de production de l'ingrédient, et est créé lorsque vous estimez le lot de commandes. Les quantités d'ingrédient requises sont réservées pour le lot de commandes. |
| Fournisseur        | Sélectionnez **Fournisseur** si le processus de production utilise un sous-traitant, et si vous souhaitez créer une sous-production ou une commande fournisseur pour le sous-traitant. Le service ou la tâche que le sous-traitant effectue doit être créé(e) en utilisant un élément de formule ou un article de service. Vous pouvez joindre l'article à l'article parent comme une ligne de formule. La gamme doit contenir une opération affectée à la ressource opérationnelle du sous-traitant. Cette opération est liée à la ligne de formule à l'aide du champ **N° opér.** . |

## <a name="formula-versions"></a>Versions de formule
Si vous créez une formule, vous devez d'abord créer une version de formule avant d'ajouter les articles de la ligne de formule et leurs caractéristiques. Chaque formule doit avoir au moins une version. Le bouton **Approbation** sur une version de formule devient disponible dès qu'un enregistrement de version a bien été enregistré. Chaque enregistrement de version de formule est associé à un ou plusieurs co-produits et sous-produits pouvant être produits lorsque obtenez le produit fini. De nombreux produits peuvent être créés à partir des mêmes ingrédients dans différentes tailles de lot, par multiples, ou avec différents rendements. Vous pouvez créer autant de versions de formule que nécessaire.

Pour gérer plusieurs versions de formule actives, utilisez les plages de date d'effet ou les champs de quantité de départ. Plusieurs versions de formule actives peuvent exister uniquement si la plage de dates et la quantité de départ ne se chevauchent pas.

Contrairement aux nomenclatures qui sont souvent associées à plusieurs versions de nomenclature, une seule version de formule existe généralement par formule. N'oubliez pas qu'une seule version de formule peut être activée pour les dimensions et la quantité de couverture pour un produit donné. Toutefois, plusieurs versions de formule peuvent exister pour d'autres motifs, et vous pouvez les sélectionner manuellement lorsque vous créez un lot de commandes.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Approuver et activer des formules et des versions de formule
Il faut approuver toutes les formules et versions de formule avant de pouvoir les utiliser pour la planification et la production. Les formules sont généralement activées pour pouvoir être utilisées. Toutefois, lors de la production, vous pouvez sélectionner une version de formule qui est approuvée, mais qui n'est pas activée.

Pour sécuriser une formule ou une version de formule, vous pouvez définir les paramètres **Édition en bloc** et **Bloquer la suppression de l'approbation** sur la page **Paramètres de contrôle de production**.

Si vous sélectionnez **Édition en bloc** et que la formule est approuvée, aucun champ sur les lignes de formule ne peut être supprimé ni modifié. Toutefois, si vous supprimez l'approbation de la formule, vous pouvez supprimer et modifier les lignes de formule. Vous pouvez également créer de nouvelles formules et de nouvelles versions de formule.

Si vous sélectionnez **Bloquer la suppression de l'approbation**, vous ne pourrez pas supprimer l'approbation d'une formule ou d'une version de formule approuvée. Toutefois, vous pouvez créer de nouvelles formules et nouvelles versions de formule, et vous pouvez supprimer l'activation de la version de formule.

Vous pouvez ajouter des niveaux de contrôle à l'aide de la fonctionnalité de signature électronique. Lorsqu'un utilisateur est paramétré pour qu'une signature électronique soit requise lors de l'approbation de la formule, une page **Signature** s'affiche lorsque la formule est activée. L'utilisateur doit être autorisé à utiliser la signature électronique, et le certificat doit être correctement validé avant que la modification puisse être validée. Si la signature ne peut pas être authentifiée, l'approbation ou la désapprobation est refusée et la modification qui a initié l'approbation ou la désapprobation revient à son état initial.

## <a name="use-the-scalable-feature"></a>Utiliser la fonctionnalité Évolutive
La fonctionnalité Évolutive est disponible que si tous les composants de la formule sont définis sur **Consommation variable**. La fonctionnalité n'est pas disponible si les composants sont définis sur **Consommation fixe** ou **Consommation de l'étape**. Lorsque cette fonctionnalité Évolutive est utilisée, toute modification apportée à un ingrédient dans une formule modifiera également la quantité des autres ingrédients sélectionnés. La taille de la formule est également modifiée. De même, si vous modifiez la taille de la formule, la quantité de tous les ingrédients évolutifs est modifiée. Cette fonction est prévue spécifiquement pour la création et la mise à jour de formule. Elle n'indique pas si la quantité d'un ingrédient sera évolutive vers le haut ou vers le bas dans un lot de commandes.

## <a name="use-step-consumption"></a>Utiliser la fonctionnalité Consommation de l'étape
La fonctionnalité Consommation de l'étape élimine la condition que vous devez saisir une quantité dans l'onglet **Ligne de formule** pour un ingrédient. Au lieu de cela, la fonctionnalité Consommation de l'étape est configurée pour que les valeurs **Série de départ** et **Quantité** soient disponibles. Les informations de l'enregistrement Consommation de l'étape par série qui répond à la quantité du lot de commande sont sélectionnées. La fonctionnalité Consommation de l'étape est utile lorsque le taux de consommation n'est pas linéaire conformément à la taille du lot de commandes et augmente uniquement la demande lorsqu'un seuil de quantité spécifique est détecté. Pour activer cette fonction pour une nouvelle formule, sous le groupe **Calcul de la consommation**, remplacez le paramètre de formule pour l'ingrédient applicable **Standard** par **Étape**. Spécifiez cette méthode de consommation dans l'onglet **Paramétrage** de la page **Ligne de formule**.
