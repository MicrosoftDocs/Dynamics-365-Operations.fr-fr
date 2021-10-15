---
title: Établir des valeurs communes pour la gestion du changement d’ingénierie
description: Cette rubrique décrit comment établir des valeurs communes utilisées pour les paramètres dans diverses parties de la gestion des modifications techniques.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c2ff21490dc71859d75923dd757e264096d4fcba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565925"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Établir des valeurs communes pour la gestion du changement d’ingénierie

[!include [banner](../includes/banner.md)]

Lorsque vous configurez la gestion des modifications techniques, vous devez établir plusieurs collections de valeurs qui seront utilisées pour remplir les listes déroulantes dans d’autres parties de l’interface utilisateur (IU). Vous devez spécifier ces valeurs en fonction des types de produits que vous produisez et de vos besoins commerciaux spécifiques.

## <a name="engineering-change-categories"></a>Catégories de modification d’ingénierie

Vous utilisez des catégories de modifications techniques pour organiser vos demandes de modification technique, afin qu’elles soient plus faciles à gérer et à examiner. Par exemple, vous pouvez trouver utile de configurer un workflow où, selon la catégorie, un service spécifique doit examiner les modifications proposées. Par conséquent, l’ordre de modification technique comprend un champ **Catégorie**.

Pour établir la collection de catégories de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Catégories de modifications techniques**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="engineering-change-priorities"></a>Priorités des modifications d’ingénierie

Vous utilisez les priorités de changement d’ingénierie pour indiquer l’importance ou l’urgence d’un ordre de changement d’ingénierie. Ils peuvent vous aider à garder une trace de l’importance d’une demande de modification technique, afin que vous puissiez facilement identifier les commandes à traiter en premier et à quelle vitesse.

Pour établir la collection de priorités de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Priorités de modifications techniques**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="engineering-change-reasons"></a>Motifs de la modification d’ingénierie

Les raisons de la modification technique indiquent la cause ou la nature de la modification de l’ordre de modification.

Pour établir la collection de motifs de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Motifs de modifications techniques**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="material-disposal-codes"></a>Codes de cession de matières

Vous utilisez des codes d’élimination des matériaux pour classer les matériaux qui sont utilisés dans vos produits finis, ou les composants qui doivent être éliminés d’une manière spécifique ou qui nécessitent un traitement avant de pouvoir être ajoutés à votre poubelle habituelle. Lorsque vous ajoutez un produit pertinent à une demande de modification technique, vous pouvez affecter un code d’élimination dans le cadre des détails de modification.

Pour établir la collection de codes d’élimination des matériaux utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Codes d’élimination des matériaux**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="received-customer-approval"></a>Approbation du client reçue

Lorsque vous concevez des produits pour un client spécifique, la conception et les spécifications doivent souvent être validées avant que le produit puisse être défini comme prêt. Le champ **Réception de l’approbation du client** vous permet d’indiquer jusqu’où le produit se trouve dans le processus d’approbation du client et/ou si l’approbation a été reçue.

Pour établir la collection des valeurs d’approbation des clients utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Réception de l’approbation du client**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Changement technique – Codes de santé et de sécurité environnementales

Si des réglementations environnementales standard en matière de santé et de sécurité, ou des réglementations ou procédures spécifiques à l’entreprise, doivent être prises en compte dans la fabrication d’un produit, vous pouvez utiliser les codes de santé et de sécurité environnementaux pour les définir. Dans l’ordre de modification technique, vous pouvez indiquer les codes qui s’appliquent à la fabrication d’un produit pendant que vous modifiez les détails du produit concerné.

Pour établir la collection de valeurs d’hygiène et de sécurité utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Codes d’hygiène et de sécurité de l’environnement**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

## <a name="engineering-change-severities"></a>Niveaux de gravité de modification d’ingénierie

Vous utilisez les niveaux de gravité des modifications techniques pour indiquer le niveau d’impact qui s’applique aux produits dans un ordre de modification technique.

Pour établir la collection de la gravité de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d’ingénierie \> Installer \> Gestion du changement d’ingénierie \> Gravité de modifications techniques**. Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l’ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.

Vous pouvez établir des règles qui s’appliquent à chaque niveau de gravité que vous créez. Pour plus d’informations sur l’attribution de ces règles, consultez la section suivante.

## <a name="engineering-change-severity-rule-sets"></a>Ensembles de règles de gravité des modifications d’ingénierie

Vous utilisez des ensembles de règles de gravité des modifications techniques pour établir un groupe de règles que vous pouvez utiliser pour calculer automatiquement la gravité de l’ordre de modification, en fonction du type de modifications des produits concernés. Pour utiliser les règles de gravité, ouvrez la page **Paramètres de gestion des modifications techniques** et définissez le champ **Règle de gravité** sur *Calculer* ou *Calculer automatiquement*.

Lorsque le système évalue la gravité, il traite les règles dans l’ordre dans lequel elles apparaissent sur la page, de haut en bas. Pour qu’une règle soit sélectionnée et que sa priorité soit établie, toutes les règles d’un ensemble de règles doivent être respectées.

Pour configurer les règles qui s’appliquent à chaque niveau de gravité de modification que vous avez défini, accédez à **Gestion du changement d’ingénierie \> Configurer \> Gestion du changement d’ingénierie \> Ensembles de règles de gravité des modifications techniques**. Suivez ensuite l’une des procédures suivantes.

- Pour créer ensemble de règles, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit plus loin dans cette section.
- Pour modifier un ensemble de règles existant, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit plus loin dans cette section.
- Pour supprimer un ensemble de règles existante, sélectionnez-le dans le volet de liste, puis sélectionnez **Supprimer** sur le volet Actions.
- Pour réorganiser la liste des ensembles de règles, sélectionnez un ensemble de règles dans le volet de liste, puis utilisez les boutons **Haut** et **Bas** du volet Actions pour le repositionner.

Pour chaque ensemble de règles, définissez le champ suivant :

- **Gravité** – Sélectionnez le niveau de gravité pour lequel établir des règles. Vous utilisez la page **Gravités des changements d’ingénierie** pour créer et nommer les niveaux. (Pour plus d’informations, voir la section précédente.)

Utilisez les boutons du raccourci **Règles** pour ajouter ou supprimer une règle pour le paramètre de gravité actuel. Chaque règle a un champ **Règle** et un champ **Nom**. Les règles sont établies par le système et indiquent les types de modifications qu’un produit peut avoir. Le nom indique le type de modification.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]