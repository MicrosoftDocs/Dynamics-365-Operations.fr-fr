---
title: "FAQ associé aux produits de traductions"
description: "Cette rubrique explique comment gérer les traductions de produits, les valeurs de dimension des produits, et les attributs des produits."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a9c991a5afaebd10b8812dfc1d67120ed4ebdfd2
ms.lasthandoff: 03/31/2017


---

# <a name="product-related-translations-faq"></a>FAQ associé aux produits de traductions

Cette rubrique explique comment gérer les traductions de produits, les valeurs de dimension des produits, et les attributs des produits. 

<a name="what-product-related-data-can-be-translated"></a>Quelles sont les informations associées aux produits qui peuvent être traduites ?
--------------------------------------------

Vous pouvez créer des traductions pour les informations associées aux produits suivantes :
-   Noms et descriptions des produits.
-   Descriptions, noms conviviaux, et texte d'aide des valeurs d'attribut des produits.
-   Noms et descriptions des valeurs de dimension des produits.

Vous pouvez traduire les informations associées aux produits dans n'importe quelle langue disponible à partir de la page **Traduction de texte**. Pour plus d'informations, voir la section suivante : **Comment créer des traductions pour les informations associées aux produits**.

## <a name="where-can-i-view-the-translated-information"></a>Où puis-je consulter les informations traduites ?
Vous pouvez afficher les traductions des informations relatives aux produits dans n'importe quel document source externe, tel qu'une facture, qui utilise une langue pour laquelle des traductions sont disponibles.

## <a name="how-do-i-create-translations-for-productrelated-information"></a>Comment créer des traductions pour les informations liées aux produits ?
Pour créer des traductions pour un produit, procédez comme suit :
1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** Courant ** &gt; ** produits lancés **.
2.  Sélectionnez un produit, puis dans le volet Actions, ** des langues ** au groupe, cliquez sur ** traductions **.
3.  Sur la page **Traduction de texte**, dans le champ **Langue**, sélectionnez une langue. Pour ajouter des langues, développez ** langue ** le champ, puis cliquez sur ** effectué correctement **.
4.  Dans le groupe **Texte traduit**, entrez des traductions dans les champs **Description** et **Nom du produit**.

Pour créer des traductions pour les attributs de produit, procédez comme suit :
1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** Courant ** &gt; ** produits lancés **.
2.  Sous **Paramétrage**, cliquez sur **Attributs**, puis sur **Attributs**.
3.  Sur la page **Attributs**, cliquez sur **Traduire**.
4.  Sur la page **Traduction de texte**, dans le champ **Langue**, sélectionnez une langue. Pour ajouter des langues, développez ** langue ** le champ, puis cliquez sur ** effectué correctement **.
5.  Dans le groupe **Texte traduit**, entrez des traductions dans les champs **Description**, **Nom convivial** et **Texte d'aide**.

Pour créer des traductions pour les valeurs de dimension de produit, procédez comme suit :
1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** Courant ** &gt; ** produits lancés **.
2.  Sélectionnez un produit, puis cliquez sur **Dimensions de produit**.
3.  Sélectionnez l'un des liens des dimensions de produit : **Configurations**, **Tailles**, **Couleurs** ou **Style**.
4.  Sélectionnez une valeur de dimension, puis cliquez sur **Traduire**.
5.  Sur la page **Traduction de texte**, dans le champ **Langue**, sélectionnez une langue. Pour ajouter des langues, développez ** langue ** le champ, puis cliquez sur ** effectué correctement **.
6.  ** Texte traduit ** dans le groupe, entrez les traductions dans ** nom ** et ** description ** des champs.

## <a name="can-the-names-of-product-variants-be-translated"></a>Les noms des variantes de produit peuvent-elles être traduites ?
Les variantes de produit sont basées sur les dimensions d'un produit lancé. Les noms de variantes de produit sont basées sur une combinaison des valeurs de dimension. Lorsque les valeurs de dimension associées à une variante de produit sont traduites, le nom de la variante de produit s'affiche dans la version traduite.  

**Exemple**  

