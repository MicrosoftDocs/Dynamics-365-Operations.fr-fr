---
title: "Concepteur de formule dans les états électroniques"
description: "Cette rubrique décrit l&quot;utilisation du concepteur de formule dans la génération d&quot;états électroniques. Lorsque vous créez un format pour un document électronique spécifique dans la génération d&quot;états électroniques, vous pouvez utiliser des formules de type Microsoft Excel pour que la transformation de données réponde aux exigences afin d&quot;exécuter et de mettre en forme ce document. Plusieurs types de tâches sont pris en charge : texte, date et heure, logique mathématique, informations, conversion du type de données, et autre (fonctions spécifiques au métier)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ac8d6c064ca826cc1c2fed07578ca9ce0c66ef66
ms.lasthandoff: 03/31/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Concepteur de formule dans les états électroniques

[!include[banner](../includes/banner.md)]


Cette rubrique décrit l'utilisation du concepteur de formule dans la génération d'états électroniques. Lorsque vous créez un format pour un document électronique spécifique dans la génération d'états électroniques, vous pouvez utiliser des formules de type Microsoft Excel pour que la transformation de données réponde aux exigences afin d'exécuter et de mettre en forme ce document. Plusieurs types de tâches sont pris en charge : texte, date et heure, logique mathématique, informations, conversion du type de données, et autre (fonctions spécifiques au métier).

<a name="formula-designer-overview"></a>Vue d'ensemble du concepteur de formule
-------------------------

La génération d'états électroniques prend en charge le concepteur de formule. Par conséquent, au moment de la création, vous pouvez configurer des expressions qui peuvent être utilisées pour les tâches suivantes au moment de l'exécution :

-   Transformation des données reçues de la base de données Microsoft Dynamics 365 for Operations qui doit être remplie en fonction d'un modèle de données de génération d'états électroniques qui est conçu pour être une source de données pour les formats de génération d'états électroniques (filtrage, regroupement, conversion des types de données, etc.).
-   Mise en forme des données qui doivent être émises vers un document électronique en cours de génération en accord avec la mise en forme et les conditions d'un format de génération d'états électroniques spécifique (en accord avec la langue, la culture ou le codage demandés, etc.).
-   Contrôle du processus de la génération de document électronique (activation/désactivation de l'émission de certains éléments de format en fonction des données de traitement, interruption de la création du document, lancement de messages pour les utilisateurs finaux, etc.).

La page du concepteur de formule peut être ouverte lorsque vous effectcuez l'une des opérations suivantes :

-   Lier des articles sources de données aux composants de modèle de données.
-   Lier des articles sources de données aux composants de format.
-   Effectuer la mise à jour des champs calculés dans le cadre des sources de données.
-   Définir des conditions de visibilité pour les paramètres d'entrée utilisateur.
-   Créer des transformations d'un format.
-   Définir les conditions d'activation pour les composants du format.
-   Définir les noms de fichiers pour les composants FICHIER du format.
-   Définir les conditions des validations du contrôle de processus.
-   Définir le texte de message des validations du contrôle de processus.

## <a name="designing-er-formulas"></a>Conception des formules de génération d'états électroniques
### <a name="data-binding"></a>Liaison de données

Le concepteur de formule de génération d'états électroniques permet de définir une expression qui transformera des données reçues des sources de données à remplir au consommateur de données au moment de l'exécution :

-   Des sources de données Dynamics 365 for Operations et des paramètres d'exécution à un modèle de données de génération d'états électroniques.
-   D'un modèle de données de génération d'états électroniques à un format de génération d'états électroniques.
-   Des sources de données Dynamics 365 for Operations et des paramètres d'exécution à un format de génération d'états électroniques.

La figure suivante présente la création d'une expression de ce type. Dans cet exemple, l'expression renvoie la valeur **Intrastat.AmountMST** du champ de la table **Déclaration d'échanges de biens** de Dynamics 365 for Operations, une fois que la valeur a été arrondie à deux décimales. [![picture-expression-binding](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) L'illustration suivante affiche l'utilisation d'une expression de ce type. Dans cet exemple, le résultat de l'expression conçue est rempli dans le composant **Transaction.InvoicedAmount** du modèle de données **Modèle de déclaration de taxe**. [![picture-expression-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) À l'exécution, la formule conçue, **ROUND (Intrastat.AmountMST, 2)**, arrondit la valeur du champ **AmountMST** de chaque enregistrement de la table **Déclaration d'échanges de biens** à deux décimales, et remplir la valeur arrondie dans le composant **Transaction.InvoicedAmount** du modèle de données **Déclaration des taxes**.

### <a name="data-formatting"></a>Mise en forme des données

Le concepteur de formule de génération d'états électroniques permet de définir une expression qui formate les données reçues des sources de données, afin que les données puissent être envoyées dans le cadre de la génération d'un document électronique. Si vous disposez d'une mise en forme qui doit être appliquée comme règle classique pour être réutilisée pour un format, vous pouvez entrer cette mise en forme une fois dans la configuration du format comme transformation nommée ayant une expression de mise en forme. Cette transformation nommée peut ensuite être liée à de nombreux composants dont la sortie doit être mise en forme en fonction de l'expression créée. La figure suivante présente la création d'une transformation de ce type. Dans cet exemple, la transformation **TrimmedString** prend les données entrantes du type de données **Chaîne**, et tronque les espaces de début et de fin lors du renvoi de la valeur de chaîne. [![picture-transformation-design](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) La figure suivante présente l'utilisation d'une transformation de ce type. Dans cet exemple, plusieurs composants de format qui envoient le texte comme résultat de la génération d'un document électronique au moment de l'exécution font référence à la transformation **TrimmedString** par son nom. [![picture-transformation-usage](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) Lorsque les composants de format font référence à la transformation **TrimmedString** (par exemple, le composant **partyName** dans l'illustration précédente), cela renvoie le texte comme sortie au document de génération. Le texte n'inclut pas les espaces de début et de fin. Si vous avez une mise en forme qui doit être appliquée individuellement, vous pouvez introduire cette mise en page en tant qu'expression individuelle d'une liaison d'un composant de format spécifique. La figure suivante présente une expression de ce type. Dans cet exemple, le composant de format **partyType** est lié à la source de données via une expression qui convertit les données entrante du champ **Model.Company.RegistrationType** dans la source de données en texte en majuscules qu'elle envoie comme résultat dans le document électronique. [![picture-binding-with-formula](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Contrôle des flux de processus

