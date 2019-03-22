---
title: Définitions de colonne dans les états financiers
description: Cet article fournit des informations sur les définitions de colonne. Une définition de colonne est un composant de l’état, ou un bloc élémentaire, qui spécifie le contenu des colonnes d’un état. Comme les définitions de ligne, des définitions de colonne de base peuvent être utilisées dans plusieurs états.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 872e7c833416f0f7d9aa0c55aadf72aec65ddaab
ms.sourcegitcommit: f6fc90585632918d9357a384b27028f2aebe9b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "832146"
---
# <a name="column-definitions-in-financial-reports"></a>Définitions de colonne dans les états financiers

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les définitions de colonne. Une définition de colonne est un composant de l’état, ou un bloc élémentaire, qui spécifie le contenu des colonnes d’un état. Comme les définitions de ligne, des définitions de colonne de base peuvent être utilisées dans plusieurs états.

## <a name="create-and-modify-a-column-definition"></a>Créer et modifier une définition de colonne

Une définition de colonne peut contenir jusqu'à 255 colonnes.

### <a name="create-a-column-definition"></a>Créer une définition de colonne

1. Dans le générateur d'état, dans le volet de navigation, cliquez sur **Définitions de colonne**.
2. Dans le menu **Fichier**, cliquez sur **Nouveau**, puis cliquez sur **Définition de colonne**.
3. Ajoutez le contenu de la définition de colonne.

### <a name="open-a-column-definition"></a>Ouvrir une définition de colonne

1. Dans le générateur d'état, dans le volet de navigation, cliquez sur **Définitions de colonne**.
2. Double-cliquez sur une définition de colonne pour l'ouvrir.

### <a name="add-a-column-to-a-column-definition"></a>Ajout d'une colonne à une définition de colonne

1. Dans le générateur d'état, cliquez sur **Définitions de colonne**, puis ouvrez ensuite la définition de colonne à modifier.
2. Sélectionnez la colonne dans laquelle une colonne doit être insérée.
3. Dans le menu **Édition**, cliquez sur **Insérer une colonne**. La nouvelle colonne s'affiche à gauche de la colonne que vous avez sélectionnée.

### <a name="delete-a-column-from-a-column-definition"></a>Suppression d'une colonne dans une définition de colonne

1. Dans le Concepteur de rapports, cliquez sur **Définitions de colonne** puis ouvrez la définition de colonne à modifier.
2. Sélectionnez la colonne à supprimer.
3. Dans le menu **Edition**, cliquez sur **Supprimer la colonne**.

## <a name="contents-of-a-column-definition"></a>Contenu d'une définition de colonne
Une définition de colonne comprend les informations suivantes :

- une colonne des descriptions des définitions de ligne ;
- les colonnes de montants qui affichent les données issues des données financières ou des calculs basés sur d'autres données dans la définition de colonne ;
- des colonnes de mise en forme ;
- des colonnes d'attribut.

Ces informations s'affichent dans les zones suivantes de la définition de colonne :

- la zone d'en-tête de la définition de colonne contient le texte et la mise en forme de titre qui apparaissent dans l'état. Un en-tête peut s'appliquer à une seule colonne de données, s'étendre sur plusieurs colonnes ou s'appliquer à certaines colonnes sous des conditions précises. La définition de colonne peut inclure autant de lignes d'en-tête de colonne que nécessaire.

    > [!NOTE]
    > Les en-têtes de colonne s'appliquent à chaque colonne de données du rapport. Les en-têtes de rapport s'appliquent à l'ensemble du rapport. Vous définissez les en-têtes d'état sous l'onglet **En-têtes et pieds de page** de la définition d'état.

- Les lignes de détail de colonne sont les lignes sous les lignes d'en-tête dans la définition de colonne. Les lignes de détail de colonne définissent les informations incluses dans l'état. Le tableau suivant répertorie et décrit les lignes de détail de colonne.

    | Nom de la ligne de détail de colonne                                                | Description                                                                                            |
    |-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
    | Type de colonne                                                           | (Obligatoire) Spécifie le type des données dans la colonne.                                                     |
    | Code registre/Catégorie d'attribut                                          | Spécifie les informations des données financières pour les colonnes des types **FD** et **ATTR**.                       |
    | Exercice Période Périodes couvertes                                    | Spécifie les informations des données financières pour les colonnes des types **FD**.                                     |
    | Formule                                                               | Spécifie une formule de calcul pour les colonnes du type **CALC**.                                        |
    | Largeur de colonne Espaces supplémentaires avant la colonne Remplacement de format Contrôle d'impression | Spécifie les options spéciales de format.                                                                        |
    | Restrictions de colonne                                                   | Permet de limiter les données.                                                                                         |
    | Unité de déclaration                                                        | Permet de restreindre la colonne de sorte qu'elle ne présente que les données de l'unité de déclaration spécifiée.                      |
    | Afficher la devise Filtre de devise                                      | Devise de format.                                                                                       |
    | Filtre de dimension                                                      | Spécifie un filtre pour limiter les données à certaines unités de déclaration de données financières.                           |
    | Filtre d'attribut                                                      | Spécifie un filtre pour restreindre les données financières.                                                       |
    | Date de début Date de fin                                                   | Restreint les données financières à des dates spécifiques.                                                         |
    | Justification                                                         | Alignement à gauche, centrage ou alignement à droite du texte de description spécifié dans la définition de ligne. |

## <a name="column-restrictions-in-a-column-definition"></a>Restrictions de colonne dans une définition de colonne
Vous pouvez utiliser des restrictions de colonne pour spécifier comment une définition de colonne utilise des données ou calcule les informations. Vous pouvez également restreindre une colonne de rapport à une unité spécifique ou à certaines dates.

> [!NOTE]
> Un code **Restrictions de colonne** remplace les paramètres conflictuels affectés dans la définition de ligne.

### <a name="column-restrictions-cell"></a>Cellule de restrictions de colonne

La cellule **Restrictions de colonne** peut inclure des codes qui limitent ou suppriment des informations, telles que la mise en forme de ligne, les détails et les montants, pour cette colonne.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Ajoute une restriction de colonne dans une définition de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Restrictions de colonne** de la colonne à limiter.
3. Dans la boîte de dialogue **Restrictions de colonne**, sélectionnez un ou plusieurs codes dans la liste, puis cliquez sur **OK**.

### <a name="column-restriction-codes"></a>Codes restriction de colonne

Le tableau suivant décrit les codes de restriction de colonne.

