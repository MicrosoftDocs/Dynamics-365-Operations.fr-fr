---
title: Configurer des hiérarchies d’organisation
description: Cette rubrique décrit comment configurer des hiérarchies d’organisation dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f6e791ffd15128d2076340515a08b5ea6be70dae
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346006"
---
# <a name="set-up-organization-hierarchies"></a>Configurer des hiérarchies d’organisation

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer des hiérarchies d’organisation dans Microsoft Dynamics 365 Commerce.

Avant de créer des canaux, vous voudrez vous assurer d’avoir configuré vos hiérarchies d’organisation.

Les hiérarchies d’organisation vous permettent d’afficher et de créer des états relatifs à votre entreprise à partir de perspectives différentes. Par exemple, vous pouvez paramétrer une hiérarchie pour les déclarations légales ou fiscales. Vous pouvez ensuite paramétrer une autre hiérarchie pour déclarer des informations financières qui ne sont pas requises par la loi, mais qui sont utilisées à des fins de déclaration interne.

Vous devez créer des organisations avant de créer une hiérarchie d’organisation. Pour plus d’informations, voir [Créer des entités juridiques](channels-legal-entities.md) ou [Créer des unités opérationnelles](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Pour plus d’informations, voir les rubriques suivantes.
- [Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Planifier votre hiérarchie d’organisation](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Créer une hiérarchie d’organisation](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Créer une hiérarchie d’organisation

Procédez comme suit pour créer une hiérarchie organisationnelle.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Hiérarchies d’organisation**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, entrez une valeur.
1. Dans la section **Objectif**, sélectionnez **Affecter un objectif**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez un objet à affecter à la hiérarchie d’organisation.
1. Dans le section **Hiérarchies affectées**, sélectionnez **Ajouter**.
1. Dans la liste, marquer la ligne sélectionnée. Recherchez la hiérarchie que vous venez de créer.
1. Cliquez sur **OK**.

L’image suivante montre un exemple de hiérarchie organisationnelle créée pour un ensemble fictif de magasins « Adventure Works ».

![Exemple de hiérarchie organisationnelle.](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Ajout d’organisations à une hiérarchie

Pour ajouter des organisations à une hiérarchie, procédez comme suit.

1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez votre hiérarchie.
1. Dans le volet Actions, sélectionnez **Afficher**.
1. Ajoutez des organisations, le cas échéant.
1. Pour ajouter une organisation, sélectionnez **Éditer** puis **Insérer**. Lorsque vous avez apporté les modifications, vous pouvez enregistrer un brouillon et publier les modifications.

L’image suivante montre une entité juridique ajoutée à la racine de la hiérarchie avec quatre centres de coûts ajoutés pour les canaux « Mall », « Outlet », « Online » et « Call Center ». Divers canaux de vente au détail, de centres d’appels et en ligne peuvent ensuite être ajoutés à chacun.

![Exemple de concepteur de hiérarchies.](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planifier votre hiérarchie d’organisation](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Créer des entités juridiques](channels-legal-entities.md)

[Créer des unités opérationnelles](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Présentation des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
