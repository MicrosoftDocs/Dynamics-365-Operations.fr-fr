---
title: Configuration des noms de champs d&quot;application en entreposant l&quot;application
description: "Cette rubrique décrit la procédure de définir et de configurer les noms et les priorités de champ d&quot;application d&quot;entrepôt dans Dynamics 365 pour les opérations."
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
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configuration des noms de champs d'application en entreposant l'application

Cette rubrique décrit la procédure de définir et de configurer les noms et les priorités de champ d'application d'entrepôt dans Dynamics 365 pour les opérations. 

** Remarque : ** La présente rubrique s'applique aux fonctions du module Gestion des entrepôts. Elle ne s'applique pas aux fonctions dans Gestion des stocks. Dynamics 365 pour les opérations - le stockage est une application que vous pouvez utiliser pour effectuer des tâches d'entrepôt. Vous pouvez définir et de configurer les noms de champs utilisés dans l'application, ainsi que de configurer la priorité à laquelle les noms de champs doit être affecté. Cette rubrique explique comment définir et de configurer les noms et priorités de champ d'application d'entrepôt, et de leur utilisation dans Dynamics 365 pour les opérations - entreposant. Pour plus d'informations sur la configuration de la connexion à Dynamics 365 pour les opérations - en entreposant, reportez-vous à des instructions [installer et configurer Dynamics 365 pour les opérations - entreposant] (install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Configuration des noms de champs d'application d'entrepôt
===================================

Lorsque vous utilisez Dynamics 365 pour les opérations - entreposant sur votre périphérique mobile, vous pouvez configurer la manière dont les métadonnées doivent figurer dans votre périphérique sur ** des noms de champs d'application d'entrepôt ** page. Dans une nouvelle société dans Dynamics 365 pour les opérations, sélectionnez ** créez le paramétrage par défaut ** pour générer des noms de champs utilisés dans les workflows de périphérique mobile d'entrepôt, puis associez -lui un mode d'entrée et un type préférés d'entrée eux. Après avoir généré tous les noms de champs, vous pouvez sélectionner les options suivantes d'entrée.

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
<td>Cette option définit si un champ de lecture ou un champ de saisie de saisie manuelle doit être affiché pour le nom du champ sélectionné. Utile pour distinguer les champs selon que des codes-barres sont utilisés pour le champ. <strong>Remarque :</strong> Pour les noms de champs avec le mode d'entrée préféré défini sur, vous pouvez entrer les informations manuellement si le code-barres est illisible ou endommagé.</td>
</tr>
<tr class="even">
<td>Type de saisie</td>
<td>Cette option définit le type d'entrée doit être utilisé pour le nom du champ sélectionné. Quatre options sont disponibles :
<ul>
<li><strong>Sélection</strong> - contient une liste d'options de choisir. Les noms de champs avec cette option ne sont pas être modifié.</li>
<li><strong>Date</strong>les noms de champs - spécifiés comme date affiche un format de date pour l'étiquette. Cela permet l'entrepôt des travailleurs à afficher dans quel format permet d'entrer la date. Les noms de champs avec cette option ne sont pas être modifié.</li>
<li><strong>Alpha</strong> - si sélectionné, le clavier du périphérique est utilisé lorsque vous entrez des informations manuellement dans l'application. On peut modifier l'expérience de clavier selon laquelle le périphérique est utilisé.</li>
<li><strong>Numérique</strong> - Pour les noms de champs qui utilisent l'entrée numérique uniquement, vous pouvez sélectionner cette option pour afficher un pavé numérique personnalisé avec le champ d'entrée au lieu du clavier du périphérique.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurez la priorité de champ d'application d'entrepôt
======================================

Sous ** priorité de champ d'application d'entrepôt ** la page, vous pouvez mettre des noms de champs en différents groupes prioritaires. Cela permet de décider quelles informations doivent être affichées dans la page de tâche principale lorsque les travailleurs d'entrepôt effectuent des tâches via l'application. Si vous cliquez sur ** créez le paramétrage par défaut **, un ensemble par défaut de groupes prioritaires est généré. Vous pouvez créer autant de groupes prioritaires si nécessaire, mais uniquement trois groupes prioritaires sont affichés dans la page de tâches. Lorsque Dynamics 365 pour les opérations envoie des métadonnées sur l'application, il affecte à chaque champ une priorité associée en fonction de son groupe élevée, et l'application affiche les trois premiers groupes prioritaires contenus dans les métadonnées sur la page de tâche. Le reste de métadonnées de débordement est affiché à une page secondaire de détails. Le tableau ci-dessous montre un exemple de cinq groupes prioritaires.

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
<td> Priorité 10</td>
<td><ul>
<li>Article</li>
<li>Quantité</li>
<li>Unité de mesure</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorité 20</td>
<td><ul>
<li>Poste de groupement</li>
<li>Groupement</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorité 30</td>
<td><ul>
<li>Description de l'article</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorité 40</td>
<td><ul>
<li>Configuration</li>
<li>Couleur</li>
<li>Taille</li>
<li>Style</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorité 50</td>
<td><ul>
<li>Entrepôt</li>
<li>Contenant</li>
</ul></td>
</tr>
</tbody>
</table>

Par exemple, si un travailleur d'entrepôt effectue une tâche sur un périphérique mobile, si les métadonnées qui seront affichées dans l'application incluent les champs suivants :

-   Article
-   Quantité
-   Unité de mesure
-   Description de l'article
-   Taille et emplacement

Selon la priorité de champ d'application d'entrepôt paramétrée dans le tableau ci-dessus, les 3 lignes suivantes d'informations s'affichent dans la page de tâches :

-   Ligne 1 : Article, la quantité, l'unité de mesure
-   Ligne 2 : Description de l'article
-   Ligne 3 : Taille

Les métadonnées restantes, par exemple, Emplacement, ne seront pas affichées dans la page de tâches, mais s'affichent sur une page de détails. Pour plus d'informations et afficher des exemples de l'interface utilisateur, reportez-vous à la validation de blog [annonçant Dynamics 365 pour les opérations - entreposant] (https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Voir également :
--------

[Installation et configuration Microsoft Dynamics 365 pour les opérations – en entreposant] (install-configure-warehousing-app.md)