| Code de restriction de colonne | Description |
|-------------------------|-------------|
| SU                      | Supprime le trait de soulignement dans une colonne dans laquelle une commande de trait de soulignement (**---**) ou une commande de double trait de soulignement (**===**) est activée dans la définition de ligne. Par exemple, vous pouvez ne pas souhaiter souligner les montants qui sont produits par un calcul de pourcentage. |
| ST                      | Supprime les totaux, de sorte que seuls les détails sont affichés dans la colonne (par exemple, une colonne de statistiques). |
| SD                      | Supprime les détails, de sorte que seules les lignes **TOT** et **CAL** (issues de la définition de ligne) sont affichées dans la colonne. |
| SL                      | Restreint les montants dans la colonne **FD** aux montants de débit. |
| CR                      | Restreint les montants dans la colonne **FD** aux montants de crédit. |
| ADJ                     | Restreint les montants dans la colonne aux montants d'ajustement de période, si ces montants sont disponibles. |
| XAD                     | Restreint les montants dans la colonne, de sorte que les montants d'ajustement de période sont exclus. |
| TP                      | Restreint les montants dans la colonne, de sorte que seules les transactions validées sont incluses, si ces transactions sont disponibles. |
| UPT                     | Restreint les montants dans la colonne, de sorte que seules les transactions non validées sont incluses, si ces transactions sont disponibles.<blockquote>[!NOTE] Les fournisseurs de données ne prennent pas tous en charge les transactions non validées. Pour plus d'informations, voir le <a href='http://go.microsoft.com/fwlink/?LinkID=162565'>guide d'intégration de données</a> pour votre système ERP Microsoft Dynamics.</blockquote> |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Restreindre une colonne à une unité de déclaration

1. Dans le Concepteur de rapports, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Unité de déclaration** de la colonne à limiter.
3. Dans la boîte de dialogue **Sélectionner une unité de déclaration**, dans la liste **Arborescence de génération d'états**, sélectionnez une arborescence.
4. Développez ou réduisez la liste des unités, sélectionnez une unité de déclaration, puis cliquez sur **OK**.

## <a name="format-column-headers"></a>Mettre en forme les en-têtes de colonne
Vous pouvez ajouter, modifier et supprimer les en-têtes affichés en haut des colonnes de l'état. Vous pouvez également configurer des en-têtes de colonne à étendue conditionnelle, selon le champ **Période** des définitions de colonne et du champ **Période de base** des définitions d'état. La fonctionnalité de période de base vous fait gagner du temps lorsque vous créez des états de prévision à court terme.

### <a name="create-and-manage-column-headers"></a>Créer et de gérer des en-têtes de colonne

Vous pouvez utiliser la boîte de dialogue **En-tête de colonne** pour ajouter, modifier et supprimer les en-têtes affichés en haut des colonnes de l'état. Le tableau suivant décrit les champs de la boîte de dialogue **En-têtes de colonne**.

| Champ                 | Description |
|-----------------------|-------------|
| Texte d'en-tête de colonne    | Ce texte apparaît dans l'en-tête de colonne. Vous pouvez taper le texte directement dans ce champ, ou cliquer sur **Insertion texte auto** pour sélectionner une option qui met à jour l'en-tête de colonne à chaque fois que l'état est généré. Pour inclure plusieurs codes d'insertion automatique, cliquez sur **Insertion texte auto** de nouveau, puis cliquez sur un autre code dans la liste. |
| Options de mise en forme        | Applique la mise en forme à un en-tête de colonne, comme un cadre ou un soulignement. |
| Étendre à partir de Étendre jusqu'à | Définissez la ou les colonnes auxquelles le texte d'en-tête s'applique. |
| Justification         | Spécifiez comment le texte d'en-tête de colonne doit être aligné pour la colonne ou la plage de colonnes spécifiée dans les champs **Étendre à partir de** et **Étendre jusqu'à**. |

### <a name="create-a-column-header"></a>Créer un en-tête de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez dans une cellule d'en-tête.
3. Dans la boîte de dialogue **En-tête de colonne**, entrez le texte d'en-tête de colonne. Sinon, cliquez sur **Insertion texte auto**, puis sélectionnez une option.
4. Dans le champ **Options de mise en forme**, sélectionnez un format pour l'en-tête.
5. Dans le champ **Étendre à partir de**, entrez la lettre de la colonne où l'en-tête de colonne doit recommencer. Dans le champ **Étendre jusqu'à**, entrez la lettre de la colonne où l'en-tête de colonne doit terminer.
6. Sous **Justification**, sélectionnez si le texte d'en-tête de colonne doit être justifié à gauche, centré ou justifié à droite.
7. Cliquez sur **OK**.

### <a name="add-a-column-header-row"></a>Ajoutez une ligne d'en-tête de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Sélectionnez une cellule dans la ligne d'en-tête.
3. Dans le menu **Édition**, cliquez sur **Insérer une ligne**. La nouvelle ligne est insérée au-dessus de la ligne sélectionnée à l'étape 2.

> [!NOTE]
> Si vous avez quatre lignes d'en-tête ou plus dans un rapport, les en-têtes se chevauchent lorsque le rapport est exporté vers une feuille de calcul Excel. Permet d'afficher tous les en-têtes de l'état, augmentez la marge supérieure dans la définition d'état.

### <a name="delete-a-column-header-row"></a>Supprimer une ligne d'en-tête de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans la ligne d'en-tête, sélectionnez la cellule à supprimer.
3. Dans le menu **Édition**, cliquez sur **Supprimer une ligne**.

### <a name="create-an-automatically-generated-header"></a>Créer un en-tête généré automatiquement

Le générateur d'états peut générer automatiquement des en-têtes de colonne, selon des codes d'insertion automatique. Les codes d'insertion automatique sont des variables mises à jour à chaque fois qu'un état est généré. Tout en-tête de colonne peut inclure de ces codes pour spécifier les informations d'état susceptibles de varier, comme les dates ou les numéros de période. Par conséquent, vous pouvez utiliser une définition de colonne pour plusieurs définitions d'état, de périodes et d'arborescences de génération d'états. Comme les codes d'insertion automatique se fondent sur les informations de calendrier des lignes détaillées de la définition de colonne, ils sont pris en charge uniquement pour les colonnes **CALC** et **FD**. La manière dont le code d'insertion automatique s'affiche dans la cellule d'en-tête de colonne affecte la manière dont ces informations sont affichées dans l'état. Dans la boîte de dialogue **En-tête de colonne**, les codes d'insertion automatique apparaissent en combinaison de majuscules et minuscules. Par conséquent, le texte apparaît dans la même combinaison dans l'état. Par exemple, dans une année civile standard, **@CalMonthLong** résout le mois **7** sur **Juillet**. Si le mois doit apparaître en majuscules (par exemple **JUILLET**), tapez le code d'insertion automatique en majuscules dans le champ **Texte de l'en-tête de colonne**. Par exemple, entrez **@CALMONTHLONG**. Vous pouvez mélanger codes et textes. Par exemple, vous entrez le texte d'en-tête suivant : **Période @ FiscalPeriod-@FiscalYear du @StartDate au @EndDate**. Le titre d'état généré ressemble au texte suivant : **Période 1-02 du 01/01/02 au 01/31/02**.

> [!NOTE]
> Le format d'une partie du texte, comme la date au format long, dépend des paramètres régionaux du serveur Finance and Operations. Pour modifier ces paramètres, cliquez sur le bouton **Début**, cliquez sur **Panneau de configuration**, puis cliquez sur **Région et langue**. Le tableau suivant répertorie les options disponibles d'insertion automatique pour les en-têtes de colonnes.


