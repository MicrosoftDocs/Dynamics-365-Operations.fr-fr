---
title: Inspectez le composant ER configuré pour éviter les problèmes d’exécution
description: Cette rubrique explique comment inspecter les composants de rapports électroniques (ER) configurés pour éviter que des problèmes d’exécution ne se produisent.
author: NickSelin
manager: AnnBe
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ba696fb7a8d9083d11cc29953cf1340a581afcf
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797339"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Inspectez le composant ER configuré pour éviter les problèmes d’exécution

[!include[banner](../includes/banner.md)]

Chaque composant de [format](general-electronic-reporting.md#FormatComponentOutbound) et [modèle de mappage](general-electronic-reporting.md#data-model-and-model-mapping-components) de [rapport électronique (ER)](general-electronic-reporting.md) configuré peut être [validé](er-fillable-excel.md#validate-an-er-format) au moment de la conception. Au cours de cette validation, une vérification de la cohérence est exécutée pour éviter les problèmes d’exécution susceptibles de se produire, tels que les erreurs d’exécution et la dégradation des performances. Pour chaque problème détecté, la vérification donne le chemin d’un élément problématique. Pour certains problèmes, un correctif automatique est disponible.

Par défaut, la validation est automatiquement appliquée dans les cas suivants pour une configuration ER contenant les composants ER mentionnés précédemment :

- Vous [importez](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) une nouvelle [version](general-electronic-reporting.md#component-versioning) d’une configuration ER dans votre instance de Microsoft Dynamics 365 Finance.
- Vous modifiez le [statut](general-electronic-reporting.md#component-versioning) de la configuration de l’ER modifiable, mis à jour de **Brouillon** à **Terminé**.
- Vous [redéfinissez](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) une configuration d’ER modifiable en appliquant une nouvelle version de base.

Vous pouvez exécuter explicitement cette validation. Sélectionnez l’une des trois options suivantes et suivez les étapes fournies :

- Option 1 :

    1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
    2. Dans l’arborescence des configurations du volet gauche, sélectionnez la configuration d’ER souhaitée qui contient le format d’ER ou le composant de mappage de modèle d’ER.
    3. Dans l’organisateur **Versions**, sélectionnez la version souhaitée de la configuration ER sélectionnée.
    4. Dans le volet Action, sélectionnez **Valider**.

- Option 2, pour un format ER :

    1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
    2. Dans l’arborescence des configurations du volet gauche, sélectionnez la configuration d’ER souhaitée qui contient le format d’ER ou le composant de format d’ER.
    3. Dans l’organisateur **Versions**, sélectionnez la version souhaitée de la configuration ER sélectionnée.
    4. Dans le volet Actions, sélectionnez **Concepteur**.
    5. Sur la page **Concepteur de formats**, sur le volet Actions, sélectionnez **Valider**.

- Option 3, pour un modèle de mappage ER :

    1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
    2. Dans l’arborescence des configurations du volet gauche, sélectionnez la configuration d’ER souhaitée qui contient le composant de modèle de mappage d’ER.
    3. Dans l’organisateur **Versions**, sélectionnez la version souhaitée de la configuration ER sélectionnée.
    4. Dans le volet Actions, sélectionnez **Concepteur**.
    5. Sur la page **Mise en correspondance de modèles à la source de données**, sur le volet Action, sélectionnez **Concepteur**.
    6. Sur la page **Concepteur de mappage de modèles**, sur le volet Action, sélectionnez **Valider**.

Pour ignorer la validation lors de l’importation de la configuration, procédez comme suit.

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Définissez l’option **Valider la configuration après l’importation** sur **Non**.

Pour ignorer la validation lorsque vous modifiez ou redéfinissez le statut de la version, procédez comme suit.

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Définissez l’option **Ignorer la validation lors du changement de statut de la configuration et de la redéfinition** sur **Oui**.

ER utilise les catégories suivantes pour regrouper les inspections des contrôles de cohérence :

- **Capacité d’exécution** – Inspections qui détectent les problèmes critiques pouvant survenir lors du runtime. Ces problèmes sont pour la plupart à un niveau **Erreur**. 
- **Performance** – Inspections qui détectent les problèmes susceptibles d’entraîner une exécution inefficace des composants ER configurés. Ces problèmes sont pour la plupart à un niveau **Avertissement**.
- **Intégrité des données** – Inspections qui détectent les problèmes pouvant entraîner une perte de données ou des problèmes de runtime. Ces problèmes sont pour la plupart à un niveau **Avertissement**.

## <a name="list-of-inspections"></a>Liste des inspections

Le tableau suivant offre une vue d’ensemble des inspections fournies par ER. Pour plus d’informations sur ces inspections, utilisez les liens de la première colonne pour accéder aux sections pertinentes de cette rubrique. Ces sections expliquent les types de composants pour lesquels ER fournit des inspections et comment vous pouvez reconfigurer les composants ER pour éviter les problèmes.

<table>
<thead>
<tr>
<th>Nom</th>
<th>Catégorie</th>
<th>Niveau</th>
<th>Message</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Conversion de type</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>Impossible de convertir l’expression de type &lt;type&gt; au champ de type &lt;type&gt;.</p>
<p><b>Erreur de runtime :</b> Exception pour type</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Compatibilité de type</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>L’expression configurée ne peut pas être utilisée comme liaison de l’élément de format actuel à une source de données, car cette expression renvoie la valeur du type de données &lt;type&gt; qui dépasse la portée des types de données pris en charge par l’élément de format actuel de type &lt;type&gt;.</p>
<p><b>Erreur de runtime :</b> Exception de type</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Élément de configuration manquant</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>Chemin d’accès introuvable &lt;chemin&gt;.</p>
<p><b>Erreur de runtime :</b> Élément de la configuration &lt;chemin d’accès&gt; introuvable</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Capacité d’exécution d’une expression avec la fonction FILTER</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>L’expression de liste de la fonction FILTER n’est pas utilisable dans une requête.</p>
<p><b>Erreur de runtime :</b> Le filtrage n’est pas pris en charge. Validez la configuration pour obtenir plus de détails à ce sujet.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Capacité d’exécution d’une source de données GROUPBY</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>Le chemin d’accès &lt;chemin d’accès&gt; ne prend pas en charge les requêtes.</td>
</tr>
<tr>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>La fonction Grouper par ne peut pas être exécutée avec une requête.</p>
<p><b>Erreur de runtime :</b> La fonction Grouper par ne peut pas être exécutée avec une requête.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Capacité d’exécution d’une source de données JOIN</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>Impossible de joindre une liste &lt;chemin d’accès&gt; qui n’est pas un filtre dans la requête.</p>
<p><b>Erreur de runtime :</b> La source de données jointe à la fonction doit être un champ calculé d’expression de filtre qui n’a pas été correctement appelé.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Préférence de la fonction FILTER comparée à WHERE</a></td>
<td>Performances</td>
<td>Avertissement</td>
<td>L’utilisation de la fonction FILTER pour l’expression est préférable à WHERE du point de vue des performances. Sélectionnez Corriger pour la remplacer automatiquement.</td>
</tr>
<tr>
<td><a href='#i8'>Préférence de la fonction ALLITEMSQUERY comparée à ALLITEMS</a></td>
<td>Performances</td>
<td>Avertissement</td>
<td>L’utilisation de la fonction ALLITEMSQUERY pour l’expression est préférable à ALLITEMS du point de vue des performances. Sélectionnez Corriger pour la remplacer automatiquement.</td>
</tr>
<tr>
<td><a href='#i9'>Prise en compte des cas de liste vide</a></td>
<td>Capacité d’exécution</td>
<td>Avertissement</td>
<td>
<p>La liste &lt;chemin d’accès&gt; n’a pas de vérification de cas de liste vide, cela peut entraîner une erreur au moment du runtime. Ajoutez un contrôle pour le cas de liste vide.</p>
<p><b>Erreur de runtime :</b> La liste est vide dans le &lt;chemin d’accès&gt;</p>
<p><b><a href='#i9a'>Problème potentiel</a> :</b> La ligne est remplie une fois tandis qu’une source de données à partir de laquelle elle est remplie contient plusieurs enregistrements</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Capacité d’exécution d’une expression avec la fonction FILTER (mise en cache)</a></td>
<td>Capacité d’exécution</td>
<td>Erreur</td>
<td>
<p>La fonction FILTER ne peut pas être appliquée au type de source de données sélectionné. Une source de données du type Enregistrements de la table est applicable uniquement lorsqu’elle n’est pas mise en cache et n’a pas de sources de données imbriquées ajoutées manuellement.</p>
<p><b>Erreur de runtime :</b> Le filtrage n’est pas pris en charge. Validez la configuration pour obtenir plus de détails à ce sujet.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Liaison manquante</a></td>
<td>Capacité d’exécution</td>
<td>Avertissement</td>
<td>
<p>Le chemin &lt;chemin d’accès&gt; n’a aucune liaison avec aucune source de données lors de l’utilisation du mappage du modèle.</p>
<p><b>Erreur de runtime :</b> Le Chemin &lt;chemin d’accès&gt; n’est pas lié</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Modèle non lié</a></td>
<td>Intégrité des données</td>
<td>Avertissement</td>
<td>Le fichier &lt;nom&gt; n’est lié à aucun composant de fichier et sera supprimé après le changement de statut de la version de configuration.</td>
</tr>
<tr>
<td><a href='#i13'>Format non synchronisé</a></td>
<td>Intégrité des données</td>
<td>Avertissement</td>
<td>Le nom défini &lt;nom du composant&gt; n’existe pas dans la feuille Excel &lt;nom de la feuille&gt;</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Conversion de type

ER vérifie si le type de données d’un champ de modèle de données est compatible avec le type de données d’une expression qui est configurée comme liaison de ce champ. Si les types de données sont incompatibles, une erreur de validation se produit dans le concepteur de mappage de modèle de gestion des états électroniques. Le message que vous recevez indique que ER ne peut pas convertir une expression de type A en un champ de type B.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer simultanément le modèle de données de gestion des états électroniques et les composants de mappage du modèle de gestion des états électroniques.
2. Dans l’arborescence du modèle de données, ajoutez un champ nommé **X** et sélectionnez **Entier** comme type de données.

    ![Champ X et le type de données Entier ajoutés à l’arborescence du mode de données sur la page Modèle de données](./media/er-components-inspections-01.png)

3. Dans le volet des sources de données du modèle de mappage, ajoutez une source de données de type **Champ calculé**.
4. Nommez la nouvelle source de données **Y** et configurez-la pour qu’elle contienne l’expression `INTVALUE(100)`.
5. Liez **X** à **Y**.
6. Dans le concepteur de modèle de données, modifiez le type de données du champ **X** du camp **Entier** à **Int64**.
7. Sélectionnez **Valider** pour inspecter le composant de mappage de modèle modifiable sur le **Concepteur de modèle de mappage**.

    ![validation du composant de mappage de modèle modifiable sur le Concepteur de modèle de mappage](./media/er-components-inspections-01.gif)

8. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage de la configuration de gestion des états électroniques sélectionnée sur la page **Configurations**.

    ![Validez pour inspecter le composant de modèle de mappage sur la page Configurations](./media/er-components-inspections-01a.png)

9. Notez qu’une erreur de validation se produit. Le message indique que la valeur du type **Entier** que l’expression `INTVALUE(100)` des résultats de la source de données **Y** ne peuvent pas être stockés dans le champ de modèle de données **X** du type **Int64**.

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter un format configuré pour utiliser le modèle de mappage.

![Erreurs de runtime sur la page Concepteur de format](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Mettez à jour la structure du modèle de données en modifiant le type de données du champ de modèle de données afin qu’il corresponde au type de données de l’expression qui est configurée pour la liaison de ce champ. Pour l’exemple précédent, le type de données du champ **X** doit être remplacé par **Entier**.

#### <a name="option-2"></a>Option 2

Mettez à jour le modèle de mappage en modifiant l’expression de la source de données liée au champ de modèle de données. Pour l’exemple précédent, l’expression de la source de données **Y** doit être remplacée par `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Compatibilité de type

ER vérifie si le type de données d’un élément de format de type de données est compatible avec le type de données d’une expression qui est configurée comme liaison de cet élément de format. Si les types de données sont incompatibles, une erreur de validation se produit dans le concepteur d’opérations ER. Le message que vous recevez indique que l’expression configurée ne peut pas être utilisée comme liaison de l’élément de format actuel à une source de données, car l’expression renvoie une valeur du type de données A qui dépasse la portée des types de données pris en charge par l’élément de format actuel de type B.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer simultanément le modèle de données ER et les composants de format ER.
2. Dans l’arborescence du modèle de données, ajoutez un champ nommé **X** et sélectionnez **Entier** comme type de données.
3. Dans l’arborescence de la structure de format, ajoutez un élément de format du type **Numérique**.
4. Nommez le nouvel élément de format **Y**. Dans le champ **Type numérique**, sélectionnez **Entier** comme type de données.
5. Liez **X** à **Y**.
6. Dans l’arborescence de la structure des formats, modifiez le type de données de l’élément de format **Y** de **Entier** à **Int64**.
7. Sélectionnez **Valider** pour inspecter le composant de format modifiable sur la page **Concepteur de format**.

    ![Validation de la compatibilité de type sur la page Concepteur de format](./media/er-components-inspections-02.gif)

8. Notez qu’une erreur de validation se produit. Le message indique que l’expression configurée ne peut accepter que des valeurs **Int64**. Par conséquent, la valeur du champ de modèle de données **X** de type **Entier** ne peut pas être entré dans l’élément de format **Y**.

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Mettez à jour la structure du format en modifiant le type de données de l’élément de format **Numérique** afin qu’il corresponde au type de données de l’expression qui est configurée pour la liaison de cet élément. Dans l’exemple précédent, la valeur du **type de données Numérique** de l’élément de format **X** doit être remplacé par **Entier**.

#### <a name="option-2"></a>Option 2

Mettez à jour le mappage de format de l’élément de format **X** en modifiant l’expression de `model.X` à `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Élément de configuration manquant

ER vérifie si les expressions de liaison contiennent uniquement des sources de données configurées dans le composant ER modifiable. Pour chaque liaison qui contient une source de données manquante dans le composant de gestion des états électroniques modifiable, une erreur de validation se produit dans le concepteur d’opérations de gestion des états électroniques ou le concepteur de mappage de modèle de gestion des états électroniques.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer simultanément le modèle de données de gestion des états électroniques et les composants de mappage du modèle de gestion des états électroniques.
2. Dans l’arborescence du modèle de données, ajoutez un champ nommé **X** et sélectionnez **Entier** comme type de données.

    ![Arborescence du modèle de données avec le champ X et le type de données Entier sur la page Modèle de données](./media/er-components-inspections-01.png)

3. Dans le volet des sources de données du modèle de mappage, ajoutez une source de données de type **Champ calculé**.
4. Nommez la nouvelle source de données **Y** et configurez-la pour qu’elle contienne l’expression `INTVALUE(100)`.
5. Liez **X** à **Y**.
6. Dans le concepteur de mappage de modèles, dans le volet des sources de données, supprimez la source de données **Y**.
7. Sélectionnez **Valider** pour inspecter le composant de mappage de modèle modifiable sur le **Concepteur de modèle de mappage**.

    ![Inspection du composant de mappage de modèle de gestion des états électroniques modifiable sur la page Concepteur de modèle de mappage](./media/er-components-inspections-03.gif)

8. Notez qu’une erreur de validation se produit. Le message indique que la liaison du champ du modèle de données **X** contient le chemin d’accès qui fait référence à la source de données **Y**, mais cette source de données est introuvable.

### <a name="automatic-resolution"></a>Résolution automatique

Sélectionnez **Délier** pour résoudre automatiquement ce problème en supprimant la liaison de source de données manquante.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Déliez le champ de modèle de données **X** pour arrêter de faire référence à la source de données **Y** inexistante.

#### <a name="option-2"></a>Option 2

Dans le volet des sources de données du concepteur de mappage de modèles de gestion des états électroniques, supprimez la source de données **Y** à nouveau.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Capacité d’exécution d’une expression avec la fonction FILTER

La fonction ER [FILTER](er-functions-list-filter.md) intégrée est utilisée pour accéder aux tables et aux vues d’application, ou aux entités de données en effectuant un seul appel SQL pour obtenir les données requises sous forme de liste d’enregistrements. Une source de données de type **Liste des enregistrements** est utilisée comme argument de cette fonction et spécifie la source de l’application pour l’appel. ER vérifie si une requête SQL directe peut être établie vers une source de données référencée dans la fonction `FILTER`. Si une requête directe ne peut pas être établie, une erreur de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez indique que l’expression ER qui inclut la fonction `FILTER` ne peut pas être exécutée au moment de l’exécution. 

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
4. Ajoutez une source de données du type **Champ calculé**.
5. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que l’expression `FILTER(Vendor, Vendor.AccountNum="US-101")` dans la source de données **Vendor** peut être interrogée.
7. Modifiez la source de données **Vendor** en ajoutant un champ imbriqué de type **Champ calculé** pour obtenir le numéro de compte du fournisseur tronqué.
8. Nommez le nouveau champ imbriqué **$AccNumber** et configurez-le pour qu’il contienne l’expression `TRIM(Vendor.AccountNum)`.
9. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que l’expression `FILTER(Vendor, Vendor.AccountNum="US-101")` dans la source de données **Vendor** peut être interrogée.

    ![La vérification de l’expression peut être interrogée sur la page Concepteur de modèle de mappage](./media/er-components-inspections-04.gif)

10. Notez qu’une erreur de validation se produit, car la source de données **Vendor** contient un champ imbriqué du type **Champ calculé** qui n’autorise pas l’expression de la source de données **FilteredVendor** à convertir dans l’instruction SQL directe.

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter un format configuré pour utiliser le modèle de mappage.

![Erreurs d’exécution qui se produisent lorsque vous exécutez le format modifiable sur la page Concepteur de format](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Au lieu d’ajouter un champ imbriqué du type **Champ calculé** à la source de données **Vendor**, ajoutez le champ imbriqué **$AccNumber** à la source de données **FilteredVendor** et configurez-le pour qu’il contienne l’expression `TRIM(FilteredVendor.AccountNum)`. De cette façon, l’expression `FILTER(Vendor, Vendor.AccountNum="US-101")` peut être exécutée au niveau de SQL et calculer le champ imbriqué **$AccNumber** par la suite.

#### <a name="option-2"></a>Option 2

Changez l’expression de la source de données **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum="US-101")` en `WHERE(Vendor, Vendor.AccountNum="US-101")`. Nous vous déconseillons de modifier l’expression d’une table contenant un grand volume de données (table transactionnelle), car tous les enregistrements seront récupérés et la sélection des enregistrements requis sera effectuée en mémoire. Par conséquent, cette approche peut entraîner de mauvaises performances. Pour plus d’informations, consultez [Fonction ER WHERE](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Capacité d’exécution d’une source de données GROUPBY

La source de données **GROUPBY** divise le résultat de la requête en groupes d’enregistrements, généralement dans le but d’effectuer une ou plusieurs agrégations sur chaque groupe. Chaque source de données **GROUPBY** peut être configurée pour être exécutée au niveau de la base de données ou en mémoire. Lorsqu’une source de données **GROUPBY** est configurée de manière à être exécutée au niveau de la base de données, ER vérifie si une requête SQL directe peut être établie vers une source de données référencée dans cette source de données. Si une requête directe ne peut pas être établie, une erreur de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez indique que la source de données **GROUPBY** ne peut pas être exécutée au moment du runtime.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Trans**. Dans le champ **Table**, sélectionnez **VendTrans** pour spécifier que cette source de données demandera la table VendTrans.
4. Ajoutez une source de données du type **Grouper par**.
5. Nommez la nouvelle source de données **GroupedTrans**, et configurez-la de la manière suivante :

    - Sélectionnez la source de données **Trans** comme source des enregistrements à regrouper.
    - Dans le champ **Lieu d’exécution**, sélectionnez **Requête** pour indiquer que vous souhaitez exécuter cette source de données au niveau de la base de données.

    ![Configuration de la source de données sur la page de paramètres "Grouper par"](./media/er-components-inspections-05a.gif)

6. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que la source de données **GroupedTrans** configurée peut être interrogée.
7. Modifiez la source de données **Trans** en ajoutant un champ imbriqué de type **Champ calculé** pour obtenir le numéro de compte du fournisseur tronqué.
8. Nommez la nouvelle source de données **$AccNumber** et configurez-la pour qu’elle contienne l’expression `TRIM(Trans.AccountNum)`.

    ![Configuration de la source de données Trans sur le concepteur de modèle de mappage](./media/er-components-inspections-05a.png)

9. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que la source de données **GroupedTrans** configurée peut être interrogée.

    ![Valider le composant de modèle de mappage de gestion des états électroniques et vérifiez que la source de données configurée, GroupedTrans, peut être interrogée sur la page du concepteur de modèles de mappage](./media/er-components-inspections-05b.png)

10. Notez qu’une erreur de validation se produit, car la source de données **Trans** contient un champ imbriqué du type **Champ calculé** qui n’autorise pas l’appel de la source de données **GroupedTrans** à convertir dans l’instruction SQL directe.

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter un format configuré pour utiliser le modèle de mappage.

![Erreurs de runtime qui se produisent lorsque l’avertissement est ignoré sur la page Concepteur de format](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Au lieu d’ajouter un champ imbriqué du type **Champ calculé** à la source de données **Trans**, ajoutez le champ imbriqué **$AccNumber** de l’élément **GroupedTrans.lines** de la source de données **GroupedTrans** et configurez-le pour qu’il contienne l’expression `TRIM(GroupedTrans.lines.AccountNum)`. De cette façon, la source de données **GroupedTrans** peut être exécutée au niveau de SQL et calculer le champ imbriqué **$AccNumber** par la suite.

#### <a name="option-2"></a>Option 2

Changer la valeur du champ **Emplacement d’exécution** pour la source de données **GroupedTrans** de **Requête** à **En mémoire**. Nous vous déconseillons de modifier la valeur d’une table contenant un grand volume de données (table transactionnelle), car tous les enregistrements seront récupérés et le groupement et l’agrégation seront effectués en mémoire. Par conséquent, cette approche peut entraîner de mauvaises performances.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Capacité d’exécution d’une source de données JOIN

La source de données [JOINDRE](er-join-data-sources.md) combine les enregistrements de deux ou plusieurs tables de base de données, en fonction des champs associés. Chaque source de données **JOIN** peut être configurée pour être exécutée au niveau de la base de données ou en mémoire. Lorsqu’une source de données **JOIN** est configurée de manière à être exécutée au niveau de la base de données, ER vérifie si une requête SQL directe peut être établie vers des sources de données référencées dans cette source de données. Si une requête SQL directe ne peut pas être établie avec au moins une source de données référencée, une erreur de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez indique que la source de données **JOIN** ne peut pas être exécutée au moment du runtime.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
4. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
5. Nommez la nouvelle source de données **Trans**. Dans le champ **Table**, sélectionnez **VendTrans** pour spécifier que cette source de données demandera la table VendTrans.
6. Ajoutez une source de données du type **Champ calculé** comme champ imbriqué de la source de données **Vendor**.
7. Nommez la nouvelle source de données **FilteredTrans** (conversion filtrée) et configurez-la pour qu’elle contienne l’expression `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Ajoutez une source de données du type **Joindre**.
9. Nommez la nouvelle source de données **JoinedList**, et configurez-la de la manière suivante :

    1. Ajouter la source de données **Vendor** comme premier ensemble d’enregistrements à joindre.
    2. Ajouter la source de données **Vendor.FilteredTrans** comme second ensemble d’enregistrements à joindre. Sélectionnez **INNER** comme type.
    3. Dans le champ **Exécuter**, sélectionnez **Requête** pour indiquer que vous souhaitez exécuter cette source de données au niveau de la base de données.

    ![Configuration de la source de données sur le concepteur de jonction](./media/er-components-inspections-06a.gif)

10. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que la source de données **JoinedList** configurée peut être interrogée.
11. Changez l’expression de la source de données **Vendor.FilteredTrans** de `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` en `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Sélectionnez **Valider** pour inspecter le composant de modèle de mappage modifiable sur la page **Concepteur de modèle de mappage** et vérifiez que la source de données **JoinedList** configurée peut être interrogée.

    ![Validez le composant de modèle de mappage modifiable et vérifiez que la source de données JoinedList configurée peut être interrogée sur la page du Concepteur de modèle de mappage](./media/er-components-inspections-06b.png)

13. Notez qu’une erreur de validation se produit, car l’expression de la source de données **Vendor.FilteredTrans** ne peut pas être convertie en appel SQL direct. De plus, l’appel SQL direct n’autorise pas l’appel de la source de données **JoinedList** à convertir en instruction SQL directe.

    ![Erreurs d’exécution suite à l’échec de la validation de la source de données JoinedList sur la page Concepteur de modèle de mappage](./media/er-components-inspections-06c.png)

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter un format configuré pour utiliser le modèle de mappage.

![Exécution du format modifiable sur la page Concepteur de format](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Changez de nouveau l’expression de la source de données **Vendor.FilteredTrans** de `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` en `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, comme le conseille l’avertissement.

![Expression mise à jour de la source de données sur le concepteur de modèle de mappage](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Option 2

Changez la valeur du champ **Exécuter** pour la source de données **JoinedList** de **Requête** à **En mémoire**. Nous vous déconseillons de modifier la valeur d’une table contenant un grand volume de données (table transactionnelle), car tous les enregistrements seront récupérés et la jonction sera effectuée en mémoire. Par conséquent, cette approche peut entraîner de mauvaises performances. Un avertissement de validation s’affiche pour vous informer de ce risque.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Préférence de la fonction FILTER comparée à WHERE

La fonction ER [FILTER](er-functions-list-filter.md) intégrée est utilisée pour accéder aux tables et aux vues d’application, ou aux entités de données en effectuant un seul appel SQL pour obtenir les données requises sous forme de liste d’enregistrements. La fonction [WHERE](er-functions-list-where.md) récupère tous les enregistrements de la source donnée et enregistre la sélection en mémoire. Une source de données de type **Liste des enregistrements** est utilisée comme argument des deux fonctions et spécifie une source pour obtenir des enregistrements. ER vérifie si un appel SQL direct peut être établie vers une source de données référencée dans la fonction **WHERE**. Si un appel direct ne peut pas être établie, un avertissement de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez vous recommande d’utiliser la fonction **FILTER** au lieu de la fonction **WHERE** pour aider à améliorer l’efficacité.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Trans**. Dans le champ **Table**, sélectionnez **VendTrans** pour spécifier que cette source de données demandera la table VendTrans.
4. Ajoutez une source de données du type **Champ calculé** comme champ imbriqué de la source de données **Vendor**.
5. Nommez la nouvelle source de données **FilteredTrans** (conversion filtrée) et configurez-la pour qu’elle contienne l’expression `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
7. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
8. Ajoutez une source de données du type **Champ calculé**.
9. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Sélectionnez **Valider** pour inspecter le composant de mappage de modèle modifiable sur le **Concepteur de modèle de mappage**.

    ![Validez pour inspecter le composant de mappage de modèle modifiable sur le Concepteur de modèle de mappage](./media/er-components-inspections-07a.png)

11. Notez que les avertissements de validation vous recommandent d’utiliser la fonction **FILTER** au lieu de la fonction **WHERE** pour les sources de données **FilteredVendor** et **FilteredTrans**.

    ![Avertissements de validation recommandant la fonction filter au lieu de la fonction where sur la page du concepteur de mappage de modèle](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Résolution automatique

Sélectionnez **Corriger** pour remplacer automatiquement la fonction **WHERE** par la fonction **FILTER** dans l’expression de toutes les sources de données qui apparaissent dans la grille de l’onglet **Avertissements** pour ce type d’inspection.

Sinon, vous pouvez sélectionner la ligne pour un seul avertissement dans la grille, puis sélectionner **Corriger la sélection**. Dans ce cas, l’expression est automatiquement modifiée uniquement dans la source de données mentionnée dans l’avertissement sélectionné.

![Sélectionnez Corriger pour remplacer automatiquement la fonction where par la fonction filter sur la page du Concepteur de modèle de mappage](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Résolution manuelle

Vous pouvez ajuster manuellement les expressions de toutes les sources de données mentionnées dans la grille de validation en remplaçant la fonction **WHERE** par la fonction **FILTER**.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Préférence de la fonction ALLITEMSQUERY comparée à ALLITEMS

Les fonctions d’ER [ALLITEMS](er-functions-list-allitems.md) et [ALLITEMSQUERY](er-functions-list-allitemsquery.md) intégrées sont utilisées pour obtenir une valeur **Liste des enregistrements** aplatie qui consiste en une liste d’enregistrements représentant tous les éléments qui correspondent au chemin d’accès spécifié. ER vérifie si un appel SQL direct peut être établie vers une source de données référencée dans la fonction **ALLITEMS**. Si un appel direct ne peut pas être établie, un avertissement de validation se produit dans le concepteur de modèle de mappage de gestion des états électroniques. Le message que vous recevez vous recommande d’utiliser la fonction **ALLITEMSQUERY** au lieu de la fonction **ALLITEMS** pour aider à améliorer l’efficacité.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
4. Ajoutez une source de données paramétrée du type **Champ calculé** pour obtenir les enregistrements de plusieurs fournisseurs.
5. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Ajoutez une source de données paramétrée du type **Champ calculé** pour obtenir les transactions de tous les fournisseurs filtrés.
7. Nommez la nouvelle source de données **FilteredVendorTrans** (conversion du fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Sélectionnez **Valider** pour inspecter le composant de mappage de modèle modifiable sur le **Concepteur de modèle de mappage**.

    ![Page du concepteur de modèle de mappage, bouton Valider](./media/er-components-inspections-08a.png)

9. Notez qu’un avertissement de validation se produit. Le message vous recommande d’utiliser la fonction **ALLITEMSQUERY** au lieu de la fonction **ALLITEMS** pour la source de données **FilteredVendorTrans**.

    ![Avertissement de validation pour utiliser la fonction ALLITEMSQUERY au lieu de la fonction ALLITEMS sur le composant de modèle ER sur la page Concepteur de modèle de mappage](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Résolution automatique

Sélectionnez **Corriger** pour remplacer automatiquement la fonction **ALLITEMS** par la fonction **ALLITEMSQUERY** dans l’expression de toutes les sources de données qui apparaissent dans la grille de l’onglet **Avertissements** pour ce type d’inspection.

Sinon, vous pouvez sélectionner la ligne pour un seul avertissement dans la grille, puis sélectionner **Corriger la sélection**. Dans ce cas, l’expression est automatiquement modifiée uniquement dans la source de données mentionnée dans l’avertissement sélectionné.

![Page du concepteur de modèle de mappage, sélectionnez Corriger la sélection](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Résolution manuelle

Vous pouvez ajuster manuellement les expressions de toutes les sources de données mentionnées dans la grille de validation en remplaçant la fonction **ALLITEMS** par la fonction **ALLITEMSQUERY**.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Prise en compte des cas de liste vide

Vous pouvez configurer votre format de gestion des états électroniques ou votre composant de modèle de mappage pour obtenir la valeur de champ d’une source de données de type **Liste des enregistrements**. ER vérifie si votre conception prend en compte le cas où une source de données appelée ne contient aucun enregistrement (c’est-à-dire qu’elle est vide), pour éviter les erreurs de runtime lorsqu’une valeur est extraite d’un champ d’un enregistrement inexistant.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer simultanément le modèle de données de gestion des états électroniques, le modèle de mappage de gestion des états électroniques et les composants de format de gestion des états électroniques.
2. Dans l’arborescence du modèle de données, ajoutez un élément racine nommé **Root3**.
3. Modifiez l’élément **Root3** en ajoutant un élément imbriqué de type **Liste des enregistrements**.
4. Nommez le nouvel élément imbriqué **Vendor**.
5. Modifier l’élément **Vendor** de la manière suivante :

    - Ajoutez un champ imbriqué du type **Chaîne** et nommez-le **Nom**.
    - Ajoutez un champ imbriqué du type **Chaîne** et nommez-le **AccountNumber**.

    ![Ajout de champs imbriqués sur la page Modèle de données](./media/er-components-inspections-09a.png)

6. Dans le volet des sources de données du modèle de mappage, ajoutez une source de données de type **Dynamics 365 for Operations \\ Enregistrements de table**.
7. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
8. Ajoutez une source de données du type **Général \\ Paramètre d’entrée utilisateur** pour rechercher un compte fournisseur dans la boîte de dialogue de runtime.
9. Nommez la nouvelle source de données **RequestedAccountNum**. Dans le champ **Étiquette**, entrez le **numéro de compte fournisseur**. Dans le champ **Nom du type de données des opérations**, laissez la valeur par défaut, **Description**.
10. Ajoutez une source de données paramétrée du type **Champ calculé** pour le fournisseur filtré qui fait l’objet de l’interrogation.
11. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Liez les éléments de modèle de données aux sources de données configurées de la manière suivante :

    - Liez **FilteredVendor** à **Vendor**.
    - Lierz **FilteredVendor.AccountNum** à **Vendor.AccountNumber**.
    - Liez **FilteredVendor.’name()’** à **Vendor.Name**.

    ![Liaison des éléments de source de données sur le concepteur de modèle de mappage](./media/er-components-inspections-09b.png)

13. Dans l’arborescence de la structure du format, ajoutez les éléments suivants pour générer un document sortant au format XML contenant les détails du fournisseur :

    1. Ajoutez l’élément XML racine **Instruction**.
    2. Pour l’élément XML **Instruction**, ajoutez l’élément XML **Tiers**.
    3. Pour l’élément XML **Tiers**, ajoutez les attributs XML imbriqués suivants :

        - Nom
        - AccountNum

14. Liez les éléments de format aux sources de données fournies de la manière suivante :

    - Liez l’élément de format **Instruction\\Tiers\\Nom** au champ de source de données **model.Vendor.Name**.
    - Liez l’élément de format **Instruction\\Tiers\\AccountNum** au champ de source de données **model.Vendor.AccountNumber**.

15. Sélectionnez **Valider** pour inspecter le composant de format modifiable sur la page **Concepteur de format**.

    ![Validez les éléments de format que vous avez liés aux sources de données sur la page Concepteur de format](./media/er-components-inspections-09c.png)

16. Notez qu’une erreur de validation se produit. Le message indique qu’une erreur peut être générée pour les composants de format **Instruction\\Tiers\\Nom** et **Instruction\\Tiers\\AccountNum** lors du runtime si la liste `model.Vendor` est vide.

    ![Erreur de validation qui notifie une erreur potentielle pour les composants de format configuré](./media/er-components-inspections-09d.png)

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter le format et sélectionnez le numéro de compte d’un fournisseur non existant. Comme le fournisseur demandé n’existe pas, la liste `model.Vendor` sera vide (c’est-à-dire qu’elle ne contiendra aucun enregistrement).

![Erreurs de runtime, car cela s’est produit lors de l’exécution du mappage de format](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Résolution automatique

Pour la ligne sélectionnée dans la grille sur l’onglet **Avertissements**, vous pouvez sélectionner **Délier**. La liaison pointée vers la colonne **Chemin d’accès** est automatiquement supprimée des éléments de format.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Vous pouvez lier l’élément de format **Instruction\\Tiers\\Nom** à l’élément de source de données `model.Vendor`. Au moment du runtime, cette liaison appelle la source de données `model.Vendor` en premier. Quand `model.Vendor` renvoie une liste d’enregistrements vide, les éléments de format imbriqués ne sont pas exécutés. Par conséquent, aucun avertissement de validation ne se produit pour cette configuration de format.

![Liez l’élément de format à l’élément de source de données sur la page Concepteur de format](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Option 2

Changez la liaison de l’élément de format **Instruction\\Tiers\\Nom** entre `model.Vendor.Name` et `FIRSTORNULL(model.Vendor).Name`. La liaison mise à jour convertit de manière conditionnelle le premier enregistrement de la source de données `model.Vendor` de type **Liste des enregistrements** en une nouvelle source de données de type **Enregistrement**. Cette nouvelle source de données contient le même ensemble de champs.

- Si au moins un enregistrement est disponible dans la source de données `model.Vendor`, les champs de cet enregistrement sont remplis avec les valeurs des champs du premier enregistrement de la source de données `model.Vendor`. Dans ce cas, la liaison mise à jour renvoie le nom du fournisseur.
- Sinon, chaque champ de l’enregistrement créé est rempli avec la valeur par défaut du type de données de ce champ. Dans ce cas, la chaîne vide est renvoyée comme valeur par défaut du type de données **Chaîne**.

Par conséquent, aucun avertissement de validation n’apparaît pour l’élément de format **Instruction\\Tiers\\Nom** lorsqu’il est lié à l’expression `FIRSTORNULL(model.Vendor).Name`.

![La liaison modifiée résout les avertissements de validation sur la page Concepteur de format](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Option 3

Si vous souhaitez spécifier explicitement les données entrées dans un document généré lorsque la source de données `model.Vendor` de type **Liste des enregistrements** ne renvoie aucun enregistrement (le texte **Indisponible** dans cet exemple), modifiez la liaison de l’élément de format **Instruction\\Tiers\\Nom** entre `model.Vendor.Name` et `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. Vous pouvez également utiliser l’expression `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Considération supplémentaire

L’inspection vous avertit également d’un autre problème potentiel. Par défaut, lorsque vous liez les éléments de format **Instruction\\Tiers\\Nom** et **Instruction\\Tiers\\AccountNum** aux champs appropriés de la source de données`model.Vendor` de type **Liste des enregistrements**, ces liaisons seront exécutées et prendront les valeurs des champs appropriés du premier enregistrement de la source de données `model.Vendor`, si cette liste n’est pas vide.

Comme vous n’avez pas lié l’élément de format **Instruction\\Tiers** avec la source de données `model.Vendor`, l’élément **Instruction\\Tiers** ne sera pas répété pour chaque enregistrement de la source de données `model.Vendor` pendant l’exécution du format. Au lieu de cela, un document généré sera rempli avec des informations provenant uniquement du premier enregistrement de la liste d’enregistrements, si cette liste contient plusieurs enregistrements. Par conséquent, il peut y avoir un problème si le format est destiné à remplir un document généré avec des informations sur tous les fournisseurs de la source de données `model.Vendor`. Pour résoudre ce problème, liez l’élément **Instruction\\Tiers** à la source de données `model.Vendor`.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Capacité d’exécution d’une expression avec la fonction FILTER (mise en cache)

Plusieurs fonctions ER intégrées, notamment [FILTER](er-functions-list-filter.md) et [ALLITEMSQUERY](er-functions-list-allitemsquery.md), sont utilisées pour accéder aux tables et aux vues d’application, ou aux entités de données en effectuant un seul appel SQL pour obtenir les données requises sous forme de liste d’enregistrements. Une source de données de type **Liste des enregistrements** est utilisée comme argument de chacune de ces fonctions et spécifie la source de l’application pour l’appel. ER vérifie si un appel SQL direct peut être établie vers une source de données référencée dans l’une de ces fonctions. Si un appel direct ne peut pas être établi, car la source de données a été marquée comme [mise en cache](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace), une erreur de validation se produit dans le concepteur de modèle de mappage ER. Le message que vous recevez indique que l’expression ER qui inclut l’une de ces fonctions ne peut pas être exécutée au moment du runtime.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de modèle de mappage de gestion des états électroniques.
2. Ajoutez une source de données du type **Dynamics 365 for Operations \\ Enregistrements de la table**.
3. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
4. Ajoutez une source de données du type **Général \\ Paramètre d’entrée utilisateur** pour rechercher un compte fournisseur dans la boîte de dialogue de runtime.
5. Nommez la nouvelle source de données **RequestedAccountNum**. Dans le champ **Étiquette**, entrez le **numéro de compte fournisseur**. Dans le champ **Nom du type de données des opérations**, laissez la valeur par défaut, **Description**.
6. Ajoutez une source de données paramétrée du type **Champ calculé** pour le fournisseur filtré qui fait l’objet de l’interrogation.
7. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Marquez la source de données **Vendor** configurée comme mise en cache.

    ![Configurez le composant de mappage de modèle sur le Concepteur de modèle de mappage](./media/er-components-inspections-10a.gif)

9. Sélectionnez **Valider** pour inspecter le composant de mappage de modèle modifiable sur le **Concepteur de modèle de mappage**.

    ![Validez la fonction de filtre appliquée à la source de données du fournisseur de cache sur la page Concepteur de modèle de mappage](./media/er-components-inspections-10a.png)

10. Notez qu’une erreur de validation se produit. Le message indique que la fonction **FILTER** ne peut pas être appliquée à la source de données **Vendor** mise en cache.

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter le format.

![Erreur d’exécution qui se produit lors de l’exécution du mappage de format sur la page Concepteur de format](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Supprimez l’indicateur **Cache** de la source de données **Fournisseur**. La source de données **FilteredVendor** deviendra alors exécutable, mais la source de données **Fournisseur** référencée dans la table VendTable sera accédée chaque fois que la source de données **FilteredVendor** est appelée.

#### <a name="option-2"></a>Option 2

Changez l’expression de la source de données **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum="US-101")` en `WHERE(Vendor, Vendor.AccountNum="US-101")`. Dans ce cas, la source de données **Fournisseur** mentionnée dans la table VendTable ne sera accessible que lors du premier appel de la source de données **Fournisseur**. Cependant, la sélection des enregistrements se fera en mémoire. Par conséquent, cette approche peut entraîner de mauvaises performances.

## <a name="missing-binding"></a><a id="i11"></a>Liaison manquante

Lorsque vous configurez un composant de format ER, le modèle de données ER de base est proposé comme source de données par défaut pour le format ER. Lorsque le format ER configuré est exécuté, le [mappage de modèle par défaut](er-country-dependent-model-mapping.md) pour le modèle de base est utilisé pour remplir le modèle de données avec des données d’application. Le concepteur de format ER affiche un avertissement si vous liez un élément de format à un élément de modèle de données qui n’est lié à aucune source de données dans le mappage de modèle actuellement sélectionné comme mappage de modèle par défaut pour le format modifiable. Ce type de liaison ne peut pas être exécuté au moment de l’exécution, car le format qui s’exécute ne peut pas remplir un élément lié avec des données d’application. Par conséquent, une erreur se produit lors du runtime.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer simultanément le modèle de données de gestion des états électroniques, le modèle de mappage de gestion des états électroniques et les composants de format de gestion des états électroniques.
2. Dans l’arborescence du modèle de données, ajoutez un élément racine nommé **Root3**.
3. Modifiez l’élément **Root3** en ajoutant un nouvel élément imbriqué de type **Liste des enregistrements**.
4. Nommez le nouvel élément imbriqué **Vendor**.
5. Modifier l’élément **Vendor** de la manière suivante :

    - Ajoutez un champ imbriqué du type **Chaîne** et nommez-le **Nom**.
    - Ajoutez un champ imbriqué du type **Chaîne** et nommez-le **AccountNumber**.

    ![Ajouter des champs imbriqués à l’article fournisseur sur la page Modèle de données](./media/er-components-inspections-11a.png)

6. Dans le volet des sources de données du modèle de mappage, ajoutez une source de données de type **Dynamics 365 for Operations \\ Enregistrements de table**.
7. Nommez la nouvelle source de données **Vendor** (fournisseur). Dans le champ **Table**, sélectionnez **VendTable** (table fournisseur) pour spécifier que cette source de données demandera la table VendTable.
8. Ajoutez une source de données du type **Général \\ Paramètre d’entrée utilisateur** pour interroger sur un compte fournisseur dans la boîte de dialogue de runtime.
9 Nommez la nouvelle source de données **RequestedAccountNum**. Dans le champ **Étiquette**, entrez le **numéro de compte fournisseur**. Dans le champ **Nom du type de données des opérations**, laissez la valeur par défaut, **Description**.
10. Ajoutez une source de données paramétrée du type **Champ calculé** pour le fournisseur filtré qui fait l’objet de l’interrogation.
11. Nommez la nouvelle source de données **FilteredVendor** (fournisseur filtré) et configurez-la pour qu’elle contienne l’expression `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Liez les éléments de modèle de données aux sources de données configurées de la manière suivante :

    - Liez **FilteredVendor** à **Vendor**.
    - Lierz **FilteredVendor.AccountNum** à **Vendor.AccountNumber**.

    > [!NOTE]
    > Le champ du modèle de données **Vendor.Name** reste non lié.

    ![Éléments de modèle de données liés à des sources de données configurées et à un élément de mode de données qui rem sur la page Concepteur de mappage de modèle](./media/er-components-inspections-11b.png)

13. Dans l’arborescence de la structure du format, ajoutez les éléments suivants pour générer un document sortant au format XML contenant les détails du fournisseur interrogés :

    1. Ajoutez l’élément XML racine **Instruction**.
    2. Pour l’élément XML **Instruction**, ajoutez l’élément XML **Tiers**.
    3. Pour l’élément XML **Tiers**, ajoutez les attributs XML imbriqués suivants :

        - Nom
        - AccountNum

14. Liez les éléments de format aux sources de données fournies de la manière suivante :

    - Liez l’élément de format **Instruction\\Tiers** à l’élément de source de données `model.Vendor`.
    - Liez l’élément de format **Instruction\\Tiers\\Nom** au champ de source de données **model.Vendor.Name**.
    - Liez l’élément de format **Instruction\\Tiers\\AccountNum** au champ de source de données **model.Vendor.AccountNumber**.

15. Sélectionnez **Valider** pour inspecter le composant de format modifiable sur la page **Concepteur de format**.

    ![Validation du composant de format ER sur la page Concepteur de format](./media/er-components-inspections-11c.png)

16. Notez qu’un avertissement de validation se produit. Le message indique que le champ de source de données **model.Vendor.Name** n’est lié à aucune source de données dans le mappage de modèle configuré pour être utilisé par le format. Par conséquent, l’élément de format **Déclaration\\Tiers\\Nom** peut ne pas être rempli lors du runtime et une exception de runtime peut se produire.

    ![Validation du composant de format ER sur la page Concepteur de format](./media/er-components-inspections-11d.png)

L’illustration suivante montre l’erreur de runtime qui se produit si vous ignorez l’avertissement et sélectionnez **Exécuter** pour exécuter le format.

![Exécution du format modifiable sur la page Concepteur de format](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Modifiez le mappage de modèle configuré en ajoutant une liaison pour le champ de source de données **model.Vendor.Name**.

#### <a name="option-2"></a>Option 2

Modifiez le format configuré en supprimant une liaison pour l’élément de format **Déclaration\\Tiers\\Nom**.

## <a name="not-linked-template"></a><a id="i12"></a>Modèle non lié

Lorsque vous configurez [manuellement](er-fillable-excel.md#manual-entry) un composant de format ER pour utiliser un modèle pour générer un document sortant, vous devez ajouter manuellement l’élément **Excel\\Fichier**, ajouter le modèle requis en tant que pièce jointe du composant modifiable et sélectionner cette pièce jointe dans l’élément **Excel\\ Fichier** ajouté. De cette manière, vous indiquez que l’élément ajouté remplira le modèle sélectionné au runtime. Lorsque vous configurez une version de composant de format dans le [statut](general-electronic-reporting.md#component-versioning) **Brouillon**, vous pouvez ajouter plusieurs modèles au composant modifiable, puis sélectionner chaque modèle dans l’élément **Excel\\Fichier** pour exécuter le format ER. De cette façon, vous pouvez voir comment les différents modèles sont remplis au moment du runtime. Si vous avez des modèles qui ne sont sélectionnés dans aucun élément **Excel\\Fichier**, le concepteur de format ER vous avertit que ces modèles seront supprimés de la version modifiable du composant de format ER lorsque son statut passe de **Brouillon** à **Terminé**.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de format ER.
2. Dans l’arborescence de la structure des formats, ajoutez l’élément **Excel\\Fichier**.
3. Pour l’élément **Excel\\Fichier** que vous venez d’ajouter, ajoutez un fichier de classeur Excel, **A.xlsx**, en pièce jointe. Utilisez le type de document configuré dans les [paramètres ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) pour spécifier le stockage des modèles au format ER.
4. Pour l’élément **Excel\\Fichier** que vous venez d’ajouter, ajoutez un autre fichier de classeur Excel, **B.xlsx**, en pièce jointe. Utilisez le même type de document que celui utilisé pour le fichier de classeur A.
5. Dans l’élément **Excel\\Fichier**, sélectionnez le fichier de classeur A.
6. Sélectionnez **Valider** pour inspecter le composant de format modifiable sur la page **Concepteur de format**.

    ![Validation du composant de format modifiable du fichier de classeur sur la page Concepteur de format](./media/er-components-inspections-12a.gif)

7. Notez qu’un avertissement de validation se produit. Le message indique que le fichier de classeur **B.xlsx** n’est lié à aucun composant, et qu’il sera supprimé une fois le statut de la version de configuration modifié.

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

Modifiez le format configuré en supprimant tous les modèles qui ne sont liés à aucun élément **Excel\\Fichier**.

## <a name="not-synced-format"></a><a id="i13"></a>Format non synchronisé

Lorsque vous [configurez](er-fillable-excel.md) un composant de format ER pour utiliser un modèle Excel pour générer un document sortant, vous devez ajouter manuellement l’élément **Excel\\Fichier**, ajouter le modèle requis en tant que pièce jointe du composant modifiable et sélectionner cette pièce jointe dans l’élément **Excel\\Fichier** ajouté. De cette manière, vous indiquez que l’élément ajouté remplira le modèle sélectionné au runtime. Étant donné que le modèle Excel ajouté a été conçu en externe, le format ER modifiable peut contenir des noms Excel qui manquent dans le modèle ajouté. Le concepteur de format ER vous avertit de toute incohérence entre les propriétés des éléments de format ER qui font référence à des noms qui ne sont pas inclus dans le modèle Excel ajouté.

Les étapes suivantes montrent comment ce problème peut se produire.

1. Commencez à configurer le composant de format ER.
2. Dans l’arborescence de la structure des formats, ajoutez l’élément **Excel\\Ficher** **Rapport**.
3. Pour l’élément **Excel\\Fichier** que vous venez d’ajouter, ajoutez un fichier de classeur Excel, **A.xlsx**, en pièce jointe. Utilisez le type de document configuré dans les [paramètres ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) pour spécifier le stockage des modèles au format ER.

    > [!IMPORTANT]
    > Assurez-vous que le classeur Excel ajouté ne contient pas le nom **ReportTitle**.

4. Ajoutez l’élément **Excel\\Cellule** **Titre** en tant qu’élément imbriqué de l’élément **Rapport**. Dans le champ **Plage Excel**, entrez **ReportTitle**.
5. Sélectionnez **Valider** pour inspecter le composant de format modifiable sur la page **Concepteur de format**.

    ![Validez les éléments et champs imbriqués sur la page Concepteur de format](./media/er-components-inspections-13a.png)

6. Notez qu’un avertissement de validation se produit. Le message indique que le nom **ReportTitle** n’existe pas sur la feuille **Feuille1** du modèle Excel que vous utilisez.

    ![Avertissement de validation que le nom ReportTitle n’existe pas sur la feuille Sheet1 du modèle Excel](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Résolution automatique

Aucune option pour résoudre automatiquement ce problème n’est disponible.

### <a name="manual-resolution"></a>Résolution manuelle

#### <a name="option-1"></a>Option 1

Modifiez le format configuré en supprimant tous les éléments qui font référence à des noms Excel manquants dans le modèle.

#### <a name="option-2"></a>Option 2

[Mettez à jour](er-fillable-excel.md#template-import) le format ER modifiable en important un modèle Excel. La structure du format ER modifiable sera [synchronisé](modify-electronic-reporting-format-reapply-excel-template.md) avec la structure du modèle Excel importé.

### <a name="additional-consideration"></a>Considération supplémentaire

Pour savoir comment la structure de format peut être synchronisée avec un modèle ER dans l’éditeur de modèle de [Gestion des documents commerciaux](er-business-document-management.md), voir [Mettre à jour la structure d’un modèle de document commercial](er-bdm-update-structure.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonction ALLITEMS ER](er-functions-list-allitems.md)

[Fonction ALLITEMSQUERY ER](er-functions-list-allitemsquery.md)

[Fonction INT64VALUE ER](er-functions-conversion-int64value.md)

[Fonction INTVALUE ER](er-functions-conversion-intvalue.md)

[Fonction FILTER ER](er-functions-list-filter.md)

[Fonction WHERE ER](er-functions-list-where.md)

[Utilisation des sources de données JOIN pour obtenir des données de plusieurs tables d’application dans les mappages de modèles ER](er-join-data-sources.md)

[Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)

[Vue d’ensemble de la gestion de document commercial](er-business-document-management.md)
