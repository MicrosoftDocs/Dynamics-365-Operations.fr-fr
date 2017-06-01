---
title: "Vue d&quot;ensemble des modèles de configuration de produit"
description: "Cet article définit les conditions et les concepts pertinents pour les modèles de configuration de produit. Les modèles de configuration de produit permettent de créer une structure de produit générale pouvant être utilisée pour configurer plusieurs variantes de produit pour un produit unique."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: yuyus
ms.dyn365.intro: Feb-16
ms.dyn365.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 30580b059a4c240ad540a9c347b0551df0ab5c02
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="product-configuration-models-overview"></a>Vue d'ensemble des modèles de configuration de produit

[!include[banner](../includes/banner.md)]


Cet article définit les conditions et les concepts pertinents pour les modèles de configuration de produit. Les modèles de configuration de produit permettent de créer une structure de produit générale pouvant être utilisée pour configurer plusieurs variantes de produit pour un produit unique.

Des modèles de configuration de produit sont créés pour représenter une structure de produit générique. Après avoir paramétré un modèle de configuration de produit, vous pouvez configurer une variante de produit distinct avec une nomenclature et une gamme uniques. Les modèles de configuration de produit utilisent les contraintes déclaratives et les calculs impératifs pour gérer les relations et les restrictions entre différentes variantes de produit. Vous pouvez configurer des articles sur les commandes client, devis de vente, commandes fournisseur et ordres de fabrication. Le tableau suivant décrit les termes et les concepts basés sur les contraintes de table.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Composants</td>
<td>Les composants sont les éléments de construction principaux d'un modèle de configuration de produit. Les composants sont affichés dans une structure arborescente sur la page <strong>Détails du modèle de configuration de produits basée sur les contraintes</strong>. Les composants peuvent contenir les éléments suivants :
<ul>
<li>Attributs</li>
<li>Contraintes</li>
<li>Calculs</li>
<li>Sous-composants</li>
<li>Droits d'accès requis pour l'utilisateur</li>
<li>Lignes de nomenclature</li>
<li>Opérations de gamme</li>
</ul></td>
</tr>
<tr class="even">
<td>Attributs</td>
<td>Les attributs décrivent toutes les fonctionnalités du modèle de configuration de produit. Vous pouvez utiliser des attributs pour spécifier les fonctions pouvant être sélectionnées lorsqu'un produit distinct est configuré. Les attributs sont utilisés dans les contraintes et les conditions. Lorsque les attributs sont créés et ajoutés à un modèle de configuration de produit, les types d'attributs associés sont référencés. Une valeur par défaut peut être définie pour un attribut. La valeur par défaut est utilisée dans l'interface utilisateur (UI) de configuration lorsque le modèle de configuration de produit est configuré. Vous pouvez indiquer qu'un attribut est obligatoire, en lecture seule ou masqué.
<ul>
<li><strong>Obligatoire</strong> : Une valeur doit être définie pour l'attribut lorsque le produit est configuré.</li>
<li><strong>En lecture seule</strong> : La valeur d'attribut est affichée lors d'une session de configuration, mais elle ne peut pas être modifiée.</li>
<li><strong>Masqué</strong> : La valeur d'attribut est incluse dans les contraintes et les conditions, mais n'est pas affichée lors d'une session de configuration.</li>
</ul>
Vous pouvez également spécifier une condition pour les attributs. Si la condition est remplie, une valeur doit être entrée pour l'attribut obligatoire. Les conditions sont des expressions qui doivent être rencontrées pour les attributs, les lignes de nomenclature et les opérations de gamme à inclure dans un modèle de configuration de produit. Un attribut référencé dans une condition devient obligatoire. Nous vous recommandons de sélectionner les attributs comme étant obligatoires sous l'onglet <strong>Attributs</strong>. Cela peut faciliter l'identification des attributs obligatoires. Les valeurs d'attribut sont essentielles dans le cadre de la réutilisation des configurations. Le système utilise les valeurs d'attribut pour déterminer si une configuration existante correspond aux sélections d'un utilisateur lors d'une session de configuration.</td>
</tr>
<tr class="odd">
<td>Types d'attributs</td>
<td>Les types d'attributs spécifient l'ensemble des types de données pour les attributs utilisés dans un modèle de configuration de produit. Les types d'attributs suivants sont utilisés :
<ul>
<li><strong>Entier</strong> avec ou sans plage</li>
<li><strong>Décimal</strong></li>
<li><strong>Texte</strong> avec ou sans liste fixe</li>
<li><strong>Booléen</strong></li>
</ul>
Si le type d'attribut est <strong>Booléen</strong>, <strong>Entier</strong> avec une plage, ou <strong>Texte</strong> avec une liste fixe, l'ensemble de valeurs est disponible lorsqu'un modèle de configuration de produit est paramétré. <strong>Remarque :</strong> Le solveur de configuration de produit identifie les types d'attributs suivants : <strong>Booléen</strong>, <strong>Texte</strong> avec une liste fixe, et <strong>Entier</strong> avec une plage. Par conséquent, seuls ces types d'attributs peuvent être utilisés dans les contraintes et les conditions d'expression.</td>
</tr>
<tr class="even">
<td>Contraintes</td>
<td>Les contraintes décrivent les restrictions de la configuration du modèle de produit. Les contraintes sont utilisées pour vous assurer que seules les valeurs valides sont sélectionnées lorsqu'un produit est configuré. Les contraintes peuvent être des contraintes d'expression ou des contraintes de table :
<ul>
<li>Les contraintes d'expression peuvent être utilisées uniquement pour le composant auquel elles sont associées. Les contraintes d'expression pour un composant peuvent référencer des attributs des sous-composants du composant. Le solveur de configuration de produit permet de résoudre les contraintes, vous devez utiliser la syntaxe de solveur lorsque vous entrez les contraintes. Pour plus d'informations, voir le lien de rubrique sur les contraintes d'expression et de table.</li>
<li>Les contraintes de table doivent être définies avant d'être appliquées à un composant dans un modèle de configuration de produit. Les contraintes de table peuvent être définies par l'utilisateur ou le système. Une contrainte de table définie par l'utilisateur est un type de matrice pouvant être utilisé pour décrire l'ensemble des combinaisons pour les valeurs d'attribut définies par les types d'attributs. Par exemple, si des haut-parleurs sont fabriqués, la matrice de la contrainte de table définie par l'utilisateur peut avoir des colonnes pour les finitions et les grilles.</li>
</ul>
<strong>Exemple</strong> Les haut-parleurs sont disponibles dans quatre finitions : noir, chêne, bois de rose, et blanc. Les haut-parleurs sont disponibles dans trois couleurs de grilles avant : noir, métal, ou blanc. La finition noire est disponible pour toutes les grilles, mais les autres finitions sont limitées à des grilles spécifiques. Le tableau suivant présente un exemple des informations affichées sous l'onglet <strong>Combinaisons autorisées</strong> sur la page <strong>Modifier une contrainte de table</strong>.
<table>
<thead>
<tr class="header">
<th>Finitions du meuble</th>
<th>Grille avant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Noir</td>
<td>Noir</td>
</tr>
<tr class="even">
<td>Noir</td>
<td>Métal</td>
</tr>
<tr class="odd">
<td>Noir</td>
<td>Blanc</td>
</tr>
<tr class="even">
<td>Chêne</td>
<td>Noir</td>
</tr>
<tr class="odd">
<td>Bois de rose</td>
<td>Blanc</td>
</tr>
<tr class="even">
<td>Blanc</td>
<td>Noir</td>
</tr>
<tr class="odd">
<td>Blanc</td>
<td>Blanc</td>
</tr>
</tbody>
</table>
Une contrainte de table définie par le système constitue une mise en correspondance entre un attribut et un champ dans une table Microsoft Dynamics 365 for Operations. Une contrainte de table définie par le système lie dynamiquement le type d'attribut au champ. Le lien permet à l'attribut dans un modèle de configuration de produit de refléter les données du champ de la table Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td>Calculs</td>
<td>Les calculs représentent un supplément aux contraintes. Vous pouvez utiliser un calcul pour effectuer des opérations arithmétiques sur les attributs de type <strong>Décimal</strong> et <strong>Entier</strong> ou les opérations logiques impliquant des attributs <strong>Texte</strong> avec une liste fixe et des types <strong>Booléens</strong>. Un calcul a un attribut cible qui maintiendra le résultat de l'expression de calcul. L'expression de calcul est conçue à l'aide de l'éditeur d'expressions.</td>
</tr>
<tr class="even">
<td>Sous-composants</td>
<td>Les sous-composants reflètent la structure arborescente du modèle de configuration de produit. Vous pouvez utiliser les sous-composants pour créer la structure du modèle de configuration de produit. Les sous-composants référencent des composants existants. Par conséquent, les sous-composants favorisent la réutilisation des composants dans plusieurs modèles de configuration de produit. Sur la page <strong>Détails de ligne de nomenclature</strong> pour un sous-composant, vous pouvez sélectionner une valeur distincte pour le sous-composant. Sinon, vous pouvez sélectionner un attribut pour lequel la valeur est sélectionnée lorsque le modèle de configuration de produit est paramétré. Pour inclure un produit comme composant ou sous-composant, vous devez spécifier ce qui suit dans la page <strong>Créer un produit</strong> lorsque vous créez le produit :
<ul>
<li>Sélectionnez <strong>Article</strong> dans le champ <strong>Type de produit</strong>.</li>
<li>Sélectionnez <strong>Produit générique</strong> dans le champ <strong>Sous-type de produit</strong>.</li>
<li>Dans le champ <strong>Technologie de configuration</strong>, sélectionnez <strong>Configuration basée sur les contraintes</strong>.</li>
</ul>
Vous pouvez voir si un produit lancé peut être utilisé comme composant ou sous-composant sous l'onglet <strong>Général</strong> de la page <strong>Détails des produits lancés</strong>. Si l'option <strong>Configuration basée sur les contraintes</strong> est sélectionnée dans le champ <strong>Technologie de configuration</strong>, le produit peut être utilisé en tant que composant ou sous-composant. Vous pouvez masquer les sous-composants afin qu'ils ne soient pas affichés à l'utilisateur au cours d'une session de configuration. Les attributs, les sous-composants et les besoins des utilisateurs associés au sous-composant sont également masqués.</td>
</tr>
<tr class="odd">
<td>Droits d'accès requis pour l'utilisateur</td>
<td>Les besoins des utilisateurs représentent une abstraction entre les besoins des utilisateurs et les composants spécifiques et les attributs. Vous ne pouvez pas mettre en correspondance un besoin d'utilisateur avec un article. Par exemple, un client souhaite acheter un système Home cinéma. Le commercial peut demander la taille de la pièce dans laquelle le client envisage d'installer le système pour déterminer le nombre de watts requis. Dans cet exemple, la taille de la pièce peut être un besoin d'utilisateur qui permet de déterminer la valeur de l'attribut appropriée pour un composant spécifique. Vous pouvez masquer les besoins d'utilisateur afin qu'ils ne soient pas affichés à l'utilisateur au cours d'une session de configuration. Les attributs, les sous-composants et les besoins des utilisateurs associés au besoin d'utilisateur sont également masqués. Vous pouvez entrer une condition pour contrôler si un besoin d'utilisateur peut être masqué. Vous devez écrire la condition à l'aide de la syntaxe du langage de modélisation d'optimisation (OML).</td>
</tr>
<tr class="even">
<td>Lignes de nomenclature</td>
<td>Les lignes de nomenclature représentent les différentes matières des composants dans le modèle de configuration de produit. Tous les articles de la page <strong>Détails de ligne de nomenclature</strong> sont disponibles pour sélection. Une condition peut être ajoutée à la ligne de nomenclature afin que les lignes de nomenclature sélectionnées pour une variante de produit distinct puissent varier, selon la sélection de l'utilisateur lorsque le modèle de configuration de produit est paramétré. Les conditions sont des expressions qui doivent être rencontrées pour les attributs, les lignes de nomenclature et les opérations de gamme à inclure dans un modèle de configuration de produit. Vous pouvez sélectionner une valeur distincte sur la page <strong>Détails de ligne de nomenclature</strong>. Sinon, vous pouvez effectuer une correspondance avec un attribut pour lequel la valeur est sélectionnée lorsque le modèle de configuration de produit est paramétré.</td>
</tr>
<tr class="odd">
<td>Opérations de gamme</td>
<td>Vous pouvez sélectionner une valeur distincte sur la page <strong>Détails de l'opération de gamme</strong>. Sinon, vous pouvez effectuer une correspondance avec un attribut pour lequel la valeur est sélectionnée lorsque le modèle de configuration de produit est paramétré. Les conditions sont entrées comme des contraintes d'expression. Les conditions sont des expressions qui doivent être rencontrées pour les attributs, les lignes de nomenclature et les opérations de gamme à inclure dans un modèle de configuration de produit.</td>
</tr>
</tbody>
</table>






