---
title: Nomenclatures et formules
description: "Cet article fournit des informations sur les nomenclatures et les formules, qui sont un élément central de la définition des produits et des variantes de produit. Les nomenclatures et les formules spécifient les matières ou les ingrédients nécessaires pour un produit spécifique. Les formules spécifient également les coproduits et les sous-produits reçus dans un contexte de production spécifique."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e7a2b316b7c7f153c0d41e31a0dffea1cf6f20b0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="bills-of-materials-and-formulas"></a>Nomenclatures et formules

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les nomenclatures et les formules, qui sont un élément central de la définition des produits et des variantes de produit. Les nomenclatures et les formules spécifient les matières ou les ingrédients nécessaires pour un produit spécifique. Les formules spécifient également les coproduits et les sous-produits reçus dans un contexte de production spécifique. 

<a name="bills-of-materials"></a>Nomenclatures
------------------

Une nomenclature définit les composants requis pour de la fabrication d'un produit. Les composants peuvent être des matières premières, des produits semi-finis ou des ingrédients. Dans certains cas, des services peuvent être référencés dans une nomenclature. Toutefois, les nomenclatures décrivent généralement les *ressources matérielles* requises.  

Lorsqu'elle est combiné avec une gamme ou un flux de production qui décrivent les opérations et les ressources requises pour fabriquer un produit, la nomenclature forme la base du calcul du coût estimé du produit.  

Une nomenclature est une entité individuelle qui est décrite par les informations suivantes :

-   L'ID nomenclature
-   Nom de la nomenclature
-   Les lignes de nomenclature qui décrivent les composants et les ingrédients
-   Les versions de nomenclature, qui définissent le produit et la période pour lesquels la nomenclature peut être utilisée

Une nomenclature seule décrit un seul niveau identifié par un identificateur unique. Les composants peuvent avoir leurs propres nomenclature référencées par des versions de nomenclature. Vous pouvez afficher et modifier la hiérarchie complète des nomenclatures pour un produit spécifique dans le concepteur de nomenclatures.

### <a name="formulas-co-products-and-by-products"></a>Formules, co-produits et sous-produits

Une formule est un sous-type de nomenclature qui est généralement utilisé pour le traitement de la production. Outre les composants et les ingrédients, une formule décrit les coproduits et les sous-produits. Dans la version actuelle, la définition des coproduits et des sous-produits de la formule requiert la version de la formule. Une formule est généralement définie pour un produit fini spécifique (une formule ou un élément de planification) défini dans la version de la formule.

### <a name="boms-in-the-product-lifecycle"></a>Les nomenclatures dans le cycle de vie de produits

Dans le cycle de vie des produits, plusieurs types de nomenclature peuvent être créés pour des raisons diverses :

-   **Ébauche/brouillon de nomenclature** – Cette nomenclature donne une estimation préliminaire des matières requises dans une phase précoce de conception proche et donne une idée grossière des coûts et des attributs de produit estimés. Cette nomenclature n'est généralement pas utilisée dans un système ERP (enterprise resource planning).
-   **Nomenclature d'ingénierie** – Cette nomenclature est généralement utilisée lors de la conception de produits basés sur des portefeuilles de produits existants. Les nomenclatures d'ingénierie sont structurées pour simplifier le processus de conception et regrouper les produits complexes dans des modules d'ingénierie. Pour les produits simples, il peut être possible d'utiliser des nomenclatures d"ingénierie pour le processus de production réel. Toutefois, pour d'autres produits, la nomenclature d'ingénierie doit être convertie en nomenclature de production réelle. Mes nomenclatures d'ingénierie sont généralement représentées par des fantômes dans la hiérarchie des nomenclatures. Bien que les nomenclatures d'ingénierie puisse être utilisée pour l'organisation et l'exécution des opérations de fabrication, cette approche peut mener à des inefficacités, en particulier dans des opérations répétitives dans lesquelles plusieurs ordres sont créés.
-   **Nomenclature de planification** – Cette nomenclature est utilisée pour prévoir les besoins matériels. La demande des composants et des ingrédients est calculée en fonction de la demande de produits finis. Comme les nomenclatures d'évaluation des coûts, les nomenclatures de planification représentent un assortiment de matériels utilisés dans une période.
-   **Nomenclature de production** – Il s'agit de la nomenclature réelle utilisée pour une production spécifique. Une nomenclature de production doit prendre en compte les ressources réelles qui permettent de fabriquer le produit. Lorsqu'un ordre de fabrication, un lot de commandes ou un kanban est créé, les différents niveaux des nomenclatures qui sont représentés par des fantômes sont réduits en un seul niveau et sont répartis sur les opérations de l'ordre.
-   **Nomenclature d'évaluation des coûts** – Cette nomenclature est utilisée pour calculer le coût estimé d'un produit. Par exemple, vous pouvez utiliser une nomenclature d'évaluation des coûts lorsque le coût standard est utilisé ou lorsque le coût planifié estimé d'un produit donné est calculé. Les nomenclatures d'évaluation des coûts peuvent faire référence à un assortiment spécifique des matières et des ressources qu'il est prévu d'utiliser. Par conséquent, vous pouvez utiliser la nomenclature d'évaluation des coûts pour créer un coût estimé représentatif d'une période et éviter des écarts dans le temps.