Le concepteur de formule de génération d'états électroniques permet de définir les expressions utilisées pour contrôler le flux de processus de génération de documents. Vous pouvez :

-   Définir des conditions qui déterminent quand un processus de création de document doit être arrêté.
-   Spécifier les expressions qui créent des messages pour l'utilisateur final, relatifs aux processus arrêtés ou lancent des messages de journal d'exécution relatifs à la continuité du processus de génération d'états.
-   Spécifier les noms de fichier de la génération de documents, et contrôler les conditions de leur création.

Chaque règle du contrôle des flux de processus est conçue comme un contrôle individuel. La figure suivante présente une validation de ce type. Voici une explication de la configuration dans cet exemple :

-   La validation est évaluée lorsque le nœud **INSTAT** est créé lors de la génération du fichier XML.
-   Si la liste des transactions est vide, la validation arrête le processus d'exécution et renvoie la valeur **FALSE**.
-   La validation renvoie un message d'erreur qui inclut le texte du libellé SYS70894 dans la langue de l'utilisateur.

[![picture-validation](./media/picture-validation.jpg)](./media/picture-validation.jpg) Exemple de validation Le concepteur de formule de génération d'états électroniques peut également être utilisé pour spécifier un nom de fichier permettant de générer un document électronique et de contrôler un processus de création de fichier. La figure suivante présente la création d'un contrôle des flux de processus de ce type. Voici une explication de la configuration dans cet exemple :

-   La liste des enregistrements de la source de données **model.Intrastat** est divisée en lots contenant jusqu'à 1 000 enregistrements.
-   Le résultat crée un fichier zip qui contient un fichier au format XML pour chaque lot qui a été créé.
-   Une expression renvoie un nom de fichier pour générer des documents électroniques en concaténant le nom et l'extension de fichier. Pour le deuxième traitement par lots et tous les traitements par lots suivants, le nom de fichier contient l'ID traitement par lots comme suffixe.
-   Une expression active (en renvoyant la valeur **TRUE**) le processus d'une création de fichier pour les lots contenant au moins un enregistrement.

