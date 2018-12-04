---
title: "Concepteur de formule dans les états électroniques (ER)"
description: "Cette rubrique décrit l'utilisation du concepteur de formule dans la génération d'états électroniques."
author: NickSelin
manager: AnnBe
ms.date: 10/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f0ded563ecf0b6d0ce67f046f631d8c4dcfc7802
ms.openlocfilehash: 1dc584355c8992ee701169fd5d29ad7b0300a498
ms.contentlocale: fr-fr
ms.lasthandoff: 10/22/2018

---

# <a name="formula-designer-in-electronic-reporting-er"></a>Concepteur de formule dans les états électroniques (ER)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l'utilisation du concepteur de formule dans la génération d'états électroniques. Lorsque vous créez un format pour un document électronique spécifique dans ER, vous pouvez utiliser des formules pour transformer les données afin qu'elles répondent aux exigences d'exécution et de mise en forme du document. Ces formules ressemblent aux formules dans Microsoft Excel. Plusieurs types de fonctions sont pris en charge dans les formules : texte, date et heure, mathématique, logique, informations, conversion du type de données et autre (fonctions spécifiques au métier).

## <a name="formula-designer-overview"></a>Vue d'ensemble du concepteur de formule

La fonctionnalité de génération d'états électroniques prend en charge le concepteur de formule. Par conséquent, au moment de la conception, vous pouvez configurer des expressions qui peuvent être utilisées pour les tâches suivantes au moment de l'exécution :

- Transformer les données reçues d'une base de données Microsoft Dynamics 365 for Finance and Operations qui doivent être saisies dans un modèle de données de génération d'états électroniques qui est conçu pour être une source de données pour les formats de génération d'états électroniques. (Par exemple, ces transformations peuvent inclure le filtrage, le regroupement et la conversion des types de données.)
- Mettre en forme des données qui doivent être émises vers un document électronique en cours de génération en accord avec la mise en forme et les conditions d'un format de génération d'états électroniques spécifique. (Par exemple, la mise en forme peut être effectuée en accord avec la langue, la culture ou le codage demandé.)
- Contrôler le processus de création de documents électroniques. (Par exemple, les expressions peuvent activer ou désactiver l'émission d'éléments spécifiques du format, en fonction des données de traitement. Elles peuvent également interrompre le processus de création du document ou envoyer des messages aux utilisateurs.)

Vous pouvez ouvrir la page **Concepteur de formule** lorsque vous effectuez l'une des actions suivantes :

- Lier des articles sources de données aux composants de modèle de données.
- Lier des articles sources de données aux composants de format.
- Effectuer la mise à jour des champs calculés dans le cadre des sources de données.
- Définir des conditions de visibilité pour les paramètres d'entrée utilisateur.
- Créer des transformations d'un format.
- Définir les conditions d'activation pour les composants du format.
- Définir les noms de fichiers pour les composants FICHIER du format.
- Définir les conditions des validations du contrôle de processus.
- Définir le texte de message des validations du contrôle de processus.

## <a name="designing-er-formulas"></a>Conception des formules de génération d'états électroniques

### <a name="data-binding"></a>Liaison de données

Le concepteur de formule de génération d'états électroniques permet de définir une expression qui transforme des données reçues des sources de données à saisir dans le consommateur de données au moment de l'exécution :

- Des sources de données Finance and Operations et des paramètres d'exécution à un modèle de données de génération d'états électroniques
- D'un modèle de données de génération d'états électroniques à un format de génération d'états électroniques
- Des sources de données Finance and Operations et des paramètres d'exécution à un format de génération d'états électroniques

La figure suivante présente la création d'une expression de ce type. Dans cet exemple, l'expression arrondit la valeur du champ **Intrastat.AmountMST** de la table Déclaration d'échanges de biens de Finance and Operations à deux décimales et retourne la valeur arrondie.

