---
title: "Contenu BI de courant d&quot;analyse de dépenses d&quot;achat"
description: "Cette rubrique décrit ce qui est inclus dans le pack de contenu des analyses des dépenses d&quot;achat pour le projet BI de courant de Microsoft. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités qui permettent de créer le pack de contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenu BI de courant d'analyse de dépenses d'achat

Cette rubrique décrit ce qui est inclus dans le pack de contenu des analyses des dépenses d'achat pour le projet BI de courant de Microsoft. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités qui permettent de créer le pack de contenu.

<a name="overview"></a>Vue d'ensemble
--------

Le pack de contenu des analyses des dépenses d'achat pour le projet BI de courant de Microsoft a été créé pour les gestionnaires des achats et des directeurs qui sont responsables des budgets. Il a conçu pour les aider à retenir un œil sur les dépenses d'achat. Elle utilise des données transactionnelles d'achat de Microsoft Dynamics 365 pour les opérations, et fournit une vue globale des chiffres entreprise d'achat et une répartition de Dépenses d'achat par le fournisseur et le produit. Le point culminant d'états change dans l'achat dépensant dans le temps. Par conséquent, ils peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépense pour des fournisseurs individuels et les produits. Dépenses d'achat de graphiques pour des catégories d'approvisionnement et groupes de fournisseurs. La catégorie et les responsables régionaux peuvent la utile pour utiliser les graphiques pour l'identification des modifications du comportement de dépense. Le pack de contenu permet aux directeurs des achats et des directeurs qui sont responsables des budgets analyser les dépenses d'achat des manières suivantes :

-   achat cumulé jusqu'(par groupe de fournisseurs et des fournisseurs individuels, la catégorie d'approvisionnement et les produits, et l'emplacement fournisseur)
-   modification Année au-dessus an d'achat (par groupe de fournisseurs et la catégorie d'approvisionnement)

## <a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
Le pack de contenu des analyses des dépenses d'achat est émis comme immobilisation de mise en œuvre pour Microsoft Dynamics Lifecycle Services (LCS) et est accessible depuis Microsoft Dynamics 365 pour les opérations. Pour plus d'informations sur la manière d'accéder à et des états BI de courant, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).

## <a name="metrics-that-are-included-in-the-content-pack"></a>Mesures incluses dans le pack de contenu
Le pack de contenu des analyses des dépenses d'achat inclut un état qui sont un ensemble de mesures. Ces mesures sont visualisées comme graphiques, vignettes, et tables. Le tableau suivant fournit une vue d'ensemble une visualisation du pack de contenu.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Page d'état</th>
<th>Graphiques</th>
<th>Tiles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Achats par fournisseur</td>
<td><ul>
<li>Fournisseurs principal 10 par l'achat (empilé graphique à barres)</li>
<li>Achat total par groupe de fournisseurs/pays/Nom (graphique à secteurs)</li>
<li>Achats par groupe de fournisseurs/pays/Nom (histogramme)</li>
<li>Achat moyen par groupe de fournisseurs/pays/Nom (histogramme)</li>
</ul></td>
<td><ul>
<li>Total des achats</li>
<li>Croissance d'achat de YOY</li>
<li>Total # fournisseurs</li>
<li>Total # de fournisseurs actifs</li>
</ul></td>
</tr>
<tr class="even">
<td>Sous-produit d'achat</td>
<td><ul>
<li>Achat par catégorie d'approvisionnement/nom du produit (histogramme)</li>
<li>Achat total par catégorie d'approvisionnement/nom du produit (graphique à secteurs)</li>
<li>Produits principal 10 par l'achat (empilé graphique à barres)</li>
</ul></td>
<td><ul>
<li>Total # de produits</li>
<li>Pourcentage actif de produit total du total # de produits</li>
<li>Numéro de produits pour l'achat de 80%</li>
</ul></td>
</tr>
<tr class="odd">
<td>Achat par le period*</td>
<td><ul>
<li>Achat par mois/jour (histogramme)</li>
<li>Écart cumulé de l'achat YOY (graphique de cascade à écriture ligne par ligne)</li>
<li>Croissance de l'achat YOY de total (histogramme)</li>
<li>Relevé d'approvisionnement (matrice)</li>
</ul></td>
<td><ul>
<li>Croissance d'achat de YOY</li>
<li>Croissance % d'achat de YOY</li>
</ul></td>
</tr>
<tr class="even">
<td>Achat par emplacement fournisseur</td>
<td><ul>
<li>Achat par ville</li>
<li>Croissance % de l'achat YOY</li>
<li>Achat par pays</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analyse des dépenses d'achat par temps</td>
<td><ul>
<li>Année en cours d'achat par mois/jour (ligne graphique)</li>
<li>Actuel d'achat et la dernière année (ligne et histogramme)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analyse des dépenses d'achat par fournisseur</td>
<td><ul>
<li>Achat % du fournisseur principal 10 d'achat (entonnoir)</li>
<li>Fournisseurs principal 10 avec YOY de dépense augmenté</li>
<li>Fournisseurs principal 10 avec YOY de dépense diminué</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

