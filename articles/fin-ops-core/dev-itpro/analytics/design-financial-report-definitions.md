---
title: Définitions d’états dans le générateur d’états financiers
description: Cet article fournit des informations sur les définitions d’état.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.form: FinancialReports
ms.openlocfilehash: 2ffef335c694af56486ccd7738818c4edda49b9e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802530"
---
# <a name="report-definitions-in-financial-report-designer"></a>Définitions d’états dans le générateur d’états financiers

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les définitions d’état. Une définition d’état est un composant d’état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d’organigramme d’entreprise facultatif pour créer un état. Une définition d’état fournit également les paramètres et les options pour la personnalisation d’un état. 

Une définition d’état est un composant d’état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d’organigramme d’entreprise facultatif pour créer un état. De plus, la définition de rapport comporte un grand nombre d’options et de paramètres pour personnaliser un rapport. Après avoir défini des définitions de ligne et des définitions de colonne, vous devez les combiner dans une définition d’état. À ce stade, vous définissez également d’autres aspects des définitions, comme le niveau de détail et la date de l’état. Vous pouvez ensuite enregistrer et générer l’état. Les états financiers offrent les niveaux de détail suivants :

- Financier
- Financier et Compte
- Financier, Compte et Transaction

Toutefois, en fonction de la manière dont les données sont stockées dans le système Microsoft Dynamics ERP, il se peut que les détails de la transaction ne soient pas disponibles dans les rapports.

## <a name="create-a-report-definition"></a>Créer une définition d’état
1. Dans le Report Designer, dans le menu **Fichier**, cliquez sur **Nouveau**, puis sélectionnez **Définition d’état**.
2. Spécifiez les informations appropriées dans les onglets **État**, **Sortie et distribution**, **En-têtes et pieds de page** et **Paramètres**.

## <a name="contents-of-a-report-definition"></a>Contenu d’une définition d’état
Le tableau suivant décrit les onglets dans une définition d’état, ainsi que la manière dont les informations sont utilisées.

<table>
<thead>
<tr>
<th>Onglet</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Etat</td>
<td>Créer un état, configurer un état, ou modifier un état existant.</td>
</tr>
<tr>
<td>Sortie et distribution</td>
<td>Modifier le type de sortie et la destination de l’état.</td>
</tr>
<tr>
<td>En-têtes et pieds de page</td>
<td>Définir et mettre en forme les en-têtes et les pieds de page de l’état. Par exemple, vous pouvez ajouter du texte ou des images à l’en-tête ou au pied de page. Les états financiers prennent en charge les fichiers image .bmp, .jpg, et .png. Vous pouvez également ajouter des codes d’insertion automatique pour insérer d’autres informations, telles que le nom de la société, un nom d’état, ou un numéro de page.</td>
</tr>
<tr>
<td>Paramètres</td>
<td>Spécifier des paramètres de définition d’état, tels que les paramètres suivants :
<ul>
<li>Mise en forme et arrondi des montants</li>
<li>Mise en forme des états détaillés</li>
<li>Mise en forme des arborescences de génération d’états</li>
<li>Générer un état sur les exceptions</li>
<li>Spécifier la conversion de devises</li>
<li>Sous-total et filtrage des détails du compte</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
