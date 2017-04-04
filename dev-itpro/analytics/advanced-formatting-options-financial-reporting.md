---
title: "Options de mise en forme avancées dans les états financiers"
description: "Lorsque vous créez un état dans les états financiers, les fonctions de mise en forme supplémentaires sont disponibles, notamment des filtres pour des dimensions, des restrictions pour des colonnes et des unités organisationnelles, des lignes non imprimées, et des instructions IF/THEN/ELSE dans les calculs."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Options de mise en forme avancées dans les états financiers

Lorsque vous créez un état dans les états financiers, les fonctions de mise en forme supplémentaires sont disponibles, notamment des filtres pour des dimensions, des restrictions pour des colonnes et des unités organisationnelles, des lignes non imprimées, et des instructions IF/THEN/ELSE dans les calculs. 

Le tableau suivant décrit les fonctions de mise en forme avancées disponibles lorsque vous créez des états.

| Fonction                   | Description                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Filtre de dimension           | Pour accéder aux ensembles de données spécifiques, vous pouvez utiliser des dimensions dans la définition de ligne et la définition de colonne. De nombreux états utilisent uniquement le segment naturel au format de ligne. Toutefois, des lignes peuvent être modifiées afin d'inclure des valeurs de dimension. Des filtres de dimension sont utilisés dans la définition de colonne pour accéder aux valeurs de dimension spécifiques. |
| Restriction d'unité de déclaration | Vous pouvez paramétrer une ligne d'état afin qu'elle indique uniquement les informations liées à une unité d'enregistrement spécifique.                                                                                                                                                                                                                      |
| Lignes NP (non imprimées)     | Les lignes non imprimées sont utiles dans de nombreux états. Si plusieurs calculs sont requis afin d'obtenir une valeur, ces calculs peuvent être masqués dans l'état imprimé. Les lignes non imprimées sont également utiles pour résoudre des créations d'état et pour le positionnement avancé de cellules.                                                    |
| Restriction de colonne         | La restriction de colonne dans la définition de ligne est utile pour masquer des valeurs pertinentes uniquement dans certaines lignes de l'état. Lorsque des calculs de pourcentage sont effectués sur une ligne, la restriction de colonne empêche les colonnes de totaux ou d'autres colonnes d'être imprimées lorsque ces numéros ne s'appliquent pas.                              |
| Saut de colonne               | Vous pouvez ajouter des sauts de colonne dans une définition de ligne pour afficher les informations d'état côte à côte. Vous pouvez ajouter plusieurs sauts de colonne dans une seule définition de ligne, les en-têtes de colonne sont alors répétés en haut de chaque colonne après le saut de colonne. Les commentaires sur un état sont indiqués entre les sauts de colonne.                              |
| Instruction IF/THEN/ELSE     | Vous pouvez modifier les calculs dans une définition de ligne ou une définition de colonne.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Positionnement avancé de cellules
Le positionnement avancé de cellules, ou *forçage*, implique de disposer des valeurs spécifiques dans des cellules spécifiques. Le forçage est par exemple souvent utilisé pour déplacer le solde approprié dans un relevé de flux de trésorerie. Vous pouvez utiliser le forçage pour les besoins suivants :

-   Pour déplacer des valeurs de Microsoft Excel dans des cellules spécifiques.
-   Pour des valeurs spécifiques codées en dur dans un état.
-   Pour modifier des signes en copiant une valeur d'une cellule précédente et en la multipliant par -1 %.

**Remarque :** Dans de nombreux cas, vous devez configurer votre définition d'état afin que les calculs de colonnes soient effectués avant les calculs de ligne. Procédez comme suit pour effectuer cette configuration :

1.  Ouvrez la définition d'état dans le Générateur d'états.
2.  Sous l'onglet **Paramètres**, sous **Priorité de calcul**, sélectionnez **Effectuer tout d'abord le calcul par colonne, puis par ligne**.

