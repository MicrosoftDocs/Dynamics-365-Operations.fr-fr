---
title: Configuration des coûts pour la gestion des commandes distribuées (DOM)
description: Cet article décrit la configuration des coûts pour la fonctionnalité de gestion des commandes distribuées (DOM) dans Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9aaff8f627adcd00be174a0b5f7bd398300cfef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862016"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Configuration des coûts pour la gestion des commandes distribuées (DOM)

[!include [banner](../includes/banner.md)]

Les organisations prennent en compte plusieurs composants de coût pour déterminer l’emplacement optimal à partir duquel traiter une commande. Certains de ces composants de coût sont le coût d’expédition, le coût de gestion et le coût d’emballage. Une combinaison de ces coûts est calculée pour déterminer l’emplacement d’exécution.

Lorsque la première itération de la gestion des commandes distribuées (DOM) dans Dynamics 365 Commerce a optimisé l’affectation des commandes à des emplacements d’exécution, elle a pris en compte la distance uniquement. Bien que la distance puisse être mise en corrélation avec le coût, elle n’est pas considérée comme un coût. Par exemple, un mode d’expédition de nuit coûte plus de trois jours d’expédition ou sept jours d’expédition sur la même distance.

La fonction de configuration des coûts permet aux détaillants de définir et de configurer des composants de coût supplémentaires qui seront calculés et pris en compte pour déterminer l’emplacement optimal à partir duquel traiter des lignes de commande.

Lorsque des composants de coût sont configurés, le solveur DOM utilise uniquement ces définitions de coût pour déterminer l’emplacement optimal pour traiter une commande. Il ne considère pas le composant de distance comme un coût. Toutefois, si aucun composant de coût n’est configuré, le solveur DOM utilise le composant de distance comme coût pour déterminer l’emplacement optimal pour traiter une commande.

## <a name="set-up-cost-components"></a>Paramétrer des composants de coût

Deux principaux types de composants de coût peuvent être définis dans le système : **Expédition** et **Autre**.

Ces deux types de composants de coût prennent en charge plusieurs bases de calcul, comme indiqué dans le tableau suivant.

<table>
<thead>
<tr>
<th>Type de composant de coût</th>
<th>Base de calcul</th>
</tr>
</thead>
<tbody>
<tr>
<td>Expédition</td>
<td>
<ul>
<li>Simple</li>
<li>Progressif</li>
</ul>
</td>
</tr>
<tr>
<td>Autre</td>
<td>
<ul>
<li>Commande client</li>
<li>Ligne de vente</li>
<li>Emplacement</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Type de composant de coût Expédition

Cette section explique comment paramétrer chaque combinaison du type de composant de coût **Expédition** et d’une base de calcul pour les coûts d’expédition. Elle explique également comment le solveur DOM utilise chaque combinaison.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Type de composant de coût = Expédition et Base de calcul = Simple

Si une combinaison du type de composant de coût **Expédition** et de la base de calcul **Simple** est utilisée, le coût d’expédition pour un mode de livraison est basé sur un coût ou une distance forfaitaire.

Vous devez paramétrer les champs suivants pour cette combinaison :

- **Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.
- **Description** – Entrez le nom et la description du facteur de coût.
- **Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique. Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.
- **Actif** – Indique si le facteur de coût est actif. Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.
- **Société** – Spécifiez l’entité juridique pour laquelle le facteur de coût est configuré. Toutes les lignes des critères de calcul doivent s’appliquer à la même entité juridique.
- **Modes de livraison** – Spécifiez les modes de livraison pour lesquels le coût est configuré.
- **Type de calcul** – Spécifiez le mode de calcul du coût pour un mode de livraison spécifique. Deux types de calcul sont pris en charge :

    - **Fixe** – Un coût forfaitaire est utilisé pour le mode de livraison. Si vous sélectionnez ce type de calcul, le champ **Coût** définit le coût forfaitaire.
    - **Par unité de distance** – Le coût pour le mode de livraison est calculé comme la valeur de coût spécifiée dans le champ **Coût** multipliée par la distance entre l’adresse de livraison et les emplacements.

- **Coût** – Spécifiez la valeur de coût qui est utilisée conjointement avec le champ **Type de calcul** pour calculer le coût pour un mode de livraison.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Type de composant de coût = Expédition et Base de calcul = Progressif

Si une combinaison du type de composant de coût **Expédition** et de la base de calcul **Progressif** est utilisée, le coût d’expédition pour un mode de livraison est basé sur un coût ou une distance forfaitaire. Toutefois, dans cette combinaison, la distance est basée sur une plage de distances progressives.