| Option et code d'insertion automatique                | Description |
|-----------------------------------------|-------------|
| Nom du mois (@CalMonthLong)              | Imprime le nom du mois actuel dans l'en-tête de colonne. Si vous décidez d'arrondir les montants dans l'état aux milliers, millions ou milliards, ou si vous définissez la largeur de colonne de l'état à moins de neuf caractères, le nom du mois est abrégé à ses trois premiers caractères. |
| Nom du mois abrégé (@CalMonthShort) | Imprime le nom du mois abrégé de la période fiscale sélectionnée. |
| Nombre de périodes (@FiscalPeriod)           | Imprime le formulaire numérique de la période fiscale identifiée pour cette colonne. Si la colonne s'étend sur plusieurs périodes, la dernière période de la sélection est imprimée. |
| Description de la période (@FiscalPeriodName)  | Imprime la description de la période fiscale identifiée dans les données financières. |
| Exercice (@FiscalYear)               | Imprime l'exercice pour la colonne au format numérique. |
| Année civile (@CalYear)                | Imprime l'année calendaire pour la colonne au format numérique. |
| Date de début (@StartDate)                 | Imprime la date de début pour la colonne. |
| Date de fin (@EndDate)                     | Imprime la date de fin pour la colonne. |
| Nom d'unité de l'arborescence (@UnitName)         | Si vous limitez une colonne à une unité spécifique de l'arborescence de génération d'états, imprimez le nom de l'unité dans l'en-tête de colonne. |
| Description de l'unité (@UnitDesc)            | Si vous limitez une colonne à une unité spécifique de l'arborescence de génération d'états, imprimez la description de l'unité dans l'en-tête de colonne. |
| Code registre (@BookCode)                   | Imprime le code registre spécifié dans la colonne. |
| Ligne vide (@Blank)                     | Insère une ligne vide l'en-tête de colonne. |

### <a name="create-a-conditional-spanning-header"></a>Créer un en-tête à étendue conditionnelle

Les en-têtes à étendue conditionnelle peuvent couvrir plusieurs colonnes basées sur des données de périodes spécifiques. Par exemple, si vous avez un état de budget pour l'exercice et souhaitez afficher les budgets réels des mois écoulés avec les budgets projetés des mois à venir, vous pouvez utiliser un en-tête à étendue conditionnelle pour mettre automatiquement l'en-tête d'état à jour. Tenez compte des éléments suivants lorsque vous créez un en-tête de fractionnement conditionnel :

- toute condition d'arrêt (champ **Étendre jusqu'à**) mis en correspondance avant une condition de début (champ **Étendre à partir de**) est ignoré. Par exemple, la colonne B a la condition d'étendue définie comme BASE+1 jusqu'à BASE, BASE est dans la colonne C, et BASE+1 est dans la colonne D. Dans ce cas, la condition d'arrêt dans la colonne C est ignorée, et l'impression de l'en-tête débute à la colonne D.
- Si vous spécifiez des en-têtes de colonne qui se chevauchent, ils se chevaucheront lors de l'impression de l'état. L'état est généré, mais l'avertissement suivant s'affiche dans le champ **État de la file d'attente de rapports** : « Les en-têtes de colonne utilisant Base recoupent d'autres en-têtes de colonne et peuvent entraîner une superposition du texte ». Par exemple, la définition d'en-tête dans la colonne B est B à BASE+1, et la définition d'en-tête dans la colonne D est BASE+1 à F. Dans ce cas, les en-têtes sont imprimés l'un au-dessus de l'autre et sont illisibles. À chaque fois que BASE est utilisé dans une définition **Étendre à partir de/Étendre jusqu'à**, assurez-vous que l'état est généré pour voir si les en-têtes se chevauchent.
- Si vous spécifiez BASE dans la définition d'étendue dans une colonne sans impression (**NP**, No Print), elle est ignoré, indépendamment de ce qui est défini dans la définition de colonne. Pour l'essentiel, ce scénario est le même que celui de ne pas créer de définition d'en-tête de colonne.
- Pour l'impression conditionnelle de colonnes (**P&lt;B**, **P&gt;=B**), les en-têtes à étendue conditionnelle se comportent comme n'importe quelle définition d'en-tête de colonne normale. Par exemple, si la condition est fausse, toute validation consécutive d'une colonne de la condition d'étendue a pour effet de lancer l'impression de l'en-tête.

#### <a name="create-a-conditional-spanning-header"></a>Créer un en-tête à étendue conditionnelle

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez dans une cellule d'en-tête.
3. Dans la boîte de dialogue **En-tête de colonne**, entrez le texte d'en-tête de colonne. Sinon, cliquez sur **Insertion texte auto**, puis sélectionnez une option.
4. Dans le champ **Options de mise en forme**, sélectionnez un style de mise en forme pour l'en-tête.
5. Spécifie une période par rapport à la période de base spécifiée lorsque l'état est généré. Dans les champs **Étendre à partir de** et **Étendre jusqu'à**, entrez une des valeurs suivantes : **BASE**, **BASE-X** ou **BASE+X**, dans lequel X est le nombre de périodes à partir de la période de base. Par exemple, si vous entrez **BASE** dans le champ **Étendre à partir de**, l'en-tête de colonne à étendue conditionnelle commence dans l'en-tête de colonne où la valeur de la **Période de base** de la définition d'état est égale à la valeur de **Période** de la définition de colonne. Elle se termine dans la colonne indiquée dans le champ **Étendre jusqu'à**. Par conséquent, si l'étendue va de BASE à M, et que la valeur de la **Période de base** de la définition d'état est **4**, l'en-tête commence dans la colonne où la période est définie sur **4** et prend fin à la colonne M. Les en-têtes commencent et se terminent aux colonnes imprimées uniquement.
6. Sous **Justification**, sélectionnez si le texte d'en-tête de colonne doit être justifié à gauche, centré ou justifié à droite.
7. Cliquez sur **OK**.

#### <a name="example-of-a-conditional-spanning-header"></a>Exemple d'en-tête à étendue conditionnelle

Phyllis crée un état pour une prévision dynamique de six mois. Elle veut que le mot « Réel » soit imprimé sur les colonnes contenant des données réelles, et le mot « Budget » sur les colonnes qui contiennent les prévisions du budget. Chaque mois que l'état est exécuté, il contient une colonne « Réel » de plus et une colonne « Budget » de moins. Bien que Phyllis puisse modifier la définition de colonne manuellement à chaque fois que l'état est généré pour ajuster les en-têtes, pour s'épargner du temps et des efforts, elle décide de créer des en-têtes à étendue conditionnelle qui créeront automatiquement les en-têtes sur les colonnes appropriées chaque exécution de l'état. Phyllis ouvre le générateur d'état, clique sur **Définition de colonne** dans le volet de navigation, et ouvre la définition de colonne de l'état. Elle entre alors les informations suivantes : la période de base dans la définition d'état est 4.