## <a name="designing-the-report"></a>Conception de l'état
Lorsque vous créez un état, vous devez créer toutes les lignes spécifiques d'abord pour que les valeurs soient extraites comme prévu. Ajoutez ensuite le format **Aucune impression** pour supprimer les détails incluant les valeurs finales. **Important :** Lorsque vous utilisez le code de format **CAL** dans la définition de ligne, vous ne pouvez pas faire de zoom avant dans les détails de la transaction. Pour obliger, les formules utilisent le format suivant : &lt;la colonne=&gt;de destination&lt;lançant le code&gt;&lt;de column.row séparent&gt; tous les autres positionnements pour une ligne par une virgule ou un espace. Voici un exemple : D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Exemples d'options de mise en forme avancées
Les exemples suivants indiquent comment mettre en forme la définition de ligne et la définition de colonne pour forcer un état de base de flux de trésorerie (exemple 1) et un état de statistiques (exemple 2).

### <a name="example-1-basic-forcing"></a>Exemple 1 : Forçage de base

Le tableau suivant présente un exemple de définition de ligne qui utilise le forçage de base.

| Code de ligne | Description                      | Code de format | Formules/lignes/unités associées | Remplacement de format | Solde normal | Contrôle d'impression | Restriction de colonne | Modificateur de ligne               | Lier aux dimensions financières |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Disponibilités, début de période (NP) |             |                             |                 |                |               |                    | Modificateur de compte = \[/BB\] | +Segment2 = \[\]1100         |
| 130      | Disponibilités, début de période      | CAL         | C=C.100,F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

Le tableau suivant présente un exemple d'une définition de colonne qui utilise le forçage de base dans la ligne.

|                              | A   | G    | C        | D      | E      | Ve    |
|------------------------------|-----|------|----------|--------|--------|------|
| En-tête 1                     |     |      |          |        |        |      |
| En-tête 2                     | A   | G    | C        | D      | E      | Ve    |
| En-tête 3                     |     |      |          |        |        |      |
| Type de colonne                  | LIGNE | DESC | FD       | FD     | FD     | CALC |
| Code registre/Catégorie d'attribut |     |      | RÉEL   | RÉEL | RÉEL |      |
| Exercice                  |     |      | BASE     | BASE   | BASE   |      |
| Période                       |     |      | BASE     | BASE   | BASE   |      |
| Périodes couvertes              |     |      | PÉRIODIQUE | Année en cours/BB | Année en cours    |      |
| Formule                      |     |      |          |        |        | E-D  |
| Largeur de colonne                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Exemple 2 : États statistiques

Le tableau suivant présente un exemple d'une définition de ligne qui utilise le forçage pour un état statistique.

| Code de ligne | Description               | Code de format | Formules/lignes/unités associées     | Remplacement de format      | Solde normal | Contrôle d'impression | Restriction de colonne | Modificateur de ligne | Lier aux dimensions financières               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Informations statistiques   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Effectifs - US            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Effectifs - International | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | Ventes aux USA                  |             |                                 |                      | C              |               |                    |              | +Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Ventes à l'international       |             |                                 |                      | C              |               |                    |              | +Segment2 = \[41\*\], 01:99\]de Segment3 = d'\[ |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | Ventes aux USA                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Ventes à l'international       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

Le tableau suivant présente un exemple d'une définition de colonne qui utilise le forçage pour un état statistique.