[![picture-file-control](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Syntaxe de base

Les expressions de génération d'états électroniques peuvent contenir le tout ou partie des éléments suivants :

-   Constantes
-   Opérateurs
-   Références
-   Chemins d'accès
-   Fonctions

#### <a name="constants"></a>Constantes

Vous pouvez utiliser le texte et les constantes numériques (valeurs qui ne sont pas calculées) lorsque vous concevez des expressions. Par exemple, l'expression **VALUE ("100") + 20 ** utilise la constante 20 et la constante de chaîne « 100 », et renvoie la valeur numérique **120**. La formule de génération d'états électroniques prend en charge les séquences d'échappement, ce qui signifie que vous pouvez spécifier cette partie de l'expression qui doit être traitée différemment. Par exemple, l'expression **"Léon Tolstoï ""Guerre et paix"" Volume 1"** renvoie la chaîne de texte **Léon Tolstoï "Guerre et paix" Volume 1**.

#### <a name="operators"></a>Opérateurs

La table suivante indique les opérateurs arithmétiques que vous pouvez utiliser pour effectuer des opérations mathématiques de base, telles que l'addition, la soustraction, la division, et la multiplication.

| Opérateur | Signifie              | Exemple |
|----------|----------------------|---------|
| +        | Addition             | 1+2     |
| -        | Négation de soustraction | 5-2 -1  |
| \*       | Multiplication       | 7\*8    |
| /        | Division             | 9/3     |

La table suivante indique les opérateurs de comparaison qui sont pris en charge, et que vous pouvez utiliser pour comparer deux valeurs.

| Opérateur | Signifie                  | Exemple    |
|----------|--------------------------|------------|
| =        | Egal                    | X=Y        |
| &gt;     | Supérieur             | X&gt;Y     |
| &lt;     | Inférieur à                | X&lt;Y     |
| &gt;=    | Supérieur ou égal à | X&gt;=Y    |
| &lt;=    | Inférieur ou égal à    | X&lt;=Y    |
| &lt;&gt; | Différent de             | X&lt;&gt;Y |

En outre, vous pouvez utiliser une esperluette (&) comme opérateur de concaténation de texte pour lier, ou concaténer, une ou plusieurs chaînes de texte en un bloc de texte unique.

| Opérateur | Signifie     | Exemple                                        |
|----------|-------------|------------------------------------------------|
| &        | Concaténer | "Rien à imprimer" & ": " & "aucun enregistrement trouvé" |

#### <a name="operator-precedence"></a>Priorité des opérateurs

L'ordre dans lequel les parties d'une expression de composant sont évaluées est important. Par exemple, le résultat de l'expression** 1 + 4 / 2** diffère selon que l'addition ou la division est effectuée en premier. Vous pouvez utiliser des parenthèses pour définir explicitement la manière dont une expression est évaluée. Par exemple, pour indiquer que l'addition doit être exécutée en premier, vous pouvez modifier l'expression précédente comme suit : **(1 + 4) / 2**. Si l'ordre des opérations à effectuer dans une expression n'est pas définie explicitement, l'ordre est basé sur la priorité par défaut attribuée aux opérateurs pris en charge. Les tables suivantes indiquent les opérateurs et leur priorité. Les opérateurs qui ont la priorité la plus élevée (par exemple, 7) sont évalués avant les opérateurs ayant une priorité inférieure (par exemple, 1).

| Priorité | Opérateurs      | Syntaxe                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Regroupement       | ( … )                                                    |
| 6          | Accès des membres  | … . …                                                    |
| 5          | Appel de fonction  | … ( … )                                                  |
| 4          | Multiplicateur | … \* … … / …                                             |
| 3          | Supplémentaire       | … + … … - …                                              |
| 2          | Comparaison     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Séparation     | … , …                                                    |

Les opérateurs sur la même ligne ont une priorité identique. Si une expression inclut plusieurs de ces opérateurs, l'expression est évaluée de gauche à droite. Par exemple, l'expression **1 + 6 / 2 \* 3 &gt; 5** renvoie la valeur **true**. Il est recommandé d'utiliser des parenthèses pour indiquer explicitement l'ordre d'évaluation des expressions, afin de faciliter la lecture et la mise à jour des expressions.

#### <a name="references"></a>Références

Toutes les sources de données du composant de génération d'états électroniques actuel (modèle ou format) qui sont disponible lors de la création d'une expression peuvent servir de références nommées. Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **ReportingDate** qui renvoie une valeur du type de données **DATETIME**. Pour obtenir cette valeur correctement mise en forme dans la génération de document, vous pouvez faire référence à la source de données dans l'expression comme suit : **DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")** Tous les caractères du nom d'une source de données de référencement qui ne représentent pas une lettre de l'alphabet doivent être précédés d'un guillemet simple ('). Si le nom d'une source de données de référencement contient au moins un symbole qui ne représente pas une lettre de l'alphabet (par exemple, les signes de ponctuation ou tous les autres symboles écrits), le nom doit être placé entre guillemets simples ('). Voici quelques exemples :

-   La source de données **Date & heure d'aujourd'hui** doit être utilisée dans une expression de génération d'états électroniques comme suit : **'Date et heure d'aujourd'hui'**
-   La méthode **name()** de la source de données **Customers** doit être référencée dans l'expression de génération d'états électroniques sous la forme : **Clients.'nom()'**

#### <a name="path"></a>Chemin

Lorsqu'une expression fait référence à une source de données structurée, vous pouvez utiliser la définition de chemin d'accès pour sélectionner un élément primitif spécifique de cette source de données. Un point (.) est utilisé pour séparer les éléments distincts d'une source de données structurée. Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement** InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient des valeurs numériques. Par conséquent, vous pouvez concevoir l'expression suivante pour calculer le montant facturé : **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**

#### <a name="functions"></a>Fonctions

La section suivante décrit les fonctions pouvant être utilisées dans les expressions de génération d'états électroniques. Toutes les sources de données de contexte d'expression (modèle de données ou format de génération d'états électroniques actuel) ainsi que les constantes peuvent être utilisées en tant que paramètres des fonctions d'appel en accord avec la liste des arguments de fonction d'appel. Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement** InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient des valeurs numériques. Par conséquent, pour calculer le montant facturé vous pouvez concevoir l'expression suivante qui utilise la fonction d'arrondi de génération d'états électroniques intégrée : **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**

## <a name="supported-functions"></a>Fonctions prises en charge.
Les tables suivantes décrivent les fonctions de manipulation des données que vous pouvez utiliser pour concevoir des modèles de données et des états de génération d'états électroniques. La liste de fonctions n'est pas définitive et peut être étendue par les développeurs. Pour afficher la liste des fonctions que vous pouvez utiliser, accédez au volet de fonctionnalités du concepteur de formule de génération d'états électroniques.

### <a name="date-and-time-functions"></a>Fonctions de date et d'heure

| Fonction                                   | Description                                                                                                                                                                                                                                                                                                                                                      | Exemple                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (datetime, days)                   | Ajoutez le nombre de jours spécifié à la valeur datetime spécifiée.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** renvoie la date et l'heure, sept jours dans le futur.                                                                                                                                                                                                                            |
| DATETODATETIME (date)                      | Convertit la valeur de date spécifiée en valeur de date et d'heure.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. 'getCurrentDate()')** renvoie la date de session actuelle de Dynamics 365 for Operations, 12/24/2015, comme **12/24/2015 12:00:00 AM**. Dans cet exemple, **CompInfo** est une source de données de génération d'états électroniques de type **Dynamics 365 for Operations/Table** qui fait référence à la table CompanyInfo. |
| NOW ()                                     | Permet de renvoyer la date et l'heure du serveur d'applications Dynamics 365 for Operations comme valeur de date et d'heure.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Permet de renvoyer la date et l'heure du serveur d'applications Dynamics 365 for Operations comme valeur de date.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Renvoie une valeur de date **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Renvoie une valeur de date et d'heure **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (datetime, format)          | Convertit la valeur de date et d'heure spécifiée en une chaîne dans le format spécifié. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy")** renvoie la date du serveur d'applications Dynamics 365 for Operations actuelle, 12/24/2015, comme **"24-12-2015"**, conformément au format personnalisé spécifié.                                                                                                          |
| DATETIMEFORMAT (datetime, format, culture) | Convertit la valeur de date et d'heure spécifiée en une chaîne dans le format et la [culture](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) spécifiés. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "d", "de")** renvoie la date du serveur d'applications Dynamics 365 for Operations actuelle, 12/24/2015, comme **"24.12.2015"**, conformément à la culture allemande sélectionnée.                                                                                                             |
| SESSIONTODAY ()                            | Renvoie la date de la session Dynamics 365 for Operations comme valeur de date.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Renvoie la date et l'heure de la session Dynamics 365 for Operations comme valeur de date et d'heure.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (date, format)                  | Retourne la représentation sous forme de chaîne de la date à l'aide du format spécifié.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** renvoie la date de la session Dynamics 365 for Operations actuelle, 12/24/2015, comme "**24-12-2015**", conformément au format personnalisé spécifié.                                                                                                                      |
| DATEFORMAT (date, format, culture)         | Convertit la valeur de date spécifiée en une chaîne dans le format et la [culture](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) spécifiés. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** renvoie la date de la session Dynamics 365 for Operations actuelle, 12/24/2015, comme **"24.12.2015"**, conformément à la culture allemande sélectionnée.                                                                                                                       |

### <a name="list-functions"></a>Fonctions de liste

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonction</th>
<th>description ;</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (input, length)</td>
<td>Fractionne la chaîne d'entrée spécifiée en sous-chaînes, dans la longueur spécifiée. Renvoie le résultat comme nouvelle liste.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> renvoie une liste composée de deux enregistrements avec un champ <strong>CHAÎNE</strong>. Le champ du premier enregistrement contient le texte <strong>&quot;abc&quot;</strong>, et le champ du deuxième enregistrement contient le texte <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (list, number)</td>
<td>Fractionne la liste spécifiée en lots, dont chacun contient le nombre d'enregistrements spécifié. Renvoie le résultat comme nouvelle liste de traitements par lots contenant les éléments suivants :
<ul>
<li>Traitements par lots comme listes régulières (composant <strong>Valeur</strong>)</li>
<li>Numéro de traitement par lots actuel (composant <strong>BatchNumber</strong>)</li>
</ul></td>
<td>Dans l'exemple suivant, la source de données <strong>Lignes</strong> est créée sous la forme d'une liste de trois enregistrements, qui est divisée en traitements par lots, dont chacun contient jusqu'à deux enregistrements. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> Voici la structure de format, dans laquelle les liaisons à la source de données <strong>Lignes</strong> sont créées pour générer une sortie au format XML qui répertorie les nœuds individuels de chaque lot et les enregistrements qu'il contient. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> Voici le résultat de l'exécution du format conçu. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, ...])</td>
<td>Renvoie une liste créée à partir des arguments spécifiés.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> renvoie un enregistrement vide, dans lequel la liste des champs contient tous les champs des listes d'enregistrements <strong>MainData</strong> et <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (list 1, list 2, ...)</td>
<td>Renvoie une liste conjointe créée à partir des listes d'arguments spécifiés.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> renvoie la liste des six enregistrements, dans lequel un champ de type de données <strong>STRING</strong> contient une seule lettre.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (list)</td>
<td>Renvoie la valeur <strong>TRUE</strong> si la liste spécifiée ne contient aucun élément. Sinon, renvoie la valeur <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (list)</td>
<td>Renvoie une liste vide à l'aide de la liste spécifiée comme source pour la structure de liste.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> renvoie une nouvelle liste vide ayant la même structure que la liste qui est renvoyée par la fonction <strong>SPLIT</strong>.</td>
</tr>
<tr class="odd">
<td>FIRST (list)</td>
<td>Renvoie le premier enregistrement de la liste spécifiée, si cet enregistrement n'est pas vide. Sinon, entraîne une exception.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (list)</td>
<td>Renvoie le premier enregistrement de la liste spécifiée, si cet enregistrement n'est pas vide. Sinon, renvoie un enregistrement <strong>null</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (list)</td>
<td>Renvoie une liste qui contient uniquement le premier élément de la liste spécifiée.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (path)</td>
<td>Renvoie une nouvelle liste aplatie qui représente tous les articles correspondant au chemin spécifié. Le chemin doit être défini comme le chemin d'accès valide de la source de données vers un élément de source de données d'un type de données de liste d'enregistrements. Le chemin d'accès aux éléments de données d'une chaîne, d'une date, etc. doit déclencher une erreur au moment de la conception dans le générateur d'expression ER.</td>
<td>Si vous entrez <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> comme source de données (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> renvoie <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (list [, expression 1, expression 2, …])</td>
<td>Permet de renvoyer la liste spécifiée, qui est triée selon les arguments spécifiés qui peuvent être définis en tant qu'expressions.</td>
<td>Si <strong>Fournisseur </strong>est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable,<strong> ORDERBY (Vendors, Vendors.'name()')</strong> renvoie la liste de fournisseurs qui est triée par noms dans l'ordre croissant.</td>
</tr>
<tr class="even">
<td>REVERSE (list)</td>
<td>Permet de renvoyer la liste spécifiée dans l'ordre de tri inverse.</td>
<td>Si <strong>Fournisseur </strong>est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> renvoie la liste de fournisseurs qui est triée par noms dans l'ordre décroissant.</td>
</tr>
<tr class="odd">
<td>WHERE (list, condition)</td>
<td>Permet de renvoyer la liste spécifiée, qui est filtrée en fonction de l'état spécifié. Contrairement à la fonction <strong>FILTRER</strong>, l'état spécifié est appliqué à la liste dans la mémoire.</td>
<td>Si <strong>Vendor</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> renvoie la liste de fournisseurs faisant partie du groupe de fournisseurs 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (list)</td>
<td>Renvoie une liste composée des enregistrements énumérés de la liste spécifiée, et qui expose les éléments suivants :
<ul>
<li>Les enregistrements de la liste spécifiée comme listes régulières (composant <strong>Valeur</strong>)</li>
<li>L'index des enregistrements actuels (composant <strong>Numéro</strong>)</li>
</ul></td>
<td>Dans l'exemple suivant, la source de données <strong>Énumérée</strong> est créée sous la forme d'une liste énumérée des enregistrements fournisseurs de la source de données <strong>Fournisseurs</strong> qui fait référence à la table <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>Voici le format, dans lequel des liaisons de données sont créées pour générer la sortie au format XML qui répertorie des fournisseurs individuels comme nœuds énumérés. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> Voici le résultat de l'exécution du format conçu. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (list)</td>
<td>Renvoie le nombre d'enregistrements dans la liste spécifiée, si la liste n'est pas vide. Sinon, renvoie la valeur <strong>0</strong> (zéro).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot;, 3))</strong> renvoie <strong>2</strong>, car la fonction <strong>SPLIT</strong> crée une liste composée de deux enregistrements.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (path)</td>
<td>Renvoie une liste des enregistrements créés à partir d'un argument de l'un des types suivants :
<ul>
<li>Énumération du modèle</li>
<li>Énumération de format</li>
<li>Conteneur</li>
</ul>
La liste créée se composera des enregistrements avec les champs suivants :
<ul>
<li>Nom</li>
<li>Étiquette</li>
<li>description ;</li>
</ul>
Les champs Étiquette et Description renvoient des valeurs au moment de l'exécution selon les paramètres de langue du format.</td>
<td>L'exemple suivant montre que l'énumération présentée dans un modèle de données. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>L'exemple suivant montre :
<ul>
<li>L'énumération du modèle insérée dans un état comme source de données.</li>
<li>L'expression ER conçue pour utiliser l'énumération du modèle comme paramètre de cette fonction.</li>
<li>La source de données du type de liste d'enregistrements inséré dans un état à l'aide de l'expression ER créée.</li>
</ul>
<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> L'exemple suivant montre les éléments de format ER liés à la source de données du type de liste d'enregistrement créée à l'aide de la fonction LISTOFFIELDS.<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>Voici le résultat de l'exécution du format conçu.<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Remarque :</strong> le texte traduit pour les étiquettes et les descriptions est renseigné dans la sortie de format ER conformément aux paramètres de langue configurés pour les éléments de format FILE et FOLDER parents.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (list, field name, delimiter)</td>
<td>Renvoie la chaîne des valeurs concaténées d'un champ depuis une liste séparée par un séparateur sélectionné.</td>
<td>Si vous entrez un SPLIT(“abc” , 1) comme source de données DS, l'expression STRINGJOIN (DS, DS.Value, ":") renvoie « a:b:c »</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (list, limit value, limit source)</td>
<td>Sépare la liste donnée en une nouvelle liste de sous-listes et renvoie le résultat dans le contenu de la liste d'enregistrements. Le paramètre de valeur limite spécifie la valeur de la limite pour diviser la liste d'origine. Le paramètre source de limite spécifie l'étape à laquelle la somme totale augmente. La limite n'est pas appliquée à un article unique de la liste donnée si la source de limite dépasse la limite définie.</td>
<td>L'exemple suivant illustre le format utilisant des sources de données. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Voici l'exécution du format de résultat qui présente la liste plate d'articles de marchandises.<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>L'exemple suivant illustre le même format ajusté afin de présenter la liste d'articles de marchandises de traitement par lots lorsqu'un seul traitement par lots doit inclure des marchandises avec le poids total ne devant pas dépasser la limite de 9.<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>Voici le résultat de l'exécution du format ajusté. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Remarque</strong> la limite n'est pas appliquée au dernier article de la liste d'origine car la valeur (11) de la source de sa limite (poids) dépasse la limite définie (9). Utilisez la fonction <strong>WHERE</strong> ou l'expression <strong>Activé</strong> de l'élément de format correspondant pour ignorer les sous-listes lors de la génération d'états (si nécessaire).</td>
</tr>
<tr class="odd">
<td>FILTER (list, condition)</td>
<td>Renvoie la liste filtrée donnée de la condition spécifiée en modifiant la requête. Contrairement à la fonction <strong>WHERE</strong>, la condition spécifiée est appliquée au niveau de base de données à une source de données ER du type d'enregistrements de table.</td>
<td>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;) renvoie la liste des seuls fournisseurs appartenant au groupe « 40 » lorsque <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table <strong>VendTable</strong></td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Fonctions logiques

| Fonction                                                                                | description ;                                                                                                                                                                                                                                                                     | Exemple                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASE (expression, option 1, résultat 1 \[, option 2, résultat 2\] … \[, résultat par défaut\]) | Permet d'évaluer la valeur d'expression spécifiée par rapport aux autres options spécifiées. Renvoie le résultat de l'option qui est égal à la valeur de l'expression. Sinon, renvoie le résultat par défaut entré en option (le dernier paramètre qui n'est pas précédé par une option.) | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** renvoie la chaîne **"WINTER"** lorsque la date de session Dynamics 365 for Operations actuelle se situe entre octobre et décembre. Sinon, elle renvoie une chaîne vide. |
| IF (condition, value 1, value 2)                                                        | Renvoie la valeur 1 spécifiée lorsque la condition donnée est remplie. Sinon, renvoie la valeur 2. Si la valeur 1 et la valeur 2 sont des enregistrements ou des listes d'enregistrements, le résultat affichera uniquement les champs qui existent dans les deux listes.                                                                     | **IF (1=2, "condition is met", "condition is not met")** renvoie la chaîne **"condition is not met"**.                                                                                                                                                      |
| NOT (condition)                                                                         | Renvoie la valeur logique inversée de la condition spécifiée.                                                                                                                                                                                                                   | **NOT (TRUE)** renvoie **FALSE**.                                                                                                                                                                                                                            |
| AND (condition 1\[, condition 2, ...\])                                                 | Renvoie la valeur **TRUE** si *toutes *les conditions spécifiées sont vraies. Sinon, renvoie la valeur **FALSE**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** renvoie **TRUE**. **AND (1=2, "a"="a")** renvoie **FALSE**.                                                                                                                                                                           |
| OR (condition 1\[, condition 2, ...\])                                                  | Renvoie la valeur **FALSE** si *toutes *les conditions spécifiées sont fausses. Renvoie la valeur **TRUE** si *l'une *des conditions spécifiées est vraie.                                                                                                                                                                 | **OR (1=2, "a"="a")** renvoie **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Fonctions mathématiques

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonction</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Retour marchandises (numéro)</td>
<td>Renvoie la valeur absolue du nombre spécifié (sans le signe).</td>
<td><strong>ABS (-1)</strong> renvoie <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (number, power)</td>
<td>Renvoie le résultat d'élever le nombre positif spécifié à la puissance spécifiée.</td>
<td><strong>POWER (10, 2)</strong> renvoie <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (string, decimal separator, digit grouping separator)</td>
<td>Convertit la chaîne spécifiée en un chiffre. Le symbole spécifié est utilisé pour séparer les parties entières et fractionnaires d'un nombre décimal, et le séparateur de millier spécifié est également utilisé.</td>
<td><strong>NUMBERVALUE(&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> renvoie la valeur <strong>1234.56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (string)</td>
<td>Convertit la chaîne spécifiée en un chiffre. Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d'union (-) est utilisé comme signe moins. Entraîne une exception si d'autres caractères non numériques sont rencontrés dans la chaîne spécifiée.</td>
<td><strong>VALUE (&quot;1 234,56&quot;)</strong> entraîne une exception.</td>
</tr>
<tr class="odd">
<td>ROUND (number, decimals)</td>
<td>Renvoie le nombre spécifié, qui est arrondi au nombre de décimales spécifié :
<ul>
<li>Si la valeur de décimale spécifiée est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales spécifié.</li>
<li>Si la valeur de décimale spécifiée est 0 (zéro), le numéro spécifié est arrondi à l'entier le plus proche.</li>
<li>Si la valeur de décimale spécifiée est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.</li>
</ul></td>
<td><strong>ROUND (1200.767, 2)</strong> arrondit à deux décimales et renvoie <strong>1200.77</strong>. <strong>ROND (1200.767), -3</strong> arrondit au multiple de 1 000 le plus proche et renvoie <strong>1 000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (number, decimals)</td>
<td>Renvoie le nombre spécifié, qui est arrondi vers le bas (vers zéro) au nombre de décimales spécifié. <strong>Remarque :</strong> cette fonction se comporte comme <strong>ROUND</strong>, mais elle arrondit toujours le nombre spécifié vers le bas.</td>
<td><strong>ROUNDDOWN (1200.767, 2)</strong> arrondit vers le bas à deux décimales et renvoie <strong>1200.76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> arrondit vers le bas au multiple de 1 000 le plus proche et renvoie <strong>1 000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (number, decimals)</td>
<td>Renvoie le nombre spécifié, qui est arrondi vers le haut (loin de zéro) au nombre de décimales spécifié. <strong>Remarque :</strong> cette fonction se comporte comme <strong>ROUND</strong>, mais elle arrondit toujours le nombre spécifié vers le haut.</td>
<td><strong>ROUNDUP (1200.763, 2)</strong> arrondit vers le haut à deux décimales et renvoie <strong>1200.77</strong>. <strong>ROUNDUP (1200.767), -3</strong> arrondit vers le haut au multiple de 1 000 le plus proche et renvoie <strong>2 000</strong>.</td>
</tr>
</tbody>
</table>

### <a name="record-functions"></a>Fonctions d'enregistrement

| Fonction             | Description                                                                                                                                                                                                                                     | Exemple                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (list) | Renvoie un enregistrement **null** ayant la même structure que la liste d'enregistrements ou l'enregistrement spécifié. **Remarque : **cette fonction est obsolète. Utilisez **EMPTYRECORD** à la place.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction **SPLIT**. |
| EMPTYRECORD (record) | Renvoie un enregistrement **null** ayant la même structure que la liste d'enregistrements ou l'enregistrement spécifié. **Remarque :** Un enregistrement **null** est un enregistrement où tous les champs ont une valeur vide (**0** \[zero\] pour les nombres, une chaîne vide pour les chaînes, etc). | **EMPTYRECORD (SPLIT ("abc", 1))** renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction **SPLIT**.   |

### <a name="text-functions"></a>Fonctions texte

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonction</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (string)</td>
<td>Permet de renvoyer la chaîne spécifiée, qui est convertie aux lettres majuscules.</td>
<td><strong>UPPER(&quot;Sample&quot;)</strong> renvoie <strong>&quot;SAMPLE&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (string)</td>
<td>Permet de renvoyer la chaîne spécifiée, qui est convertie aux lettres minuscules.</td>
<td><strong>LOWER (&quot;Sample&quot;)</strong> renvoie <strong>&quot;sample&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (string, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié du début de la chaîne spécifiée.</td>
<td><strong>LEFT (&quot;Sample&quot;, 3)</strong> renvoie <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (string, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié de la fin de la chaîne spécifiée.</td>
<td><strong>RIGHT (&quot;Sample&quot;, 3)</strong> renvoie <strong>&quot;ple&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (string, starting position, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié de la chaîne spécifiée, en commençant à l'emplacement spécifié.</td>
<td><strong>MID (&quot;Sample&quot;, 2, 3)</strong> renvoie <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (string)</td>
<td>Retourne le nombre de caractères dans la chaîne spécifiée.</td>
<td><strong>LEN (&quot;Sample&quot;)</strong> renvoie <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (number)</td>
<td>Permet de renvoyer la chaîne de caractères référencée par le nombre Unicode spécifié.</td>
<td><strong>CHAR (255)</strong> renvoie <strong>&quot;ÿ&quot;</strong>. <strong>Remarque :</strong> la chaîne retournée dépend de l'encodage sélectionné dans l'élément de format FILE parent. La liste d'encodages pris en charge figure dans la rubrique <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe d'encodage</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (string 1 [, string 2, …])</td>
<td>Renvoie toutes les chaînes de texte spécifiées, associées dans une chaîne.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> renvoie <strong>&quot;abcdef&quot;</strong>. <strong>Remarque :</strong> L'expression <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> renvoie également <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (string, pattern, replacement)</td>
<td>Permet de renvoyer la chaîne spécifiée, dans laquelle toutes les occurrences des caractères de la chaîne de modèle spécifiée sont remplacées par les caractères correspondant à la position de la chaîne de remplacement spécifiée.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> remplace le modèle <strong>&quot;cd&quot;</strong> par la chaîne <strong>&quot;GH&quot;</strong> et renvoie <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (string, pattern, replacement, regular expression flag)</td>
<td>Lorsque l'indicateur d'expression régulière spécifié est la valeur <strong>true</strong>, renvoie la chaîne spécifiée, qui est modifiée en appliquant l'expression régulière spécifiée sous la forme d'un argument de modèle pour cette fonction. Cette expression est utilisée pour rechercher les caractères qui doivent être remplacés. Les caractères de l'argument de remplacement spécifié sont utilisés pour remplacer les caractères qui sont recherchés. Lorsque l'indicateur d'expression régulière spécifié est <strong>false</strong>, cette fonction se comporte comme <strong>TRANSLATE</strong>.</td>
<td>  <strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> applique une expression régulière qui supprime tous les symboles non-numériques, et renvoie <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> remplace le modèle <strong>&quot;cd&quot;</strong> par la chaîne <strong>&quot;GH&quot;</strong> et renvoie <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (input)</td>
<td>Renvoie l'entrée spécifiée, qui est convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance Dynamics 365 for Operations actuelle. Pour les valeurs de type <strong>real</strong>, la conversion de chaîne est limitée à deux décimales.</td>
<td>Si les paramètres régionaux du serveur d'instance Dynamics 365 for Operations sont définis comme <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> renvoie la date de session Dynamics 365 for Operations actuelle, 12/17/2015, comme chaînes de texte <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> renvoie <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (string 1, string 2[, string 3, ...])</td>
<td>Permet de renvoyer la chaîne spécifiée, qui est mise en forme en substituant toutes les occurrences de <strong>%N</strong> par le <em>n</em>ième argument. Les arguments sont des chaînes. Si un argument n'est pas fourni pour un paramètre, le paramètre est renvoyé comme <strong>&quot;%N&quot;</strong> dans la chaîne. Pour les valeurs de type <strong>real</strong>, la conversion de chaîne est limitée à deux décimales.</td>
<td>Dans cet exemple, la source de données <strong>PaymentModel</strong> renvoie la liste des enregistrements client via le composant <strong>Customer</strong> et la valeur de la date de traitement via le champ <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> Dans le format de génération d'états électroniques conçu pour générer un fichier électronique pur les clients sélectionnés, <strong>PaymentModel</strong> est sélectionné comme source de données et contrôle le flux de processus. Une exception est entraînée pour les utilisateurs finaux lorsqu'un client sélectionné est arrêté à la date lorsque l'état est traité. La formule qui est conçue pour ce type de contrôle de traitement peut utiliser les ressources suivantes :
<ul>
<li>Libellé Dynamics 365 for Operations SYS70894, avec le texte suivant :
<ul>
<li><strong>Pour l'anglais (États-Unis) :</strong> &quot;Nothing to print&quot;</li>
<li><strong>Pour l'allemand :</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Libellé Dynamics 365 for Operations SYS18389, avec le texte suivant :
<ul>
<li><strong>Pour l'anglais :</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Pour l'allemand :</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
Voici la formule qui peut être conçue : FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;)) Si un rapport est traité pour le <strong>client Litware Retail</strong> le 17 décembre 2015, dans la culture <strong>américaine et l'anglais</strong> <strong>(États-Unis)</strong>, cette formule renvoie le texte suivant, qui peut être présenté comme message d'exception à l'utilisateur final : &quot;Nothing to print. Customer Litware Retail is stopped for 12/17/2015.&quot; Si le même état est traité pour le<strong> client Litware Retail</strong> le 17 décembre 2015, dans la <strong>culture et la langue</strong> <strong>allemandes</strong>, cette formule renvoie le texte suivant, qui utilise un format de date différent : &quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot; <strong>Remarque : </strong>la syntaxe suivante est appliquée aux formules de génération d'états électroniques pour les libellés :
<ul>
<li><strong>Pour les libellés des ressources Dynamics 365 for Operations :</strong> <strong>@&quot;X&quot;</strong>, où X est l'ID libellé de l'arbre d'objets d'application (AOA)</li>
<li><strong>Pour les libellés se trouvant dans les configurations de génération d'états électroniques :</strong> <strong>@&quot;ER_LABEL:X&quot;</strong>, où X est l'ID libellé dans la configuration de génération d'états électroniques</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (number, format)</td>
<td>Renvoie la représentation sous forme de chaîne du nombre spécifié au format spécifié. (Pour plus d'informations sur les formats pris en charge, voir <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> et <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personnalisés</a>.) Le contexte dans lequel cette fonction est exécutée détermine la culture utilisée pour formater des numéros.</td>
<td>Pour la culture américaine, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> renvoie <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> renvoie <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)</td>
<td>Renvoie le nombre défini (converti) des chaînes de texte dans la langue définie. Le code de langue est facultatif : lorsqu'il est défini comme une chaîne vide, le code de langue de contexte actuelle (défini pour un dossier ou un fichier de génération) sera utilisé à la place. Le code devise est facultatif. Lorsqu'il est défini comme une chaîne vide, la devise de la société est utilisée. Notez que le paramètre <strong>Imprimer le nom de la devise</strong> et le paramètre <strong>Décimales</strong> sont analysés pour les codes de langue suivants uniquement : <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Notez que le paramètre <strong>Imprimer le nom de la devise</strong> est analysé uniquement pour les sociétés Dynamics 365 for Operations avec le contexte du pays prenant en charge la déclinaison de la devise.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2) renvoie “One Thousand Two Hundred Thirty Four and 56” NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0) renvoie “Sto dwadzieścia” NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2) renvoie “Сто двадцать евро 21 евроцент”</td>
</tr>
<tr class="odd">
<td>PADLEFT (string, length, padding chars)</td>
<td>Renvoie une chaîne de longueur spécifique dans laquelle le début de la chaîne actuelle est entourée par les caractères spécifiés.</td>
<td>PADLEFT (“1234”, 10, “ “) returns the text string “      1234”</td>
</tr>
</tbody>
</table>

### <a name="data-collection-functions"></a>Fonctions de collecte des données

Fonction

description ;

Exemple

FORMATELEMENTNAME ()

Retourne le nom de l'élément du format actuel. Renvoie une chaîne vide lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé.

Fait référence au Guide de tâche **ER Utiliser les données de la sortie du format pour compter et additionner** (qui fait partie du processus commercial **Acquérir/Développer des composants de services/solutions informatiques**) pour en savoir plus sur l'utilisation de ces fonctions.

SUMIFS (key string for summing, criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\])