|                     |  A   | B             | C             | D             | E             | Ve             | V             | A             | I             | J             | k             | L             | F             |
|---------------------|------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| En-tête 1            |      | Réel        | Budget        |               |               |               |               |               |               |               |               |               |               |
| En-tête 2            |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| En-tête 3            |      |               |               |               |               |               |               |               |               |               |               |               |               |
| Type de colonne         | DESC | DF            | DF            | DF            | DF            | DF            | DF            | DF            | DF            | DF            | DF            | FD            | FD            |
| Code registre/Attribut |      | RÉEL        | BUDGET2012    | RÉEL        | BUDGET2012    | RÉEL        | BUDGET2012    | RÉEL        | BUDGET2012    | RÉEL        | BUDGET2012    | RÉEL        | BUDGET2012    |
| Année fiscale         |      | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          |
| Période               |      | 1             | 1             | 2             | 2             | 3             | 3             | 4             | 4             | 5             | 5             | 6             | 6             |
| Périodes couvertes     |      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      |
| Largeur de colonne        | 30   | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            |
| Contrôle d'impression       |      | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        |

Phyllis double-clique sur une cellule d'en-tête de colonne pour ouvrir la boîte de dialogue **En-tête de colonne**,où elle entre les informations suivantes.

| Champ              | Valeur                 |
|--------------------|-----------------------|
| Texte d'en-tête de colonne | Réel                |
| Insertion texte auto    | Aucune sélection n'est effectuée. |
| Options de mise en forme     | Zone                   |
| Justification      | Aucune sélection n'est effectuée. |
| Étendre à partir de        | B                     |
| Étendre jusqu'à          | BASE                  |
| En-tête de budget      | BASE+1 jusqu'à la colonne de fin  |

Une fois qu'elle a terminé d'entrer les informations, Phyllis clique sur **OK**. Elle double-clique ensuite sur la cellule d'en-tête de la colonne C pour ouvrir la boîte de dialogue **En-tête de colonne**,où elle entre les informations suivantes.

| Champ              | Valeur                 |
|--------------------|-----------------------|
| Texte d'en-tête de colonne | Budget                |
| Insertion texte auto    | Aucune sélection n'est effectuée. |
| Options de mise en forme     | Zone                   |
| Justification      | Aucune sélection n'est effectuée. |
| Étendre à partir de        | C                     |
| Étendre jusqu'à          | BASE+2                |

À présent, à chaque fois que cet état est généré, le mot « Réel » est imprimé sur les colonnes contenant des données réelles, et le mot « Budget » est imprimé sur les colonnes qui contiennent les prévisions du budget. En outre, le nombre de colonnes sera ajusté chaque mois.

## <a name="apply-column-justification"></a>Appliquer la justification de colonne
La cellule **Justification** est utilisée pour appliquer la mise en forme de justification à une colonne de description dans un état. Cette option n'affecte que les descriptions de colonne, pas les valeurs actuelles.

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Justification**.
3. Sélectionnez l'une des valeurs suivantes dans la liste :

    - **Aucun** – Aucune justification n'est appliquée.
    - **Gauche** – Alignement à gauche des descriptions de colonne.
    - **Centre** – Centrage des descriptions de colonne.
    - **Droite** – Alignement à droite des descriptions de colonne.

## <a name="add-special-formatting-options"></a>Ajouter des options de mise en forme spéciales
Dans la définition de colonne, les lignes détaillées de mise en forme de colonne appliquent une mise en forme spéciale aux colonnes sélectionnées. Bien que certaines des options de **Contrôle d'impression** et de **Restrictions de colonne** soient spécifiques aux colonnes **FD**, la plupart des options s'appliquent à tous les types de colonne. Cette mise en forme spécifiée dans la définition de colonne remplace la mise en forme spécifiée dans la définition d'état. Toutefois, cette mise en forme spécifiée dans la définition de ligne remplace la mise en forme spécifiée dans la définition de colonne. Les lignes suivantes sont considérées comme des lignes de mise en forme :

- Largeur de colonne
- Espaces supplémentaires avant la colonne
- Remplacement de format/devise
- Contrôle d'impression

### <a name="changing-the-column-width"></a>Modifier la largeur de colonne

La cellule **Largeur de colonne** spécifie le nombre de caractères à utiliser pour la largeur de cette colonne dans l'état imprimé. La largeur de colonne est importante pour les colonnes qui contiennent des montants (les colonnes du type **CALC**, **WKS** ou **FD** ), des descriptions (les colonnes du type **DESC** ), ou du remplissage (colonnes du type **FILL**). Par défaut, l'option **Ajustement automatique** est sélectionnée, de sorte que la largeur de chaque colonne est automatiquement ajustée pour s'adapter le contenu.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Spécifier la largeur d'une colonne dans un état

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans la cellule **Largeur de colonne**, entrez le nombre d'espaces pour la largeur de la colonne. La largeur maximale de n'importe quelle colonne est 255 caractères (ce nombre inclut les centimes, les virgules et les parenthèses). Sinon, pour autoriser le générateur d'états à sélectionner la largeur appropriée pour la colonne, selon le contenu des cellules, double-cliquez sur la cellule **Largeur de colonne**, puis cliquez sur **AutoFit**.

### <a name="add-space-between-columns"></a>Ajouter de l'espace entre les colonnes

La cellule **Espaces supplémentaires avant la colonne** spécifie la largeur du séparateur entre une colonne et les colonnes adjacentes dans la définition de colonne. Le paramètre **Espaces supplémentaires avant la colonne** affecte toutes les lignes de détail de colonne pour la colonne, mais pas les lignes d'en-tête de colonne. Utilisez cette option pour séparer des groupes de colonnes ou ajouter quelques espaces avant la description, de sorte que la colonne de description soit mise en retrait par rapport aux titres alignés à gauche dans l'état. Le nombre par défaut d'espaces entre chaque colonne est deux. Vous pouvez modifier ce paramètre sous l'onglet **Paramètres** dans la définition d'état.

#### <a name="specify-the-space-between-columns"></a>Spécifiez l'espace entre les colonnes

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans la cellule **Espaces supplémentaires avant la colonne**, entrez le nombre d'espaces à insérer entre les colonnes.

### <a name="specify-a-format-currency-override"></a>Spécifier un remplacement de devise/format

La cellule **Remplacement de format/devise** spécifie la mise en forme de la décimale, de la devise et des montants en pourcentage dans la colonne. Cette mise en forme remplace toute mise en forme spécifiée dans la définition d'état ou les réglages par défaut du système.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Application d'une substitution de format/devise à une colonne de rapport

1. Dans le Concepteur de rapports, ouvrez la définition de colonne à modifier.
2. Double-cliquez dans une cellule **Substitution de format/devise** d'une colonne de montant.
3. Dans la boîte de dialogue **Remplacement de format**, sélectionnez les options de mise en forme.

