---
title: Recherche dans le programme SEFA
description: Cette rubrique fournit des informations sur l’enquête sur l’annexe des dépenses des bourses fédérales.
author: velofog
manager: Ann Beebe
ms.date: 04/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PSNProjSEFAinquiry
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.tgt_pltfrm: ''
ms.custom: ''
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-alpavk
ms.search.validFrom: 2020-4-01
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 0b4228a9592efb54714186fc6b36276e915dc122
ms.sourcegitcommit: be51e892003778e71b67fb409a8e16965c89b5ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2020
ms.locfileid: "3618453"
---
# <a name="schedule-of-expenditures-of-federal-awards-inquiry"></a>Recherche dans le programme SEFA

[!include [banner](../includes/banner.md)]

Selon le Bureau de la gestion et la circulaire budgétaire A-133, les organismes qui reçoivent des fonds fédéraux sont soumis à des obligations d’audit, également appelées audits uniques. Le processus d’audit sert à rendre compte des revenus et des dépenses des subventions fédérales de façon récurrente. Une partie du rapport d’audit unique comprend l’annexe des dépenses des bourses fédérales (SEFA).

L’enquête sur l’annexe des dépenses des bourses fédérales comprend le titre et le numéro du Catalogue de l’aide nationale fédérale (CFDA), le numéro de la subvention, l’année de la subvention, le nom de l’organisme fédéral qui fournit les fonds et le nom de l’entité de validation. L’enquête concerne une période déterminée. En règle générale, cette période est la même que celle des états financiers, qui est un exercice.

L’enquête inclut les subventions dont les dates de projection se situent dans la plage de dates sélectionnée. La colonne **Organisme concédant** de la demande indique le client de la subvention ou, pour une subvention de validation, l’organisme concédant. Pour une subvention de validation, la colonne **Organisme de validation** montre le client de la subvention. Si la subvention n’est pas une subvention de validation, la colonne **Organisme de validation** est vide.

## <a name="set-up-the-cfda-clusters"></a>Paramétrage des clusters CFDA

Vous devez configurer les clusters CFDA qui peuvent être associés à des numéros CFDA dans l’enquête sur l’annexe des dépenses des bourses fédérales.

1. Aller à **Gestion de projets et comptabilité \> Configurer \> Subventions \> Catalogue des clusters d’assistance nationale fédérale**.
2. Sélectionnez **Nouveau** pour créer un cluster CFDA.
3. Entrez le nom du cluster.
4. Sélectionnez **Enregistrer** pour enregistrer les modifications.

## <a name="set-up-cfda-numbers"></a>Définir les numéros CFDA

Vous devez configurer les numéros CFDA qui peuvent être ajoutés aux subventions et inclus dans l’enquête sur l’annexe des dépenses des bourses fédérales.

1. Aller à **Gestion de projets et comptabilité \> Configurer \> Subventions \> Catalogue des numéros d’assistance nationale fédérale**.
2. Sélectionnez **Nouveau** pour créer un numéro CFDA.
3. Entrez le numéro CFDA dans la colonne **Numéro**.
4. Appuyez sur la touche **Tab**.
5. Entrez le titre CFDA dans la colonne **Description**.
6. Appuyez sur la touche **Tab**.
7. Facultatif : Dans le champ **Cluster de programmes**, ajoutez le cluster CFDA approprié.
8. Sélectionnez **Enregistrer** pour enregistrer les modifications.

## <a name="set-up-grants-to-report-for-the-schedule-of-expenditures-of-federal-awards-inquiry"></a>Mettre en place des subventions à déclarer dans l’enquête sur l’annexe des dépenses des bourses fédérales

1. Aller à **Gestion de projet et comptabilité \> Subventions \> Subventions** et sélectionnez une subvention existante.
2. Sur le raccourci **Installer**, dans le champ **Catalogue de l’aide national fédérale**, attribuez le numéro CFDA. Le numéro CFDA sur la subvention détermine le cluster CFDA pour la génération d’états.
3. Sur le raccourci **Informations de contact**, entrez les informations sur le concédant en procédant comme suit :

    1. Dans le champ **Client de la subvention**, saisissez le client responsable de la subvention. Pour une subvention existante, ces informations peuvent déjà être saisies.
    2. Indiquez si le client de la subvention est le bailleur de fonds. Si le client de la subvention est le bailleur de fonds, décochez la case **Valider**. Si un autre client est le bailleur de fonds et que le client de la subvention est responsable des dépenses et du suivi de l’argent, cochez la case **Validation**.

4. Si vous avez coché la case **Valider** à l’étape précédente, dans le champ **Organisme concédant**, entrez le client qui a fourni la subvention. L’organisme concédant et le client de la subvention ne peuvent pas être le même client.

Voici un exemple d’une subvention de validation :

Le gouvernement fédéral a financé un projet d’infrastructure pour un État. Le gouvernement fédéral a donné l’argent à l’État à dépenser. Dans ce cas, le gouvernement fédéral est l’organisme concédant et l’État est le client de la subvention.

> [!NOTE] 
> Lorsque vous activez la fonction pour la première fois, les numéros CFDA initiaux seront entrés en utilisant les numéros existants sur les subventions.

## <a name="exclude-grants-from-sefa-reporting-based-on-the-grant-type"></a>Exclure les subventions des rapports SEFA en fonction du type de subvention

1. Accédez à **Gestion et comptabilité des projets \> Configurer \> Subventions \> Types de subventions**.
2. Sur le raccourci **Informations par défaut**, cochez la case **Exclure de ’annexe des dépenses des bourses fédérales**.
3. Sélectionnez **Enregistrer** pour enregistrer les modifications.

## <a name="run-the-schedule-of-expenditures-of-federal-awards-inquiry"></a>Exécutez le calendrier des dépenses de l’enquête sur les bourses fédérales

1. Aller à **Gestion de projets et comptabilité \> Demandes de renseignements et rapports \> Demande de subvention \> Annexe des dépenses des bourses fédérales**.
2. Dans la section **Paramètres**, procédez comme suit :

    1. Dans le champ **Intervalle de dates**, sélectionnez le code de l’intervalle de dates. Sinon, dans les champs **Date de début** et **Date de fin**, définissez l’intervalle de dates.
    2. Facultatif : Pour inclure uniquement les transactions facturées en tant que revenus dans l’enquête, définissez l’option **Inclure uniquement les revenus facturés** sur **Oui**.

## <a name="columns"></a>Colonnes

L’enquête sur l’annexe des dépenses des bourses fédérales comprend les colonnes suivantes :

- Nom du groupement Catalogue d’assistance nationale fédérale
- Agence du donateur
- Organisme de validation
- Nom de la subvention
- ID subvention
- ID candidature de subvention
- Catalogue d’assistance nationale fédérale
- Réceptions
- Dépenses
