---
title: Organiser les composants d'état dans le concepteur d'état
description: Après la création des blocs élémentaires et des états générés, il est utile d’organiser ces objets afin qu’ils soient plus faciles à localiser. Cet article explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d'états.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3f2b34cccfd84a9e4bb76e7a1da64e5cefa9982e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551741"
---
# <a name="organize-report-components-in-report-designer"></a>Organiser les composants d'état dans le concepteur d'état

[!include [banner](../includes/banner.md)]

Après la création des blocs élémentaires et des états générés, il est utile d’organiser ces objets afin qu’ils soient plus faciles à localiser. Cet article explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d'états.

Vous pouvez renommer des dossiers, des états, des blocs élémentaires, ainsi que d'autres objets dans le concepteur d'état pour aider à organiser vos fichiers. Selon le type d'objet que vous renommez, vous devrez peut-être mettre à jour des associations avec cet objet.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Renommer un dossier ou un bloc élémentaire dans Report Designer
Dans le Concepteur de rapports, vous pouvez renommer des dossiers, des définitions de rapport, des définitions de ligne, des définitions de colonne et des définitions d'organigramme d'entreprise.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Attribution d'un nouveau nom à un dossier ou à un bloc élémentaire dans le Concepteur de rapports

1. Dans le Concepteur de rapports, utilisez le volet de navigation pour localiser le dossier ou l'objet à renommer.
2. Cliquez avec le bouton droit sur le dossier ou l'objet, puis cliquez sur **Renommer**. Le champ **Nom** dans le volet de navigation devient disponible.
3. Entrez un nouveau nom, puis appuyez sur Entrer.
4. Si le bloc élémentaire est une définition de ligne, une définition de colonne, ou une définition d'arborescence de génération d'états, vous devez mettre à jour d'autres blocs élémentaires associés à lui. Cliquez avec le bouton droit sur le bloc élémentaire que vous avez renommé à l'étape 3, sélectionnez **Associations**, puis sélectionnez un article dans la liste pour le mettre à jour.
5. Répétez l'étape 4 jusqu'à ce que tous les articles associés soient mis à jour.

## <a name="create-and-manage-report-groups"></a>Créer et gérer des groupes d'états
Vous pouvez regrouper les définitions d'état pour générer plusieurs états simultanément. Pour créer, modifier, supprimer, puis générer des groupes d'états, vous devez avoir le rôle de concepteur ou d'administrateur. Les utilisateurs ayant le rôle de générateur peuvent générer des groupes d'états et peuvent également modifier le paramètre des définitions d'état utilisateur pour des groupes d'états.

### <a name="create-a-report-group"></a>Créer un groupe d'états

1. Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.
2. Dans le menu **Fichier**, cliquez sur **Nouveau** &gt; **Définition de groupe d'état** pour ouvrir un nouveau groupe d'état dans la fenêtre du visualiseur. Sinon, cliquez sur le bouton **Groupe d'états** ![Groupe d'états](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Groupe d'états") sur la barre d’outils.
3. Cliquez sur l'onglet **Groupe de rapports**. Pour remplacer les informations sur les différentes définitions d'état pour la génération de cet état, activez la case à cocher **Remplacer les paramètres de la société, des détails et de date à partir des définitions d'état**. Les informations sur le nom de la société, le niveau de détail, les paramètres provisionnels et la date sont fournis automatiquement mais vous pouvez toujours effectuer des mises à jour.
4. Pour générer plusieurs états affichant les devises de déclaration, activez la case à cocher **Inclure toutes les devises de déclaration**. Vous pouvez ensuite accéder à plusieurs en cliquant sur le bouton **Devise** dans la visionneuse Web lorsque vous afficherez l'état.
5. Dans le champ **États dans le groupe**, cliquez sur **Ajouter** pour sélectionner les états à inclure dans le groupe d'états. Pour sélectionner plusieurs états dans la boîte de dialogue **Ajouter**, maintenez la touche Ctrl enfoncée alors que vous sélectionnez des états. Lorsque vous avez terminé la sélection des états, cliquez sur **OK**.
6. Cliquez sur **Fichier** &gt; **Enregistrer** pour enregistrer le nouveau groupe d'états.

### <a name="modify-a-report-group"></a>Modifier un groupe d'états

1. Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.
2. Double-cliquez sur le groupe d'états à modifier.
3. Sur l'onglet **Groupe d'états**, apportez les modifications que vous souhaitez.
4. Dans le menu **Fichier**, cliquez sur **Enregistrer** pour enregistrer le groupe d'états modifié ou sur le bouton **Enregistrer** ![Enregistrer](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Enregistrer") dans la barre d'outils.

> [REMARQUE] Si vous avez planifié des états à générer à intervalles définis, vous pouvez remplacer ces paramètres et déclarer un état immédiatement.

### <a name="generate-a-report-group-report"></a>Générer un état du groupe d'états

1. Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.
2. Ouvrez le groupe d'états à générer.
3. Cliquez sur le bouton **Générer un état** ![Générer un état](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Générer un état") pour générer des états.

### <a name="delete-a-report-group"></a>Supprimer un groupe d'états

1. Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.
2. Cliquez avec le bouton droit sur le groupe d'états à supprimer, puis sélectionnez **Supprimer**.
3. Lorsqu’un message de confirmation apparaît, cliquez sur **Oui**.

## <a name="report-group-tab-controls"></a>Contrôles de l'onglet Groupe d'états
Le tableau suivant décrit les contrôles l'onglet **Groupe d'états**.

<table>
<thead>
<tr>
<th>Contrôle</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Remplacer les paramètres de la société, des détails et de date à partir des définitions d'état</td>
<td>Activez cette case à cocher pour remplacer les définitions d'état individuelles des états dans ce groupe d'états pour la génération de ces états uniquement.</td>
</tr>
<tr>
<td>Nom de la société</td>
<td>Sélectionnez la société à utiliser pour les états.</td>
</tr>
<tr>
<td>Niveau de détail</td>
<td>Permet de spécifier le niveau de détail souhaité dans l'état.
<ul>
<li><strong>Rapport financier</strong> − Rapport de synthèse de haut niveau. Vous ne pouvez pas effectuer de zoom avant dans les comptes et les dimensions, à l'exception de ceux ajoutés via une arborescence de génération d'états.</li>
<li><strong>Financier &amp; Compte</strong> − État qui contient une synthèse de haut niveau et des détails du compte.</li>
<li><strong>Financier, Compte &amp; Transaction</strong> État qui contient une synthèse de haut niveau et des détails de la transaction.</li>
</ul></td>
</tr>
<tr>
<td>Provisionnel</td>
<td>Permet de spécifier les types d'activités souhaités dans l'état.
<ul>
<li><strong>Activité validée uniquement</strong> − Inclut uniquement les transactions et les soldes validés dans vos données financières.</li>
<li><strong>Activité validée et non validée</strong> − Inclut tous les soldes et transactions entrés et validés dans vos données financières.</li>
<li><strong>Activité non validée uniquement</strong> − Inclut uniquement les transactions entrées mais pas encore validées dans vos données financières.</li>
</ul></td>
</tr>
<tr>
<td>Inclure toutes les devises de déclaration</td>
<td>Toutes les devises de déclaration supplémentaires configurées dans votre système Microsoft Dynamics ERP sont indiquées ici. Activez cette case à cocher pour générer des états supplémentaires dans les devises indiquées. Pour afficher ces rapports dans la visionneuse Web, cliquez sur le bouton <strong>Devise</strong> et sélectionnez une devise.</td>
</tr>
<tr>
<td>Informations de date non enregistrées avec la définition d'état</td>
<td><ul>
<li>Période de base</li>
<li>Année de base</li>
<li>Période couverte</li>
</ul>
Seuls les paramètres de période de base par défaut sont enregistrés avec la définition d'état.</td>
</tr>
<tr>
<td>Informations de date enregistrées avec la définition d'état</td>
<td><ul>
<li>Date de l'état</li>
<li>Période de base par défaut</li>
</ul></td>
</tr>
<tr>
<td>États dans le groupe</td>
<td>Permet d'ajouter, de supprimer, et de trier à nouveau les états dans le groupe d'états.
<ul>
<li>Pour ajouter des définitions de rapport au groupe de rapports, double-cliquez sur ce dernier pour l'ouvrir, puis cliquez sur <strong>Ajouter</strong>. Sélectionnez les rapports à inclure dans le groupe de rapports, puis cliquez sur <strong>OK</strong>.</li>
<li>Pour supprimer un rapport du groupe de rapports, sélectionnez-le, puis cliquez sur <strong>Supprimer</strong>.</li>
<li>Pour modifier l'ordre dans lequel les états sont générés, sélectionnez un état dans la liste, puis cliquez sur <strong>Déplacer vers le haut</strong> ou <strong>Déplacer vers le bas</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)