|                              | A   | B    | C      | D            | E     | Ve            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| En-tête 1                     | A   | B    | C      | D            | E     | Ve            |
| En-tête 2                     | -   | -    | Année en cours    | Ventes annuelles | Personnel | $ par personne |
| En-tête 3                     |     |      |        |              |       |              |
| Type de colonne                  | LIGNE | DESC | FD     | CALC         | CALC  | CALC         |
| Code registre/Catégorie d'attribut |     |      | RÉEL |              |       |              |
| Exercice                  |     |      | BASE   |              |       |              |
| Période                       |     |      | BASE   |              |       |              |
| Périodes couvertes              |     |      | Année en cours    |              |       |              |
| Formule                      |     |      |        |              |       | E-D          |
| Largeur de colonne                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Restriction d'une ligne à une unité de déclaration spécifique
Lorsqu'une ligne d'état est limitée à une unité de déclaration spécifique, cette ligne indique les données liées uniquement pour l'unité de déclaration nommée et ignore les données des autres unités de déclaration dans l'arborescence de génération d'états. Par exemple, vous pouvez créer une ligne qui fournit des détails sur toutes les dépenses opérationnelles pour un département spécifique. Votre état peut contenir des données en double s'il contient une arborescence de génération d'états et une définition de ligne ayant plus que le compte normal. Par exemple, vous avez une arborescence de génération d'états qui répertorie les six départements de votre organisation, et vous avez également une définition de ligne qui répertorie une combinaison spécifique d'un compte et d'un département dans la ligne. Lorsque vous générez l'état, la combinaison spécifique d'un compte et d'un département est imprimée à chaque niveau de l'arborescence de génération d'états, même si ce département ne correspond pas forcément au contenu de l'arborescence. Ce comportement se produit car la ligne remplace ce qui est généralement filtré par la définition d'état. Pour éviter la duplication des données, vous pouvez limiter une ligne à une unité d'enregistrement spécifique. **Remarque :** Si une ligne inclut des dimensions, et si vous limitez cette ligne à une unité de déclaration enfant, le montant de la ligne est inclus pour cette unité enfant et pour ses unités parents, mais aucune duplication ne se produit.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Limiter une ligne à une unité de déclaration

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis sélectionnez une définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Formules/lignes/unités associées** appropriée.
3.  Dans la boîte de dialogue **Sélectionner une unité de déclaration**, dans le champ **Arborescence de génération d'états**, sélectionnez l'arborescence affectée dans la définition d'état.
4.  Sélectionnez une unité de déclaration, puis cliquez sur **OK**. La restriction apparaît dans la cellule de la définition de ligne.
5.  Double-cliquez sur la cellule de la colonne **Liens vers les dimensions financières** de la ligne limitée, puis entrez un lien vers le système de données financières.

## <a name="selecting-print-control-in-a-row-definition"></a>Sélection du contrôle d'impression dans une définition de ligne
Vous pouvez spécifier des codes de contrôle d'impression pour chaque colonne à l'aide de la cellule **Contrôle d'impression**.

### <a name="add-print-control-codes-to-a-report-row"></a>Ajouter des codes de contrôle d'impression à une ligne d'état

1.  Dans le Concepteur de rapports, ouvrez la définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Contrôle d'impression**.
3.  Dans la boîte de dialogue **Contrôle d'impression**, sélectionnez un code de contrôle d'impression, ou appuyez sur la touche Ctrl et maintenez-la enfoncée pour sélectionner plusieurs codes. Vous pouvez également entrer des codes de contrôle d'impression directement dans la cellule **Contrôle d'impression**. Utilisez des virgules pour séparer plusieurs codes de contrôle d'impression.
4.  Sélectionnez n'importe quelles options conditionnelles d'impression.
5.  Cliquez sur **OK**.

### <a name="regular-print-control-codes"></a>Codes de contrôle d'impression normaux

Le tableau suivant décrit les codes de contrôle d'impression courants pour une définition de ligne.