Les types de nomenclature utilisés réellement dans une implémentation dépendent de l'implémentation, ainsi que des scénarios et des besoins de l'entreprise. Dans les implémentations simples, une nomenclature de planification, une nomenclature de production et une nomenclature d'évaluation des coûts peuvent être modélisées comme une seule nomenclature. Dans les environnements ayant de fréquentes modifications techniques et plusieurs gammes alternatives, un plus grand ensemble de types de nomenclature est probablement requis.

### <a name="approval-of-boms-and-formulas"></a>Approbation des nomenclatures et des formules

Chaque nomenclature et chaque formule peuvent être séparément approuvées ou non approuvées. Généralement, l'approbation d'une nomenclature ou d'une formule se produit lorsque la première version de nomenclature pertinente est approuvée. Toutefois, dans certains scénarios d'entreprise, ces approbations peuvent constituer différentes étapes du processus et peuvent impliquer différents propriétaires de processus.  

Notez que, si une nomenclature est non approuvée, toutes les versions de nomenclature associées sont également non approuvées.

## <a name="bom-and-formula-versions"></a>Versions de nomenclature et de formule
Pour lier une nomenclature ou une formule spécifique à une variante de produit qui peut être produite, vous devez créer une version de nomenclature ou une version de formule. La validité des versions de nomenclature et des versions de formule peut être contrainte par période, quantité, site, dimensions de produit spécifiques, et d'autres critères. Les versions de formule ont d'autres attributs supplémentaires importants, tels que le rendement, les définitions de coproduit et de sous-produit et les instructions de répartition des coûts pour la formule.

### <a name="approval-of-bom-and-formula-versions"></a>Approbation de versions de nomenclature et de formule

Avant qu'une version de nomenclature puisse être utilisée dans le processus de fabrication ou de planification, elle doit être approuvée. Lorsqu'une version de nomenclature est approuvée, la nomenclature associée peut également être approuvée, selon le choix de l'utilisateur et ses droits d'authentification. Notez qu'une version de nomenclature peut être approuvée uniquement si la nomenclature associée elle-même est approuvée.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Activation de la nomenclature ou de la version de formule par défaut

Pour définir une nomenclature ou une formule particulière comme version de nomenclature ou de formule par défaut, utilisée par la planification ou utilisées pour créer des ordres de fabrication, vous devez activer sa version. Lorsqu'une version est activée, l'unicité de la version pour les contraintes données (par exemple, période, site ou quantité) est vérifiée. Vous recevez un message d'erreur si la version que vous tentez d'activer est en conflit avec une version qui est déjà active. Vous devez alors désactiver la version en conflit ou modifier les contraintes de version (généralement la période) pour empêcher une activation ambiguë.

### <a name="product-change-with-case-management"></a>Modification de produit avec gestion de dossier