[![Liaison de données](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

La figure suivante présente l'utilisation d'une expression de ce type. Dans cet exemple, le résultat de l'expression conçue est saisi dans le composant **Transaction.InvoicedAmount** du modèle de données **Modèle de déclaration de taxe**.

[![Liaison de données utilisée](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

À l'exécution, la formule conçue, **ROUND (Intrastat.AmountMST, 2)**, arrondit la valeur du champ **AmountMST** pour chaque enregistrement de la table Déclaration d'échanges de biens à deux décimales. Elle saisit ensuite la valeur arrondie dans le composant **Transaction.InvoicedAmount** du modèle de données **Déclaration de taxe**.

### <a name="data-formatting"></a>Mise en forme des données

Le concepteur de formule de génération d'états électroniques permet de définir une expression qui formate les données reçues des sources de données, afin que les données puissent être envoyées dans le cadre de la génération d'un document électronique. Vous disposez peut-être d'une mise en forme qui doit être appliquée comme règle classique pour être réutilisée pour un format. Dans ce cas, vous pouvez entrer cette mise en forme une fois dans la configuration du format comme transformation nommée ayant une expression de mise en forme. Cette transformation nommée peut ensuite être liée à de nombreux composants de format dont la sortie doit être mise en forme en fonction de l'expression de mise en forme créée.

La figure suivante présente la création d'une transformation de ce type. Dans cet exemple, la transformation **TrimmedString** tronque les données entrantes du type de données **Chaîne** en supprimant les espaces de début et de fin. Elle retourne ensuite la valeur de chaîne tronquée.

[![Transformation](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

La figure suivante présente l'utilisation d'une transformation de ce type. Dans cet exemple, plusieurs composants de format envoient le texte comme résultat de la génération du document électronique au moment de l'exécution. Tous ces composants de format font référence à la transformation **TrimmedString** par son nom.

[![Transformation utilisée](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Lorsque les composants de format, comme le composant **partyName** dans l'illustration précédente, font référence à la transformation **TrimmedString**, cette dernière renvoie le texte comme résultat de la génération du document électronique. Le texte n'inclut pas les espaces de début et de fin.

Si vous avez une mise en forme qui doit être appliquée individuellement, vous pouvez introduire cette mise en page en tant qu'expression individuelle d'une liaison d'un composant de format spécifique. La figure suivante présente une expression de ce type. Dans cet exemple, le composant de format **partyType** est lié à la source de données via une expression qui convertit les données entrantes du champ **Model.Company.RegistrationType** dans la source de données en texte en majuscules. L'expression envoie ensuite ce texte comme résultat dans le document électronique.

[![Application de la mise en forme à un composant individuel](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Contrôle des flux de processus

Le concepteur de formule de génération d'états électroniques permet de définir les expressions utilisées pour contrôler le flux de processus de génération de documents électroniques. Vous pouvez effectuer les tâches suivantes :

- Définir des conditions qui déterminent quand un processus de création de document doit être arrêté.
- Spécifier les expressions qui créent des messages pour l'utilisateur, relatifs aux processus arrêtés ou lancent des messages de journal d'exécution relatifs à la continuité du processus de génération d'états.
- Spécifier les noms de fichier de la génération de documents électroniques, et contrôler les conditions de leur création.

Chaque règle du contrôle des flux de processus est conçue comme un contrôle individuel. La figure suivante présente une validation de ce type. Voici une explication de la configuration dans cet exemple :

- La validation est évaluée lorsque le nœud **INSTAT** est créé lors de la génération du fichier XML.
- Si la liste des transactions est vide, la validation arrête le processus d'exécution et renvoie la valeur **FALSE**.
- La validation renvoie un message d'erreur qui inclut le texte du libellé SYS70894 Finance and Operations dans la langue de l'utilisateur.

[![Contrôle](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Le concepteur de formule de génération d'états électroniques peut également être utilisé pour générer un nom de fichier permettant de générer un document électronique et de contrôler le processus de création de fichier. La figure suivante présente la création d'un contrôle des flux de processus de ce type. Voici une explication de la configuration dans cet exemple :

- La liste des enregistrements de la source de données **model.Intrastat** est divisée en lots. Chaque lot contient jusqu'à 1 000 enregistrements.
- Le résultat crée un fichier zip qui contient un fichier au format XML pour chaque lot qui a été créé.
- Une expression renvoie un nom de fichier pour générer des documents électroniques en concaténant le nom de fichier et son extension. Pour le deuxième traitement par lots et tous les traitements par lots suivants, le nom de fichier contient l'ID traitement par lots comme suffixe.
- Une expression active (en renvoyant la valeur **TRUE**) le processus de création de fichier pour les lots contenant au moins un enregistrement.

[![Contrôle de fichier](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Syntaxe de base

Les expressions de génération d'états électroniques peuvent contenir le tout ou partie des éléments suivants :

- Constantes
- Opérateurs
- Références
- Chemins d'accès
- Fonctions

#### <a name="constants"></a>Constantes

Lorsque vous concevez des expressions, vous pouvez utiliser les constantes de texte et numériques, c'est-à-dire les valeurs qui ne sont pas calculées. Par exemple, l'expression **VALUE ("100") + 20** utilise la constante numérique **20** et la constante de chaîne **100** et renvoie la valeur numérique **120**. Le concepteur de formule de génération d'états électroniques prend en charge les séquences d'échappement. Par conséquent, vous pouvez spécifier une chaîne d'expression qui doit être traitée différemment. Par exemple, l'expression **"Léon Tolstoï ""Guerre et paix"" Volume 1"** renvoie la chaîne de texte **Léon Tolstoï "Guerre et paix" Volume 1**.

#### <a name="operators"></a>Opérateurs

Le tableau suivant indique les opérateurs arithmétiques que vous pouvez utiliser pour effectuer des opérations mathématiques de base, telles que l'addition, la soustraction, la multiplication et la division.

| Opérateur | Signifie               | Exemple |
|----------|-----------------------|---------|
| +        | Addition              | 1+2     |
| -        | Soustraction, négation | 5-2, -1 |
| \*       | Multiplication        | 7\*8    |
| /        | Service              | 9/3     |

Le tableau suivant décrit les opérateurs de comparaison pris en charge. Vous pouvez utiliser ces opérateurs pour comparer deux valeurs.

| Opérateur | Signifie                  | Exemple    |
|----------|--------------------------|------------|
| =        | Egal                    | X=Y        |
| &gt;     | Supérieur             | X&gt;Y     |
| &lt;     | Inférieur à                | X&lt;Y     |
| &gt;=    | Supérieur ou égal à | X&gt;=Y    |
| &lt;=    | Inférieur ou égal à    | X&lt;=Y    |
| &lt;&gt; | Différent de             | X&lt;&gt;Y |

En outre, vous pouvez utiliser une esperluette (&) comme opérateur de concaténation de texte. De cette manière, vous pouvez lier ou concaténer une ou plusieurs chaînes de texte en un bloc de texte unique.

| Opérateur | Signifie     | Exemple                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Concaténer | "Rien à imprimer" & ":&nbsp;" & "aucun enregistrement trouvé" |

##### <a name="operator-precedence"></a>Priorité des opérateurs

L'ordre dans lequel les parties d'une expression de composant sont évaluées est important. Par exemple, le résultat de l'expression **1 + 4 / 2** varie selon que l'addition ou la division est effectuée en premier. Vous pouvez utiliser des parenthèses pour définir explicitement la manière dont une expression est évaluée. Par exemple, pour indiquer que l'addition doit être exécutée en premier, vous pouvez modifier l'expression précédente comme suit : **(1 + 4) / 2**. Si vous n'indiquez pas explicitement l'ordre des opérations à effectuer dans une expression, l'ordre est basé sur la priorité par défaut attribuée aux opérateurs pris en charge. Le tableau suivant indique la priorité affectée à chaque opérateur. Les opérateurs qui ont la priorité la plus élevée (par exemple, 7) sont évalués avant les opérateurs ayant une priorité inférieure (par exemple, 1).

| Priorité | Opérateurs      | Syntaxe                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Regroupement       | ( … )                                                                   |
| 6          | Accès des membres  | … . …                                                                   |
| 5          | Appel de fonction  | … ( … )                                                                 |
| 4          | Multiplicateur | … \* …<br>… / …                                                         |
| 3          | Supplémentaire       | … + …<br>… - …                                                          |
| 2          | Comparaison     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Séparation     | … , …                                                                   |

Si une expression comprend plusieurs opérateurs consécutifs qui ont la même priorité, ces opérations sont évaluées de gauche à droite. Par exemple, l'expression **1 + 6 / 2 \* 3 &gt; 5** renvoie la valeur **true**. Il est recommandé d'utiliser des parenthèses pour indiquer explicitement l'ordre des opérations dans les expressions, afin de faciliter la lecture et la mise à jour des expressions.

#### <a name="references"></a>Références

Toutes les sources de données du composant de génération d'états électroniques actuel qui sont disponibles lors de la création d'une expression peuvent servir de références nommées. (Le composant de génération d'états électroniques actuel peut être un modèle ou un format). Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **ReportingDate**, qui renvoie une valeur du type de données **DATETIME**. Pour formater correctement cette valeur dans le document de génération, vous pouvez référencer la source de données dans l'expression comme suit : **DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")**.

Tous les caractères du nom d'une source de données de référencement qui ne représentent pas une lettre de l'alphabet doivent être précédés d'un guillemet simple ('). Si le nom d'une source de données de référencement contient au moins un symbole qui ne représente pas une lettre de l'alphabet, le nom doit être placé entre guillemets simples ('). (Par exemple, ces symboles non alphabétiques peuvent être les signes de ponctuation ou tous les autres symboles écrits). Voici quelques exemples :

- La source de données **Date & heure d'aujourd'hui** doit être utilisée dans une expression de génération d'états électroniques comme suit : **'Date et heure d'aujourd'hui'**
- La méthode **name()** de la source de données **Clients** doit être référencée dans l'expression de génération d'états électroniques comme suit : **Customers.'name()'**

Si les méthodes des sources de données Finance and Operations ont des paramètres, la syntaxe suivante est utilisée pour appeler ces méthodes :

- Si la méthode **isLanguageRTL** de la source de données **Système** a un paramètre **EN-US** du type de données **Chaîne**, cette méthode doit être mentionnée dans une expression ER comme suit : **System.'isLanguageRTL'("EN-US")**.
- Les guillemets ne sont pas obligatoires lorsqu'un nom de méthode ne contient que des symboles alphanumériques. Toutefois, ils sont obligatoires pour une méthode de table si le nom inclut des parenthèses.

Lorsque la source de données **System** est ajoutée à une mise en correspondance ER qui fait référence à la classe d'application **Global** de Finance and Operations, l'expression retourne la valeur booléenne, **FALSE**. L'expression modifiée **System.' isLanguageRTL'("AR")** renvoie la valeur booléenne **TRUE**.

Vous pouvez limiter la façon dont les valeurs sont transférées aux paramètres de ce type de méthode :

- Seules les constantes peuvent être transférées aux méthodes de ce type. Les valeurs des constantes sont définies au moment de la conception.
- Seuls les types de données (de base) primitifs sont pris en charge pour les paramètres de ce type. (Les types de données primitifs sont nombre entier, réel, booléen, chaîne, etc.).

#### <a name="paths"></a>Chemins d'accès

Lorsqu'une expression fait référence à une source de données structurée, vous pouvez utiliser la définition de chemin d'accès pour sélectionner un élément primitif spécifique de cette source de données. Un point (.) est utilisé pour séparer les éléments distincts d'une source de données structurée. Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement **InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient tous les deux des valeurs numériques. Par conséquent, vous pouvez concevoir l'expression suivante pour calculer le montant facturé : **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Fonctions

La section suivante décrit les fonctions pouvant être utilisées dans les expressions de génération d'états électroniques. Toutes les sources de données du contexte d'expression (modèle de données ou format de génération d'états électroniques actuel) peuvent être utilisées en tant que paramètres des fonctions d'appel en accord avec la liste des arguments des fonctions d'appel. Les constantes peuvent également être utilisées comme paramètres des fonctions d'appel. Par exemple, le modèle de données de génération d'états électroniques actuel contient la source de données **InvoiceTransactions** qui renvoie une liste des enregistrements. La structure d'enregistrement **InvoiceTransactions** contient les champs **AmountDebit** et **AmountCredit** qui renvoient tous les deux des valeurs numériques. Par conséquent, pour calculer le montant facturé, vous pouvez concevoir l'expression suivante qui utilise la fonction d'arrondi de génération d'états électroniques intégrée : **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Fonctions prises en charge.

Les tables suivantes décrivent les fonctions de manipulation des données que vous pouvez utiliser pour concevoir des modèles de données et des états de génération d'états électroniques. La liste des fonctions n'est pas fixe. Les développeurs peuvent l'étendre. Pour afficher la liste des fonctions que vous pouvez utiliser, ouvrez le volet de fonctions du concepteur de formule de génération d'états électroniques.

### <a name="date-and-time-functions"></a>Fonctions de date et d'heure

| Fonction | Description | Exemple |
|----------|-------------|---------|
| ADDDAYS (datetime, days) | Ajoute le nombre de jours spécifié à la valeur de date/heure spécifiée. | **ADDDAYS (NOW(), 7)** renvoie la date et l'heure, sept jours dans le futur. |
| DATETODATETIME (date) | Convertit la valeur de date spécifiée en valeur de date/heure. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** renvoie la date de la session Finance and Operations actuelle, 24 décembre 2015, sous la forme **12/24/2015 12:00:00 AM**. Dans cet exemple, **CompInfo** est une source de données de génération d'états électroniques de type **Finance and Operations/Table** qui fait référence à la table CompanyInfo. |
| NOW () | Renvoie la date et l'heure du serveur d'applications Finance and Operations comme valeur de date/heure. | |
| TODAY () | Permet de renvoyer la date du serveur d'applications Finance and Operations comme valeur de date. | |
| NULLDATE () | Renvoie une valeur de date **null**. | |
| NULLDATETIME () | Renvoie une valeur de date/heure **null**. | |
| DATETIMEFORMAT (datetime, format) | Convertit la valeur de date/heure spécifiée en une chaîne dans le format spécifié. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy")** renvoie la date du serveur d'applications Finance and Operations actuelle, 24 décembre 2015, sous la forme **"24-12-2015"**, en fonction du format personnalisé spécifié. |
| DATETIMEFORMAT (datetime, format, culture) | Convertit la valeur de date/heure spécifiée en une chaîne dans le format et la [culture](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) spécifiés. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "d", "de")** renvoie la date du serveur d'applications Finance and Operations actuelle, 24 décembre 2015, sous la forme **"24.12.2015"**, en fonction de la culture allemande sélectionnée. |
| SESSIONTODAY () | Renvoie la date de la session Finance and Operations comme valeur de date. | |
| SESSIONNOW () | Renvoie la date et l'heure de session Finance and Operations comme valeur de date/heure. | |
| DATEFORMAT (date, format) | Renvoie une représentation sous forme de chaîne de la date spécifiée dans le format spécifié. | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** renvoie la date de la session Finance and Operations actuelle, 24 décembre 2015, sous la forme **"24-12-2015"**, en fonction du format personnalisé spécifié. |
| DATEFORMAT (date, format, culture) | Convertit la valeur de date spécifiée en une chaîne dans le format et la [culture](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) spécifiés. (Pour plus d'informations sur les formats pris en charge, consultez [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) et [personnalisé](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** renvoie la date de la session Finance and Operations actuelle, 24 décembre 2015, sous la forme **"24.12.2015"**, selon la culture allemande sélectionnée. |
| DAYOFYEAR (date) | Renvoie une représentation sous forme de nombre entier du nombre de jours entre le 1er janvier et la date spécifiée. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))** retourne **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))** retourne **1**. |
| DAYS (date 1, date 2) | Renvoie le nombre de jours entre la première date spécifiée et la deuxième date spécifiée. Renvoie une valeur positive lorsque la première date est postérieure à la deuxième date ; renvoie **0** (zéro) lorsque la première date est égale à la deuxième date ; sinon, renvoie une valeur négative lorsque la première date est antérieure à la deuxième date. | **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS(NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))** renvoie **-1**. |

### <a name="data-conversion-functions"></a>Fonctions de conversion des données

| Fonction | Description | Exemple |
|----------|-------------|---------|
| DATETODATETIME (date) | Convertit la valeur de date spécifiée en valeur de date/heure. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** renvoie la date de la session Finance and Operations actuelle, 24 décembre 2015, sous la forme **12/24/2015 12:00:00 AM**. Dans cet exemple, **CompInfo** est une source de données de génération d'états électroniques de type **Finance and Operations/Table** qui fait référence à la table CompanyInfo. |
| DATEVALUE (chaîne, format) | Renvoie une représentation sous forme de date de la chaîne spécifiée dans le format spécifié. | **DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")** renvoie la date 21 décembre 2016, en fonction du format personnalisé spécifié et de la culture par défaut **EN-US** de l'application. |
| DATEVALUE (chaîne, format, culture) | Renvoie une représentation sous forme de date de la chaîne spécifiée dans le format et la culture spécifiés. | **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")** renvoie la date 21 janvier 2016, en fonction du format personnalisé et de la culture spécifiés. Toutefois, **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")** lève une exception pour informer l'utilisateur que la chaîne spécifiée n'est pas identifiée comme une date valide. |
| DATETIMEVALUE (chaîne, format) | Renvoie une représentation sous forme de date et d'heure de la chaîne spécifiée dans le format spécifié. | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** renvoie 2:55:00 AM le 21 décembre 2016, en fonction du format personnalisé spécifié et de la culture **EN-US** de l'application par défaut. |
| DATETIMEVALUE (chaîne, format, culture) | Renvoie une représentation sous forme de date/heure de la chaîne spécifiée dans le format et la culture spécifiés. | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")** renvoie 2:55:00 AM le 21 décembre 2016, en fonction du format personnalisé et de la culture spécifiés. Toutefois, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")** lève une exception pour informer l'utilisateur que la chaîne spécifiée n'est pas identifiée comme une date/heure valide. |

### <a name="list-functions"></a>Fonctions de liste

<table>
<thead>
<tr>
<th>Fonction</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr>
<td>SPLIT (input, length)</td>
<td>Fractionne la chaîne d'entrée spécifiée en sous-chaînes, dans la longueur spécifiée. Renvoie le résultat comme nouvelle liste.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> renvoie une liste composée de deux enregistrements avec un champ <strong>CHAÎNE</strong>. Le champ du premier enregistrement contient le texte <strong>&quot;abc&quot;</strong>, et le champ du deuxième enregistrement contient le texte <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr>
<td>SPLIT (entrée, séparateur)</td>
<td>Fractionne la chaîne d'entrée spécifiée en sous-chaînes, en fonction du délimiteur spécifié.</td>
<td><strong>SPLIT (&quot;XAb aBy&quot;, &quot;aB&quot;)</strong> renvoie une liste composée de trois enregistrements avec un champ <strong>CHAÎNE</strong>. Le champ dans le premier enregistrement contient le texte <strong>&quot;X&quot;</strong>, le champ du deuxième enregistrement contient le texte &quot;&nbsp;&quot; et le champ dans le troisième enregistrement contient le texte <strong>&quot;y&quot;</strong>. Si le séparateur est vide, une nouvelle liste est retournée, composée d'un enregistrement avec un champ <strong>CHAÎNE</strong> qui contient le texte d'entrée. Si l'entrée est vide, une nouvelle liste vide est retournée.
Si l'entrée ou le séparateur n'est pas spécifié (null), une exception d'application est levée.</td>
</tr>
<tr>
<td>SPLITLIST (list, number)</td>
<td>Fractionne la liste spécifiée en lots, dont chacun contient le nombre d'enregistrements spécifié. Renvoie le résultat comme nouvelle liste de traitements par lots contenant les éléments suivants :
<ul>
<li>Traitements par lots comme listes régulières (composant <strong>Valeur</strong>)</li>
<li>Numéro de traitement par lots actuel (composant <strong>BatchNumber</strong>)</li>
</ul>
</td>
<td>Dans l'illustration suivante, une source de données <strong>Lignes</strong> est créée sous la forme d'une liste de trois enregistrements. Cette liste est divisée en lots, dont chacun contient jusqu'à deux enregistrements.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>L'illustration suivante présente la structure de format conçue. Dans cette structure de format, les liaisons à la source de données <strong>Lignes</strong> sont créées pour générer une sortie au format XML. Cette sortie répertorie les nœuds individuels de chaque lot et les enregistrements qu'il contient.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>L'illustration suivante présente le résultat de l'exécution du format conçu.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>
</td>
</tr>
<tr>
<td>LIST (record 1 [, record 2, …])</td>
<td>Renvoie une liste créée à partir des arguments spécifiés.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> renvoie un enregistrement vide, dans lequel la liste des champs contient tous les champs des listes d'enregistrements <strong>MainData</strong> et <strong>OtherData</strong>.</td>
</tr>
<tr>
<td>LISTJOIN (list 1, list 2, …)</td>
<td>Renvoie une liste conjointe créée à partir des listes d'arguments spécifiés.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> renvoie une liste de six enregistrements, dans lequel un champ de type de données <strong>STRING</strong> contient une seule lettre.</td>
</tr>
<tr>
<td>ISEMPTY (list)</td>
<td>Renvoie la valeur <strong>TRUE</strong> si la liste spécifiée ne contient aucun élément. Sinon, renvoie la valeur <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr>
<td>EMPTYLIST (list)</td>
<td>Renvoie une liste vide à l'aide de la liste spécifiée comme source pour la structure de liste.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> renvoie une nouvelle liste vide ayant la même structure que la liste qui est renvoyée par la fonction <strong>SPLIT</strong>.</td>
</tr>
<tr>
<td>FIRST (list)</td>
<td>Renvoie le premier enregistrement de la liste spécifiée, si cet enregistrement n'est pas vide. Sinon, entraîne une exception.</td>
<td></td>
</tr>
<tr>
<td>FIRSTORNULL (list)</td>
<td>Renvoie le premier enregistrement de la liste spécifiée, si cet enregistrement n'est pas vide. Sinon, renvoie un enregistrement <strong>null</strong>.</td>
<td></td>
</tr>
<tr>
<td>LISTOFFIRSTITEM (list)</td>
<td>Renvoie une liste qui contient uniquement le premier élément de la liste spécifiée.</td>
<td></td>
</tr>
<tr>
<td>ALLITEMS (path)</td>
<td>Cette fonction s'exécute en tant que sélection en mémoire. Elle renvoie une nouvelle liste aplatie qui représente tous les articles correspondant au chemin spécifié. Le chemin doit être défini comme le chemin d'accès valide de la source de données vers un élément de source de données d'un type de données de liste d'enregistrements. Les éléments de données tels que la chaîne de chemin d'accès et la date doivent déclencher une erreur dans le générateur d'expression ER au moment de la conception.</td>
<td>Si vous entrez <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> comme source de données (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> renvoie <strong>3</strong>.</td>
</tr>
<tr>
<td>ALLITEMSQUERY (path)</td>
<td>Cette fonction s'exécute en tant que requête SQL jointe. Elle renvoie une nouvelle liste aplatie qui représente tous les articles correspondant au chemin spécifié. Le chemin d'accès spécifié doit être défini comme chemin d'accès de source de données valide d'un élément de source de données d'un type de données de liste d'enregistrements, et il doit contenir au moins une relation. Les éléments de données tels que la chaîne de chemin d'accès et la date doivent déclencher une erreur dans le générateur d'expression ER au moment de la conception.</td>
<td>Définissez les sources de données suivantes dans la mise en correspondance des modèles :
<ul>
<li><strong>CustInv</strong> (type <strong>Enregistrements de la table</strong>), qui fait référence à la table CustInvoiceTable</li> 
<li><strong>FilteredInv</strong> (type <strong>Champ calculé</strong>), qui contient l'expression <strong>FILTER (CustInv, CustInv.InvoiceAccount = &quot;US-001&quot;)</strong></li>
<li><strong>JourLines</strong> (type <strong>Champ calculé</strong>), qui contient l'expression <strong>ALLITEMSQUERY (FilteredInv.'&lt;Relations'.CustInvoiceJour.'&lt;Relations'.CustInvoiceTrans)</strong></li>
</ul>
<p>Lorsque vous exécutez la mise en correspondance des modèles pour appeler la source de données <strong>JourLines</strong>, l'instruction SQL suivante est exécutée :</p>
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN CUSTINVOICETRANS T3 WHERE...
</td>
</tr>
<tr>
<td>ORDERBY (list [, expression 1, expression 2, …])</td>
<td>Renvoie la liste spécifiée une fois qu'elle a été triée en fonction des arguments spécifiés. Ces arguments peuvent être définis comme expressions.</td>
<td>Si <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>ORDERBY (Vendors, Vendors.'name()')</strong> renvoie une liste de fournisseurs qui est triée par nom dans l'ordre croissant.</td>
</tr>
<tr>
<td>REVERSE (list)</td>
<td>Permet de renvoyer la liste spécifiée dans l'ordre de tri inverse.</td>
<td>Si <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> renvoie une liste de fournisseurs qui est triée par nom dans l'ordre décroissant.</td>
</tr>
<tr>
<td>WHERE (list, condition)</td>
<td>Renvoie la liste spécifiée une fois qu'elle a été filtrée en fonction de la condition spécifiée. La condition spécifiée est appliquée à la liste en mémoire. Ainsi, la fonction <strong>WHERE</strong> diffère de la fonction <strong>FILTER</strong>.</td>
<td>Si <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> renvoie la liste des fournisseurs faisant partie du groupe de fournisseurs 40.</td>
</tr>
<tr>
<td>ENUMERATE (list)</td>
<td>Renvoie une liste composée des enregistrements énumérés de la liste spécifiée, et qui expose les éléments suivants :
<ul>
<li>Les enregistrements de la liste spécifiée comme listes régulières (composant <strong>Valeur</strong>)</li>
<li>L'index des enregistrements actuels (composant <strong>Numéro</strong>)</li>
</ul>
</td>
<td>Dans l'illustration suivante, une source de données <strong>Énumérée</strong> est créée sous la forme d'une liste énumérée des enregistrements fournisseurs de la source de données <strong>Fournisseurs</strong> qui fait référence à la table VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>L'illustration suivante présente le format. Dans ce format, des liaisons de données sont créées pour générer la sortie au format XML. Cette sortie répertorie des fournisseurs individuels comme nœuds énumérés.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>L'illustration suivante présente le résultat de l'exécution du format conçu.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>
</td>
</tr>
<tr>
<td>COUNT (list)</td>
<td>Renvoie le nombre d'enregistrements dans la liste spécifiée, si la liste n'est pas vide. Sinon, renvoie la valeur <strong>0</strong> (zéro).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot;, 3))</strong> renvoie <strong>2</strong>, car la fonction <strong>SPLIT</strong> crée une liste composée de deux enregistrements.</td>
</tr>
<tr>
<td>LISTOFFIELDS (path)</td>
<td>Renvoie une liste d'enregistrements créée à partir d'un argument de l'un des types suivants :
<ul>
<li>Énumération du modèle</li>
<li>Énumération de format</li>
<li>Conteneur</li>
</ul>
<p>La liste créée comprend des enregistrements avec les champs suivants :</p>
<ul>
<li>Nom</li>
<li>Étiquette</li>
<li>Description</li>
</ul>
À l'exécution, les champs <strong>Étiquette</strong> et <strong>Description</strong> renvoient des valeurs basées sur les paramètres de langue du format.
</td>
<td>Dans l'illustration suivante, une énumération est présentée dans un modèle de données.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>Les détails suivants sont illustrés dans le graphique ci-dessous :</p>
<ul>
<li>L'énumération du modèle est insérée dans un état comme source de données.</li>
<li>Une expression ER utilise l'énumération de modèle comme paramètre de la fonction <strong>LISTOFFIELDS</strong>.</li>
<li>Une source de données du type de liste d'enregistrements est insérée dans un état à l'aide de l'expression ER créée.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>L'exemple suivant montre les éléments de format ER liés à la source de données du type de liste d'enregistrements créée à l'aide de la fonction <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>L'illustration suivante présente le résultat de l'exécution du format conçu.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE] Selon les paramètres de langue configurés pour les éléments de format FILE et FOLDER parents, le texte traduit pour les étiquettes et les descriptions est renseigné dans la sortie du format ER.</blockquote>
</td>
</tr>
<tr>
<td>LISTOFFIELDS (path, language)</td>
<td>Renvoie une liste d'enregistrements créée à partir d'un argument, par exemple une énumération de modèle, une énumération de format ou un conteneur. La liste créée comprend des enregistrements avec les champs suivants :
<ul>
<li>Nom</li>
<li>Étiquette</li>
<li>Description</li>
<li>Est traduit</li>
</ul>
À l'exécution, les champs <strong>Étiquette</strong> et <strong>Description</strong> renvoient des valeurs basées sur les paramètres de langue du format et la langue spécifiée. Le champ <strong>Est traduit</strong> indique si le champ <strong>Libellé</strong> a été traduit dans la langue spécifiée.
</td>
<td>Par exemple, vous utilisez le type de source de données <strong>Champ calculé</strong> pour configurer les sources de données <strong>enumType_de</strong> et <strong>enumType_deCH</strong> pour l'énumération du modèle de données <strong>enumType</strong>.
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
<p>Dans ce cas, vous pouvez utiliser l'expression suivante pour obtenir l'étiquette de la valeur d'énumération en allemand suisse, si la traduction est disponible. Si la traduction suisse-allemande n'est pas disponible, l'étiquette est en allemand.</p>
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
</td>
</tr>
<tr>
<td>STRINGJOIN (list, field name, delimiter)</td>
<td>Renvoie une chaîne composée des valeurs concaténées du champ spécifié dans la liste spécifiée. Les valeurs sont séparées par le séparateur spécifié.</td>
<td>Si vous entrez <strong>SPLIT(&quot;abc&quot; , 1)</strong> comme source de données (DS), <strong>STRINGJOIN (DS, DS.Value, &quot;-&quot;)</strong> renvoie <strong>&quot;a-b-c&quot;</strong>.</td>
</tr>
<tr>
<td>SPLITLISTBYLIMIT (list, limit value, limit source)</td>
<td>Sépare la liste spécifiée en une nouvelle liste de sous-listes et renvoie le résultat dans le contenu de la liste d'enregistrements. Le paramètre <strong>limit value</strong> définit la valeur de la limite pour diviser la liste d'origine. Le paramètre <strong>limit source</strong> définit l'étape à laquelle la somme totale augmente. La limite n'est pas appliquée à un article unique de la liste d'origine si la source de limite dépasse la limite définie.</td>
<td>L'illustration suivante présente un format. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p>L'illustration suivante présente les sources de données utilisées pour le format.</p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>L'illustration suivante présente le résultat de l'exécution du format. Dans ce cas, la sortie est une liste plate des articles de marchandise.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>Dans les illustrations suivantes, le même format a été ajusté de manière à présenter la liste des articles de marchandise par lots lorsqu'un seul lot doit inclure des marchandises et le poids total ne doit pas dépasser la limite de 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>L'illustration suivante présente le résultat de l'exécution du format ajusté.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE] La limite n'est pas appliquée au dernier article de la liste d'origine, car la valeur (11) de la source de sa limite (poids) dépasse la limite définie (9). Utilisez la fonction <strong>WHERE</strong> ou l'expression <strong>Activé</strong> de l'élément de format correspondant pour ignorer les sous-listes lors de la génération d'états, si nécessaire.</blockquote>
</td>
</tr>
<tr>
<td>FILTER (list, condition)</td>
<td>Renvoie la liste spécifiée une fois que la requête a été modifiée pour filtrer la condition spécifiée. Cette fonction diffère de la fonction <strong>WHERE</strong>, car la condition spécifiée est appliquée à toute source de données ER du type <strong>Enregistrements de table</strong> au niveau de la base de données. La liste et la condition peuvent être définies à l'aide de tables et de relations.</td>
<td>Si <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable, <strong>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> renvoie la liste des fournisseurs faisant partie du groupe de fournisseurs 40. Si <strong>Fournisseur</strong> est configuré comme source de données de génération d'états électroniques qui fait référence à la table VendTable et si <strong>parmVendorBankGroup</strong> est configuré comme source de données de génération d'états électroniques qui renvoie une valeur du type de données <strong>Chaîne</strong>, <strong>FILTER (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> renvoie la liste des comptes fournisseurs appartenant à un groupe bancaire spécifique.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Fonctions logiques

| Fonction | Description | Exemple |
|----------|-------------|---------|
| CASE (expression, option 1, result 1 \[, option 2, result 2\] ... \[, default result\]) | Permet d'évaluer la valeur d'expression spécifiée par rapport aux autres options spécifiées. Renvoie le résultat de l'option qui est égal à la valeur de l'expression. Sinon, renvoie le résultat par défaut en option, si un résultat par défaut est spécifié. (Le résultat par défaut est le dernier paramètre qui n'est pas précédé par une option.) | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** renvoie la chaîne **"WINTER"** lorsque la date de session Finance and Operations actuelle se situe entre octobre et décembre. Sinon, elle renvoie une chaîne vide. |
| IF (condition, value 1, value 2) | Renvoie la première valeur spécifiée lorsque la condition spécifiée est remplie. Sinon, renvoie la deuxième valeur spécifiée. Si la valeur 1 et la valeur 2 sont des enregistrements ou des listes d'enregistrements, le résultat affiche uniquement les champs qui existent dans les deux listes. | **IF (1=2, "condition is met", "condition is not met")** renvoie la chaîne **"condition is not met"**. |
| NOT (condition) | Renvoie la valeur logique inversée de la condition spécifiée. | **NOT (TRUE)** renvoie **FALSE**. |
| AND (condition 1\[, condition 2, …\]) | Renvoie la valeur **TRUE** si *toutes* les conditions spécifiées sont vraies. Sinon, renvoie la valeur **FALSE**. | **AND (1=1, "a"="a")** renvoie **TRUE**. **AND (1=2, "a"="a")** renvoie **FALSE**. |
| OR (condition 1\[, condition 2, …\]) | Renvoie la valeur **FALSE** si *toutes* les conditions spécifiées sont fausses. Renvoie la valeur **TRUE** si *l'une* des conditions spécifiées est vraie. | **OR (1=2, "a"="a")** renvoie **TRUE**. |
| VALUEIN (entrée, liste, expression d'élément de liste) | Détermine si l'entrée spécifiée correspond à une valeur quelconque d'un article dans la liste spécifiée. Retourne **TRUE** si l'entrée spécifiée correspond au résultat de l'exécution de l'expression spécifiée pour au moins un enregistrement. Sinon, renvoie la valeur **FALSE**. Le paramètre **entrée** représente le chemin d'accès d'un élément de données source. La valeur de cet élément est mise en correspondance. Le paramètre **liste** représente le chemin d'accès d'un élément de source de données du type de liste d'enregistrements comme une liste d'enregistrements qui contient une expression. La valeur de cet élément est comparée à l'entrée spécifiée. L'argument **expression d'article de liste** représente une expression qui indique ou contient un champ unique de la liste spécifiée à utiliser pour la mise en correspondance. | Pour obtenir des exemples, consultez la section [Exemples : VALUEIN (entrée, liste, expression d'élément de liste)](#examples-valuein-input-list-list-item-expression) ci-après. |

#### <a name="examples-valuein-input-list-list-item-expression"></a>Exemples : VALUEIN (entrée, liste, expression d'élément de liste)
En général la fonction **VALUEIN** est traduite en un ensemble de conditions **OR** :

(input = list.item1.value) OR (input = list.item2.value) OR …

##### <a name="example-1"></a>Exemple 1 :
Vous définissez la source de données suivante dans votre modèle de mise en correspondance : **Liste** (type **Champ calculé**). Cette source de données contient l'expression **SPLIT ("a,b,c", ",")**.

Lorsqu'une source de données est appelée qui est configurée comme l'expression **VALUEIN ("B", List, List.Value)**, elle retourne **TRUE**. Dans ce cas, la fonction **VALUEIN** est traduite en l'ensemble de conditions suivant :

**(("B" = "a") or ("B" = "b") or ("B" = "c"))**, où **("B" = "b")** est égal à **TRUE**

Lorsqu'une source de données est appelée qui est configurée comme l'expression **VALUEIN ("B", List, LEFT(List.Value, 0))**, elle retourne **FALSE**. Dans ce cas, la fonction **VALUEIN** est traduite en la condition suivante :

**("B" = "")**, qui n'est pas égal à **TRUE**

Notez que la limite supérieure du nombre de caractères dans le texte d'une telle condition est de 32 768 caractères. Par conséquent, vous ne devez pas créer de sources de données susceptibles de dépasser cette limite au moment de l'exécution. Si la limite est dépassée, l'application cesse de s'exécuter, et une exception est levée. Par exemple, cette situation peut se produire si la source de données est configurée comme **WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)**, et les listes **List1** et **List2** contiennent un grand nombre d'enregistrements.

Dans certains cas, la fonction **VALUEIN** est traduite en une instruction de base de données à l'aide de l'opérateur **EXISTS JOIN**. Ce comportement se produit lorsque la fonction **FILTER** est utilisée et que les conditions suivantes sont remplies :

- L'option **ASK FOR QUERY** est désactivée pour la source de données de la fonction **VALUEIN** qui fait référence à la liste d'enregistrements. (Aucune condition supplémentaire n'est appliquée à cette source de données au moment de l'exécution.)
- Aucune expression imbriquée n'est configurée pour la source de données de la fonction **VALUEIN** qui fait référence à la liste d'enregistrements.
- Un élément de liste de la fonction **VALUEIN** fait référence à un champ (pas à une expression ou à une méthode) de la source de données spécifiée.

Envisagez d'utiliser cette option au lieu de la fonction **WHERE** comme décrit précédemment dans cet exemple.

##### <a name="example-2"></a>Exemple 2 :

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- **In** (type **Enregistrements de la table**), qui fait référence à la table Intrastat
- **Port** (type **Enregistrements de la table**), qui fait référence à la table IntrastatPort

Lorsqu'une source de données est appelée qui est configurée comme l'expression **FILTER (In, VALUEIN(In.Port, Port, Port.PortId)**, l'instruction SQL suivante est générée pour retourner les enregistrements filtrés de la table Intrastat :

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Pour les champs **dataAreaId**, l'instruction SQL finale est générée en utilisant l'opérateur **IN**.

##### <a name="example-3"></a>Exemple 3

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- **Le** (type **Champ calculé**), qui contient l'expression **SPLIT ("DEMF,GBSI,USMF", ",")**
- **In** (type **Enregistrements de table**), qui fait référence à la table Intrastat et pour laquelle l'option **Cross-company** est activée

Lorsqu'une source de données est appelée qui est configurée comme expression **FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)**, l'instruction SQL finale contient la condition suivante :

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

### <a name="mathematical-functions"></a>Fonctions mathématiques

| Fonction | Description  | Exemple |
|----------|-------------|---------|
| Retour marchandises (numéro) | Renvoie la valeur absolue du nombre spécifié. (En d'autres termes, renvoie le nombre sans son signe.) | **ABS (-1)** renvoie **1**. |
| POWER (number, power) | Renvoie le résultat d'élever le nombre positif spécifié à la puissance spécifiée. | **POWER (10, 2)** renvoie **100**. |
| NUMBERVALUE (string, decimal separator, digit grouping separator) | Convertit la chaîne spécifiée en un chiffre. Le séparateur décimal spécifié est utilisé entre les parties entières et fractionnaires d'un nombre décimal. Le séparateur de regroupement de chiffres spécifié est utilisé comme séparateur de milliers. | **NUMBERVALUE("1 234,56", ",", " ")** renvoie la valeur **1234.56**. |
| VALUE (string) | Convertit la chaîne spécifiée en un chiffre. Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d'union (-) est utilisé comme signe moins. Lève une exception si la chaîne spécifiée contient d'autres caractères non numériques. | **VALUE ("1 234,56")** entraîne une exception. |
| ROUND (number, decimals) | Renvoie le nombre spécifié une fois qu'il a été arrondi au nombre de décimales spécifié :<ul><li>Si la valeur du paramètre **decimals** est supérieure à 0 (zéro), le numéro spécifié est arrondi au nombre de décimales.</li><li>Si la valeur du paramètre **decimals** est **0** (zéro), le numéro spécifié est arrondi à l'entier le plus proche.</li><li>Si la valeur du paramètre **decimals** est inférieure à 0 (zéro), le numéro spécifié est arrondi à gauche de la virgule.</li></ul> | **ROUND (1200.767, 2)** arrondit à deux décimales et renvoie **1200.77**. **ROND (1200.767), -3** arrondit au multiple de 1 000 le plus proche et renvoie **1 000**. |
| ROUNDDOWN (number, decimals) | Renvoie le nombre spécifié une fois qu'il a été arrondi au nombre inférieur de décimales spécifié.<blockquote>[!NOTE] Cette fonction se comporte comme **ROUND**, mais elle arrondit toujours le nombre spécifié vers le bas (vers zéro).</blockquote> | **ROUNDDOWN (1200.767, 2)** arrondit vers le bas à deux décimales et renvoie **1200.76**. **ROUNDDOWN (1700.767, -3)** arrondit vers le bas au multiple de 1 000 le plus proche et renvoie **1 000**. |
| ROUNDUP (number, decimals) | Renvoie le nombre spécifié une fois qu'il a été arrondi au nombre supérieur de décimales spécifié.<blockquote>[!NOTE] Cette fonction se comporte comme **ROUND**, mais elle arrondit toujours le nombre spécifié vers le haut (loin de zéro).</blockquote> | **ROUNDUP (1200.763, 2)** arrondit vers le haut à deux décimales et renvoie **1200.77**. **ROUNDUP (1200.767), -3** arrondit vers le haut au multiple de 1 000 le plus proche et renvoie **2 000**. |

### <a name="data-conversion-functions"></a>Fonctions de conversion des données

| Fonction | Description | Exemple |
|----------|-------------|---------|
| VALUE (string) | Convertit la chaîne spécifiée en un chiffre. Les virgules et les points (.) sont considérés comme des séparateurs de nombres décimaux, et un trait d'union (-) est utilisé comme signe moins. Lève une exception si la chaîne spécifiée contient d'autres caractères non numériques. | **VALUE ("1 234,56")** entraîne une exception. |
| NUMBERVALUE (string, decimal separator, digit grouping separator) | Convertit la chaîne spécifiée en un chiffre. Le séparateur décimal spécifié est utilisé entre les parties entières et fractionnaires d'un nombre décimal. Le séparateur de regroupement de chiffres spécifié est utilisé comme séparateur de milliers. | **NUMBERVALUE("1 234,56", ",", " ")** renvoie **1234.56**. |
| INTVALUE (chaîne) | Renvoie une représentation sous forme de nombre entier de la chaîne spécifiée. Les décimales sont tronquées. | **INTVALUE ("100.77")** renvoie **100**. |
| INTVALUE (nombre) | Renvoie une représentation sous forme de nombre entier du nombre spécifié. Les décimales sont tronquées. | **INTVALUE (-100.77)** retourne **-100**. |
| INT64VALUE (string) | Renvoie une représentation int64 de la chaîne spécifiée. Les décimales sont tronquées. | **INT64VALUE ("22565422744")** renvoie **22565422744**. |
| INT64VALUE (number) | Renvoie une représentation int64 du nombre spécifié. Les décimales sont tronquées. | **INT64VALUE (22565422744.00)** retourne **22565422744**. |

### <a name="record-functions"></a>Fonctions d'enregistrement

| Fonction | Description | Exemple |
|----------|-------------|---------|
| NULLCONTAINER (list) | Renvoie un enregistrement **null** ayant la même structure que la liste d'enregistrements ou l'enregistrement spécifié.<blockquote>[!NOTE] Cette fonction est obsolète. Utilisez **EMPTYRECORD** à la place.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction **SPLIT**. |
| EMPTYRECORD (record) | Renvoie un enregistrement **null** ayant la même structure que la liste d'enregistrements ou l'enregistrement spécifié.<blockquote>[!NOTE] Un enregistrement **null** est un enregistrement où tous les champs ont une valeur vide. Une valeur vide correspond à **0** (zéro) pour les nombres, à une chaîne vide pour les chaînes, etc.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction **SPLIT**. |

### <a name="text-functions"></a>Fonctions texte

<table>
<thead>
<tr>
<th>Fonction</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr>
<td>UPPER (string)</td>
<td>Renvoie la chaîne spécifiée une fois qu'elle a été convertie en lettres majuscules.</td>
<td><strong>UPPER(&quot;Sample&quot;)</strong> renvoie <strong>&quot;SAMPLE&quot;</strong>.</td>
</tr>
<tr>
<td>LOWER (string)</td>
<td>Renvoie la chaîne spécifiée une fois qu'elle a été convertie en lettres minuscules.</td>
<td><strong>LOWER (&quot;Sample&quot;)</strong> renvoie <strong>&quot;sample&quot;</strong>.</td>
</tr>
<tr>
<td>LEFT (string, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié du début de la chaîne spécifiée.</td>
<td><strong>LEFT (&quot;Sample&quot;, 3)</strong> renvoie <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr>
<td>RIGHT (string, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié de la fin de la chaîne spécifiée.</td>
<td><strong>RIGHT (&quot;Sample&quot;, 3)</strong> renvoie <strong>&quot;ple&quot;</strong>.</td>
</tr>
<tr>
<td>MID (string, starting position, number of characters)</td>
<td>Renvoie le nombre de caractères spécifié de la chaîne spécifiée, en commençant à l'emplacement spécifié.</td>
<td><strong>MID (&quot;Sample&quot;, 2, 3)</strong> renvoie <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr>
<td>LEN (string)</td>
<td>Retourne le nombre de caractères dans la chaîne spécifiée.</td>
<td><strong>LEN (&quot;Sample&quot;)</strong> renvoie <strong>6</strong>.</td>
</tr>
<tr>
<td>CHAR (number)</td>
<td>Permet de renvoyer la chaîne de caractères référencée par le nombre Unicode spécifié.</td>
<td><strong>CHAR (255)</strong> renvoie <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE] La chaîne retournée par cette fonction dépend de l'encodage sélectionné dans l'élément de format FILE parent. Pour obtenir la liste des codages pris en charge, consultez <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe de codage</a>.</blockquote>
</td>
</tr>
<tr>
<td>CONCATENATE (string 1 [, string 2, …])</td>
<td>Renvoie toutes les chaînes de texte spécifiées une fois qu'elles ont été associées dans une chaîne.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> renvoie <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE] L'expression <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> renvoie également <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr>
<td>TRANSLATE (string, pattern, replacement)</td>
<td>Renvoie la chaîne spécifiée une fois que toutes les occurrences des caractères de la chaîne de modèle spécifiée ont été remplacées par les caractères à la position correspondante dans la chaîne de remplacement spécifiée.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> remplace le modèle <strong>&quot;cd&quot;</strong> par la chaîne <strong>&quot;GH&quot;</strong> et renvoie <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>REPLACE (string, pattern, replacement, regular expression flag)</td>
<td>Lorsque le paramètre <strong>indicateur d'expression régulière</strong> spécifié a la valeur <strong>true</strong>, renvoie la chaîne spécifiée une fois qu'elle a été modifiée en appliquant l'expression régulière spécifiée sous la forme de l'argument <strong>modèle</strong> pour cette fonction. Cette expression est utilisée pour rechercher les caractères qui doivent être remplacés. Les caractères de l'argument <strong>remplacement</strong> spécifié sont utilisés pour remplacer les caractères qui sont recherchés. Lorsque le paramètre <strong>indicateur d'expression régulière</strong> spécifié a la valeur <strong>false</strong>, cette fonction se comporte comme <strong>TRANSLATE</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> applique une expression régulière qui supprime tous les symboles non-numériques, et renvoie <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> remplace le modèle <strong>&quot;cd&quot;</strong> par la chaîne <strong>&quot;GH&quot;</strong> et renvoie <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>TEXT (input)</td>
<td>Renvoie l'entrée spécifiée une fois qu'elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance Finance and Operations actuelle. Pour les valeurs de type <strong>real</strong>, la conversion de chaîne est limitée à deux décimales.</td>
<td>Si les paramètres régionaux du serveur de l'instance Finance and Operations sont définis comme <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> renvoie la date de la session Finance and Operations actuelle, 17 décembre 2015, comme chaîne de texte <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> renvoie <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr>
<td>FORMAT (string 1, string 2[, string 3, …])</td>
<td>Renvoie la chaîne spécifiée une fois qu'elle a été mise en forme en substituant toutes les occurrences de <strong>%N</strong> par le <em>ième</em> argument. Les arguments sont des chaînes. Si un argument n'est pas fourni pour un paramètre, le paramètre est renvoyé comme <strong>&quot;%N&quot;</strong> dans la chaîne. Pour les valeurs de type <strong>real</strong>, la conversion de chaîne est limitée à deux décimales.</td>
<td>Dans l'illustration suivante, la source de données <strong>PaymentModel</strong> renvoie la liste des enregistrements client via le composant <strong>Customer</strong> et la valeur de la date de traitement via le champ <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>Dans le format de génération d'états électroniques conçu pour générer un fichier électronique pur les clients sélectionnés, <strong>PaymentModel</strong> est sélectionné comme source de données et contrôle le flux de processus. Une exception est levée pour informer les utilisateurs finaux lorsqu'un client sélectionné est arrêté à la date lorsque l'état est traité. La formule qui est conçue pour ce type de contrôle de traitement peut utiliser les ressources suivantes :</p>
<ul>
<li>Libellé Finance and Operations SYS70894, avec le texte suivant :
<ul>
<li><strong>Pour l'anglais (États-Unis) :</strong> &quot;Nothing to print&quot;</li>
<li><strong>Pour l'allemand :</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Libellé Finance and Operations SYS18389, avec le texte suivant :
<ul>
<li><strong>Pour l'anglais :</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Pour l'allemand :</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Voici la formule qui peut être conçue :</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Si un rapport est traité pour le client <strong>Litware Retail</strong> le 17 décembre 2015, dans la culture <strong>EN-US</strong> et la langue <strong>EN-US</strong>, cette formule renvoie le texte suivant, qui peut être présenté à l'utilisateur comme message d'exception :</p>
<p>&quot;Nothing to print. Customer Litware Retail is stopped for 12/17/2015.&quot;</p>
<p>Si le même état est traité pour le client <strong>Litware Retail</strong> le 17 décembre 2015, dans la culture <strong>DE</strong> et la langue <strong>DE</strong>, la formule renvoie le texte suivant, qui utilise un format de date différent :</p>
<p>&quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE] La syntaxe suivante est appliquée aux formules de génération d'états électroniques pour les libellés :
<ul>
<li><strong>Pour les libellés des ressources Finance and Operations :</strong> <strong>@&quot;X&quot;</strong>, où <strong>X</strong> est l'ID libellé de l'arbre d'objets d'application (AOA)</li>
<li><strong>Pour les libellés se trouvant dans les configurations de génération d'états électroniques :</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, où <strong>X</strong> est l'ID libellé dans la configuration de génération d'états électroniques</li>
</ul>
</blockquote>
</td>
</tr>
<tr>
<td>NUMBERFORMAT (number, format)</td>
<td>Renvoie une représentation sous forme de chaîne du nombre spécifié dans le format spécifié. (Pour plus d'informations sur les formats pris en charge, voir <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> et <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personnalisés</a>.) Le contexte dans lequel cette fonction est exécutée détermine la culture utilisée pour formater des numéros.</td>
<td>Pour la culture américaine, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> renvoie <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> renvoie <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr>
<td>NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)</td>
<td>Renvoie le nombre spécifié une fois qu'il a été défini (converti en chaînes de texte) dans la langue spécifiée. Le code langue est facultatif. Lorsqu'il est défini comme une chaîne vide, le code langue du contexte d'exécution est utilisé. (Le code langue du contexte d'exécution est défini pour un dossier ou un fichier en cours de génération). Le code devise est également facultatif. Lorsqu'il est défini comme une chaîne vide, la devise de la société est utilisée.
<blockquote>[!NOTE] Les paramètres <strong>print currency name flag</strong> et <strong>decimal points</strong> sont analysés pour les codes de langue suivants uniquement : <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> et <strong>RU</strong>. En outre, le paramètre <strong>print currency name flag</strong> est analysé uniquement pour les sociétés Finance and Operations où le contexte du pays ou de la région prend en charge la déclinaison des noms de devise.</blockquote>
</td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> renvoie <strong>&quot;One Thousand Two Hundred Thirty Four and 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> renvoie <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> renvoie <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr>
<td>PADLEFT (string, length, padding chars)</td>
<td>Renvoie une chaîne de longueur spécifique, où le début de la chaîne spécifiée est entouré par les caractères spécifiés.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> renvoie la chaîne de texte <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr>
<td>TRIM (string)</td>
<td>Renvoie la chaîne de texte spécifiée une fois que les espaces de début et de fin ont été tronqués, et une fois que plusieurs espaces entre les mots ont été supprimés.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sample&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;text&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> renvoie <strong>&quot;Sample text&quot;</strong>.</td>
</tr>
<tr>
<td>GETENUMVALUEBYNAME (chemin d'accès de la source de données d'énumération, texte de libellé de la valeur d'énumération)</td>
<td>Renvoie une valeur de la source de données d'énumération spécifiée, en fonction du texte spécifié de l'étiquette d'énumération.</td>
<td>Dans l'illustration suivante, l'énumération <strong>ReportDirection</strong> est présentée dans un modèle de données. Notez que les étiquettes sont définies pour les valeurs d'énumération.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Les détails suivants sont illustrés dans le graphique ci-dessous :</p>
<ul>
<li>L'énumération du modèle <strong>ReportDirection</strong> est insérée dans un état comme source de données, <strong>$Direction</strong>.</li>
<li>Une expression ER, <strong>$IsArrivals</strong>, est conçue pour utiliser l'énumération du modèle comme paramètre de cette fonction. La valeur de cette expression est <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>
</td>
</tr>
<tr>
<td>GUIDVALUE (input)</td>
<td>Convertissez l'entrée spécifiée du type de données <strong>Chaîne</strong> en un élément de données du type de données <strong>GUID</strong>.<blockquote>[!NOTE] Pour créer une conversion dans la direction opposée (c'est-à-dire, pour convertir l'entrée spécifiée du type de données <strong>GUID</strong> en un élément de données de type de données <strong>Chaîne</strong>), vous pouvez utiliser la fonction <strong>TEXT()</strong>.</blockquote></td>
<td>Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :
<ul>
<li><strong>myID</strong> (type <strong>Champ calculé</strong>), qui contient l'expression <strong>GUIDVALUE(&quot;AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0&quot;)</strong></li>
<li><strong>Users</strong> (type <strong>Enregistrements de la table</strong>), qui fait référence à la table UserInfo</li>
</ul>
Lorsque ces sources de données sont définies, vous pouvez utiliser une expression comme <strong>FILTER (Users, Users.objectId = myID)</strong> pour filtrer la table UserInfo selon le champ <strong>objectId</strong> du type de données <strong>GUID</strong>.
</td>
</tr>
<tr>
<td>JSONVALUE (id, path)</td>
<td>Analysez les données au format JavaScript Object Notation (JSON) qui sont accessibles par le chemin spécifié pour extraire une valeur scalaire basée sur l'ID spécifié.</td>
<td>La source de données <strong>$JsonField</strong> contient les données suivantes au format JSON : <strong>{&quot;BuildNumber&quot;:&quot;7.3.1234.1&quot;, &quot;KeyThumbprint&quot;:&quot;7366E&quot;}</strong>. Pour cette source de données, </strong>JSONVALUE ( &quot;BuildNumber&quot;, $JsonField)</strong> renvoie la valeur <strong>7.3.1234.1</strong> du type de données <strong>Chaîne</strong>.</td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Fonctions de conversion des données

| Fonction | Description | Exemple |
|----------|-------------|---------|
| TEXT (input) | Renvoie l'entrée spécifiée une fois qu'elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l'instance Finance and Operations actuelle. Pour les valeurs de type **real**, la conversion de chaîne est limitée à deux décimales. | Si les paramètres régionaux du serveur de l'instance Finance and Operations sont définis comme **EN-US**, **TEXT (NOW ())** renvoie la date de la session Finance and Operations actuelle, 17 décembre 2015, comme chaîne de texte **"12/17/2015 07:59:23 AM"**. **TEXT (1/3)** renvoie **"0.33"**. |
| QRCODE (chaîne) | Renvoie une image de code à réponse rapide (code QR) au format binaire base64 pour la chaîne spécifiée. | **QRCODE ("Sample text")** renvoie **U2FtcGxlIHRleHQ=**. |

### <a name="data-collection-functions"></a>Fonctions de collecte des données

| Fonction | Description | Exemple |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Renvoie le nom de l'élément du format actuel. Renvoie une chaîne vide lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | Pour en savoir plus sur l'utilisation de cette fonction, consultez le guide de tâche **ER Utiliser les données de la sortie du format pour compter et additionner**, qui fait partie du processus d'entreprise **Acquérir/Développer des composants de services/solutions informatiques**. |
| SUMIFS (key string for summing, criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\]) | Renvoie la somme des valeurs collectées pour les nœuds XML (où le nom est défini comme clé) durant l'exécution du format et qui remplit les conditions spécifiées (paires de plages et de valeurs). Renvoie une valeur **0** (zéro) lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | |
| SUMIF (key string for summing, criteria range string, criteria value string) | Renvoie la somme des valeurs collectées pour les nœuds XML (où le nom est défini comme clé) durant l'exécution du format et qui remplit la condition spécifiée (une plage et valeur). Renvoie une valeur **0** (zéro) lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | |
| COUNTIFS (criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\]) | Renvoie le nombre de nœuds XML, qui a été collecté durant l'exécution du format, et qui remplit les conditions spécifiées (paires de plages et de valeurs). Renvoie une valeur **0** (zéro) lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | |
| COUNTIF (criteria range string, criteria value string) | Renvoie le nombre de nœuds XML, qui a été collecté durant l'exécution du format, et qui remplit la condition spécifiée (une plage et valeur). Renvoie une valeur **0** (zéro) lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | |
| COLLECTEDLIST (criteria range1 string, criteria value1 string \[, criteria range2 string, criteria value2 string, …\]) | Renvoie la liste des valeurs collectées pour les nœuds XML durant l'exécution du format, et qui remplit les conditions spécifiées (une plage et valeur). Renvoie une liste vide lorsque l'indicateur **Collecter les détails sur les sorties** des fichiers actuels est désactivé. | |

### <a name="other-business-domainspecific-functions"></a>Autre fonctions (spécifiques au domaine d'affaires)

| Fonction | description ; | Exemple |
|----------|-------------|---------|
| CONVERTCURRENCY (amount, source currency, target currency, date, company) | Convertit le montant en devises spécifié de la devise source spécifiée dans la devise cible spécifiée à l'aide des paramètres de la société Finance and Operations spécifiée à la date spécifiée. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** renvoie l'équivalent d'un euro en dollars US à la date de session actuelle, basée sur les paramètre de la société DEMF. |
| ROUNDAMOUNT (number, decimals, round rule) | Arrondit le montant spécifié au nombre de décimales spécifié en fonction de la règle d'arrondi spécifiée.<blockquote>[!NOTE] La règle d'arrondi doit être spécifiée comme valeur d'énumération **RoundOffType** de Finance and Operations.</blockquote> | Si le paramètre **model.RoundOff** est défini sur **Inférieur**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** renvoie la valeur **1000.78**. Si le paramètre **model.RoundOff** est défini sur **Normal** ou **Rounding-up**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** renvoie la valeur **1000.79**. |
| CURCredRef (digits) | Renvoie une référence créditeur, selon les chiffres du numéro de facture spécifié. | **CURCredRef ("VEND-200002")** renvoie **"2200002"**. |
| MOD\_97 (digits) | Renvoie une référence créditeur, comme une expression MOD97, selon les chiffres du numéro de facture spécifié. | **MOD\_97 ("VEND-200002")** renvoie **"20000285"**. |
| ISOCredRef (digits) | Renvoie une référence créditeur ISO (Organisation internationale de normalisation), en fonction des chiffres et des symboles alphabétiques du numéro de facture spécifié.<blockquote>[!NOTE] Pour éliminer des symboles de l'alphabet qui ne sont pas conformes à la norme ISO, le paramètre d'entrée doit être traduit avant d'être transmis à cette fonction.</blockquote> | **ISOCredRef ("VEND-200002")** renvoie **"RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (string, number) | Obtient l'ID de dimension financière supplémentaire spécifié. Dans le paramètre **string**, les dimensions sont représentées dans cette chaîne comme des ID séparés par des virgules. Le paramètre **number** définit le code souche de la dimension demandée dans la chaîne. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** renvoie **"CC"**. |
| GetCurrentCompany () | Renvoie une représentation sous forme de texte du code de l'entité juridique (société) à laquelle un utilisateur est actuellement connecté. | **GETCURRENTCOMPANY ()** renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA** dans Finance and Operations. |
| CH\_BANK\_MOD\_10 (digits) | Renvoie une référence créditeur, comme une expression MOD10, selon les chiffres du numéro de facture spécifié. | **CH\_BANK\_MOD\_10 ("VEND-200002")** renvoie **3**. |
| FA\_SUM (fixed asset code, value model code, start date, end date) | Renvoie le conteneur de données préparé du montant des immobilisations pour la période spécifiée. | **FA\_SUM ("COMP-000001", "Current", Date1, Date2)** renvoie le conteneur de données préparé de l'immobilisation **"COMP-000001"** avec le modèle de valeur **"Current"** pour une période allant de **Date1** à **Date2**. |
| FA\_BALANCE (fixed asset code, value model code, reporting year, reporting date) | Renvoie le conteneur de données préparé du solde des immobilisations. L'année de génération d'états doit être spécifiée comme valeur de l'énumération **AssetYear** dans Finance and Operations. | **FA\_SUM ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** renvoie le conteneur de données préparé des soldes de l'immobilisation **"COMP-000001"** avec le modèle de valeur **"Current"** à la date de la session Finance and Operations actuelle. |
| TABLENAME2ID (string) | Renvoie une représentation sous forme d'entier d'un ID table pour le nom de table spécifié. | **TABLENAME2ID ("Intrastat")** renvoie **1510**. |
| ISVALIDCHARACTERISO7064 (string) | Renvoie la valeur booléenne **TRUE** lorsque la chaîne donnée représente un numéro de compte bancaire international (IBAN) valide. Sinon, renvoie la valeur booléenne **FALSE**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** retourne **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** retourne **FALSE**. |
| NUMSEQVALUE (code souche de numéros, portée, ID portée) | Retourne la nouvelle valeur générée à partir d'une souche de numéros, selon le code souche de numéros, la portée, ainsi que l'ID portée spécifiés. La portée doit être spécifié comme valeur de l'énumération **ERExpressionNumberSequenceScopeType** (**Partagé**, **Entité juridique**, ou **Société**). Pour la portée **Partagé**, spécifiez une chaîne vide comme ID portée. Pour les portées **Société** et **Entité juridique**, spécifiez le code société comme ID portée. Pour les portées **Société** et **Entité juridique**, si vous spécifiez une chaîne vide comme ID portée, le code société actuel est utilisé. | Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :<ul><li>**enumScope** (type **énumération Dynamics 365 for Operations**), qui fait référence à l'énumération **ERExpressionNumberSequenceScopeType**</li><li>**NumSeq** (type **Champ calculé**), qui contient l'expression **NUMSEQVALUE ("Gene\_1", enumScope.Company, "")**</li></ul>Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros **Gene\_1** qui a été configurée pour la société qui fournit le contexte sous lequel le format ER est exécuté. |
| NUMSEQVALUE (code souche de numéros) | Retourne la nouvelle valeur générée d'une souche de numéros, d'après la souche de numéros spécifiée, la portée **Société**, et (comme ID portée) le code société qui fournit le contexte sous lequel format ER est exécuté. | Vous définissez la source de données suivante dans votre modèle de mise en correspondance : **NumSeq** (type **Champ calculé**). Cette source de données contient l'expression **NUMSEQVALUE ("Gene\_1")**. Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros **Gene\_1** qui a été configurée pour la société qui fournit le contexte sous lequel le format ER est exécuté. |
| NUMSEQVALUE (ID enregistrement de souche de numéros) | Retourne la nouvelle valeur générée à partir d'une souche de numéros, selon l'ID enregistrement de la souche de numéros spécifié. | Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :<ul><li>**LedgerParms** (type **Table**), qui fait référence à la table LedgerParameters</li><li>**NumSeq** (type **Champ calculé**), qui contient l'expression **NUMSEQVALUE (LedgerParameters.'numRefJournalNum()'.NumberSequenceId)**</li></ul>Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros qui a été configurée dans les paramètres de la comptabilité pour la société qui fournit le contexte sous lequel le format ER est exécuté. Cette souche de numéros identifie de manière unique les journaux et sert de numéro de lot qui relie les transactions. |

### <a name="functions-list-extension"></a>Extension de la liste des fonctions

La génération d'état électroniques prend en charge une capacité d'extension de la liste des fonctions utilisées dans les expressions de génération d'états électroniques. Pour cela, certaines opérations d'ingénierie sont requises. Pour obtenir des informations détaillées, consultez [Extension de la liste des fonctions de génération d'états électroniques](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des États électroniques](general-electronic-reporting.md)
- [Extension de la liste des fonctions de génération d'états électroniques (ER)](general-electronic-reporting-formulas-list-extension.md)