| Code de contrôle d'impression | Traduction du code de contrôle d'impression         | Description                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP (aucune impression)                 | Ligne non imprimée                                 | Empêche les montants de la ligne d'être imprimés sur l'état, et exclut les montants des calculs. Pour inclure une colonne non imprimable dans un calcul, consultez la colonne directement dans la formule de calcul. Par exemple, la ligne non imprimée 240 est incluse dans le calcul suivant : **230+240+250**. Toutefois, la ligne non imprimée 240 n'est pas incluse dans le calcul suivant : **230:250**. |
| CS                 | Symbole monétaire ; permet d'utiliser un format de devise dans cette ligne | Permet d'indiquer le symbole monétaire dans tous les montants non exprimés en pourcentage. Les valeurs en pourcentage n'ont jamais de symbole monétaire.                                                                                                                                                                                                                                                                                                |
| XD                 | Permet de supprimer une ligne dans l'état détaillé du compte            | Permet de supprimer l'affichage des comptes sur des états détaillés de comptes et des états détaillés de transaction. Ce contrôle d'impression est utile lorsqu'une ligne inclut plusieurs comptes qui ne doivent pas être répertoriés dans l'état détaillé de compte ou l'état détaillé de transaction.                                                                                                                                                           |
| X0                 | Permet de supprimer la ligne si elle ne contient que des zéros                        | Permet d'exclure une ligne de l'état si toutes les cellules dans cette ligne sont vides ou contiennent des zéros. Ce contrôle d'impression est significatif uniquement si l'option de suppression du solde nul n'est pas sélectionnée dans la définition d'état.                                                                                                                                                                                            |
| B0                 | Permet de laisser vides les colonnes contenant des zéros                         | Permet de laisser les colonnes vides dans une ligne contenant des montants nuls.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Permet de supprimer le repositionnement                                  | Permet de supprimer le cumul Si l'état utilise une arborescence de génération d'état, les montants de cette ligne ne sont pas repositionnés dans les nœuds parents suivants.                                                                                                                                                                                                                                                                               |
| SR                 | Permet de supprimer l'arrondi                                | Permet d'empêcher les montants de cette ligne d'être arrondis.                                                                                                                                                                                                                                                                                                                                                          |
| XT                 | Permet de supprimer une ligne dans l'état détaillé de transaction        | Permet de supprimer l'affichage des transactions dans les états détaillés de transaction. Ce contrôle d'impression est utile lorsqu'une ligne inclut plusieurs comptes qui ne doivent pas être répertoriés dans l'état détaillé de transaction.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Codes de contrôle d'impression conditionnels

Le tableau suivant décrit les codes de contrôle d'impression conditionnels pour une définition de ligne.

| Code de contrôle d'impression | Description                                  |
|--------------------|----------------------------------------------|
| (aucune)             | Efface la sélection d'impression conditionnelle.       |
| SL                 | Permet d'imprimer uniquement les soldes débiteurs pour cette ligne.  |
| CR                 | Permet d'imprimer uniquement les soldes créditeurs pour cette ligne. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Cellule Restriction de colonne dans une définition de ligne
La cellule **Restriction de colonne** dans une définition de ligne a plusieurs objectifs. Selon le type de ligne, vous pouvez utiliser la cellule **Restriction de colonne** pour spécifier l'une des tâches suivantes :

-   La cellule peut limiter l'impression des montants de ligne dans une colonne spécifique. Cette fonction est utile si vous créez un bilan tabulaire.
-   La cellule peut préciser la colonne des montants à trier.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Utilisation d'une formule de calcul dans une définition de ligne
Une formule de calcul dans une définition de ligne peut inclure **+**, **-**, **\***, et **/** les opérateurs, et également ** IF/THEN/ELSE ** des relevés. En outre, un calcul peut impliquer des cellules et des montants absolus (les nombres réels inclus dans la formule). La formule peut comporter jusqu'à 1 024 caractères. Les calculs ne peuvent pas être appliqués aux lignes contenant des cellules de type **Liens vers les dimensions financières** (FD). Toutefois, vous pouvez inclure des calculs dans les lignes consécutives, supprimer l'impression de ces lignes, puis totaliser les lignes de calcul.

### <a name="operators-in-a-calculation-formula"></a>Opérateurs dans une formule de calcul

Une formule de calcul utilise des opérateurs plus complexes qu'une formule de total de ligne. Toutefois, vous pouvez utiliser **\*** et **/** les opérateurs utilisés avec les opérateurs supplémentaires pour multiplier (\*) et de diviser (/) des montants. Pour utiliser une plage ou une somme dans une formule de calcul, vous devez utiliser un arobase (@) devant tout code de ligne, sauf si vous utilisez une colonne dans la définition de ligne. Par exemple, pour ajouter le montant de la ligne 100 au montant de la ligne 330, vous pouvez utiliser la formule de total de ligne ** 100+330 ** ou la formule de calcul **@100+@330**. **Remarque :** Vous devez utiliser un arobase (@) avant chaque code de ligne que vous utilisez dans une formule de calcul. Sinon, le nombre est désigné comme un montant absolu. Par exemple, la formule **@100+330 ** ajoute 330 EUR au montant de la ligne 100. Lorsque vous référencez une colonne dans une formule de calcul, le signe arobase (@) n'est pas nécessaire.