Le dossier de modification de produit pour approbation et activation de la nomenclature nouvelles ou modifiée et des versions de la nomenclature fournit un moyen facile pour afficher une vue d'ensemble des contraintes de version de nomenclature. Vous pouvez également approuver et activer toutes les nomenclatures et les formules liées à une modification spécifique pour une date d'activation.

### <a name="alternative-bom-versions"></a>Versions de nomenclature alternatives

Parfois, la version de nomenclature ou la version de formule active ne doit pas être utilisée pour les prévisions, les ventes, ou un produit parent. Dans ce cas, vous pouvez sélectionner une nomenclature spécifique approuvée dans le cadre de la demande (ligne de prévision, ligne de vente, ou ligne de nomenclature) si une version de nomenclature ou une version de formule approuvée existe pour la nomenclature ou la formule alternative.  

Lorsque des ordres prévisionnels, des ordres de fabrication ou des kanbans sont créés, le superviseur d'atelier ou le planificateur peut utiliser n'importe quelle version de nomenclature approuvée valide à la date de production planifiée demandée pour organiser la fabrication d'un produit particulier. La version de nomenclature utilisée ne doit pas être activée comme version de nomenclature par défaut.

## <a name="bom-and-formula-lines"></a>Lignes de nomenclature et formule
Une ligne de nomenclature est créée pour chaque matière, service ou ingrédient. La ligne définit la consommation prévue de la variante de produit spécifiée et définit également les différents attributs associés à la consommation prévue.  

Les lignes de nomenclature peuvent avoir les types de ligne suivante : **Article****Fantôme****Approvisionnement invariable****Fournisseur**.

### <a name="item"></a>Article

Sélectionnez le type de ligne **Article** pour les matières ou les services qui sont consommés directement, et qui ne requièrent pas davantage d'éclatement ou d'approvisionnement invariable.

### <a name="phantom"></a>Fantôme

Sélectionnez le type de ligne **Fantôme** lorsque vous souhaitez éclater les articles de nomenclature de niveau inférieur contenus dans la ligne de nomenclature. Dans le calcul PDP/MRP, dans le calcul des coûts planifiés, ou à l'estimation d'un ordre de fabrication utilisant des lignes de nomenclature du type **Fantôme**, la ligne de nomenclature parent qui fait référence une variante de produit qui a une nomenclature fantôme est remplacée par les composants répertoriés en tant que lignes de nomenclature dans cette nomenclature, comme déterminé par la version de nomenclature active applicable de cette variante de produit. Si la variante de produit a une gamme active applicable, les opérations de cette gamme sont fusionnées dans la gamme parent.  

Notez que les fantômes sont généralement utilisés pour simplifier le processus d'ingénierie. L'utilisation étendue des nomenclatures fantômes à plusieurs niveaux a un impact sur les performances, en particulier dans les scénarios de fabrication très répétitifs. Pour améliorer les performances, vous devez éviter les hiérarchies de fantômes profondes. Au lieu de cela, utilisez les nomenclatures de production pré-éclatées et les gammes.

### <a name="pegged-supply"></a>Approvisionnement invariable

Sélectionnez le type de ligne **Approvisionnement invariable** lorsque vous souhaitez créer une sous-production, un kanban d'événement de ligne de nomenclature, ou une commande fournisseur directe pour toute variante de produit à laquelle la ligne de nomenclature fait référence. La sous-production, le kanban d'événement ou la commande fournisseur est créée lorsque vous estimez l'ordre de fabrication. Les quantités requises d'articles sont automatiquement réservées pour la consommation de l'ordre de production.

### <a name="vendor"></a>Fournisseur

Sélectionnez le type de ligne **Vendor** si le processus de production utilise un sous-traitant et si vous souhaitez créer automatiquement une sous-production ou une commande fournisseur pour le sous-traitant.  

**Remarque sur les opérations sous-traitées dans une nomenclature :** le service ou les travaux effectués par le sous-traitant doivent être créés comme article de service suivi dans le stock. Vous devez associer l'article de service à l'article parent comme une ligne de nomenclature. La gamme doit contenir une opération affectée à la ressource opérationnelle du sous-traitant.




