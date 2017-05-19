---
title: Configurer les noms de champ d&quot;application dans l&quot;application Entreposage
description: "Cette rubrique décrit comment définir et configurer les noms et les priorités de champ d&quot;application d&quot;entrepôt dans Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 73fcc19b9ee17a691206019efbff29c4967f4e2f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configurer les noms de champ d'application dans l'application Entreposage

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment définir et configurer les noms et les priorités de champ d'application d'entrepôt dans Dynamics 365 for Operations. 

**Remarque :** cette rubrique s'applique aux fonctionnalités du module Gestion des entrepôts. Elle ne s'applique pas aux fonctionnalités du module Gestion des stocks. Dynamics 365 for Operations - Entreposage est une application que vous pouvez utiliser pour effectuer des tâches d'entrepôt. Vous pouvez définir et configurer les noms de champ utilisés dans l'application, et aussi configurer la priorité d'affectation des noms de champ. Cette rubrique explique comment définir et configurer ces noms et priorités de champ d'application d'entrepôt, et comment les utiliser dans Dynamics 365 for Operations - Entreposage. Pour des informations détaillées sur la configuration de la connexion à Dynamics 365 for Operations - Entreposage, reportez-vous au didacticiel [Installation et configuration de Dynamics 365 for Operations - Entreposage]](install-configure-warehousing-app.md)

<a name="configure-warehouse-app-field-names"></a>Configurer les noms de champ d'application d'entrepôt
===================================

Lorsque vous utilisez Dynamics 365 for Operations - Entreposage sur votre appareil mobile, vous pouvez configurer l'affichage des métadonnées sur votre appareil dans la page **Noms de champ d'application d'entrepôt**. Dans une nouvelle société de Dynamics 365 for Operations, sélectionnez **Créer un paramétrage par défaut** pour générer tous les noms de champ qui seront utilisés dans les workflows d'appareil mobile d'entrepôt, puis affectez-leur un mode et un type de saisie favoris. Après avoir généré tous les noms de champ, vous pouvez sélectionner les options de saisie suivantes.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>description ;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mode de saisie favori</td>
<td>Cette option définit si un champ de lecture ou un champ de saisie manuelle doit être affiché pour le nom de champ sélectionné. Cela est utile pour distinguer les champs selon que des codes-barres sont utilisés pour le champ. <strong>Remarque :</strong> pour les noms de champ dont le mode de saisie favori est défini sur <strong>Lecture</strong>, vous pouvez entrer les informations manuellement si le code-barres est illisible ou endommagé.</td>
</tr>
<tr class="even">
<td>Type de saisie</td>
<td>Cette option définit le type de saisie à utiliser pour le nom de champ sélectionné. Quatre options sont disponibles :
<ul>
<li><strong>Sélection</strong> - Contient une liste d'options parmi lesquelles choisir. Les noms de champ avec cette option ne sont pas modifiables.</li>
<li><strong>Date</strong> - Les noms de champs spécifiés comme date affichent un format de date avec l'étiquette. Cela permet aux magasiniers de déterminer le format de saisie de la date. Les noms de champ avec cette option ne sont pas modifiables.</li>
<li><strong>Alpha</strong> - Si cette option est sélectionnée, le clavier du périphérique est utilisé lors de la saisie manuelle d'informations dans l'application. L'expérience au clavier peut être modifiée selon le périphérique utilisé.</li>
<li><strong>Numérique</strong> - Pour les noms de champ qui utilisent la saisie numérique uniquement, vous pouvez sélectionner cette option pour afficher un pavé numérique personnalisé avec le champ de saisie au lieu du clavier du périphérique.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurer la priorité du champ d'application d'entrepôt
======================================

Sur la page **Priorité du champ d'application d'entrepôt**, vous pouvez classer les noms de champ dans différents groupes de priorité. Cela permet de déterminer quelles informations doivent être affichées sur la page de tâches principale lorsque les magasiniers effectuent des tâches via l'application. Si vous cliquez sur **Créer un paramétrage par défaut**, un ensemble de groupes de priorité par défaut est généré. Vous pouvez créer autant de groupes de priorité que nécessaire, mais seuls trois groupes de priorité seront affichés sur la page de tâches. Lorsque Dynamics 365 for Operations envoie des métadonnées à l'application, il affecte à chaque champ une priorité relative selon son groupe de priorité, et l'application affiche les trois premiers groupes de priorité contenus dans les métadonnées de la page de tâches. Les métadonnées restantes seront affichées sur une page de détails secondaire. Le tableau ci-dessous présente un exemple de cinq groupes de priorité.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe de priorité</th>
<th>Champs affectés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Priorité 10</td>
<td><ul>
<li>Article</li>
<li>Quantité</li>
<li>Unité de mesure</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorité 20</td>
<td><ul>
<li>Poste de groupement</li>
<li>Groupement</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorité 30</td>
<td><ul>
<li>Description de l'article</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorité 40</td>
<td><ul>
<li>Configuration</li>
<li>Couleur</li>
<li>Taille</li>
<li>Style</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorité 50</td>
<td><ul>
<li>Entrepôt</li>
<li>Contenant</li>
</ul></td>
</tr>
</tbody>
</table>

Par exemple, lorsqu'un magasinier effectue une tâche sur un appareil mobile, si les métadonnées qui seront affichées dans l'application comprennent les champs suivants :

-   Article
-   Quantité
-   Unité de mesure
-   Description de l'article
-   Taille et emplacement

Selon la priorité du champ d'application d'entrepôt paramétrée dans le tableau ci-dessus, les 3 lignes d'informations ci-après seront affichées sur la page de tâches :

-   Ligne 1 : Article, Quantité, Unité de mesure
-   Ligne 2 : Description de l'article
-   Ligne 3 : Taille

Les métadonnées restantes, par exemple, Emplacement, ne seront pas affichées sur la page de tâches, mais sur une page de détails. Pour en savoir plus et pour consulter des exemples de l'interface utilisateur, reportez-vous à la publication de blog [Annonce de Dynamics 365 for Operations - Entreposage](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Voir également :
--------

[Installation et configuration de Microsoft Dynamics 365 for Operations – Entreposage](install-configure-warehousing-app.md)




