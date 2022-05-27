---
title: Générer des tableaux d’analyse consolidés
description: Cette rubrique décrit les différents scénarios où vous pouvez générer des tableaux d’analyse consolidés.
author: aprilolson
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 092123d6f5f74d2ff160f2ebffdc2c049ccc3f65
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716521"
---
# <a name="generate-consolidated-financial-statements"></a>Générer des tableaux d’analyse consolidés

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les différents scénarios où vous pouvez générer des tableaux d’analyse consolidés.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Consolidations sur un seul niveau et plusieurs niveaux dans les entités juridiques
La méthode de consolidation la plus simple à l’aide de l’outil États financiers consiste à utiliser des organigrammes d’entreprise pour regrouper les données de sociétés ayant les mêmes plans de comptes et périodes fiscales. Voici les principales étapes de la consolidation à l’aide d’un organigramme d’entreprise.

1. Créez une définition de ligne et vérifiez que tous les comptes appropriés de toutes les sociétés sont inclus dans les lignes.
2. Créez une définition de colonne incluant toutes les colonnes requises pour l’état que vous créez.
3. Créez un organigramme d’entreprise incluant un nœud de génération d’états pour chaque société que vous utilisez dans les états consolidés.

> [!TIP]
> Pour plus d’informations sur la création et la gestion des définitions de ligne, des définitions de colonne et des organigrammes d’entreprise, voir [Composants de l’état financier](../../fin-ops-core/dev-itpro/analytics/financial-report-components.md).

L’illustration ci-dessous montre comment vous pouvez utiliser une définition d’organigramme d’entreprise dans l’outil États financiers pour identifier chaque société que vous consoliderez.

![Définition d’organigramme d’entreprise.](./media/reporting-tree-definition.png "Définition d’organigramme d’entreprise")

Comme le montre l’état consolidé dans l’illustration suivante, lorsque vous utilisez l’organigramme d’entreprise avec une définition d’état, vous pouvez afficher chaque société séparément. Les montants consolidés sont affichés au niveau de synthèse.

![Consolider le niveau de synthèse des montants.](./media/consolidate-amount-summary-level.png "Consolider le niveau de synthèse des montants")

Vous pouvez également créer un organigramme d’entreprise à plusieurs niveaux qui inclut autant de niveaux que nécessaire. L’illustration suivante présente une définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par région.

![Définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par région.](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par région")

L’illustration suivante présente une définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par fonction.

![Définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par fonction.](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Définition d’organigramme d’entreprise à plusieurs niveaux avec des cumuls par fonction")

### <a name="viewing-companies-side-by-side"></a>Affichage de sociétés côte à côte
De nombreux clients préfèrent les états où les sociétés apparaissent côte à côte, et où une colonne affiche le total consolidé. Ce format est facile à obtenir après avoir créé l’organigramme d’entreprise. Voici les principales étapes pour afficher des sociétés côte à côte dans les tableaux d’analyse consolidés.

1. Créez une définition de colonne incluant une colonne **Dimension financière** pour chaque société.
2. Utilisez le champ **Unité organisationnelle** pour sélectionner l’arborescence et l’unité organisationnelle pour chaque colonne.
3. Facultatif : ajoutez des en-têtes et des colonnes de total.

L’illustration suivante présente une définition de colonne dans un format côte à côte.

![Définition de colonne dans un format côte à côte.](./media/column-definition-side-by-side-format.png "Définition de colonne dans un format côte à côte")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Consolidations qui utilisent des structures d’organisation créées à partir des entités juridiques
Les hiérarchies d’organisation contenant des dimensions ou des entités juridiques créent dynamiquement des définitions d’organigramme d’entreprise dans l’outil États financiers. Il est facile de simplifier les consolidations en ajoutant une hiérarchie d’organisation à votre état dans l’outil États financiers. Selon la date de l’état, l’outil Financial reporting sélectionne la hiérarchie d’organisation avant ou à la date d’effet, comme indiqué dans l’illustration suivante.

![Créer dynamiquement une définition d’arborescence de génération d’états.](./media/dynamically-create-reporting-tree-definitions.png "Créer dynamiquement une définition d’arborescence de génération d’états")

## <a name="consolidations-that-involve-eliminations"></a>Consolidations impliquant des éliminations
Les transactions d’élimination font communément partie du processus de consolidation. Dans cet exemple, cinq comptes sont éliminés pendant la consolidation : 142600, 211400, 401420, 401180 et 510820. Les sociétés peuvent paramétrer leurs comptes intersociétés différemment. Par exemple, certaines sociétés définissent le dernier chiffre sur 9 si le compte est utilisé dans les transactions intersociétés. Quelle que soit la méthode, si vous connaissez les comptes intersociétés, vous pouvez afficher les éliminations dans vos tableaux d’analyse consolidés.

L’illustration suivante présente une définition de colonne pour un compte de résultat consolidé. Trois comptes intersociétés de résultat sont définis pour chaque société à l’aide du filtre de dimension. Les colonnes F, G et H incluent les comptes d’élimination uniquement pour les sociétés USMF, USRT et DEMF. Ces colonne sont paramétrées de manière à **ne pas** être imprimées sur le tableau d’analyse.

![Définition de colonne pour un compte de résultat consolidé.](./media/column-definition-consolidated-income-statement.png "Définition de colonne pour un compte de résultat consolidé")

Lorsque l’état est généré, les montants d’élimination sont calculés dans les colonnes F, G et H, et leur total est affiché dans la colonne I. La colonne J affiche les montants consolidés. Ces montants de consolidation excluent les éliminations pour les sociétés USMF, USRT et DEMF.

> [!TIP]
> Créez un deuxième état qui affiche uniquement les entrées d’élimination, et utilisez-le dans un groupe d’états incluant votre état consolidé. Vous disposez ainsi de toutes les informations nécessaires pour créer les écritures de journal requises.

L’illustration suivante présente l’état consolidé.

![État consolidé d’un compte de résultat.](./media/consolidated-report-income-statement.png "État consolidé d’un compte de résultat")

Que vous utilisiez des comptes, des dimensions, ou les deux, l’outil États financiers vous permet de filtrer les entrées d’élimination à l’aide des fonctions de filtrage de dimension.

## <a name="minority-interest"></a>Participation minoritaire
Une société peut détenir uniquement un pourcentage d’une autre société. Dans ce cas, lorsque vous générez un état consolidé, il est important de tenir compte uniquement du pourcentage détenu par la société. L’outil États financiers affiche la participation minoritaire de plusieurs façons, selon les préférences de l’utilisateur. L’une d’elles consiste à utiliser un pourcentage de cumul dans la définition d’organigramme d’entreprise. Il est également possible d’afficher la participation minoritaire en tant que ligne distincte dans un état.

### <a name="using-the-reporting-tree-definition"></a>Utilisation de la définition d’organigramme d’entreprise
Dans la définition d’organigramme d’entreprise, entrez le pourcentage de participation dans la colonne **% de cumul** (colonne H), comme indiqué dans l’illustration suivante. Lorsque l’état est généré, ce pourcentage sera utilisé pour calculer le montant consolidé. Dans cet exemple, Contoso ne détient que 80 % de Contoso Germany. Vous pouvez entrer **80** ou **0,8** dans la colonne **% de cumul**, et 80 % seront cumulés au niveau consolidé.

> [!NOTE]
> Vous pouvez appliquer ce pourcentage de participation à n’importe quelle unité organisationnelle, pas uniquement au niveau de la société. 

![Utilisation du pourcentage de la définition d’organigramme d’entreprise.](./media/Using-reporting-tree-definition-percentage.png "Utilisation du pourcentage de la définition d’organigramme d’entreprise")

Lorsque l’état est généré, l’état Contoso Germany affichera 100 % du montant des ventes, et 80 % du montant sera alloué et cumulé au niveau consolidé pour les ventes.

Si vous détenez moins de 1 %% d’une société, vous pouvez activer la case à cocher **Autoriser un cumul inférieur à 1 %%** dans l’onglet **Options supplémentaires** de la page **Paramètres de l’état**, comme indiqué dans l’illustration suivante. Dans ce cas, les valeurs de la colonne **% de cumul** dans l’organigramme d’entreprise seront considérées comme inférieures à 1 %%. Par exemple, si vous entrez **0,8**, 0,8 %% est cumulé au niveau consolidé, et non 80 %%. Vous pouvez également obtenir le même résultat en laissant la case à cocher **Autoriser un cumul inférieur à 1 %%** désactivée et en entrant **0,008** dans la colonne **% de cumul**.

![Options de définition de génération d’états.](./media/reporting-setting-options.png "Options de définition de génération d’états")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Affichage de la participation en tant que ligne distincte dans l’état consolidé
Une autre option de la participation minoritaire consiste à afficher 100 %% de la filiale pour chaque ligne de l’état, mais à soustraire la participation minoritaire du revenu net.

Comme le montre l’illustration suivante, une instruction **IF THEN ELSE** et une restriction de colonne dans la définition de ligne peuvent être utilisées pour calculer la participation minoritaire dans les états financiers.

![Affichage de la participation en tant que ligne distincte dans l’état consolidé.](./media/Showing-ownership-separate-row-consolidated-report.png "Affichage de la participation en tant que ligne distincte dans l’état consolidé")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Plans de comptes multiples dans les entités juridiques
Souvent, chaque entité juridique a son propre plan de comptes mais souhaite générer des tableaux d’analyse consolidés. Dans ce cas, l’outil États financiers peut être utilisé pour consolider les données, afin que vous puissiez générer des états financiers consolidés. Voici les principales étapes de la consolidation lorsque différents plans de comptes existent dans des entités juridiques.

1. Créez une définition de ligne avec plusieurs liens vers les dimensions financières. Il devrait y avoir un lien pour chaque plan de comptes.
2. Utilisez la restriction d’unité organisationnelle dans la définition de colonne pour affecter chaque société à la colonne appropriée.


Plusieurs liens vers les dimensions financières peuvent être ajoutés à chaque ligne de la définition de ligne pour le plan de comptes de chaque société. Dans l’illustration suivante, la société USMF utilise l’ensemble de comptes dans la première colonne **Lien vers les dimensions financières** (colonne J), et la société DEMF utilise les comptes dans la deuxième colonne **Lien vers les dimensions financières** (colonne K).

> [!TIP]
> Pour plus d’informations sur la cellule **Lien vers les dimensions financières**, voir Spécifier la cellule Lien vers les dimensions financières.

![Définir le premier lien des comptes vers les dimensions financières.](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Définir le premier lien des comptes vers les dimensions financières")

Vous pouvez utiliser un organigramme d’entreprise pour définir quel lien vers les dimensions financières de la définition de ligne est utilisé avec chaque société. Sélectionnez la définition de ligne dans la colonne E, puis sélectionnez le lien approprié dans la colonne F, comme indiqué dans l’illustration suivante.

![Lien vers les dimensions financières de la définition de ligne utilisé.](./media/link-financial-dimensions-row-definition-used.png "Lien vers les dimensions financières de la définition de ligne utilisé")

> [!TIP]
> Lorsque vous créez des liens vers les dimensions financières, utilisez la description pour identifier les sociétés auxquelles chaque lien s’applique. Vous pouvez ainsi sélectionner plus facilement la société appropriée lorsque vous créez un organigramme d’entreprise. Dans la définition de colonne, le champ **Unité organisationnelle** vous permet de limiter chaque colonne à une unité de l’organigramme d’entreprise, afin que vous puissiez afficher les données côte à côte. Si vous n’indiquez pas de société spécifique pour une colonne, les données consolidées de toutes les sociétés seront affichées.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Différents calendriers fiscaux dans plusieurs entités juridiques
Chaque entité juridique peut avoir son propre calendrier fiscal mais doit générer des tableaux d’analyse consolidés. La consolidation peut être effectuée de deux manières lorsque différentes périodes fiscales existent dans des entités juridiques :

- Créez une définition de colonne, puis utilisez la période et l’année pour mettre en correspondance les périodes appropriées pour chaque société.
- Sous **Paramètres** \> **Autre** \> **Options supplémentaires**, indiquez si la date de fin de la période ou le numéro de la période est utilisé pour la consolidation.

Lorsque vous créez une définition de colonne pour plusieurs sociétés qui ont différentes périodes fiscales, il est important de définir quelle société sera affectée au champ **Nom de la société** dans la définition d’état. Le calendrier fiscal de cette société sera utilisé comme calendrier fiscal de base pour la définition d’état. Par exemple, le tableau suivant présente la période fiscale qui était configurée pour les sociétés USMF et INMF. Pour les états consolidés, vous souhaitez utiliser le calendrier fiscal de la société USMF. La colonne « Mise en correspondance » indique la période et l’année équivalentes pour chaque société si un état est généré pour le 30 juin 2018.

| Société   | Exercice                                  | Mise en correspondance                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Exercice, du 1er juillet au 30 juin          | Période 12, exercice 2018 | 
| INMF      | Année civile, du 1er janvier au 31 décembre | Période 6, exercice 2018  |

Dans l’illustration suivante, la société USMF est spécifiée dans le champ **Nom de la société** de la définition d’état. Par conséquent, le calendrier fiscal de la société USMF sera utilisé comme calendrier fiscal de base. Dans cet exemple, lorsqu’un état est généré pour le 30 juin 2018, la société USMF utilisera la période BASE, qui est définie comme la période 12 dans la définition d’état. La société INMF utilisera BASE-6, qui correspond à la période 6. Les deux colonnes incluront des données pour juin 2018.

![Période de base de l’état.](./media/report-base-period.png "Période de base de l’état")

L’illustration suivante présente les options de la définition d’état qui vous permettent de spécifier si le numéro de la période ou la date de fin de la période est utilisé pour la consolidation.

![Options de la définition d’état – Numéro de la période.](./media/options-report-definition-period-number.png "Options de la définition d’état – Numéro de la période")

## <a name="business-unit-consolidations"></a>Consolidations d’unité commerciale
Cette rubrique porte sur l’utilisation des définitions d’organigramme d’entreprise et des hiérarchies d’organisation dans l’outil États financiers à des fins de consolidation. Vous pouvez également utiliser l’organigramme d’entreprise pour créer des états de consolidation d’unité commerciale, tels que des états sur les ventes ou les opérations dans le monde entier. Ces états sont une exigence courante. Pour les créer, sélectionnez une société et une dimension pour chaque unité que vous souhaitez consolider. Par exemple, dans l’illustration suivante, le cumul des unités commerciales est obtenu en répétant chaque société dans la colonne **Société** (colonne A) et en identifiant un groupe de valeurs de dimension de département par société dans la colonne **Dimensions** (colonne D).

![États de consolidations d’unité commerciale.](./media/business-unit-consolidation-reports.png "États de consolidations d’unité commerciale")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Consolidations impliquant plusieurs devises de déclaration
L’outil États financiers offre une plus grande flexibilité lorsque vous affichez les données réelles, budgétaires, de contrôle budgétaire et de planification budgétaire dans plusieurs devises. En regroupant les principales données de paramétrage, il n’est pas nécessaire d’effectuer d’autres paramètres dans l’outil États financiers pour afficher un état, dans n’importe quelle devise, à tout moment, pour n’importe quel utilisateur.

### <a name="prerequisites"></a>Conditions préalables
Pour calculer correctement les soldes convertis, l’outil États financiers requiert que la catégorie **Compte Bénéfices non répartis** soit affectée au compte Bénéfices non répartis dans la liste **Compte principal**. L’outil États financiers ne prend pas en charge la validation sur le compte Bénéfices non répartis. Si des transactions sont validées sur le compte Bénéfices non répartis, les soldes convertis ne seront pas calculés correctement. Nous recommandons aux utilisateurs de paramétrer un compte Bénéfices non répartis supplémentaire pour valider les ajustements sur le compte Bénéfices non répartis.

Dans le compte principal, les champs **Type de taux de change des états financiers** et **Type de la conversion de devises** dans l’organisateur **États financiers** doivent être définis pour chaque compte, comme indiqué dans l’illustration suivante. Vous pouvez effectuer cette tâche pour chaque compte, ou vous pouvez utiliser les modèles de compte pour généraliser facilement les modifications.

- Dans le champ **Type de taux de change des états financiers**, sélectionnez le type de taux de change contenant les devises et les taux de change à appliquer au compte. Ce tableau de devises et de taux de change sera appliqué aux données réelles dans l’outil États financiers.
- Dans le champ **Type de la conversion de devises**, sélectionnez la méthode utilisée pour calculer le taux de change du compte. Cette méthode de conversion de devises est utilisée pour les données réelles et budgétaires dans l’outil États financiers.

![Comptes principaux des états financiers.](./media/Financial-reporting-main-accounts.png "Comptes principaux des états financiers")

Pour les données de budget, de contrôle budgétaire et de planification budgétaire, le type de taux de change est défini dans la page **Comptabilité**. Ce tableau sera utilisé pour extraire les taux de change, et le type de conversion de devises affecté au compte sera utilisé.

### <a name="currency-translation-methods"></a>Méthodes de conversion de devises
Quatre options sont disponibles pour calculer les taux de change dans l’outil États financiers :

- **Moyenne pondérée** – Cette méthode est utilisée le plus souvent pour les comptes de résultat. Elle utilise la formule suivante :

    (Taux de change x Jours en vigueur) ÷ Jours dans la période

- **Moyenne** – Cette méthode est une autre méthode pour les comptes de résultat. Elle utilise la formule suivante :

    Total des taux de change ÷ Nombre de taux de change

- **Actuel** – Cette méthode est utilisée le plus souvent pour les comptes de bilan. Le taux de change utilisé correspond au taux avant ou à la date de l’état ou de la colonne dans l’outil États financiers.
- **Date de transaction** – Cette méthode est utilisée pour les comptes d’immobilisations. Le taux de change utilisé correspond au taux défini le jour de l’acquisition de l’immobilisation. Si un taux n’est pas entré pour cette date, le taux précédent entré au plus près de la date d’acquisition de l’immobilisation est utilisé.

### <a name="report-designer-options-for-currency-translation"></a>Options du concepteur d’états pour la conversion de devises
Dans l’outil États financiers, un état peut être affiché dans plusieurs devises de déclaration. Les champs suivants de la définition d’état prennent en charge cette fonctionnalité :

- Section **Informations de devise** dans la page **Définition d’état**. Cette section affiche la devise dans laquelle les valeurs sont affichées lors de la génération d’un état.
- Nouvelle case à cocher **Inclure toutes les devises de déclaration**. Lorsque cette case à cocher est activée, un état pour chaque devise de déclaration sera ajouté à la file d’attente des états après la génération de l’état qui utilise la devise fonctionnelle de la société. Si la case à cocher est désactivée, vous pouvez toujours sélectionner une devise de déclaration dans la visionneuse Web. Dans ce cas, la devise de déclaration ne sera traitée que lorsque vous la sélectionnerez.

Les options de la définition d’état vous permettent de convertir facilement un état dans toutes vos devises de déclaration. Par conséquent, vous pouvez éliminer les définitions d’état en double qui diffèrent uniquement dans les devises utilisées. Si un état doit afficher plusieurs devises côte à côte, vous pouvez continuer à utiliser le champ **Devise affichée** dans la page **Définition de colonne** pour convertir uniquement cette colonne de l’état dans une autre devise de déclaration.

### <a name="currency-translation-adjustment"></a>Ajustement de la conversion de devises
L’ajustement de la conversion de devises (CTA) est la différence entre les taux utilisés pour calculer les comptes de bilan et le taux utilisé pour les comptes de résultat. Cette différence entraînera un déséquilibre du bilan. Vous pouvez utiliser l’outil États financiers pour calculer le CTA de deux manières :

- Utilisez la page **Ajustements d’arrondi** dans la définition de ligne, comme indiqué dans l’illustration suivante.

    ![Ajustement de la conversion de devises – Ajustements d’arrondi.](./media/Currency-translation-adjustment-rounding-adjustments.png "Ajustement de la conversion de devises – Ajustements d’arrondi")

    Lorsque vous spécifiez la ligne qui doit afficher l’ajustement d’arrondi (CTA), la ligne du total des immobilisations, la ligne du total des passifs et des capitaux propres et le seuil approprié, l’outil États financiers calcule la différence et place le montant sur la ligne souhaitée. Une ligne nommée **Ajustement d’arrondi** sera créée et affichée lorsque vous effectuerez un zoom avant, comme indiqué dans l’illustration suivante.

    ![Zoom avant sur l’ajustement d’arrondi.](./media/rounding-adjustment-drill-down.png "Zoom avant sur l’ajustement d’arrondi")

- Placez tous les comptes dans une plage, depuis les immobilisations jusqu’aux dépenses. Comme indiqué dans l’illustration suivante, la différence correspondra au même montant que l’ajustement d’arrondi (CTA). Par conséquent, vous pouvez l’utiliser comme total pour vérifier que la page d’ajustement d’arrondi n’inclut pas des soldes de compte manquants.

    ![Vérification de l’écran Ajustement d’arrondi.](./media/rounding-adjustment-form-check.png "Vérification de l’écran Ajustement d’arrondi")

### <a name="balance-calculation-approach"></a>Approche de calcul du solde
Pour obtenir des montants correctement convertis lorsque des devises sont utilisées, l’outil États financiers utilise les méthodes de calcul suivantes pour les soldes :

- **Moyenne pondérée et moyenne** – Chaque période est calculée à sa moyenne pondérée, et est totalisée pour les colonnes telles que Trimestriel et Cumul à ce jour.
- **Historique** – Tout compte qui utilise la méthode de conversion historique renvoie toujours à la date de transaction. Si une date d’acquisition est associée à la transaction, elle est utilisée pour obtenir le taux de change. Chaque période est ensuite totalisée et enregistrée pour améliorer le temps de calcul.
- **Actuel** – Les colonnes calculées et de total, telles que les colonnes pour Trimestriel et Cumul à ce jour sont calculées au taux au comptant qui est déterminé dans la colonne ou dans l’état. Par exemple, la colonne **Trimestre 1** utilisera le taux du 31 mars si une année civile est utilisée.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour plus d’informations sur la consolidation et les conversions de devises, consultez la rubrique parent de cette rubrique [Vue d’ensemble des consolidations financières et conversion de devises](./financial-consolidations-currency-translation.md).

Pour plus d’informations sur la saisie des détails des consolidations en ligne, voir [Consolidations financières en ligne](./consolidate-online.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