Vous devez paramétrer les champs suivants pour cette combinaison :

- **Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.
- **Description** – Entrez le nom et la description du facteur de coût.
- **Coût par défaut** – Spécifiez le coût qui doit être utilisé pour un mode de livraison si la distance entre l’adresse de livraison et l’emplacement n’est pas comprise dans les distances progressives pour le mode de livraison.
- **Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique. Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.
- **Actif** – Indique si le facteur de coût est actif. Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.
- **Société** – Spécifiez l’entité juridique pour laquelle le facteur de coût est configuré. Toutes les lignes des critères de calcul doivent s’appliquer à la même entité juridique.
- **Modes de livraison** – Spécifiez les modes de livraison pour lesquels le coût est configuré.
- **Type de distance** – Spécifiez si la définition de la distance progressive est une distance à vol d’oiseau ou une distance kilométrique.
- **Unités de distance** – Spécifiez l’unité de mesure de la distance progressive.
- **Distance à partir de** – Spécifiez la plage de début de la distance progressive.
- **Distance jusqu’à** – Spécifiez la plage de fin de la distance progressive.
- **Type de calcul** – Spécifiez le mode de calcul du coût pour un mode de livraison et une distance progressive spécifiques. Deux types de calcul sont pris en charge :

    - **Fixe** – Un coût forfaitaire est utilisé pour le mode de livraison. Si vous sélectionnez ce type de calcul, le champ **Coût** définit le coût forfaitaire.
    - **Par unité de distance** – Le coût pour le mode de livraison et la distance progressive est calculé comme la valeur de coût spécifiée dans le champ **Coût** multipliée par la distance entre l’adresse de livraison et les emplacements.

- **Coût** – Spécifiez la valeur de coût qui est utilisée conjointement avec le champ **Type de calcul** pour calculer le coût pour un mode de livraison.

> [!NOTE]
> - Lorsque vous définissez des distances progressives, le système valide qu’aucune distance ne manque ou que des distances ne se chevauchent pas.
> - Le type de distance utilisé pour un mode de livraison doit être le même pour toutes les distances progressives.

### <a name="other-cost-component-type"></a>Type de composant de coût Autre

Cette section explique comment paramétrer chaque combinaison du type de composant de coût **Autre** et d’un autre type de coût pour les coûts hors expédition. Elle explique également comment le solveur DOM utilise chaque combinaison.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Type de composant de coût = Autre et Autre type de coût = Commande client

Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Commande client** est utilisée pour définir les coûts hors expédition au niveau de la commande client.

Vous devez paramétrer les champs suivants pour cette combinaison :

- **Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.
- **Description** – Entrez le nom et la description du facteur de coût.
- **Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique. Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.
- **Actif** – Indique si le facteur de coût est actif. Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.
- **Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau de la commande client.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Type de composant de coût = Autre et Autre type de coût = Ligne de vente

Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Ligne de vente** est utilisée pour définir les coûts hors expédition au niveau de la ligne de commande client.

Vous devez paramétrer les champs suivants pour cette combinaison :

- **Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.
- **Description** – Entrez le nom et la description du facteur de coût.
- **Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique. Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.
- **Actif** – Indique si le facteur de coût est actif. Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.
- **Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau de la ligne de commande client.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Type de composant de coût = Autre et Autre type de coût = Emplacement

Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Emplacement** est utilisée pour définir les coûts hors expédition pour un groupe d’emplacements ou un emplacement individuel.

Vous devez paramétrer les champs suivants pour cette combinaison :

- **Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.
- **Description** – Entrez le nom et la description du facteur de coût.
- **Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique. Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.
- **Actif** – Indique si le facteur de coût est actif. Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.
- **Groupe d’exécution** – Spécifiez le groupe d’emplacements pour lesquels le coût hors expédition est défini.
- **Emplacement d’exécution** – Spécifiez l’emplacement pour lequel le coût hors expédition est défini.

    > [!NOTE]
    > Vous ne pouvez pas spécifier un groupe d’exécution et un emplacement d’exécution sur la même ligne pour les critères de calcul basés sur l’emplacement.

- **Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau du groupe d’exécution ou au niveau de l’emplacement d’exécution.

> [!IMPORTANT]
> Pour que DOM prenne en compte ces coûts au moment de l’exécution, vous devez ajouter le facteur de coût au profil d’exécution approprié.


[!INCLUDE[footer-include](../includes/footer-banner.md)]