### <a name="create-a-calculation-formula"></a>Créer une formule de calcul

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Code de format**, puis sélectionnez **CAL**.
3.  Entrez la formule de calcul dans la cellule **Formules/Lignes/Unités associées**.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Exemple d'une formule de calcul pour des lignes spécifiques

Dans cet exemple, la formule de calcul **@100+@330** signifie que le montant de la ligne 100 est ajouté au montant de la ligne 330. La formule de total de ligne ** 340+370 ** ajoute le montant de la ligne 340 au montant de la ligne 370. (Montant de la ligne 370 est le montant de la formule de calcul.)

| Code de ligne | Description                 | Code de format | Formules/lignes/unité associées | Contrôle d'impression | Modificateur de ligne | Lier aux dimensions financières |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Disponibilités, début de période |             |                            | NP (aucune impression)            | BB           | 1100:1110\]+Compte=\[       |
| 370      | Disponibilités, début d'exercice   | CAL         | @100+@330                  | NP (aucune impression)            |              |                              |
| 400      | Disponibilités, début de période | TOT         | 340+370                    |               |              |                              |

Lorsque le code de format d'une ligne dans une définition de ligne est **CAL**, et que vous entrez un calcul mathématique dans la cellule **Formules/lignes/unités associées**, vous devez également entrer la lettre de la colonne et de la ligne associées dans l'état. Par exemple, entrez ** A.120 ** pour représenter la colonne A, la ligne 120. Sinon, vous pouvez utiliser le signe arobase (@) pour indiquer toutes les colonnes. Par exemple, entrez **@120** pour représenter toutes les colonnes de la ligne 120. On des activités un calcul mathématique qui ne possède pas de lettre de colonne ou un arobase (@) est un nombre réel. ** Remarque : ** Si vous utilisez un code ligne d'étiquette pour indiquer une ligne, vous devez utiliser un point (.) comme séparateur entre la lettre de colonne et l'étiquette (par exemple, ** A.GROSS\_MARGIN/A.SALES **). Si vous utilisez un arobase (@), aucun séparateur n'est pas obligatoire (par exemple, **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Exemple d'une formule de calcul pour une colonne spécifique

Dans cet exemple, la formule de calcul **E=C.340** signifie que le calcul dans la cellule de la colonne C, la ligne 340, est effectué uniquement sur la colonne E. **Remarque :** Lorsque vous référencez une colonne dans une formule de calcul, un arobase (@) n'est pas nécessaire.

| Code de ligne | Description                 | Code de format | Formules/lignes/unité associées | Contrôle d'impression | Modificateur de ligne | Lier aux dimensions financières |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Disponibilités, début de période |             |                            | NP (aucune impression)            | BB           | 1100:1110\]+Compte=\[       |
| 370      | Disponibilités, début d'exercice   | CAL         | E=C.340                    | NP (aucune impression)            |              |                              |
| 400      | Disponibilités, début de période | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Modification d'un nombre dans les colonnes sélectionnées

Lorsque vous modifiez un nombre ou un calcul dans une colonne d'une ligne spécifique mais que vous ne souhaitez pas affecter d'autres colonnes dans l'état, vous pouvez spécifier **CAL** (Calcul) dans la colonne **Code de format** de la définition de ligne.

-   Pour effectuer un calcul sur toutes les colonnes de l'état (**FD**), n'entrez pas d'affectation de colonne.
-   Pour limiter une formule aux colonnes spécifiques, entrez la lettre de colonne, un signe égal (**=**), puis la formule.
-   Vous pouvez spécifier plusieurs colonnes. Lorsque vous utilisez un arobase (@) avec un emplacement spécifique de colonne, ce signe est lié à la ligne.
-   Vous pouvez entrer plusieurs formules de colonne dans une ligne. Séparez les formules par des virgules.

### <a name="calculation-examples"></a>Exemples de calcul

