---
title: Validation des coûts indirects
description: Cet article explique comment valider les coûts indirects, créer des groupes de coûts et ajouter des nœuds à la feuille de coûts pour les coûts indirects.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 04af10760ec50d60cbbc31c233109dffb786933c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868429"
---
# <a name="indirect-cost-posting"></a>Validation des coûts indirects

Les coûts indirects sont des coûts qui ne sont pas directement liés à une seule activité du processus de production. Les exemples incluent les coûts administratifs tels que les salaires des employés, les coûts du service de comptabilité et les frais généraux tels que le loyer, les services publics et le coût des machines.

## <a name="calculating-indirect-costs"></a>Calcul des coûts indirects

Microsoft Dynamics 365 Finance ne dispose pas d’un moyen automatisé pour calculer le taux des coûts indirects. Vous devez déterminer vos coûts indirects, créer des codes de coûts indirects et gérer le taux pour chaque coût indirect dans la feuille de coûts.

Le processus exact utilisé pour calculer les coûts indirects peut varier légèrement d’une entreprise à l’autre. Toutefois, le processus inclut généralement les étapes de base suivantes :

1. Créer une liste des coûts indirects à comptabiliser en production. Cette liste peut inclure le loyer, les dépenses administratives, les frais de comptabilité et les frais juridiques. Elle ne doit pas inclure les coûts des matières premières ou les coûts de main-d’œuvre qui sont reconnus dans les gammes de production.
2. Additionner tous les coûts indirects. Vous pouvez regrouper des types de coûts indirects similaires ou les séparer. Chaque coût indirect configuré peut avoir différents comptes principaux qui sont utilisés pour la validation en comptabilité.
3. Comparer les coûts indirects à un facteur, également appelé base d’absorption. Vous pouvez choisir n’importe quel facteur. Voici quelques exemples courants :

    - Recettes
    - Quantité totale produite
    - Temps de réglage
    - Temps d’exécution

    Vous pouvez sélectionner la période pour laquelle vous souhaitez calculer vos coûts indirects (mensuelle, trimestrielle ou annuelle, par exemple). La somme de vos coûts indirects et la somme de votre facteur doivent correspondre à la même durée. La formule suivante est utilisée pour calculer le taux du coût indirect :

    *Taux du coût indirect* = *Dépenses totales du coût indirect* &divide; *Facteur total*

4. Créez des groupes de coûts indirects.
5. Configurez la feuille de coûts avec vos tarifs.
6. Gérez le coût de vos coûts indirects dans la version d’évaluation des coûts.