### <a name="add-a-print-control-code"></a>Ajouter un code de contrôle d'impression

La cellule **Contrôle d'impression** peut contenir des codes qui règlent les caractéristiques d'affichage ou d'impression d'une colonne. Il existe deux types de codes de contrôle d'impression : les codes de contrôle d'impression normaux et les codes de contrôle d'impression conditionnels.

#### <a name="regular-print-control-codes"></a>Codes de contrôle d'impression normaux

| Code de contrôle d'impression | Traduction                                     | Description |
|--------------------|-------------------------------------------------|-------------|
| NP                 | Non imprimable                                     | Exclut les montants de cette colonne de l'état imprimé et des calculs. Pour inclure une colonne non imprimable dans un calcul, consultez la colonne directement dans la formule de calcul. Par exemple, la colonne C non imprimable est incluse dans le calcul suivant : **B+C+D**. Cependant, la colonne C non imprimable n'est pas incluse dans le calcul suivant : **B:D**. |
| XCR                | Modifie le signe si le solde typique de la ligne est un crédit | Crée un budget ou un état comparatif où tout écart défavorable (tel qu'un déficit de produit ou un dépassement de dépense) est toujours négatif. Appliquez ce code à une colonne **CALC** pour inverser le signe du montant de la colonne si le solde typique d'une ligne donnée est un crédit (comme identifié par un **C** dans la colonne **Solde normal** de la définition de ligne).<blockquote>[!NOTE] Pour les lignes <strong>TOT</strong> et </strong>CAL</strong> qui comportent généralement un solde, veillez à entrer un <strong>C</strong> dans la colonne <strong>Solde normal</strong> dans la définition de ligne.</blockquote> |
| X0                 | Supprime la colonne si elle ne contient que des zéros ou des espaces          | Permet d'exclure une colonne **FD** de l'état si toutes les cellules dans cette colonne sont vides ou contiennent des zéros. |
| SR                 | Permet de supprimer l'arrondi                               | Permet d'empêcher les montants de cette colonne d'être arrondis. |
| XR                 | Permet de supprimer le cumul                                 | Permet de supprimer le cumul Si l'état utilise une arborescence de génération d'états, les montants de cette colonne ne sont pas cumulés dans les nœuds parent suivants. |
| RP                 | Répéter la colonne dans chaque page                      | Répète une colonne spécifiée dans chaque page d'un état. Par exemple, vous pouvez utiliser le code de contrôle d'impression **RP** pour inclure une colonne du type **ROW** qui ajoute des codes de ligne dans chaque page. |
| WT                 |  Ajuste le texte                                      |  Si le texte d'une colonne est trop long pour l'espace, ajuste le texte pour le maintenir intégralement dans la colonne. |

#### <a name="conditional-print-control-codes"></a>Codes de contrôle d'impression conditionnels

| Code de contrôle d'impression conditionnel | description ;                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (aucune)                         | Efface la sélection d'impression conditionnelle.                                                  |
| P&lt;B                         | Affiche une colonne spécifiée uniquement si la période est inférieure à la période de base.             |
| P&gt;B                         | Affiche une colonne spécifiée uniquement si la période est supérieure à la période de base.             |
| P=B                            | Affiche une colonne spécifiée uniquement si la période est égale à la période de base.              |
| P&lt;=B                        | Affiche une colonne spécifiée uniquement si la période est inférieure ou égale à la période de base. |
| P&gt;=B                        | Affiche une colonne spécifiée uniquement si la période est supérieure ou égale à la période de base. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Ajouter des codes de contrôle d'impression à une colonne d'état

1. Dans le Concepteur de rapports, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Contrôle d'impression**.
3. Dans la boîte de dialogue **Contrôle d'impression**, sélectionnez un code dans la liste **Sélectionner des options de contrôle d'impression**. Pour sélectionner plusieurs codes, maintenez la touche CTRL enfoncée tout en sélectionnant les codes souhaités.
4. Sélectionnez une option dans le champ **Options d'impression conditionnelle**. Par défaut, **(aucun)** est sélectionné. Vous ne pouvez sélectionner qu'un code d'impression conditionnelle à la fois.
5. Cliquez sur **OK**.

> [!TIP]
> Vous pouvez également entrer des codes de contrôle d'impression directement dans la cellule **Contrôle d'impression**. Utilisez des virgules pour séparer plusieurs codes de contrôle d'impression.

## <a name="column-types"></a>Types de colonnes
Le type d'informations que chaque colonne comporte dans un état est spécifié par la valeur indiquée dans la ligne **Type de colonne** dans la définition de colonne. Chaque définition de colonne doit contenir au moins une colonne de description (**DESC**) et une colonne de montant (**DF**, **FLC** ou **CALC**).

> [!NOTE]
> Les codes Type de colonne ne s'appliquent pas à tous les systèmes de gestion comptable. Si vous sélectionnez un type qui n'est pas valide pour votre système comptable, cette colonne est vide dans l'état.

### <a name="specify-a-column-type"></a>Spécifier un type de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans la colonne appropriée, double-cliquez sur une cellule dans la ligne **Type de colonne**.
3. Dans la liste, sélectionnez un type de colonne. Le tableau suivant décrit les différents types de colonne :

    <table>
    <thead>
    <tr>
    <th>Code de type de colonne</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>DF</td>
    <td>Permet d'afficher les données financières lorsque vous utilisez une colonne <strong>Lier aux dimensions financières</strong> dans la définition de ligne. Lorsque vous sélectionnez le type de la colonne <strong>DF</strong>, les paramètres par défaut sont automatiquement spécifiés pour les lignes suivantes : <ul>
    <li><strong>Code registre / Catégorie d'attribut :</strong> RÉEL</li>
    <li><strong>Code registre / Catégorie d'attribut :</strong> RÉEL</li>
    <li><strong>Année fiscale :</strong> BASE</li>
    <li><strong>Période :</strong> BASE</li>
    <li><strong>Périodes couvertes :</strong> – PERIODIC</li>
    <li><strong>Largeur de colonne :</strong> 14</li>
    </ul>
Vous pouvez modifier ces paramètres par défaut.</td>
    </tr>
    <tr>
    <td>CALC</td>
    <td>Affiche le résultat d'un calcul simple ou complexe spécifié dans la cellule <strong>Formule</strong>. Pour plus d'informations, consultez <a href="advanced-formatting-options-financial-reporting.md">Options de mise en forme avancées dans les états financiers</a>.</td>
    </tr>
    <tr>
    <td>DESC</td>
    <td>Affiche la description de ligne de la définition de ligne. Bien que la colonne de description soit souvent la première colonne de l'état, elle peut se trouver à n'importe quelle position.</td>
    </tr>
    <tr>
    <td>LIGNE</td>
    <td>Affiche différents codes de ligne pour les lignes financières de la colonne <strong>Code de ligne</strong> dans la définition de ligne. Pour plus d'informations, consultez <a href="row-definitions-financial-reporting.md">Définitions de ligne dans les états financiers</a>.</td>
    </tr>
    <tr>
    <td>ACCT (Codes compte)</td>
    <td>Affiche les valeurs des segments de données financières ou les valeurs de dimension qui s'appliquent à chaque ligne. Pour les rapports détaillés du compte et des transactions, le compte complet est imprimé (par exemple, <strong>110140-070-0101</strong>). Si des plages sont spécifiées dans la colonne <strong>Lien vers les dimensions financières</strong> d'une définition de ligne associée, la plage est placée entre crochets et traitée comme une valeur unique (par exemple, <strong>[110140:110700]-070-[0101:0200]</strong>). Pour les rapports financiers et les rapports de haut niveau qui peuvent être une combinaison de plusieurs comptes, le lien vers les données financières à partir de la définition de ligne (par exemple, <strong>1100:1200</strong>) est imprimé.</td>
    </tr>
    <tr>
    <td>FILL</td>
    <td>Remplit la cellule avec un caractère entouré de guillemets simples. Si vous n'entrez pas de caractère, la colonne est vide. Par exemple, pour remplir une colonne avec des points de suspension (...), entrez <strong>FILL</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr>
    <td>PAGE</td>
    <td>Insérer un saut de page vertical dans l'état. Les colonnes qui se trouvent à droite de la colonne <strong>PAGE</strong> s'affichent sur une autre page.</td>
    </tr>
    <tr>
    <td>ATTR</td>
    <td>Si votre système comptable prend en charge les attributs, affiche un attribut de compte ou de transaction dans la colonne. Un attribut, qui doit s'appliquer à un seul compte complet, extrait les informations sous-jacentes de compte ou de transaction à partir des données financières. Les attributs de niveau Compte affichent des données à partir du compte et les attributs de niveau Transaction affichent les données générées lors de la validation de la transaction. Lorsque vous sélectionnez <strong>ATTR</strong> comme type de colonne, spécifiez la catégorie d'attribut dans la ligne de détails <strong>Code registre/Catégorie d'attribut</strong> de la définition de colonne.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Colonne Dimensions financières

Les définitions de ligne **Définition de colonne** suivantes s'appliquent aux colonnes dont le type est **FD** (montants des dimensions financières).

#### <a name="book-codeattribute-category-cell"></a>Cellule Code registre/Catégorie d'attribut

La cellule **Code registre/Catégorie d'attribut**  identifie le code registre des données dans la colonne **FD**. Une définition de colonne peut inclure plusieurs colonnes de réel, de budget et de statistiques. Une définition de colonne peut également afficher différentes périodes, comme la période en cours ou l'année à ce jour, et différents montants. La liste des codes registre reflète les options de réel, de budget, et de statistiques (non financières) qui ont été établies dans vos données financières.

#### <a name="fiscal-year-cell"></a>Cellule Exercice

La cellule **Exercice** identifie l'exercice que la colonne doit inclure. L'année peut être relative à l'année de base spécifiée lorsque l'état est généré. Les options suivantes sont disponibles :

| Option  | Description                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Utilisez l'année de base spécifiée au moment de la génération de l'état.                                                                          |
| BASE+\# | Utilisez l'année qui est \# années après l'année de base. Par exemple, pour utiliser la troisième année après l'année de base, entrez **BASE+3**. |
| BASE-\# | Utilisez l'année qui est \# années avant l'année de base. Par exemple, pour utiliser l'année précédente, entrez **BASE-1**.                 |
| \#      | Entrez l'exercice en cours.                                                                                                |

#### <a name="period-cell"></a>Cellule Période

La cellule **Période** identifie la période fiscale que la colonne doit inclure. La période peut être relative à la période de base spécifiée lorsque l'état est généré. Les options suivantes sont disponibles :

| Option          | description ; |
|-----------------|-------------|
| BASE            | Utilisez la période de base. |
| BASE+\#         | Utilisez la période qui est \# périodes après la période de base. Par exemple, pour utiliser la troisième période après la période de base, entrez **BASE+3**. |
| BASE-\#         | Utilisez la période qui est \# périodes avant la période de base. Par exemple, pour utiliser la période précédente, entrez **BASE-1**. |
| BASE-\#:BASE    | Utilisez plusieurs périodes, depuis plusieurs périodes avant la période de base jusqu'à la période de base. Par exemple, pour utiliser les trois périodes précédentes et la période de base, entrez **BASE-3:BASE**. |
| BASE:BASE+\#    | Utilisez plusieurs périodes, depuis plusieurs périodes avant la période de base jusqu'à plusieurs périodes après la période de base. Par exemple, pour utiliser la période précédente et les deux périodes suivantes, entrez **BASE:BASE+2**. |
| BASE-\#:BASE+\# | Utilisez plusieurs périodes, depuis plusieurs périodes avant la période de base jusqu'à plusieurs périodes après la période de base. Par exemple, pour utiliser les trois périodes précédentes, la période de base et les deux périodes suivantes, entrez **BASE-3:BASE+2**. |
| 1:BASE          | Utilisez plusieurs périodes, depuis la première période jusqu'à la période de base. |
| \#              | Utilisez toujours un nombre spécifique de périodes. Il n'est pas recommandé d'utiliser cette option, car elle réduit la flexibilité de la définition de colonne. |
| \#                                       : \#           | Utilisez toujours une plage de périodes spécifique. Il n'est pas recommandé d'utiliser cette option, car elle réduit la flexibilité de la définition de colonne. |

Vous pouvez dépasser les limites de l'exercice dans toutes les spécifications de période, et vous pouvez combiner des années dans une plage de périodes. Par exemple, vous spécifiez des périodes comme **BASE-5** (pour représenter les six dernières périodes) et exécutez un état qui a une période de base 2. Dans ce cas, l'état présente les données des deux premières périodes de l'exercice spécifié et les quatre dernières périodes de l'exercice précédent.

### <a name="specify-the-periods-for-an-fd-column"></a>Spécification des périodes d'une colonne DF

1. Dans le Concepteur de rapports, ouvrez la définition de colonne à modifier.
2. Dans une colonne **FD**, double-cliquez sur la cellule dans la ligne **Période**, puis sélectionnez une option dans la liste.
3. Dans la barre de formule au-dessus du volet de navigation, ou dans la cellule **Période**, remplissez la formule. Remplacez tout symbole de chiffre (\#) par la valeur appropriée.

#### <a name="periods-covered-cell"></a>Cellule Périodes couvertes

La cellule **Périodes couvertes** identifie le montant que la colonne doit afficher. Ce montant est relatif à la valeur dans les cellules **Exercice** et **Période** de la colonne. Les options suivantes sont disponibles :

| Option      | Description                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PÉRIODIQUE    | Affiche la somme de l'activité pour la période en cours ou la plage de périodes. |
| PÉRIODIQUE/BB | Affiche le solde de début pour la période en cours ou la plage de périodes.   |
| ANNÉE EN COURS         | Affiche la somme de l'activité de l'année en cours.                               |
| Année en cours/BB      | Affiche le solde d'ouverture pour l'année.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Spécifier les périodes couvertes pour une colonne FD

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans une colonne **FD**, double-cliquez sur la cellule dans la ligne **Périodes couvertes**, puis sélectionnez une option dans la liste.

### <a name="attribute-filter-in-a-column-definition"></a>Attribuer un filtre dans une définition de colonne

Les attributs sont des valeurs de données financières qui définissent de manière plus approfondie un compte ou une transaction. Les attributs de compte possibles sont **Actif**, **Passif**, **Produit** et **Dépense**. Les attributs de transaction sont **Description de transaction** et **Date d'effet de la transaction**. La prise en charge des attributs peut différer entre les systèmes ERP Microsoft Dynamics. La cellule **Filtre d'attribut** restreint les données dans les colonnes **FD** aux valeurs spécifiques ou aux plages des catégories d'attribut. Bien que cette fonctionnalité puisse être utilisée avec une colonne **ATTR**, la colonne **ATTR** n'est pas nécessaire. Dans une colonne **FD** , il existe une limite aux comptes ou aux transactions que l'état inclura en fonction du filtre d'attributs.

> [!NOTE]
> Pour savoir quels attributs sont pris en charge par votre système ERP, voir le guide d'intégration de votre système.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Appliquer un filtre d'attributs pour une colonne FD d'un état

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Filtre d'attribut** d'une colonne **DF**.
3. Dans la boîte de dialogue **Filtre d'attribut**, double-cliquez sur une cellule dans la colonne **Attribut**, puis sélectionnez le type de filtre.
4. Pour limiter davantage les résultats, entrez une plage dans les colonnes **À partir de** et **Jusqu'à**. La cellule **À partir de** doit contenir une valeur.
5. Cliquez sur **OK**.

#### <a name="example-of-an-attribute-filter"></a>Exemple d'un filtre d'attribut

L'exemple suivant montre une partie de description de colonne ayant un attribut de compte dans la ligne **Code registre/Catégorie d'attribut**. Le filtre d'attribut pour cette colonne spécifie la plage des valeurs à inclure dans l'état.

|                              | A    | B                   |
|------------------------------|------|---------------------|
| Type de colonne                  | DESC | DF                  |
| Code registre/Catégorie d'attribut |      | RÉEL              |
| Année fiscale                  |      | BASE                |
| Période                       |      | 1:BASE              |
| Périodes couvertes              |      | PÉRIODIQUE            |
| ...                          |      |                     |
| Largeur de colonne                 | 30   |                     |
| ...                          |      |                     |
| Filtre d'attribut             |      | Référence=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Filtre de dimension dans une définition de colonne

Un filtre de dimension est utilisé pour limiter la colonne **FD** à des valeurs de dimension spécifiques. Le filtre peut inclure une seule dimension, une plage de dimensions ou un groupe de dimensions. Le filtre peut également inclure des ensembles de valeurs de dimension. Comme les valeurs de dimension peuvent varier, il n'est pas nécessaire qu'un système basé sur les \\dimensions financières\\dimensions corresponde à une longueur exacte. Le filtre est appliqué, indépendamment du fait que l'état inclut une arborescence de génération d'états. Vous pouvez utiliser un caractère générique (\* ou ?) à n'importe quelle position. Lorsque vous spécifiez plusieurs comptes, mettez une virgule entre les comptes, comme dans l'exemple suivant : +Compte=\[1200\], +Compte=\[1100\], Service=\[01?\] pour recevoir tous les services d'un compte spécifique, vous pouvez exclure la dimension de service du filtre de dimension. Par exemple, les deux filtres de dimension suivants sont traités de la même manière :

- +Compte=\[1100\],Département
- +Compte=\[1100\]

Vous pouvez également utiliser n'importe quelle combinaison de caractères alphanumériques pour la correspondance exacte, et vous pouvez définir des dimensions partielles. Par exemple, **Emplacement = \[10\*\]** inclut toutes les valeurs de dimension d'emplacement qui commencent par 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Appliquer un filtre de dimension à une colonne dans un état

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Filtre de dimension** pour une colonne **FD**.
3. Dans la boîte de dialogue **Dimensions**, entrez les filtres à appliquer.
4. Cliquez sur **OK**.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Mettre en forme un état à plusieurs devises dans une définition de colonne

Un état à plusieurs devises peut afficher des montants dans la devise comptable de la comptabilité, la déclaration comptable, la devise de transaction d'origine ou la devise de déclaration convertie. La devise comptable d'une société est définie dans les paramètres de comptabilité. Ne confondez pas ce paramètre avec les options régionales spécifiques du système d'exploitation, où vous pouvez configurer les symboles de devise par défaut utilisés dans les états. Les cellules relatives aux devises suivantes sont disponibles dans la définition de colonne :

- **Affichage de devise** – Permet de spécifier le type de devise (comptabilité, déclaration, transaction ou déclaration convertie) dans lequel les transactions sont affichées. La conversion en une fonctionnalité de devise de déclaration est parfois appelée conversion de devise. La conversion de devise désigne la capacité de déclarer les montants de la comptabilité dans une devise qui n'est pas forcément la devise fonctionnelle ou de déclaration de la société ou la devise dans laquelle la transaction a été saisie.
- **Filtre de devise** – Spécifie un filtre de devise. Seules les transactions qui sont entrées dans la devise sélectionnée sont affichées dans l'état.

> 
Pour déterminer la devise comptable d'une société, procédez comme suit.

1. Dans le Concepteur de rapports, dans le menu **Société**, cliquez sur **Sociétés**.
2. Dans la boîte de dialogue **Sociétés**, sélectionnez une société, puis cliquez sur **Afficher**.
3. Dans la boîte de dialogue **Afficher la société**, sous **Options régionales**, vous pouvez afficher la devise définie pour la société sélectionnée.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Spécifier la devise dans un état à plusieurs devises

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Double-cliquez sur la cellule **Affichage de devise** dans la colonne **FD** appropriée, puis sélectionnez l'option d'affichage des informations de devise : **Devise comptable**, **Déclaration de comptabilité**, la devise de conversion ou sélectionnez pour convertir en une autre devise de déclaration.
3. Double-cliquez sur la cellule **Filtre de devise** dans la colonne **FD** appropriée, puis sélectionnez le code devise approprié dans la liste. Seules les transactions qui sont entrées dans cette devise sont affichées dans l'état.


### <a name="example-for-currency-display-and-currency-filter-cells"></a>Exemple pour les cellules Afficher la devise et Filtre de devise

Phyllis a effectué les sélections de devise suivantes dans sa définition de colonne :

- **Filtre de devise :** Yen
- **Affichage de devise :** devise comptable de la comptabilité (dollars américains)

En raison du filtre de devise que Phyllis a sélectionné, l'état inclut seulement les transactions qui ont été entrées en Yens japonais (JPY). En raison de l'affichage de devise sélectionné, l'état affiche ces transactions dans la devise comptable, à savoir le dollar américain (USD).

#### <a name="currency-filter-and-currency-display-combinations"></a>Combinaisons de Filtre de devise de Afficher la devise

Le tableau suivant présente les résultats de l'état qui peuvent exister pour diverses combinaisons des options dans les cellules **Afficher la devise** et **Filtre de devise** en raison des sélections que Phyllis a effectuées. LA devise fonctionnelle est le dollar américain, USD.


| Cellule Afficher la devise                        | Cellule Filtre de devise | Résultat de l'état |
|----------------------------------------------|----------------------|---------------|
| Devise de la transaction                 | **YEN**              | **Y6 000** – Le résultat affiche uniquement les transactions qui ont été entrées en JPY. |
| Devise comptable de la comptabilité | **YEN**              |**$60** – Le résultat affiche uniquement les transactions qui ont été entrées en JPY et affiche ces transactions en USD.<blockquote>[!NOTE] Le taux de conversion est approximativement 100 JPY pour 1 USD.</blockquote> |
| Devise comptable de la comptabilité | Vide                | **2 310 USD** - Le résultat affiche toutes les données dans la devise comptable spécifiée en comptabilité.<blockquote>[!NOTE] Ce montant correspond à la somme de toutes les transactions dans la devise comptable.</blockquote> |
| Devise de la transaction                 | Vide                | **$2 250** – Le résultat affiche tous les montants dans la devise dans laquelle la transaction a été exécutée. Autrement dit, le total est ajouté aux montants de différentes devises. |

### <a name="calculation-column-in-a-column-definition"></a>Colonne de calcul dans une définition de colonne

Un type de colonne **CALC** dans une définition de colonne prend en charge des calculs complexes dans la cellule **Formule**, et peut inclure les opérateurs **+**, **-**, **\*** et **/**, ainsi que des instructions **IF/THEN/ELSE**. Une colonne de calcul peut également faire référence à toute autre colonne, même à des colonnes suivantes. En outre, une colonne de calcul peut inclure l'exercice et la période pour prendre en charge les en-têtes de colonne. La formule du calcul peut comporter jusqu'à 1 024 caractères. Pour exprimer le résultat du calcul en pourcentage, utilisez un remplacement de format spécial.

> [!NOTE]
> Les résultats des formules de calcul n'incluent pas les valeurs des plages de colonnes non imprimables. Par exemple, **A:D** imprime **0** (zéro), alors que **A+B+C** pour les valeurs non imprimables calcule la valeur.

#### <a name="operators-in-calculation-columns"></a>Opérateurs dans les colonnes de calcul

Pour ajouter, soustraire, multiplier ou diviser des colonnes, entrez les lettres des colonnes dans l'ordre du calcul, puis utilisez l'opérateur approprié pour séparer toutes les lettres de colonne. Le tableau suivant décrit les opérateurs que vous pouvez utiliser dans une colonne de calcul.

| Opérateur | Exemple de calcul | description ; |
|----------|---------------------|-------------|
| +        | A+C                 | Additionne le montant de la colonne A au montant de la colonne C. |
| :        | A:C A:C-D           | Additionne une plage de colonnes consécutives. Par exemple, la formule **A:C** additionne les sommes des colonnes A à c, et la formule **A:C-D** additionne les sommes des colonnes A à c, puis soustrait le montant de la colonne D. |
| -        | A-C                 | Permet de soustraire le montant de la colonne A du montant de la colonne C.<blockquote>[!NOTE] Vous pouvez également utiliser le signe moins (-) pour inverser les signes d'une colonne. Par exemple, utilisez <strong>- A+B</strong> pour ajouter l'opposé du montant de la colonne A au montant de la colonne B.</blockquote> |
| \*       | A\*C                | Multiplie le montant de la colonne A par le montant de la colonne C. |
| /        | A/C                 | Divise le montant de la colonne A par le montant de la colonne C. |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Utiliser une formule de calcul dans une définition de colonne

1. Dans le générateur d'état, ouvrez la définition de colonne à modifier.
2. Dans la colonne **CALC** appropriée, entrez une formule dans la cellule **Formule**.

#### <a name="complex-calculations"></a>Calculs complexes

Un calcul complexe peut contenir toute combinaison de cellules de référence, d'opérateurs, de valeurs et de niveaux de parenthèses imbriquées. Par exemple, pour calculer la moyenne des colonnes A et B, utilisez la formule de calcul **((A+B)/2)**.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Spécifier des cellules d'état dans un calcul de colonne

Vous pouvez faire référence à une cellule spécifique de l'état en entrant une lettre de colonne et un code de ligne. Par exemple, **B.100** fait référence au code de ligne 100 dans la colonne B. Vous pouvez diviser une colonne en entier par le montant d'une cellule spécifique de l'état qui se trouve dans la même colonne. Par exemple, le calcul **B/B.100** signifie que le montant dans la colonne B doit être divisée par la valeur située au code de ligne 100 dans la colonne B. Si le calcul fait référence à une colonne qui dépend d'une autre colonne, la colonne dépendante est résolue en premier. Si une colonne fait référence à une autre colonne qui elle-même fait référence à la première colonne, vous provoquerez une erreur de référence circulaire.

> [!NOTE]
> Il se peut que le calcul soit incorrect si vous modifiez la priorité de calcul du rapport. Vous pouvez définir la priorité de calcul sous l'onglet **Paramètres** de la définition d'état.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Multiplier ou diviser une colonne par une ligne de base

Vous pouvez créer une colonne qui affiche toutes les valeurs dans une colonne spécifiée sous la forme d'un pourcentage d'un nombre de base. Par conséquent, vous pouvez indiquer des relations entre les lignes, comme un pourcentage d'une ligne de vente ou un pourcentage d'une ligne de dépenses totales. Pour multiplier ou diviser chaque ligne dans une colonne spécifique par une ligne de base, entrez la colonne à utiliser dans le calcul, puis entrez **\*BASEROW** ou **/BASEROW**. Par exemple, entrez **C\*BASEROW** ou **C/BASEROW**.

> [!NOTE]
> Lorsque vous utilisez une ligne de base dans une définition de colonne, vérifiez que chaque définition de ligne utilisée avec cette définition de colonne contient au moins une ligne de base pour les calculs.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Diviser le montant dans une colonne par le nombre de périodes

Vous pouvez diviser le montant dans une colonne par un nombre de périodes spécifié. Par exemple, la formule **B/Périodes** divise la valeur de la colonne B par le nombre de périodes dans la colonne B. Si le calcul s'étend sur plusieurs colonnes, spécifiez le nombre de périodes à utiliser dans le calcul. Par exemple, la formule **(B+C)/Périodes** ajoute les montants de la colonne B et de la colonne C, puis divise le résultat par la valeur de période.

## <a name="additional-resources"></a>Ressources supplémentaires

[Définitions de ligne dans les états financiers](row-definitions-financial-reporting.md)

[Options de mise en forme avancées dans les états financiers](advanced-formatting-options-financial-reporting.md)