| Calcul            | Action créée                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Pour chaque colonne, la valeur de la ligne 130 est multipliée par 0,75. Le résultat est ensuite placé dans la ligne actuelle de chaque colonne. |
| B=@130\*.75            | Le même calcul est effectué uniquement sur la colonne B.                                                                      |
| A, B, C=@100/(@130)\*.75 | A= (A.100/A.130)\*.75 B= (B.100/B.130)\*.75 C= (C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>Instructions IF/THEN/ELSE dans une définition de ligne

Les instructions **IF/THEN/ELSE** peuvent être ajoutées à n'importe quel calcul valide et être utilisées avec le format **CAL**. Vous devez entrer des formules de calcul **IF/THEN/ELSE** dans la cellule de la colonne **Formules/lignes/unités associées**. ** IF/THEN/ELSE ** les formules de calcul utilisent le format suivant : IF &lt;la formule ELSE formule vraie&gt; ou &lt;fausse&gt; de relevé &lt;ALORS&gt; ** formule &lt;ELSE&gt;** la partie du relevé est facultative.

#### <a name="if-statements"></a>Instructions IF

Après l'instruction **IF**, les instructions peuvent être évaluées comme true ou false. Après l'instruction **IF**, les instructions peuvent impliquer une évaluation unique, ou il peut s'agir d'une instruction complexe qui peut contenir plusieurs expressions. Voici quelques exemples :

-   ** IF A.2000&gt;** (évaluation simple)
-   ** IF A.2000&gt;ET A.20010&lt;, 000 ** (instruction complexe)
-   ** IF A.20010000&gt;OU ((A.340/B.1200)\*2 &lt;1200)** (Relevé complexe contenant plusieurs expressions)

Le terme **Periods** dans une instruction **IF** représente le nombre de périodes pour l'état. Ce terme est généralement utilisé pour calculer une moyenne de l'année en cours. Par exemple, lorsque vous exécutez un état pour la période 7 YTD, l'instruction **B.150/Periods** signifie que la valeur de la ligne 150 de la colonne B est divisée par 7.

#### <a name="then-and-else-formulas"></a>Formules THEN et ELSE

Les formules **THEN** et **ELSE** peuvent être n'importe quel calcul valide et être des affectations très simples de valeur ou bien des formules complexes. Par exemple, l'instruction ** IF A.2000&gt;THEN A=B.200 ** le moyen « , si la valeur de la cellule de la colonne A de la ligne 200 est supérieure à 0 (zéro), ont mis la valeur de la cellule de la colonne B de la ligne 200 de la cellule dans la colonne A de la ligne actuelle. » L'instruction **IF/THEN** précédente place une valeur dans une colonne de la ligne actuelle. Toutefois, vous pouvez également utiliser un arobase (@) dans les évaluations true/false ou la formule pour représenter toutes les colonnes. Voici quelques exemples supplémentaires qui sont décrits dans les sections suivantes :

-   ** IF A.200 &gt;THEN 0 B.200 ** : Si la valeur de la cellule A.200 est positive, la valeur de la cellule B.200 se mise en chaque colonne de la ligne actuelle.
-   ** IF A.200 &gt;THEN 0 @200** : Si la valeur de la cellule A.200 est positive, la valeur de chaque colonne de la ligne 200 est placée dans la colonne correspondante dans la ligne actuelle.
-   ** IF @200&gt;0 THEN @200** : Si la valeur de la ligne 200 de la colonne actuelle est positive, la valeur de la ligne 200 est placée dans la même colonne de la ligne actuelle.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Restriction d'un calcul dans une unité de déclaration dans une définition de ligne

Pour limiter un calcul à une seule unité organisationnelle dans un organigramme d'entreprise, de sorte que le montant qui en résulte ne soit pas cumulé jusqu'à une unité de niveau supérieur, vous pouvez utiliser **@Unit** le code en ** de Formules/Lignes/Unités connexes ** la cellule dans la définition de ligne. **@Unit** le code est répertorié dans la colonne B de l'organigramme d'entreprise, ** nom d'unité **. Lorsque vous utilisez **@Unit** le code, les valeurs ne sont pas cumulées, mais le calcul est évalué à chaque niveau de l'organigramme d'entreprise. **Remarque :** Pour utiliser cette fonction, une arborescence de génération d'états doit être associée à la définition de ligne. La ligne de calcul peut faire référence à une ligne de calcul ou à une ligne de données financières. Le calcul est enregistré dans la cellule **Formules/lignes/unités associées** de la définition de ligne et de la restriction financière du type de données. Le calcul doit utiliser un calcul conditionnel qui commence par ** IF @Unit** ingénierie. Voici un exemple : IF @Unit(VENTES) ALORS @100 AUTREMENT 0 ce calcul comprend le montant de la ligne 100 dans chaque colonne du rapport, mais que pour l'unité de vente. Si plusieurs unités sont nommées SALES, le montant apparaît dans chacune d'entre elles. En outre, la ligne 100 peut être une ligne de données financières et peut être définie comme non imprimée. Dans ce cas, le montant n'apparaît pas dans les unités de l'arborescence. Vous pouvez également limiter le montant à une seule colonne de l'état, comme la colonne H par exemple, à l'aide d'une restriction de colonne pour imprimer la valeur uniquement dans cette colonne de l'état. Vous pouvez inclure des combinaisons **OR** dans une instruction **IF**. Voici un exemple : IF @Unit(VENTES) OU @Unit(SALESWEST) ALORS 5 @100 ELSE vous pouvez spécifier l'unité dans une limitation de type dans l'une des manières suivantes :

-   Entrez un nom d'unité pour inclure les unités qui correspondent. Par exemple, ** IF @Unit(VENTES) ** active le calcul pour n'importe quelle unité qui est nommée SALES, même s'il y a plusieurs unités de vente dans l'organigramme d'entreprise.
-   Entrez le nom d'unité et la société pour limiter le calcul aux unités spécifiques d'une société spécifique. Par exemple, entrez ** IF @Unit(POINT : CULMINANTVENTES **) pour limiter le calcul aux unités de vente dans la société de POINT. CULMINANT
-   Entrez le code hiérarchique complet à partir de l'arborescence de génération d'états pour limiter le calcul à une unité spécifique. Par exemple, entrez ** IF @Unit(SUMMARY^ACME^WEST COAST^SALES) **. **Remarque :** Pour rechercher le code hiérarchique complet, cliquez dans la définition d'arborescence de génération d'état, puis sélectionnez **Copier Identificateur d'unité de génération d'états (code H-)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Permet de limiter un calcul à une unité de génération d'état

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Code de format**, puis sélectionnez **CAL**.
3.  Cliquez sur ** de Formules/Lignes/Unités connexes ** la cellule, puis entrez un calcul conditionnel qui commence par ** IF @Unit** ingénierie.

### <a name="ifthenelse-statements-in-a-column-definition"></a>Instructions IF/THEN/ELSE dans une définition de colonne

Une instruction **IF/THEN/ELSE** permet à n'importe quel calcul de dépendre des résultats de n'importe quelle autre colonne. Vous pouvez vous référer à d'autres colonnes, mais pas à une cellule d'état de l'instruction **IF**. Tous les calculs doivent être appliqués dans la colonne entière. Par exemple, l'instruction ** IF B100&gt;THEN B C ELSE\*1,25 ** le moyen « , si le montant de la colonne B est supérieur à 100, sont mis la valeur de la colonne B dans ** CALC ** colonne. Si le montant de la colonne B n'est pas supérieur à 100, multipliez la valeur de la colonne C par 1,25, et placez le résultat dans la colonne **CALC**. » Suivez toujours l'instruction **IF** avec une instruction logique qui peut être évaluée comme TRUE ou FALSE. Les formules que vous utilisez pour l'instruction **THEN** et l'instruction **ELSE** peuvent contenir des références vers n'importe quel nombre de colonnes, et ces formules peuvent être aussi complexes que vous le souhaitez. **Remarque :** Vous ne pouvez pas mettre les résultats d'un calcul dans une autre colonne. Les résultats doivent figurer dans la colonne qui contient la formule.