> [!NOTE]
> Vous pouvez utiliser le module **Contrôle de gestion** pour accumuler les coûts et déterminer vos frais généraux à partir de différentes sources, telles que la production, les projets et la comptabilité. Pour plus d’informations, voir [Contrôle de gestion](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Différents organismes de réglementation ont publié des directives sur les types de coûts pouvant être inclus en tant que coûts indirects ou frais généraux dans le coût de vos produits finis. Avant de commencer à configurer les coûts indirects, nous vous recommandons de vérifier auprès de votre comptable et des réglementations locales que vous êtes bien en conformité.

## <a name="create-cost-groups-for-indirect-costs"></a>Créer des groupes de coûts pour les coûts indirects

Vous devez créer au moins un groupe de coûts à utiliser pour les coûts indirects. Il n’y a pas de limite au nombre de groupes de coûts que vous pouvez utiliser. Réfléchissez à la manière dont vous calculez vos coûts et s’il existe différents taux pour différents types de coûts. Par exemple, votre organisation fabrique des produits alimentaires. Certaines matières premières et produits finis sont des produits secs et ont un coût indirect d’entreposage. Les autres matières premières et produits finis sont réfrigérés et ont un coût indirect plus élevé. Dans ce cas, vous pouvez créer deux groupes de coûts : **Frais généraux sur matières sèches** et **Frais généraux sur matières premières réfrigérées**.

Pour créer un groupe de coûts pour les coûts indirects, procédez comme suit :

1. Accédez à **Contrôle de la production &gt; Paramétrage &gt; Gammes &gt; Groupes de coûts**.
2. Sélectionnez **Nouveau** pour créer un groupe.
3. Dans le champ **Groupe de coûts**, entrez un nom unique pour le groupe de coûts, tel que **MATOVH**.
4. Dans le champ **Nom**, entrez une description du groupe de coûts, tel que **Frais généraux sur matières**.
5. Dans le champ **Type de groupe de coûts**, sélectionnez **Indirect**.
6. Facultatif : dans le champ **Comportement**, sélectionnez **Coûts fixes** ou **Coût variable**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Configurer la feuille de coûts pour les coûts indirects

Après avoir créé un ou plusieurs groupes de coûts, vous pouvez configurer votre feuille de coûts avec les coûts indirects et définir votre calcul. Vous souhaiterez peut-être regrouper les coûts indirects dans la feuille de coûts. Pour regrouper les coûts indirects, vous pouvez créer un en-tête dans la feuille de coûts. Vous devez créer au moins un nœud pour chaque groupe de coûts dans la feuille de coûts. Pour chaque groupe de coûts pour les coûts indirects, vous pouvez ajouter un autre calcul de coûts indirects.

### <a name="indirect-cost-node-types"></a>Types de nœuds de coût indirect

Cette section décrit les différents types de nœuds pour les coûts indirects.

#### <a name="surcharge"></a>Surcharge

**Surtaxe** est l’un des types de coûts indirects les plus courants. Il calcule un pourcentage de coût à partir d’une base d’absorption des coûts sur l’ordre de fabrication. Vous devez définir la base d’absorption en sélectionnant les groupes de coûts qui sont liés à vos composants de matière ou de temps dans la feuille de calcul.

Par exemple, un supplément de 3 % peut être ajouté au coût de production pour toutes les matières premières d’un ordre de fabrication.

#### <a name="rate"></a>Taux

Un coût indirect de type **Taux** est utilisé pour ajouter un montant fixe de coût à l’ordre de fabrication à partir d’une base d’absorption des coûts sur l’ordre de fabrication. Le taux peut être basé sur l’un des trois sous-types :

- **Processus** : le tarif est basé sur le temps d’exécution dans la gamme.
- **Paramétrage** : le tarif est basé sur le temps de paramétrage dans la gamme.
- **Quantité** : Le taux est basé sur la quantité produite.

Vous devez définir la base d’absorption en sélectionnant les groupes de coûts qui sont liés aux composants de matière ou de temps dans la feuille de calcul.

Par exemple, un montant fixe de 2,00 dollars américains (USD) est ajouté à chaque ordre de fabrication, en fonction du temps d’exécution dans la gamme pour le groupe de coûts de main-d’œuvre dans votre feuille de coûts.

#### <a name="output-unit-based"></a>Basé sur l’unité de sortie

Un coût indirect de type **Basé sur l’unité de sortie** est calculé en multipliant le montant spécifié sur le raccourci **Taux** de la feuille de coûts par le sous-type sélectionné. Vous pouvez sélectionner la quantité, le poids ou le volume du produit fini comme multiplicateur du coût indirect.

Par exemple, vous pouvez utiliser la quantité pour calculer 1,50 USD pour l’amortissement de la machine pour chaque quantité produite. Vous pouvez aussi utiliser le volume pour calculer 2,00 USD pour les coûts de réfrigération correspondant au volume d’espace que les produits finis occupent dans vos unités de réfrigération.

#### <a name="input-unit-based"></a>Basé sur l’unité d’entrée

Un coût indirect de type **Basé sur l’unité d’entrée** est calculé en multipliant la quantité de matières premières consommées sur un ordre de fabrication par un montant. Vous pouvez utiliser le poids ou le volume des entrées sur l’ordre de fabrication pour calculer le total. Vous pouvez limiter le calcul à un sous-ensemble de matériaux en sélectionnant un ou plusieurs groupes de coûts sur le raccourci **Base d’absorption** de la feuille de coûts.

Par exemple, vous pouvez utiliser le volume des entrées pour un groupe de coûts spécifique lié aux produits réfrigérés pour ajouter 1,00 USD à l’ordre de fabrication.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Créer un nœud total pour les coûts indirects dans la feuille de coûts

Pour créer un nœud total pour les coûts indirects dans la feuille de coûts, procédez comme suit :

1. Accédez à **Gestion des coûts &gt; Paramétrage des stratégies comptables de coût indirect &gt; Feuille de coûts**.
2. Dans l’arborescence, sélectionnez un nœud qui représente le coût des marchandises qui ont été fabriquées.
3. Sélectionnez **Nouveau** pour créer un nœud.
4. Dans le champ **Sélectionner le type de nœud**, sélectionnez **Total**.
5. Dans le champ **Code**, entrez un ID unique pour le nœud, tel que **Frais généraux de production**.
6. Activez la case à cocher **En-tête**.
7. Activez la case à cocher **Total**.
8. Cliquez sur **OK**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Créer un nœud de groupe de coûts indirects dans la feuille de coûts

Pour créer un nœud de groupe de coûts indirects dans la feuille de coûts, procédez comme suit :

1. Accédez à **Gestion des coûts &gt; Paramétrage des stratégies comptables de coût indirect &gt; Feuille de coûts**.
2. Dans l’arborescence, sélectionnez le nœud sous lequel vous souhaitez créer le coût indirect. Par exemple, sélectionnez le nœud total pour **Frais généraux de production**.
3. Sélectionnez **Nouveau** pour créer un nœud.
4. Dans le champ **Sélectionner le type de nœud**, sélectionnez **Groupe de coûts**.
5. Dans le champ **Code**, entrez un ID unique pour le nœud, tel que **TRANSP**.
6. Dans le champ **Description**, entrez une brève description, comme **Frais généraux du transport**.
7. Cliquez sur **OK**.
8. Dans le champ **Groupe de coûts**, sélectionnez le groupe de coûts, tel que **OVH1 : Frais généraux du transport**.

### <a name="create-a-surcharge-indirect-cost"></a>Créer un coût indirect supplémentaire

Pour créer un coût indirect supplémentaire dans la feuille de coûts, procédez comme suit :

1. Accédez à **Gestion des coûts &gt; Paramétrage des stratégies comptables de coût indirect &gt; Feuille de coûts**.
2. Dans l’arborescence, sélectionnez le nœud de groupe de coûts indirects sous lequel vous souhaitez créer le coût indirect. Par exemple, sélectionnez le nœud total pour **TRANSP : Frais généraux du transport**.
3. Sélectionnez **Nouveau** pour créer un nœud.
4. Dans le champ **Sélectionner le type de nœud**, sélectionnez **Supplément**.
5. Dans le champ **Code**, entrez un ID unique pour le nœud, tel que **Supplément pour le transport**.
6. Cliquez sur **OK**.
7. Dans le champ **Sous-type**, sélectionnez **Total**.
8. Dans le raccourci **Base d’absorption**, sélectionnez **Nouveau** pour créer un code de coût.
9. Dans le champ **Code**, sélectionnez un groupe de coûts à utiliser pour calculer le supplément.
10. Facultatif : répétez les étapes 8 à 9 pour chaque groupe de coûts supplémentaires que vous souhaitez utiliser pour le calcul.
11. Dans le raccourci **Supplément**, cliquez sur **Nouveau** pour créer un taux.
12. Dans le champ **Version**, sélectionnez la version d’évaluation des coûts à laquelle ajouter le supplément.
13. Facultatif : dans le champ **Site**, saisissez le site auquel appliquer le supplément.
14. Dans le champ **Pourcentage**, entrez le pourcentage à calculer sur les ordres de fabrication à partir des groupes de coûts définis dans le raccourci **Base d’absorption**.
15. Sur le raccourci **Validations dans la comptabilité**, sélectionnez le compte principal à utiliser pour les champs **Coût indirect estimé absorbé**, **Coût estimé du coût indirect consommé, travaux en cours**, **Coût indirect absorbé**, et **Coût du coût indirect consommé, travaux en cours**.
16. Facultatif : sur le raccourci **Dimensions financières**, spécifiez les dimensions financières à saisir par défaut sur les transactions lorsqu’elles sont validées en comptabilité.

La procédure précédente montre comment créer un coût indirect de type **Supplément**. Des étapes similaires sont utilisées pour créer d’autres types de coûts indirects. Les sections suivantes décrivent les différences pour chaque type.

#### <a name="rate"></a>Taux

- À l’étape 4, sélectionnez **Taux** à la place de **Supplément**.
- À l’étape 7, sélectionnez **Processus**, **Paramétrage** ou **Quantité** à la place de **Total**.
- À l’étape 11, utilisez le raccourci **Taux** au lieu du raccourci **Supplément**.
- À l’étape 14, saisissez un montant dans le champ **Montant** au lieu d’un pourcentage dans le champ **Pourcentage** .

#### <a name="output-unit-based"></a>Basé sur l’unité de sortie

- À l’étape 4, sélectionnez **Basé sur l’unité de sortie** à la place de **Supplément**.
- À l’étape 7, sélectionnez **Quantité**, **Poids** ou **Volume** à la place de **Total**.
- Ignorez les étapes 8 à 10.
- À l’étape 11, utilisez le raccourci **Taux** au lieu du raccourci **Supplément**.

#### <a name="input-unit-based"></a>Basé sur l’unité d’entrée

- À l’étape 4, sélectionnez **Basé sur l’unité d’entrée** à la place de **Supplément**.
- À l’étape 7, sélectionnez **Poids** ou **Volume** à la place de **Total**.
- À l’étape 11, utilisez le raccourci **Taux** au lieu du raccourci **Supplément**.
