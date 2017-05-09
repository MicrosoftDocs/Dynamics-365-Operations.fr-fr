---
title: "Modifier les cellules de définition de ligne"
description: "Cet article décrit les informations nécessaires pour chaque cellule dans une définition de ligne sur un état financier et explique comment entrer ces informations."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 16 - 09 - 06
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: b61364c9055e5c5a63592c7f05551d0c145924b9
ms.lasthandoff: 03/29/2017


---

# <a name="modify-row-definition-cells"></a>Modifier les cellules de définition de ligne

Cet article décrit les informations nécessaires pour chaque cellule dans une définition de ligne sur un état financier et explique comment entrer ces informations. 

# <a name="specify-a-row-code-in-a-row-definition"></a>Spécifier un code de ligne dans une définition de ligne

Dans les définitions de ligne, les nombres ou les libellés dans la cellule**Code de ligne** identifient chaque ligne dans la définition de ligne. Vous pouvez spécifier le code de ligne pour faire référence à des données dans les calculs et les totaux.

### <a name="row-code-requirements"></a>Conditions requises par les codes de ligne

Chaque ligne nécessite un code de ligne. Vous pouvez mixer les codes de ligne numériques, alphanumériques et non définis (vide) dans une définition de ligne. Le code de ligne peut être n'importe quel entier positif (inférieur à 100 000 000) ou un nom descriptif identifiant cette ligne. Un nom descriptif doit suivre les règles suivantes :

-   le libellé doit commencer par une lettre (a à z ou A à Z), et peut être n'importe quelle combinaison des chiffres et de lettres jusqu'à 16 caractères. **Remarque :** le libellé peut inclure le caractère de soulignement (\_), mais aucun autre caractère spécial n'est autorisé.
-   Le libellé ne peut pas utiliser l'un des mots réservés suivants : AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO, ou RPO.

Les exemples suivants sont des codes de ligne valides :

-   320
-   TL\_NET\_INCOME
-   TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Modifier un code de ligne dans une définition de ligne

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Dans la ligne appropriée, entrez la nouvelle valeur dans la cellule dans la colonne **Code de ligne**.

### <a name="reset-numeric-row-codes"></a>Réinitialiser des codes de ligne numériques

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Dans le menu **Édition**, cliquez sur **Renuméroter les lignes**.
3.  Dans la boîte de dialogue **Renuméroter les lignes**, spécifiez les nouvelles valeurs pour le code de ligne de départ et son incrément. Vous pouvez réinitialiser les codes de ligne numériques à des valeurs équidistantes. Toutefois, le générateur d'états ne renumérote que les codes de ligne qui commencent par des chiffres (par exemple, 130 ou 246). Il ne renumérote pas les codes de ligne qui commencent par des lettres (par exemple, INCOME\_93 ou TP0693). **Remarque :** lorsque vous renumérotez des codes de ligne, le générateur d'états met à jour automatiquement les références **TOT** et **CAL**. Par exemple, si une ligne **TOT** fait référence à une plage qui commence avec le code de ligne 100, et que vous renumérotez les lignes en commençant par 90, la référence **TOT** par de 100 à 90.

## <a name="add-a-description"></a>Ajouter une description
La cellule de description fournit la description des données financières contenues dans la ligne de l'état, par exemple « Produit »ou « Revenu net ». Le texte dans la cellule **Description** apparaît dans l'état exactement comme il a été entré dans la définition de ligne. **Remarque :** la largeur de la colonne de description dans l'état est définie dans la définition de colonne. Si le texte dans la colonne **Description** dans la définition de ligne est long, vérifiez la largeur de la colonne **DESC**. Lorsque vous utilisez la boîte de dialogue **Insérer des lignes à partir de**, les valeurs dans la colonne **Description** sont les valeurs de segment ou les valeurs de dimension issues des données financières. Vous pouvez insérer des lignes pour ajouter un texte descriptif, tel qu'un en-tête de section ou un total de section, et pour ajouter une mise en forme, telle qu'une ligne avant une ligne de total. Si l'état inclut une arborescence de génération d'états, vous pouvez inclure le texte supplémentaire défini pour les unités de déclaration dans l'arborescence de génération d'états. Vous pouvez également limiter le texte supplémentaire à une unité de déclaration spécifique.

### <a name="add-the-description-for-a-line-on-a-report"></a>Ajouter la description pour une ligne d'un état

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Sélectionnez la cellule **Description**, puis entrez le nom de la ligne de l'état.
3.  Appliquez la mise en forme.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Ajouter du texte supplémentaire à partir d'une arborescence de génération d'états dans la description

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Entrez le code de texte supplémentaire et tout autre texte dans la cellule **Description** appropriée.
3.  Appliquez la mise en forme.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Limiter le texte supplémentaire à une unité de déclaration spécifique

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Déterminez la ligne à laquelle le texte supplémentaire doit être créé, puis double-cliquez sur la cellule dans la colonne **Formules/lignes/unités associées**.
3.  Dans la boîte de dialogue **Sélectionner une unité de déclaration**, dans le champ **Arborescence de génération d'états**, sélectionnez une arborescence de génération d'états.
4.  Dans le champ **Sélectionner une unité de déclaration pour la restriction**, développez ou réduisez l'arborescence de génération d'états, puis sélectionnez une unité de déclaration.

## <a name="add-a-format-code"></a>Ajouter un code de format
La cellule **Code de format** offre une sélection de mises en forme prédéfinies pour le contenu de cette ligne. Si la cellule **Code de format** est vide, la ligne est interprétée comme une ligne de détail de données financières. **Remarque :** si un état contient des lignes en un format qui ne correspond pas à une somme associées à des lignes de montant qui ont été supprimées (par exemple, en raison de soldes nuls), vous pouvez utiliser la colonne **Formules/Lignes/Unités associées** pour empêcher les lignes de titre et de format d'être imprimées.