Renvoie une somme des valeurs des nœuds (avec le nom défini comme clé) de XML, qui a été collectée durant cette exécution de format et remplit les conditions entrées (paires de plage et de valeur). Renvoie une valeur de zéro lorsque l'indicateur **Collecter les détails sur les sorties **des fichiers actuels est désactivé.

SUMIF (key string for summing, criteria range string, criteria value string)

Renvoie une somme des valeurs des nœuds (avec le nom défini comme clé) de XML, qui a été collectée durant cette exécution de format et remplit la condition entrée (plage et valeur). Renvoie une valeur de zéro lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé.

COUNTIFS (criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\])

Renvoie un nombre de nœuds de XML, qui a été collectée durant cette exécution de format et remplit les conditions entrées (paires de plage et de valeur). Renvoie une valeur de zéro lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé.

COUNTIF (criteria range string, criteria value string)

Renvoie un nombre de nœuds de XML, qui a été collectée durant cette exécution de format et remplit la condition entrée (plage et valeur). Renvoie une valeur de zéro lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé.

COLLECTEDLIST (criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\])

Renvoie une liste des valeurs des nœuds de XML, qui a été collectée durant cette exécution de format et remplit les conditions entrées (plage et valeur). Renvoie une liste vide lorsque l'indicateur **Collecter les détails sur les sorties **des fichiers actuels est désactivé.

