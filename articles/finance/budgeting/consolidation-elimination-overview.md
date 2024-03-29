---
title: Vue d’ensemble de la consolidation et de l’élimination
description: Cet article fournit des informations générales sur le processus de consolidation et d’élimination. Il inclut des réponses à un certain nombre de questions posées fréquemment.
author: panolte
ms.date: 11/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13151"
- intro-internal
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757c7634fc929ead018d1ddcca4cc223c1a95638
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779905"
---
# <a name="consolidation-and-elimination-overview"></a>Vue d’ensemble de la consolidation et de l’élimination

[!include [banner](../includes/banner.md)]

Cet article fournit des informations générales sur le processus de consolidation et d’élimination. Il inclut des réponses à un certain nombre de questions posées fréquemment.

Lorsque vous consolidez des données, les résultats financiers de plusieurs filiales sont combinés à ceux d’une seule société consolidée. Les filiales peuvent utiliser différentes versions ou différents systèmes, qu’elles ne possèdent peut-être pas entièrement, et peuvent utiliser des devises différentes. Il existe plusieurs options pour consolider les données :

-   **Consolidation en ligne** : Cette option consolide les soldes comptables quotidiens par comptes et dimensions sélectionnés, et les enregistre dans une société de consolidation.
-   **États financiers** : Cette option active la consolidation des transactions et des soldes, et peut être générée à tout moment. Plusieurs niveaux de hiérarchies peuvent être créés, et plusieurs devises de déclaration peuvent être affichées.
-   **Consolider avec importation** : Cette option importe les soldes dans une société de consolidation.
-   **Exporter soldes de la société** : Cette option fournit un fichier d’exportation des soldes de la société. Le fichier peut ensuite être importé dans d’autres instances ou systèmes. Les états financiers peuvent également être utilisés pour exporter les soldes vers un fichier Microsoft Excel.

Les éliminations peuvent être déclarées de plusieurs manières :

-  Les règles d’élimination peuvent être paramétrées dans le système, puis traitées lors du processus de consolidation ou via une proposition d’élimination. Les règles peuvent être validées pour n’importe quelle société pour laquelle le processus **Utiliser pour le processus d’élimination financière** est sélectionné dans le paramétrage de l’entité juridique.
-   Une société séparée peut être créée et utilisée pour déterminer manuellement et valider des transactions d’élimination. Cette société peut être utilisée dans le processus de consolidation ou dans les états financiers.
-  Les comptes et les dimensions financières qui permettent de déterminer l’activité intersociétés peuvent être filtrés sur une définition de ligne ou une définition de colonne dans les états financiers, et des capacités complètes d’exploration peuvent être utilisées. Une colonne ou une ligne calculée peut ensuite être utilisée pour supprimer les comptes et les dimensions financières du total consolidé.

Il existe plusieurs scénarios de consolidation, et chaque méthode permet de gérer les scénarios de différentes manières.

## <a name="frequently-asked-questions"></a>Forum aux questions
Je préfère valider les éliminations dans une base de données. Quelles sont les options disponibles ?
 - Vous avez le choix entre plusieurs options. Vous pouvez utiliser l’option **Consolidation en ligne**, et inclure les éliminations lors du processus ou comme proposition. Les transactions seront validées dans la société de consolidation. Sinon, vous pouvez avoir une société séparée dans laquelle vous créez manuellement les éliminations. Vous l’utilisez ensuite dans les états financiers ou dans le processus de consolidation.

Nous avons besoin de disposer de nos résultats consolidés dans plusieurs devises de déclaration.
 - L’option **États financiers** propose un nombre illimité de devises de déclaration. Les données sont converties lors de la génération des états, selon le type de taux de change et la méthode de conversion de devise définis pour le compte principal. Toutefois, étant donné que l’option **Consolidation en ligne** ne dispose que d’une seule devise de déclaration, une société consolidée est requise pour chaque devise de déclaration si vous utilisez cette option. L’option **États financiers** est la méthode recommandée.

Je souhaite afficher les détails de transaction pour chaque société.
 - L’option **États financiers** constitue la solution, car les détails de transaction peuvent être affichés pour autant de sociétés que celles incluses dans la définition d’arborescence de génération d’états.

Nous utilisons la planification ou le contrôle budgétaire, et il doit être consolidé.
 - L’option **États financiers** constitue la solution pour consolider les données de planification budgétaire ou de contrôle budgétaire.

Nos filiales sont réparties à travers le monde, et nous avons plusieurs plans de comptes. Quelle est la meilleure méthode pour consolider nos données ?
- Plusieurs options s’offrent à vous lorsque vous devez traiter plusieurs plans de comptes. Vous pouvez utiliser l’option **Consolidation en ligne**, puis choisir d’utiliser le compte de consolidation défini dans le compte principal ou un groupe de comptes de consolidation. Vous pouvez également utiliser l’option **États financiers**, inclure plusieurs liens vers les dimensions financières dans la définition de ligne, et faire correspondre les comptes.

Nous exigeons plusieurs niveaux de consolidation. Autrement dit, nous commençons par consolider toutes nos filiales européennes avec la devise Livre sterling (GBP). Nous consolidons ensuite ces données et convertissons le montant consolidé en dollars US. De quelle manière devons-nous procéder ?
- Lorsque plusieurs niveaux de consolidation sont requis, et que différentes devises sont utilisées à chaque niveau, vous devez utiliser l’option **Consolidation en ligne**. Il convient de créer plusieurs sociétés de consolidation dont la comptabilité et les devises de déclaration sont différentes. La consolidation doit être exécutée plusieurs fois. L’option **États financiers** convertit toujours de la devise comptable de la société source vers la devise sélectionnée.

Certaines de nos filiales utilisent un système différent. Comment pouvons-nous les consolider ?
- Utilisez l’option **Consolider avec importation** pour importer les soldes dans une société de consolidation.

Certaines de nos filiales ne sont pas détenues à 100 %. Quelle est la meilleure méthode pour les consolider ?
- Plusieurs options s’offrent à vous pour les filiales qui ne sont pas détenues à 100 %. L’option **États financiers** vous permet de définir une définition d’arborescence de génération d’états et la propriété. Vous pouvez également utiliser une ligne ou une colonne calculée pour représenter le montant que vous possédez partiellement. Vous pouvez même indiquer la participation minoritaire sur sa propre ligne dans un état. Vous pouvez également utiliser l’option **Consolidation en ligne**. L’onglet **Entités juridiques** comporte une colonne **Propriété** dans laquelle vous pouvez définir le pourcentage détenu par la société mère.

Notre organisation doit présenter les consolidations par unité commerciale ou souhaite utiliser les hiérarchies d’organisation.
- L’option **États financiers** constitue la solution. Les hiérarchies d’organisation qui comportent des entités juridiques ou des dimensions financières peuvent être reportées dans les états financiers. Vous pouvez également créer vos propres hiérarchies à plusieurs niveaux à l’aide d’une définition d’arborescence de génération d’états ayant une combinaison d’entités juridiques et de valeurs de dimension.

Nous avons plusieurs instances du système.
- Vous pouvez consolider les données à l’aide de l’option **Exporter soldes de la société** pour exporter à partir d’une instance, puis l’option **Consolider avec importation** sur l’autre instance.

Puis-je consolider mon budget si son statut est **BROUILLON** ? 
- Vous ne pourrez pas traiter ou compléter vos budgets dans la société de consolidation. Nous avons recommandé d’utiliser Financial Reporting pour consolider les projets de budget.

Pour plus d’informations, voir [Réévaluation de devise dans une société de consolidation](../general-ledger/currency-revaluation-consolidation-company.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