### <a name="add-a-format-code-to-a-report-row"></a>Ajouter un code de format à une ligne d'état

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis sélectionnez une définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Code de format**.
3.  Sélectionnez un code de format dans la liste. Le tableau suivant décrit les codes de format et leurs actions.
    | Code de format                   | Interprétation du code de format | Action|
    |---|---|---|
    | (Aucun)                        |                                    | Désactive la cellule **Code de format**.                                                                                                                                                                               |
    | TOT                           | Total                              | Identifie une ligne qui utilise des opérateurs mathématiques dans la colonne **Formules/Lignes/Unités associées**. Les totaux contiennent des opérateurs simples, comme **+** ou **-**.                                                      |
    | CAL                           | Calcul                        | Identifie une ligne qui utilise des opérateurs mathématiques dans la colonne **Formules/Lignes/Unités associées**. Les calculs contiennent des opérateurs complexes tels que **+**, **-**, **\***, **/** et **IF/THEN/ELSE**. |
    | DES                           | description ;                        | Identifie un en-tête ou une ligne vide dans un état.                                                                                                                                                        |
    | LFT RGT CEN                   | Gauche Droite Centre                  | Aligne le texte de description de la ligne dans la page de l'état, quel que soit le positionnement du texte dans la définition de colonne.                                                                                               |
    | CBR                           | Modifier la ligne de base                    | Identifie une ligne qui définit la ligne de base pour les calculs de colonne.                                                                                                                                               |
    | COLUMN                        | Saut de colonne                       | Démarre une nouvelle colonne dans l'état.                                                                                                                                                                             |
    | PAGE                          | Saut de page                         | Démarre une nouvelle page dans l'état.                                                                                                                                                                               |
    | ---                           | Soulignement simple                   | Met une ligne simple sous toutes les colonnes de montant de l'état.                                                                                                                                                     |
    | ===                           | Soulignement double                   | Met une ligne double sous toutes les colonnes de montant de l'état.                                                                                                                                                     |
    | LINE1                         | Ligne fine                          | Trace une ligne fine en travers de la page.                                                                                                                                                                      |
    | LINE2                         | Ligne épaisse                         | Trace une ligne épaisse en travers de la page.                                                                                                                                                                     |
    | LINE3                         | Ligne pointillée                        | Trace une ligne pointillée simple en travers de la page.                                                                                                                                                                    |
    | LINE4                         | Ligne épaisse et ligne fine           | Trace une ligne double en travers de la page. La ligne supérieure est épaisse et la ligne inférieure est fine.                                                                                                                       |
    | LINE5                         | Ligne fine et ligne épaisse           | Trace une ligne double en travers de la page. La ligne supérieure est fine et la ligne inférieure est épaisse.                                                                                                                       |
    | BXB BXC                       | Ligne marquée par une bordure                          | Trace une bordure autour de les lignes d'état qui commencent par la ligne **BXB** et se terminent par la ligne **BXC**.                                                                                                               |
    | REM                           | Remarque                             | Identifie une ligne correspondant à une ligne de commentaire qui ne doit pas être imprimée dans l'état. Par exemple, une ligne de remarque peut expliquer vos techniques de mise en forme.                                                            |
    | SORT ASORT SORTDESC ASORTDESC | Trier                               | Trie les dépenses ou les produits, trie un état de budget réel ou d'écart de budget par écart le plus important, ou trie les descriptions de ligne par ordre alphabétique.                                                                   |

## <a name="specify-related-formulasrowsunits"></a>Spécifier les formules/lignes/unités associées
La cellule **Formules/lignes/unités associées** a plusieurs fonctionnalités. Selon le type de ligne, une cellule **Formules/Lignes/Unités associées** peut exécuter une des tâches suivantes :

-   Définir les lignes à inclure dans un calcul lorsque vous utilisez un code de format **TOT** ou **CAL**.
-   Lier une ligne de mise en forme à une ligne de montant, de sorte que la mise en forme soit imprimée uniquement lorsque le montant associé est imprimé.
-   Limiter une ligne à une unité de déclaration spécifique.
-   Définir la ligne de base des calculs lorsque vous utilisez le code de format **BASEROW**.
-   Définir les lignes à trier lorsque vous utilisez l'un des codes de format de tri.

### <a name="use-a-row-total-in-a-row-definition"></a>Utiliser un total de ligne dans une définition de ligne

Utilisez une formule de total de ligne pour ajouter ou soustraire des montants dans d'autres lignes. Une formule de création d'un total de ligne peut inclure les opérateurs + et - pour combiner différents codes de lignes et plages. Les plages sont indiquées par un deux-points (:). La formule peut comporter jusqu'à 1 024 caractères. Voici un exemple d'une formule standard de totalisation : 400+420+430+450+460PASSIF+CAPITAUX PROPRES520 : 546520:546-PASSIF

### <a name="components-of-a-row-total-formula"></a>Composants d'une formule de total de ligne

Lorsque vous créez une formule de total de ligne, vous devez utiliser des codes de ligne pour spécifier les lignes à ajouter ou à soustraire dans la définition de ligne actuelle, vous devez utiliser des opérateurs pour spécifier comment les lignes sont combinées. Les lignes de total et les lignes de montant peuvent être utilisées dans n'importe quelle combinaison. **Remarque :** toutes les lignes de total qui figurent dans une plage sont exclues. Pour créer un total général, vous pouvez spécifier la plage de lignes. Si la première ligne d'une plage est une ligne de total, cette ligne est incluse dans le nouveau total. Le tableau suivant décrit la manière dont les opérateurs sont utilisés dans les formules de total de ligne.

| Opérateur | Exemple de formule | description ;                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Ajoute le montant de la ligne 100 au montant de la ligne 330.        |
| :        | 100:330         | Additionne les totaux de toutes les lignes entre la ligne 100 et la ligne 330.    |
| -        | 100-330         | Soustrait le montant de la ligne 100 du montant de la ligne 330. |

### <a name="create-a-row-total"></a>Créer un total de ligne

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Code de format** dans la définition de ligne, et sélectionnez **TOT**.
3.  Dans la cellule **Formules/Lignes/Unités associées**, entrez la formule du total.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relier une ligne de format à une ligne de montant

Dans la colonne **Code de format** dans une définition de ligne, les codes de format **DES**, **LFT**, **RGT**, **CEN**, **---** et **===** appliquent la mise en forme aux lignes qui ne comportent pas un montant. Pour éviter que cette mise en forme soit imprimée lorsque les lignes de montant correspondantes sont supprimées (par exemple, parce que les lignes de montant contiennent des valeurs zéro ou aucune activité de période), vous devez associer les lignes de format aux lignes de montant correspondantes. Cette fonctionnalité est utile lorsque vous souhaitez empêcher les en-têtes ou la mise en forme associés aux sous-totaux d'être imprimés lorsqu'il n'existe aucun détail à imprimer pour la période. **Remarque :** vous pouvez également empêcher les lignes de montant détaillées d'être imprimées en désactivant l'option pour d'affichage des lignes sans montants. Cette option est située sous l'onglet **Paramètres** de la définition d'état. Par défaut, les comptes de détails de transaction ayant un solde nul ou aucune activité sur la période sont supprimés des états. Pour afficher ces comptes de détail des transactions, activez la case à cocher **Afficher les lignes sans montant** sous l'onglet **Paramètres** de la définition d'état.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relier une ligne de format à une ligne de montant

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis sélectionnez une définition de ligne à modifier.
2.  Dans la ligne de mise en forme, dans la cellule **Formules/Lignes/Unités associées**, entrez le code de ligne de la ligne de montant à supprimer. **Remarque :** pour supprimer une ligne de montant, le solde de la ligne doit être 0 (zéro). Une ligne de montant comportant un solde ne peut pas être supprimée.
3.  Dans le menu **Fichier**, cliquez sur **Enregistrer**.

### <a name="example-of-preventing-printing-of-rows"></a>Empêcher l'impression des lignes, exemple

Dans l'exemple suivant, Phyllis souhaite empêcher que le titre et les traits de soulignement dans la ligne **Disponibilités totales** de son état soient imprimés, car il n'y a eu aucune activité dans aucun des comptes de disponibilités. Par conséquent, dans la ligne 220 (qui est une ligne de format comme l'indique le code de format **---**), dans la cellule **Formules/Lignes/Unités associées**, elle entre **250**, qui est le code de ligne de la ligne de montant qu'elle souhaite supprimer. [![RelatedRowsRowDefinition](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Sélectionner la ligne de base pour un calcul de colonne
Dans la déclaration relationnelle, vous affectez une ou plusieurs lignes de base dans la définition de ligne à l'aide du code de format **CBR** (ligne de changement de base). Une ligne de base est alors référencée par un calcul dans la définition de colonne. Voici quelques exemples de typiques de calculs CBR :

-   Pourcentage du produit total tel qu'il a trait à des articles de produit individuels
-   Pourcentage des dépenses totales tel qu'il a trait à des articles de dépenses individuels
-   Pourcentage de marge brute tel qu'il a trait aux détails de la division ou du département

Une ou plusieurs lignes de base sont définies dans la définition de ligne, puis la définition de colonne détermine la relation dans laquelle la ligne de base est déclarée. Le code utilisé dans la formule de colonne est **BASEROW**. Les opérations mathématiques de base suivantes sont utilisées avec **BASEROW** : division, multiplication, addition et soustraction. L'opération le plus souvent utilisée est la division par **BASEROW**, où le résultat est affiché en pourcentage. Les calculs de colonne qui utilisent **BASEROW** dans leur formule utilisent la définition de la ligne pour les codes de ligne de base associés. Les lignes **CBR** ont les caractéristiques suivantes :

-   Les lignes **CBR** ne sont pas imprimées dans l'état terminé.
-   Le code de format **CBR**et son code de ligne associé sont positionnés au-dessus de la ligne ou de la section qui affiche les calculs associés.

Dans une définition de colonne, le type de colonne **CALC** affiche la colonne qui spécifie une formule dans la ligne **Formule**. Cette formule traite les données de cette colonne de l'état et utilise le mot clé Baserow (ligne de référence) pour baser les calculs sur les codes format **CBR** dans la ligne. Dans la définition de ligne, le code de format **CBR** définit la ligne de base pour les colonnes qui calculent un pourcentage ou sont multipliées par la ligne de base pour chaque ligne de l'état. Vous pouvez avoir plusieurs codes de format **CBR** dans un format de ligne, comme un pour les ventes nettes, un pour les ventes brutes et un pour les dépenses totales. Généralement, le code de format **CBR** est utilisé pour créer un pourcentage pour les comptes qui sont comparés à une ligne de total. Une ligne de base est utilisée pour tous les calculs jusqu'à ce qu'une autre ligne de base soit définie. Vous devez définir un code de format **CBR** de début et un code de format **CBR ** de fin. Par exemple, pour déterminer les dépenses comme un pourcentage des ventes nettes, vous pouvez diviser la valeur de chaque ligne de dépense par la valeur indiquée dans la ligne des ventes nettes. Dans ce cas, la ligne des ventes réelles est la ligne de base. Vous pouvez définir une définition de colonne qui indique les résultats en cours et pour l'année à ce jour, avec un pourcentage de base de chaque résultat, comme indiqué dans l'exemple qui suit. Commencez par une déclaration des revenus détaillée.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Sélectionner la ligne de base dans une définition de ligne pour un calcul de colonne

1.  Dans le générateur d'état, cliquez sur **Définitions de colonne**, puis ouvrez ensuite la définition de colonne pour une déclaration des revenus.
2.  Ajoutez une colonne à la définition de colonne, puis définissez le type de colonne sur **CALC**.
3.  Dans la cellule **Formule** de la nouvelle colonne, entrez la formule **X/BASEROW**, où **X** est le type de la colonne **FD** pour afficher un pourcentage.
4.  Double-cliquez sur la cellule **Remplacement de format/devise**.
5.  Dans la boîte de dialogue **Remplacement de format**, dans la liste **Catégorie de format**, sélectionnez **Pourcentage**, puis cliquez sur **OK**.
6.  Dans le menu **Fichier**, cliquez sur **Enregistrer sous** pour enregistrer la définition de colonne sous un nouveau nom. Ajoutez **CBR** au nom de fichier actuel (par exemple, **CUR\_YTD\_CBR**). Cette définition de colonne est votre définition de colonne de base.
7.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne pour la modifier en utilisant le calcul de ligne de base.
8.  Insérez une nouvelle ligne au-dessus de la ligne où le calcul de ligne de base doit commencer.
9.  Double-cliquez sur la cellule **Code de format** de la définition de ligne, puis sélectionnez **CBR**.
10. Dans la cellule **Formules/Lignes/Unités associées**, entrez le numéro du code de ligne pour la ligne de base.

### <a name="example-of-base-row-calculation"></a>Exemple de calcul de ligne de base

Dans l'exemple suivant d'une définition de ligne, la ligne 100 indique que la ligne de base des calculs est la ligne 280. [![Exemple de calcul de ligne de base.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png) Dans l'exemple suivant d'une définition de colonne, les calculs utilisent le code de format **CBR**. Le calcul dans la colonne C divise la valeur de la colonne B de l'état par la valeur contenue dans la ligne 280 et la colonne B. Le remplacement de format de la colonne B imprime le résultat du calcul sous la forme d'un pourcentage. De même, chaque montant dans la colonne E correspond au montant dans la colonne D sous la forme d'un pourcentage des ventes nettes. [![Exemple de définition de colonne.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png) L'exemple suivant présente un état pouvant être généré à partir des calculs précédents. [![Exemple d'état à partir des calculs précédents.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Sélectionner un code de tri pour une définition de ligne
Les codes de tri permettent de trier les comptes ou les valeurs, de trier un état de budget réel ou d'écart de budget par écart le plus important, ou de trier les descriptions de ligne par ordre alphabétique. Les codes de tri disponibles sont les suivants :

-   **SORT** – Trie l'état dans l'ordre croissant, selon les valeurs dans la colonne spécifiée.
-   **ASORT** – Trie l'état dans l'ordre croissant, selon la valeur absolue des valeurs dans la colonne spécifiée. Autrement dit, le signe de chaque valeur est ignoré lorsque les valeurs sont triées. Ce code de format ordonne les valeurs par l'importance de l'écart, indépendamment du fait que cet écart est positif ou négatif.
-   **SORTDESC** – Trie l'état dans l'ordre décroissant, selon les valeurs dans la colonne spécifiée.
-   **ASORTDESC** – Trie l'état dans l'ordre décroissant, selon la valeur absolue des valeurs dans la colonne spécifiée.

### <a name="select-a-sorting-code"></a>Sélectionner un code de tri

1.  Dans le générateur d'état, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2.  Double-cliquez sur la cellule **Code de format**, puis sélectionnez un code de tri.
3.  Dans la cellule **Formules/Lignes/Unités associées**, spécifiez la plage de codes de ligne à trier. Pour spécifier une plage, entrez le premier code de ligne, deux-points (:), puis le dernier code de ligne. Par exemple, entrez **160:490** pour indiquer que la plage va de la ligne 160 à la ligne 490.
4.  Dans la cellule **Restriction de colonne**, entrez la lettre de la colonne d'état à utiliser pour le tri. **Remarque :** n'incluez que les lignes de montant dans un calcul de tri.

### <a name="examples-of-ascending-and-descending-column-values"></a>Exemples de valeurs de colonne croissantes et décroissantes

Dans l'exemple suivant, les valeurs de la colonne D de l'état seront triées dans l'ordre croissant pour les lignes 160 à 490. En outre, les valeurs absolues de la colonne G de l'état seront triées dans 'ordre décroissant pour les lignes 610 à 940.

| Code de ligne | Description                                         | Code de format | Formules/lignes/unités associées | Solde normal | Restriction de colonne | Lier aux dimensions financières |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Trié par écart mensuel dans l'ordre croissant       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Ventes                                               |             |                             | C              |                    | 4100                         |
| 190      | Retours sur ventes                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Produits d'intérêts                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Trié par écart dans l'année en cours (en valeur absolue) dans l'ordre décroissant | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | V                  |                              |
| 610      | Ventes                                               |             |                             | C              |                    | 4100                         |
| 640      | Retours sur ventes                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Produits d'intérêts                                     |             |                             | C              |                    | 7000                         |

Voici un exemple de l'état généré.

**Analyse de l'écart (trié par écart)**

**Régions de Pékin et d'Atlanta**

**Pour les sept mois se terminant le 31 juillet 2013**

**Juillet**

**YTD**

**Réel**

**Budget**

**Variation**

**Réel**

**Budget**

**Variation**

**Trié par écart mensuel dans l'ordre croissant**

Coût des marchandises vendues

873 872

236 144

(637 728)

4 864 274

1 590 315

(3 273 959)

Salaires

97 624

65 573

(32 051)

653 884

441 664

(212 220)

Remises

36 383

24 152

(12 231)

241 562

162 670

(78 892)

Retours sur ventes

10 917

7 246

(3 671)

62 809

48 803

(14 006)

Frais de location

12 052

9 019

(3 033)

80 444

60 748

(19 696)

Dépenses de bureau

5 023

3 291

(1 732)

33 420

22 098

(11 322)

Dépenses de déplacement

7 656

7 641

(15)

51 062

51 469

407

Ventes

1 240 119

410 389

829 730

7 139 288

2 764 549

4 374 739

**Trié par écart dans l'année en cours (en valeur absolue) dans l'ordre décroissant**

Ventes

1 240 119

410 389

829 730

7 139 288

2 764 549

4 374 739

Dépenses de déplacement

7 656

7 641

(15)

51 062

51 469

407

Dépenses de bureau

5 023

3 291

(1 732)

33 420

22 098

(11 322)

Retours sur ventes

10 917

7 246

(3 671)

62 809

48 803

(14 006)

Frais de location

12 052

9 019

(3 033)

80 444

60 748

(19 696)

Remises

36 383

24 152

(12 231)

241 562

162 670

(78 892)

Salaires

97 624

65 573

(32 051)

653 884

441 664

(212 220)

Coût des marchandises vendues

873 872

236 144

(637 728)

4 864 274

1 590 315

(3 273 959)

## <a name="specify-a-format-override-cell"></a>Spécifier une cellule de remplacement de format
La cellule **Remplacement de format** spécifie la mise en forme utilisée pour la ligne lorsque l'état est imprimé. Cette mise en forme remplace la mise en forme spécifiée dans la définition de colonne et la définition d'état. Par défaut, la mise en forme spécifiée dans ces définitions est la devise. Si une ligne de l'état répertorie le nombre d'immobilisations, comme le nombre de bâtiments, et qu'une autre ligne répertorie la valeur monétaire de ces immobilisations, vous pouvez remplacer la mise en forme de la devise et entrer une mise en forme numérique pour la ligne qui spécifie le nombre de bâtiments. Vous spécifiez ces informations dans la boîte de dialogue **Dépassement de format**. Les options disponibles dépendent de la catégorie de format sélectionnée. La zone **Exemple** de la boîte de dialogue spécifie des exemples de format. Les catégories de formats d'export suivants sont disponibles :

-   Mise en forme de devise
-   Mise en forme numérique
-   Mise en forme de pourcentage
-   Mise en forme personnalisée

### <a name="override-cell-formatting"></a>Remplacer la mise en forme de la cellule

1.  Dans le Concepteur de rapports, ouvrez la définition de ligne à modifier.
2.  Dans la ligne pour laquelle remplacer le format, double-cliquez sur la cellule dans la colonne **Remplacement de format**.
3.  Dans la boîte de dialogue **Remplacement de format**, sélectionnez les options de mise en forme à utiliser pour cette ligne dans l'état.
4.  Cliquez sur **OK**.

### <a name="currency-formatting"></a>Mise en forme de devise

La mise en forme de devise s'applique au montant fiscal et inclut le symbole de devise. Les options suivantes sont disponibles :

-   **Symbole de devise** – Le symbole de la devise pour l'état. Cette valeur remplace le paramètre des **Options régionales** pour les informations de l'entreprise.
-   **Nombres négatifs** – Les nombres négatifs peuvent avoir un signe moins (-), ils peuvent apparaître entre parenthèses, ou peuvent être munis d'un triangle (∆).
-   **Décimales** – Le nombre de chiffres à afficher après le séparateur décimal.
-   **Texte de remplacement de valeur nulle** – Le texte à inclure dans l'état si le montant est 0 (zéro). Ce texte s'affiche comme la dernière ligne dans la zone **Exemple**. **Remarque :** si l'impression est supprimée pour les valeurs nulle ou une activité nulle sur la période, ce texte est supprimé.

### <a name="numeric-formatting"></a>Mise en forme numérique

La mise en forme numérique s'applique à n'importe quel montant et n'inclut pas de symbole de devise. Les options suivantes sont disponibles :

-   **Nombres négatifs** – Les nombres négatifs peuvent avoir un signe moins (-), ils peuvent apparaître entre parenthèses, ou peuvent être munis d'un triangle (∆).
-   **Décimales** – Le nombre de chiffres à afficher après le séparateur décimal.
-   **Texte de remplacement de valeur nulle** – Le texte à inclure dans l'état si le montant est 0 (zéro). Ce texte s'affiche comme la dernière ligne dans la zone **Exemple**. **Remarque :** si l'impression est supprimée pour les valeurs nulle ou une activité nulle sur la période, ce texte est supprimé.

### <a name="percentage-formatting"></a>Mise en forme de pourcentage

La mise en forme de pourcentage inclut le signe de pourcentage (%). Les options suivantes sont disponibles :

-   **Nombres négatifs** – Les nombres négatifs peuvent avoir un signe moins (-), ils peuvent apparaître entre parenthèses, ou peuvent être munis d'un triangle (∆).
-   **Décimales** – Le nombre de chiffres à afficher après le séparateur décimal.
-   **Texte de remplacement de valeur nulle** – Le texte à inclure dans l'état si le montant est 0 (zéro). Ce texte s'affiche comme la dernière ligne dans la zone **Exemple**. **Remarque :** si l'impression est supprimée pour les valeurs nulle ou une activité nulle sur la période, ce texte est supprimé.

### <a name="custom-formatting"></a>Mise en forme personnalisée

Utilisez la catégorie de mise en forme personnalisée pour créer un remplacement de format personnalisé. Les options suivantes sont disponibles :

-   **Type** – Le format personnalisé.
-   **Texte de remplacement de valeur nulle** – Le texte à inclure dans l'état si le montant est 0 (zéro). Ce texte s'affiche comme la dernière ligne dans la zone **Exemple**. **Remarque :** si l'impression est supprimée pour les valeurs nulle ou une activité nulle sur la période, ce texte est supprimé.

Le type doit représenter la valeur positive, puis la valeur négative. En général, vous entrez un format similaire qui différencie les valeurs positives et des valeurs négatives. Par exemple, pour spécifier que les valeurs positives et négatives ont deux décimales, mais que les valeurs négatives apparaissent entre parenthèses, entrez **0.00;(0.00)**. Le tableau suivant présente des formats personnalisés que vous pouvez utiliser pour contrôler le format de vos valeurs. Tous ces exemples démarrent à la valeur 1234,56.

| Format                         | Positif   | Négatif     | Zéro    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);“”       | 1 235      | (1 235)      | (Vide) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1 234,56   | (1 234,56)   | zéro    |
| 0.00%;(0.00%)                  | 123456,00 % | (123456,00 %) | 0,00 %   |

## <a name="specify-a-normal-balance-cell"></a>Spécifier une cellule de solde normal
La cellule **Solde normal** dans une définition de ligne contrôle du signe des montants dans une ligne. Pour inverser le signe d'une ligne, ou si le solde normal d'un compte est un crédit, entrez un **C** dans la cellule **Solde normal** pour cette ligne. Le générateur d'états inverse le signe de tous les comptes de bilan dans cette ligne. Lorsque le générateur d'états convertit ces comptes, il supprime la caractéristique débit/crédit de tous les montants et rend la totalisation immédiate. Par exemple, pour calculer le bénéfice, vous soustrayez les dépenses du revenu. Généralement, les lignes calculées et totalisées ne sont pas affectées par le code **C**. Toutefois, le contrôle d'impression **XCR** dans la définition de colonne inverse le signe de toute ligne contenant un **C** dans la colonne **Solde normal**. Cette mise en forme est particulièrement importante lorsque vous souhaitez afficher tous les écarts défavorables comme des montants négatifs. Si un nombre calculé ou totalisé a un signe erroné, entrez un **C** dans la cellule **Solde normal** pour la ligne pour inverser le signe.

## <a name="specify-a-row-modifier-cell"></a>Spécifier une cellule de modificateur de ligne
Le contenu de la cellule **Modificateur de ligne** dans une définition de ligne remplace les exercices, les périodes, ainsi que d'autres informations spécifiées dans la définition de colonne pour cette ligne. Le modificateur sélectionné s'applique à chaque compte de la ligne. Vous pouvez modifier chaque ligne à l'aide d'un ou plusieurs des types de modificateurs suivants :

-   Modificateurs de compte
-   Modificateurs de code registre
-   Attributs de compte et de transaction

### <a name="override-a-column-definition"></a>Remplacer une définition de colonne

1.  Dans le Concepteur de rapports, ouvrez la définition de ligne à modifier.
2.  Dans la ligne dans laquelle vous souhaitez remplacer la définition de colonne, double-cliquez sur la cellule **Modificateur de ligne**.
3.  Dans la boîte de dialogue **Modificateur de ligne**, sélectionnez une option dans le champ **Modificateur de compte**. Pour obtenir une description des options, consultez la section « Modificateurs de compte ».
4.  Dans le champ **Modificateur de code registre**, sélectionnez le code registre à utiliser pour la ligne.
5.  Sous **Attributs**, procédez comme suit pour ajouter une entrée pour chaque attribut devant être inclus avec le code de ligne :
    1.  Double-cliquez sur la cellule **Attribut**, puis sélectionnez un nom d'attribut. **Attention :** remplacez le symbole dièse (\#) par une valeur numérique.
    2.  Double-cliquez sur la cellule **À partir de**, puis entrez la première valeur de la plage.
    3.  Double-cliquez sur la cellule **Jusqu'à**, puis entrez la dernière valeur de la plage.

6.  Cliquez sur **OK**.

### <a name="account-modifiers"></a>Modificateurs de compte

Lorsque vous sélectionnez un compte spécifique, le générateur d'états combine généralement le compte et les exercices, les périodes, et les autres informations que vous spécifiez dans la définition de colonne. Vous pouvez utiliser des informations différentes, comme différentes des périodes fiscales, pour des lignes spécifiques. Le tableau suivant décrit la disponibilité des modificateurs de compte. Remplacez le symbole dièse (\#) par une valeur égale ou inférieure au nombre de périodes d'un exercice.

| Modificateur de compte | Ce qui est imprimé                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Le solde d'ouverture pour un compte.                                                     |
| /\#              | Le solde pour la période spécifiée.                                                     |
| /-\#             | Le solde pour la période qui se situe \# périodes avant la période actuelle.                  |
| /+\#             | Le solde pour la période qui se situe \# périodes après la période actuelle.                   |
| /C               | Solde de la période actuelle.                                                       |
| /C-\#            | Le solde pour la période qui se situe \# périodes avant la période actuelle.                  |
| /C+\#            | Le solde pour la période qui se situe \# périodes après la période actuelle.                   |
| /Y               | Le solde de l'année en cours jusqu'à la période actuelle.                                      |
| /Y-\#            | Le solde de l'année en cours jusqu'à la période qui se situe \# périodes avant la période actuelle. |
| /Y+\#            | Le solde de l'année en cours jusqu'à la période qui se situe \# périodes après la période actuelle.  |

### <a name="book-code-modifiers"></a>Modificateurs de code registre

Vous pouvez limiter une ligne à un code registre existant. La définition de colonne doit inclure au moins une colonne **FD** ayant un code registre. **Remarque :** la restriction de code registre pour une ligne remplace les restrictions de code registre dans la définition de colonne pour cette ligne.

### <a name="account-and-transaction-attributes"></a>Attributs de compte et de transaction

Certains systèmes comptables prennent en charge les attributs de compte et de transaction dans les données financières. Ces attributs fonctionnent comme des segments de compte virtuel, et peuvent comporter des informations supplémentaires sur le compte ou la transaction. Ces informations supplémentaires peuvent être des ID de compte, des ID de lots, des codes postaux ou d'autres attributs. Si votre système comptable prend en charge les attributs, vous pouvez utiliser les attributs de compte ou les attributs de transaction comme modificateurs de ligne dans la définition de ligne. Pour plus d'informations sur la manière de remplacer les informations de ligne, consultez la section « Remplacer une définition de colonne » plus haut dans le présent article.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Spécifier un lien vers la cellule Dimensions financières
La cellule **Lier aux dimensions financières** contient des liens vers des données financières qui doivent être incluses dans chaque ligne d'un état. Cette cellule contient des valeurs de dimension, mais vous pouvez spécifier des cellules dans une feuille de calcul Microsoft Excel en lieu et place ou en complément des valeurs de segment ou des valeurs de dimension. Pour ouvrir la boîte de dialogue **Dimensions**, double-cliquez sur la cellule **Lier aux dimensions financières**. **Remarque :** le générateur d'état ne peut pas sélectionner de comptes, de dimensions ni de champs à partir du système ERP Microsoft Dynamics comportant des caractères réservés suivants : &, \*, \[, \], {, ou }. Pour spécifier des informations pour une ligne qui est déjà dans la définition de ligne, ajoutez les informations dans la cellule **Lier aux dimensions financières**. Pour ajouter de nouvelles lignes liées aux données financières, utilisez la boîte de dialogue **Insérer des lignes à partir de** pour créer des lignes dans la définition d'état. L'en-tête de colonne change, selon la configuration de la colonne, comme indiqué dans le tableau suivant.

| Type de lien sélectionné       | La description de la colonne Lier change comme suit |
|----------------------------------|----------------------------------------------------|
| Dimensions financières             | Lier aux dimensions financières                       |
| Feuille de calcul externe               | Lier à une feuille de calcul                                  |
| Dimensions financières + feuille de calcul | Lier aux dimensions financières + à une feuille de calcul           |
| État Management Reporter       | État Management Reporter                         |

### <a name="specify-a-dimension-or-range"></a>Spécifier une dimension ou une plage

1.  Dans le Concepteur de rapports, ouvrez la définition de ligne à modifier.
2.  Double-cliquez sur une cellule dans la colonne **Lier aux dimensions financières**.
3.  Dans la boîte de dialogue **Dimensions**, double-cliquez sur une cellule sous le nom de la dimension.
4.  Dans la boîte de dialogue pour la dimension, sélectionnez **Individuelle ou plage**.
5.  Dans le champ **À partir de**, entrez la dimension de départ, ou cliquez sur ![Parcourir](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Parcourir") pour rechercher des dimensions disponibles. Pour entrer une plage de dimensions, entrez la dimension de fin dans le champ **Jusqu'à**.
6.  Cliquez sur **OK** pour fermer la boîte de dialogue pour la dimension. La boîte de dialogue **Dimensions** affiche la dimension ou la plage mise à jour.
7.  Cliquez sur **OK** pour fermer la boîte de dialogue **Dimensions**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Afficher les comptes à solde nul dans une définition de ligne
Par défaut, le générateur d'états n'imprime aucune ligne n'ayant pas de solde correspondant dans les données financières. Par conséquent, vous pouvez créer une définition de ligne qui inclut toutes les valeurs de segment naturel ou toutes les valeurs de dimension, puis utiliser cette définition de ligne pour n'importe lequel de vos départements.

### <a name="modify-zero-balance-settings"></a>Modifier les paramètres de solde nul

1.  Dans le générateur d'état, ouvrez la définition d'état à modifier.
2.  Sous l'onglet **Paramètres**, sous **Autre mise en forme**, sélectionnez les options pour la définition de ligne utilisée dans la définition d'état.
3.  Dans le menu **Fichier**, cliquez sur **Enregistrer** pour enregistrer vos modifications.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Utiliser des caractères génériques et des plages dans une définition de ligne
Quand vous entrez une valeur de segment naturel dans la boîte de dialogue **Dimensions**, vous pouvez utiliser un caractère générique (? ou \*) à n'importe quelle position d'un segment. Le générateur d'états extrait toutes les valeurs pour les positions définies, sans tenir compte des caractères génériques. Par exemple, la définition de ligne ne contient que des valeur de segment naturel, et les segments naturels ont quatre caractères. En entrant **6???** dans une ligne, vous demandez au générateur d'états d'inclure tous les comptes ayant une valeur de segment naturel commençant par 6. Si vous entrez **6\***, vous obtenez les mêmes résultats, mais ceux-ci incluent en plus les valeurs d'autre longueur, telles que **60** et **600000**. Le générateur d'états remplace chaque caractère générique (?) par la gamme complète des valeurs possibles, qui incluent des lettres et des caractères spéciaux. Par exemple, dans la plage **12?0** à **12?4**, le caractère générique dans **12?0** est remplacé par la valeur la plus faible dans le jeu de caractères, et le caractère générique dans **12?4** est remplacé par la valeur la plus élevée dans le jeu de caractères. **Remarque :** vous devez éviter d'utiliser des caractères génériques pour les comptes de début et de fin de plages. Si vous utilisez des caractères génériques dans le compte de début ou le compte de fin, vous pouvez obtenir des résultats inattendus.

### <a name="single-segment-or-single-dimension-ranges"></a>Plages comprenant un seul segment ou une seule dimension

Vous pouvez spécifier une plage de valeurs de segment ou de valeurs de dimension. L'avantage de spécifier une plage est que vous n'avez pas besoin mettre la définition de ligne à jour à chaque fois qu'une nouvelle valeur de segment ou de dimension est ajoutée aux données financières. Par exemple, la plage **+Compte=\[6100:6900\]** extrait les valeurs des comptes 6100 à 6900 dans le montant de ligne. Lorsqu'une plage inclut un caractère générique (?), le générateur d'états n'évalue pas la plage caractère par caractères. Au lieu de cela, on détermine le haut et le bas de la plage, puis les valeurs extrêmes dans cette plage et toutes les valeurs entre elles. **Remarque :** le générateur d'état ne peut pas sélectionner de comptes, de dimensions ni de champs à partir du système ERP Microsoft Dynamics comportant des caractères réservés suivants : &, \*, \[, \], {, ou }. Vous pouvez ajouter une esperluette (&) que lorsque vous générez automatiquement des définitions de ligne à l'aide de la boîte de dialogue **Insérer des lignes à partir de dimensions** .

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Plages de plusieurs segment ou de plusieurs dimensions

Lorsque vous entrez une plage à l'aide de combinaisons de plusieurs valeurs de dimension, la comparaison de plage est effectuée sur la base d'une dimension financière\dimension par dimension. La comparaison de plage ne peut pas être effectuée caractère par caractère ou sur la base d'un segment partiel. Par exemple, l'intervalle **+Compte=\[5000:6000\], Département=\[1000:2000\], Centre de coût=\[00\]** inclut uniquement les comptes correspondant à chaque segment. Dans ce cas, la première dimension doit se situer dans la plage de 5000 à 6000, la deuxième dimension doit se situer dans la plage de 1000 à 2000, et la dernière dimension doit être 00. Par exemple, **+Compte=\[5100\], Département=\[1100\], Centre de coût=\[01\]** n'est pas inclus dans l'état, car le dernier segment est hors de la plage spécifiée. Si une valeur de segment inclut des espaces, entourez cette valeur par des crochets (\[ \]). Les valeurs suivantes sont valides pour un segment à quatre caractères : **\[ 234\], \[123 \], \[1 34\]**. Les valeurs de dimension doivent être entourées de crochets (\[ \]), et le générateur d'états ajoute ces crochets pour vous. Quand une plage de plusieurs segment ou de plusieurs dimensions inclut des caractères génériques (? ou \*), les extrémités haute et basse de la plage entière de plusieurs segments ou de plusieurs dimensions sont déterminées, puis les valeurs de fin et toutes les valeurs entre elles sont incluses. Si vous avez une plage étendue, comme toute la plage de comptes de 40000 à 99999, vous devez spécifier un compte de début et un compte de fin valides à chaque fois que c'est possible. **Remarque :** le générateur d'état ne peut pas sélectionner de comptes, de dimensions ni de champs à partir du système ERP Microsoft Dynamics comportant des caractères réservés suivants : &, \*, \[, \], {, ou }. Vous pouvez ajouter une esperluette (&) que lorsque vous générez automatiquement des définitions de ligne à l'aide de la boîte de dialogue **Insérer des lignes à partir de dimensions** .

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Ajouter ou soustraire d'autres comptes dans une définition de ligne
Pour ajouter ou soustraire des montants en devises dans un compte des montants en devises dans un autre compte, vous pouvez utiliser le signe plus (+) et le signe moins (-) dans la cellule **Lier aux dimensions financières**. Le tableau suivant présente les formats acceptables pour ajouter et soustraire des liens aux données financières.

| Opération                                                                               | Utiliser ce format                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Additionner deux comptes pleinement qualifiés.                                                       | +Division=\[000\], Compte=\[1205\], Département=\[00\]+Division=\[100\], Compte=\[1205\], Département=\[00\] |
| Additionner deux valeurs de segment.                                                                 | +Compte=\[1205\]+Compte=\[1210\]                                                                           |
| Additionner des valeurs de segment qui incluent des caractères génériques.                                    | +Compte=\[120?+Compte=\[11??\]                                                                             |
| Additionner une plage de comptes pleinement qualifiés.                                                | +Division=\[000:100\], Compte=\[1205\], Département=\[00\]                                                   |
| Additionner une plage de valeurs de segment.                                                          | +Account=\[1200:1205\]                                                                                       |
| Additionner une plage de valeurs de segment qui incluent des caractères génériques.                         | +Compte=\[120?:130?\]                                                                                       |
| Soustraire un compte pleinement qualifié d'un autre compte pleinement qualifié.              | +Division=\[000\], Compte=\[1205\], Département=\[00\]-Division=\[100\], Compte=\[1205\], Département=\[00\] |
| Soustraire une valeur de segment d'une autre valeur de segment.                                  | +Compte=\[1205\]-Compte=\[1210\]                                                                           |
| Soustraire une valeur de segment qui inclut un caractère générique d'une autre valeur de segment. | +Compte=\[1200\]-Compte=\[11??\]                                                                           |
| Soustraire une plage de comptes pleinement qualifiés.                                           | -Division=\[000:100\], Compte=\[1200:1205\], Département=\[00:01\]                                           |
| Soustraire une plage de valeurs de segment.                                                     | -Compte=\[1200:1205\]                                                                                       |
| Soustraire une plage de valeurs de segment qui incluent des caractères génériques.                    | -Compte=\[120?:130?\]                                                                                       |

Bien que vous puissiez modifier les comptes directement, vous pouvez également utiliser la boîte de dialogue **Dimensions** pour appliquer la mise en forme correcte à vos liaisons aux données financières. Toutes ces valeurs peuvent comporter des caractères génériques (? ou \*). Toutefois, le générateur d'état ne peut pas sélectionner de comptes, de dimensions ni de champs à partir du système ERP Microsoft Dynamics comportant des caractères réservés suivants : &, \*, \[, \], {, ou }. **Remarque :** pour soustraire des valeurs, vous devez mettre des parenthèses autour de ces valeurs. Par exemple, si vous entrez **450?-(4509)**, cela s'affiche comme **+Compte=\[4509\]-Account=\[450?\]**, et vous demandez au générateur d'états de soustraire le montant pour le segment de compte 4509 du montant de tous les segments de compte commençant par 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Ajouter ou soustraire des comptes d'autres comptes

1.  Dans le Concepteur de rapports, ouvrez la définition de ligne à modifier.
2.  Dans la ligne appropriée, double-cliquez sur la cellule dans la colonne **Lier aux dimensions financières**.
3.  Dans la première ligne de la boîte de dialogue **Dimensions**, procédez comme suit :
    1.  Dans le premier champ, sélectionnez les dimensions (par défaut), ou cliquez pour ouvrir la boîte de dialogue **Gérer les ensembles de dimensions**, où vous pouvez créer, modifier, copie, ou supprimer un ensemble.
    2.  Double-cliquez sur la cellule **Opérateur+/-**, puis sélectionnez l'opérateur plus (**+**) ou moins (**-**) qui s'applique à une ou plusieurs valeurs de dimension ou ensembles de la ligne.
    3.  Dans la colonne de valeur de dimension appropriée, double-cliquez sur la cellule pour ouvrir la boîte de dialogue **Dimensions** et sélectionnez si cette valeur de dimension concerne une plage ou une valeur individuelle, un jeu de valeurs de dimension ou des comptes de totalisation. Pour obtenir une description des champs dans la boîte de dialogue **Dimensions**, consultez la section « Description de la boîte de dialogue Dimension ».
    4.  Entrez des valeurs de segment dans la colonne **À partir de** et la colonne **Jusqu'à**.

4.  Répétez les étapes 2 à 3 pour ajouter d'autres opérations.

**Remarque :** l'opérateur s'applique à toutes les dimensions dans la ligne.

## <a name="description-of-the-dimensions-dialog-box"></a>Boîte de dialogue Description des dimensions
Le tableau suivant décrit les champs de la boîte de dialogue **Dimensions**.

| Article                | Description                                                                                                                                                                                                                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Individuelle ou plage | Dans le champ **À partir de**, entrez le nom d'un compte, ou cliquez sur le bouton **Parcourir** ![Parcourir](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Parcourir") pour chercher le compte. Pour sélectionner une plage, entrez ou cherchez une valeur dans le champ **Jusqu'à**.                                             |
| Ensemble de valeurs de dimension | Dans le champ **Nom**, entrez le nom d'un ensemble de valeurs de dimensions. Pour créer, modifier, copier ou supprimer un ensemble, cliquez sur **Gérer les ensembles de valeurs de dimension**. Le champ **Formule** est rempli avec la formule issue de la cellule **Lier aux dimensions financières** pour cette valeur de dimension définie dans la définition de ligne. |
| Compte de totalisation   | Dans le champ **Nom**, entrez ou recherchez une dimension des comptes de totalisation. Le champ **Formule** est rempli avec la formule issue de la cellule **Lier aux dimensions financières** pour ce compte de totalisation dans la définition d'état.                                                                       |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Ajouter des ensembles de valeurs de dimension dans une définition de ligne
Un ensemble de valeurs de dimension est un groupe de valeurs de dimension auquel on a donné un nom. Un ensemble de valeurs de dimensions peut contenir des valeurs dans une seule dimension, mais vous pouvez utiliser un ensemble de valeurs de dimension dans plusieurs définitions de ligne, définitions de colonne, définitions d'arborescence de génération d'états et définitions d'état. Vous pouvez également combiner des ensembles de valeurs de dimension dans une définition d'état. Lorsqu'une modification de vos données financières requiert que vous modifiiez l'ensemble de valeurs de dimension, vous pouvez mettre à jour la définition de l'ensemble des valeurs de dimension, et cette mise à jour s'appliquera à toutes les zones utilisant l'ensemble de valeurs de dimension. Par exemple, si vous indiquez souvent une plage de valeurs pour lier vos données financières, comme les valeurs de 5100 à 5600, vous pouvez affecter cette plage à un ensemble de comptes nommé Ventes. Après avoir créé un ensemble de valeurs de dimension, vous pouvez sélectionner cet ensemble comme liaison aux données financière. Autre exemple, si la plage de valeur de 5100 à 5600 est affectée aux Ventes, et que 4175 est affectée aux Remises, vous pouvez déterminer le total des ventes en soustrayant les Remises des Ventes. Cette opération est indiquée comme **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Créer un ensemble de valeurs de dimension

1.  Dans le générateur d'état, ouvrez la définition de ligne, de colonne ou d'arborescence à modifier.
2.  Dans le menu **Édition**, cliquez sur **Gérer les ensembles de valeurs de dimension**.
3.  Dans la boîte de dialogue **Gérer les ensembles de valeurs de dimension**, dans le champ **Dimension**, sélectionnez le type de l'ensemble de valeurs de dimension à créer, puis cliquez sur **Nouveau**.
4.  Dans la boîte de dialogue **Nouveau**, entrez un nom et une description pour l'ensemble.
5.  Dans la colonne **À partir de**, double-cliquez sur une cellule.
6.  Dans la boîte de dialogue **Compte**, sélectionnez le nom du compte dans la liste, ou cherchez l'entrée dans le champ **Rechercher**. Cliquez ensuite sur **OK**.
7.  Répétez les étapes 5 à 6 dans la colonne **Jusqu'à** pour définir une formule pour cet opérateur.
8.  Lorsque la formule est terminée, cliquez sur **OK**.
9.  Dans la boîte de dialogue **Gérer les ensembles de dimensions**, cliquez sur **Fermer**.

### <a name="update-a-set-of-dimension-values"></a>Mettre à jour un ensemble de valeurs de dimension

1.  Dans le générateur d'état, ouvrez la définition de ligne, de colonne ou d'arborescence à modifier.
2.  Dans le menu **Édition**, cliquez sur **Gérer les ensembles de valeurs de dimension**.
3.  Dans la boîte de dialogue **Gérer les ensembles de valeurs de dimension**, dans le champ **Dimension**, sélectionnez le type de dimension.
4.  Dans la liste, sélectionnez l'ensemble de valeurs de dimension à définir, puis cliquez sur **Modifier**.
5.  Dans la boîte de dialogue **Modifier**, modifiez les valeurs de la formule à inclure dans l'ensemble. **Remarque :** si vous ajoutez de nouveaux comptes ou dimensions, vérifiez que vous modifiez les ensembles de valeurs de dimension existants pour incorporer les modifications.
6.  Double-cliquez sur la cellule, puis sélectionnez l'opérateur, le compte **À partir de**, et le compte **Jusqu'à** appropriés.
7.  Cliquez sur **OK** pour fermer la boîte de dialogue **Modifier** et enregistrer vos modifications.

### <a name="copy-a-dimension-set"></a>Copier un ensemble de dimensions

1.  Dans le générateur d'état, ouvrez la définition de ligne, de colonne ou d'arborescence à modifier.
2.  Dans le menu **Édition**, cliquez sur **Gérer les ensembles de valeurs de dimension**.
3.  Dans la boîte de dialogue **Gérer les ensembles de valeurs de dimension**, dans le champ **Dimension**, sélectionnez le type de dimension.
4.  Dans la liste, sélectionnez l'ensemble à copier, puis cliquez sur **Enregistrer sous**.
5.  Entrez un nouveau nom pour l'ensemble copié, puis cliquez sur **OK**.

### <a name="delete-a-dimension-set"></a>Supprimer un ensemble de dimensions

1.  Dans le générateur d'état, ouvrez la définition de ligne, de colonne ou d'arborescence à modifier.
2.  Dans le menu **Édition**, cliquez sur **Gérer les ensembles de valeurs de dimension**.
3.  Dans la boîte de dialogue **Gérer les ensembles de valeurs de dimension**, dans le champ **Dimension**, sélectionnez le type de dimension.
4.  Sélectionnez l'ensemble à supprimer, puis cliquez sur **Supprimer**. Cliquez sur **Oui** pour supprimer définitivement cet ensemble de valeurs de dimensions.


<a name="see-also"></a>Voir également :
--------

[Génération d'états financiers pour Microsoft Dynamics 365 for Operations](financial-reporting-intro.md)


