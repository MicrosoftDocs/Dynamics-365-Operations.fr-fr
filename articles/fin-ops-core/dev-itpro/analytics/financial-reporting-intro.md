---
title: États financiers
description: La génération d’états financiers permet aux professionnels financiers et commerciaux de créer, tenir à jour, déployer et afficher les tableaux d’analyse. Elle dépasse les contraintes traditionnelles liées à la génération d’états pour vous aider à concevoir efficacement différents types d’états.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7da0d1aa4bb10658c66fce996e00b5714125f100
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682694"
---
# <a name="financial-reporting"></a>États financiers

[!include [banner](../includes/banner.md)]

La génération d’états financiers pour l’application permet aux professionnels financiers et commerciaux peuvent utiliser pour créer, tenir à jour, déployer, et afficher les tableaux d’analyse. Elle dépasse les contraintes traditionnelles liées à la génération d’états pour vous aider à concevoir efficacement différents types d’états.

La génération d’états financiers comprend la prise en charge de la dimension. Par conséquent, les segments de comptes ou de dimensions sont immédiatement disponibles. Aucun outil supplémentaire ni étape de configuration n’est nécessaire.

## <a name="financial-reporting-setup"></a>Configuration des états financiers
La page **Configuration des états financiers** contient une liste de toutes les dimensions financières du système. **Comptabilité** \> **Paramétrage de la comptabilité** \> **Configuration des états financiers**.

La page **Configuration des états financiers** comporte deux sections qui déterminent les données pour lesquelles vous générez un état dans les états financiers :

- **Onglet Dimensions** - Comme chaque société utilise des dimensions et des structures de compte différentes, il n’existe aucun moyen de déterminer l’ordre dans lequel les utilisateurs souhaitent afficher toutes les dimensions financières dans les états. Cette page vous permet de définir l’ordre dans lequel les dimensions financières doivent apparaître lorsque vous créez et affichez un état dans les états financiers.
- **Onglet Attributs** - Permet d’indiquer si vous souhaitez utiliser **Fournisseurs** et **Clients** comme attributs pour le filtrage et la conception d’états. La génération d’un état sur le fournisseur et le client n’est utile que si vous n’entrez pas plusieurs fournisseurs ou clients dans un document unique lors de la validation des transactions. Si vous sélectionnez Fournisseur et/ou Client, cela ajoute du temps supplémentaire à l’intégration.

## <a name="financial-reporting-components"></a>Composants de la génération d’états financiers
Les composants suivants la génération d’états financiers sont simples à utiliser pour créer, afficher et planifier les rapports.

| Composant        | Fonctions | Informations supplémentaires |
|------------------|-----------|------------------------|
| Concepteur de rapports  | Créez des blocs élémentaires d’état pouvant être combinés pour définir et générer un état. L’Assistant de rapport dirige les utilisateurs peu expérimentés tout au long du processus de création. Les utilisateurs expérimentés peuvent créer des blocs élémentaires d’état ou modifier les blocs élémentaires existants pour répondre à leurs besoins. | |
| Planifications de rapport | Planifiez un état unique ou un groupe d’états afin qu’il soit généré régulièrement. | [Générer les états financiers](generate-financial-report.md) |

## <a name="features"></a>Équipements
<table>
<thead>
<tr>
<th>Fonctionnalité</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Flexibilité de la conception des rapports</td>
<td>Le générateur d’états fournit les options de génération d’états suivantes lorsque vous créez un état :
<ul>
<li>Enregistrez les combinaisons de dimension et réutilisez les dimensions pour plusieurs états.</li>
<li>Contrôlez la façon dont les descriptions de dimension sont affichées et mises en forme.</li>
<li>Identifiez les comptes ou les dimensions qui ont été omis des blocs élémentaires de rapport.</li>
<li>Mettez les en-têtes en forme pour les prévisions à court terme.</li>
</ul>
</td>
</tr>
<tr>
<td>Collaboration des rapports financiers</td>
<td>Les fonctions suivantes vous permettent de gérer la génération et la distribution des rapports :
<ul>
<li>Programmez les états afin qu’ils soient générés automatiquement sur une base journalière, hebdomadaire, mensuelle ou annuelle.</li>
<li>Exportez au format XPS en lecture seule, offrant une sécurité optimale des documents grâce aux signatures numériques.</li>
<li>Exporter vers une feuille de calcul Microsoft Excel.</li>
<li>Pour partager des états, vous pouvez créer des e-mails contenant des liens vers les états en question.</li>
</ul>
</td>
</tr>
<tr>
<td>Affichage interactif des rapports</td>
<td>Des fonctionnalités interactives vous permettent d’effectuer les tâches suivantes :
<ul>
<li>Modifier la date d’état pour l’état que vous visualisez.</li>
<li>Modifier la devise d’état pour l’état que vous visualisez.</li>
<li>Affichez l’état dans une vue de synthèse ou une vue détaillée.</li>
<li>Ajouter des filtres de dimension pour limiter le contenu de l’état à une dimension spécifique ou à une combinaison de dimensions.</li>
<li>Ajouter des filtres d’attribut pour limiter le contenu de l’état à un attribut spécifique ou à une combinaison d’attributs.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ressources supplémentaires
[Générer les états financiers](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]