Votre produit est un T-shirt qui existe en différentes tailles et couleurs, et les noms des variantes sont basés sur les informations suivantes :
-   Numéro de produit : \#3
-   Dimensions : Taille et couleur
-   Valeurs de dimension de taille : S, M et L
-   Valeurs de dimension de couleur : Rouge, Vert, Noir

Nom d'une variante de produit en cours selon les valeurs de dimension petites et rouge est **\#3 : Petit : Rouge **.  

Un client souhaite acheter des T-shirts en taille S et rouges, et le nom du T-shirt doit apparaître en français sur la facture. Vous traduire les valeurs de dimension, petit et Rouge, dans le français, et le nom de la variante de produit est **\#3 : Petit : Fard à joues **.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tip</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour définir la langue préférée d'un client, procédez comme suit :
<ol>  
<li>Cliquez <strong>Ventes et marketing</strong> &gt; <strong>Commune</strong> &gt; <strong>Clients</strong> &gt; <strong>Tout</strong><strong>clients</strong>sur.</li>
<li>Double-cliquez sur un client pour ouvrir la page <strong>Clients</strong>. Sous l'onglet <strong>Général</strong>, dans le champ <strong>Langue</strong>, sélectionnez <strong>langue</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Que se produit-il si un client a une langue préférée pour laquelle aucune traduction n'est disponible ?
Si des traductions ne sont pas disponibles dans la langue préférée du client, les noms et les descriptions s'affichent dans la langue globale de votre société.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Puis-je gérer les traductions pour une série de valeurs de dimension simultanément ?
Les valeurs de dimension sont spécifiques à un produit et vous pouvez gérer les traductions pour les valeurs de dimension pour chaque produit. Toutefois, si vous créez un groupe de valeurs de dimension et créez des traductions pour les valeurs du groupe de valeurs, il est plus simple de gérer les traductions.   

**Example**  

Votre société produit des T-shirts de différents styles, et chaque style sera disponible dans les tailles S, M et L. Les tailles sont regroupées dans un groupe de valeurs de dimension. Lorsqu'un nouveau style de T-shirt est ajouté, vous pouvez l'associer au groupe de valeurs de dimension utilisé pour les tailles, de sorte que toutes les tailles soient disponibles pour le produit. Vous pouvez également ajouter ou modifier des traductions pour les tailles dans le groupe de valeurs de dimension à tout moment.  

Une valeur de dimension associée à un produit via un groupe de variantes de dimension doit être mise à jour depuis le groupe de variantes de produit.   
Pour créer un groupe de valeurs de dimension, procédez comme suit :
1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** paramétrage ** &gt; ** groupes de variantes **.
2.  Sélectionnez **Groupes** **de tailles**, **Groupes de couleurs** ou **Groupes de styles**.
3.  Cliquez sur ** nouveau **, puis entrez ensuite le nom du groupe ** taille ** ** au groupe **, ** groupe de couleurs **, ou ** Groupe de styles ** champ. Cliquez sur **Tailles**, **Couleurs** ou **Styles** pour créer des lignes pour les groupes.
4.  ** Taille ** ** au groupe ** lignes, ** couleur ** ** groupe ** ** lignes **, ou ** le Groupe de styles Lignes ** page, cliquez sur ** nouveau **, puis créez des tailles, couleurs, et styles pour les groupes.

Pour gérer les traductions des valeurs d'un groupe de valeurs de dimension, procédez comme suit :
1.  Respectez la procédure précédente pour créer un groupe de valeurs de dimension pour ouvrir la page **Lignes de groupes de tailles**, **Lignes de groupes de couleurs** ou **Lignes de groupes de styles**.
2.  Cliquez sur **Traduction de texte**. Dans ** traduction de texte ** page, ** texte traduit ** dans le groupe, entrez des traductions dans ** nom ** et ** description ** des champs.

## <a name="when-can-translations-of-productrelated-information-be-managed"></a>Lorsque les traductions d'informations liées aux produits peuvent -elles être traitées ?
Les traductions des informations relatives aux produits peuvent être gérées à tout moment. Lorsque les traductions sont mises à jour pour une valeur de dimension associée à un produit, les informations sur le produit sont mises à jour, que le produit ait des transactions ou non.