### <a name="other-business-domainspecific-functions"></a>Autre fonctions (spécifiques au domaine d'affaires)

| Fonction                                                                         | description ;                                                                                                                                                                                                                                                        | Exemple                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (amount, source currency, target currency, date, company)        | Convertit le montant en devises spécifié de la devise source dans la devise cible à l'aide des paramètres de la société Dynamics 365 for Operations spécifiée à la date spécifiée.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** renvoie l'équivalent d'un euro en dollars US à la date de session actuelle, basée sur les paramètre de la société DEMF.                                                                                                                                  |
| ROUNDAMOUNT (number, decimals, round rule)                                       | Arrondit le montant spécifié en fonction de la règle d'arrondi spécifiée et du nombre de décimales spécifié. **Remarque :** la règle d'arrondi doit être spécifiée comme valeur d'énumération **RoundOffType** Dynamics 365 for Operations.                          | Si le paramètre **model.RoundOff** est défini sur ****Downward****, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** renvoie la valeur **1000.78**. Si le paramètre **model.RoundOff** est défini sur **Normal** ou **Rounding-up**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** renvoie la valeur **1000.79**. |
| CURCredRef (digits)                                                              | Renvoie une référence créditeur, selon les chiffres du numéro de facture spécifié.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** renvoie **"2200002"**.                                                                                                                                                                                                                                                         |
| MOD\_97 (digits)                                                                 | Renvoie une référence créditeur, comme une expression MOD97, selon les chiffres du numéro de facture spécifié.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** renvoie **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (digits)                                                              | Renvoie une référence créditeur ISO, selon les chiffres et les symboles alphabétiques du numéro de facture spécifié. **Remarque : **pour éliminer des symboles de l'alphabet qui ne sont pas conformes à la norme ISO, le paramètre d'entrée doit être traduit avant d'être transmis à cette fonction. | **ISOCredRef ("VEND-200002")** renvoie **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (string, number)                                  | Obtenir l'ID de dimension financière supplémentaire. Les dimensions sont représentées dans cette chaîne comme des ID séparés par des virgules. Les numéros définissent le code souche de la dimension demandée dans cette chaîne.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3) renvoie “CC”                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Renvoie le code de la société enregistrée actuelle.                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                               |
| CH\_BANK\_MOD\_10 (digits)                                                       | Renvoie une référence créditeur, comme une expression MOD10, selon les chiffres du numéro de facture spécifié.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("VEND-200002") renvoie 3                                                                                                                                                                                                                                                                   |
| FA\_SUM (fixed asset code, value model code, start date, end date)               | Retourne le conteneur de données préparé des montants d'une immobilisation pour une période.                                                                                                                                                                                         | FA\_SUM ("COMP-000001", “Current”, Date1, Date2) renvoie le conteneur de données préparé de l'immobilisation « COMP-000001 » avec le modèle de valeur « Current » pour une période allant de Date1 à Date2.                                                                                                                        |
| FA\_BALANCE (fixed asset code, value model code, reporting year, reporting date) | Retourne le conteneur de données préparé des soldes d'une immobilisation. L'année de génération d'états doit être spécifiée comme valeur de l'énumération Dynamics 365 for Operations **AssetYear**.                                                                                           | FA\_SUM ("COMP-000001", “Current”, AxEnumAssetYear.ThisYear, SESSIONTODAY ()) renvoie le conteneur de données préparé des soldes de l'immobilisation « COMP-000001 » avec le modèle de valeur « Current » à la date de session 365 for Operations actuelle.                                                                |

### <a name="functions-list-extension"></a>Extension de la liste des fonctions

La génération d'état électroniques prend en charge une capacité d'extension de la liste des fonctions utilisées dans les expressions de génération d'états électroniques. Pour cela, certaines opérations d'ingénierie sont requises. Pour obtenir des informations détaillées, consultez [Extension de la liste des fonctions de génération d'états électroniques](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)

[Extension de la liste des fonctions de génération d'états électroniques (ER)](general-electronic-reporting-formulas-list-extension.md)