achat\* cette année et la dernière année, et croissance par catégorie d'approvisionnement

## <a name="data-model-and-entities"></a>Modèle de données et entités
Dynamics 365 pour les données d'opérations est utilisé pour l'état du pack de contenu des analyses des dépenses d'achat. Ces données sont représentées comme mesures globales présentées dans le magasin d'entité, qui est une base de données SQL Microsoft qui est optimisée pour analyses. Pour plus d'informations sur le magasin d'entité, voir [intégration BI de courant avec le magasin d'entité dans Dynamics] (valider de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales dans ce pack de contenus est le sous-ensemble de mesures globales qui sont disponibles dans le cube achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics 365 pour les opérations 2012 R3. Dans le stade les mesures globales du cube dans le magasin d'entité, vous devez les rendre déployables. Pour plus d'informations, voir la procédure pour les mesures d'agrégat d'échelonnement dans le magasin d'entité dans le champ [intégration BI de courant avec le magasin d'entité dans Dynamics] (valider de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures suivantes d'agrégat principaux sont livrées directement depuis les lignes de facture entité et sont utilisées comme base du pack de contenu.

| Entité        | Key aggregate measurements | Source de données pour Dynamics 365 pour les opérations | Champ              | description ;                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Lignes de facture | Achats                   | VendInvoiceTrans                            | SOMME (LineAmountMST) | Montant en devise comptable |

Le tableau suivant indique les mesures principales qui sont calculées du pack de contenu de l'entité de lignes de facture.

| Mesure               | Calcul                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Année en cours d'achat | Année en cours d'achat = SOMME ('achat\]de lines'entity_PLACEHOLDER\[de facture)                                            |
| Achat l'année dernière    | Achat l'année dernière = CALCULENT (SOMME (« achat\]), SAMEPERIODLASTYEAR (date\]de lines'entity_PLACEHOLDER\[de facture\[de dates)) |
| Croissance d'achat de YOY   | Croissance d'achat de YOY = année en cours\] d'achat \[– Achat l'année dernière\]\[                            |

Les dimensions suivantes clés du pack de contenu sont utilisées en tant que filtres pour découper les mesures en tranches globales, afin de pouvoir accomplir plus de granularité et d'analyses analytique plus approfondie.

| Entité                 | Exemples d'attributs                                |
|------------------------|-------------------------------------------------------|
| Fournisseurs                | Pays de groupes de fournisseurs, de fournisseur ou régions, nom du fournisseur |
| Produits               | Numéro de produit, nom, nom de groupes d'articles        |
| Catégories d'approvisionnement | Catégorie d'approvisionnement, noms de catégories d'approvisionnement      |
| Entités juridiques         | Nom de l'entité juridique                                     |
| dates ;                  | Dates, contrepartie d'exercice                                    |

Par défaut, les données du schéma du pack de contenu pour l'année civile en cours. Toutefois, vous pouvez modifier le filtre date dans la section de filtres d'état. Vous pouvez également modifier le filtre de la société.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)



