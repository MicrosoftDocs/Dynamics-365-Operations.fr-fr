---
title: Restreindre la modification des informations personnelles
description: Empêcher les employés de modifier leurs coordonnées dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5e3eeb66d4f32b1fea1a43fff9f5b09d87d1f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018707"
---
# <a name="restrict-editing-of-personal-information"></a>Restreindre la modification des informations personnelles

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

Cette rubrique décrit comment empêcher les employés de modifier les détails de contact dans Dynamics 365 Human Resources. Vous souhaiterez peut-être empêcher les employés de modifier certaines informations de contact, telles que leur adresse professionnelle ou leur adresse e-mail.

> [!NOTE]
> Pour utiliser cette fonctionnalité, vous devez d’abord activer **(Aperçu) Empêchez les employés d’ajouter ou de modifier des adresses et des informations de contact à des fins spécifiques** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).<br><br>![Activer la fonctionnalité d’aperçu](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Choisissez les informations qu’un employé peut ajouter ou modifier

1. Dans Human Resources, sélectionnez **Gestion du personnel**, sélectionnez **Liens**, puis sélectionnez **Paramètres Human Resources**.

   ![Accéder aux paramètres de Human resources](./media/hr-employee-self-service-human-resources-parameters.png)

2. Sur la page **Paramètres des ressources humaines**, sélectionnez l’onglet **Libre-service des employés**.

   ![Sélectionnez Libre-service employé](./media/hr-employee-self-service-tab.png)

3. Sur l’onglet **Libre-service des employés**, décochez toutes les informations dans la section **Adresse et coordonnées** que vous ne souhaitez pas que les employés ajoutent ou modifient. Dans cet exemple, nous avons décoché les coordonnées **Professionnelles**.

   ![Restreindre la modification des informations de contact professionnel](./media/hr-employee-self-service-restrict-business.png)

4. Sélectionnez **Enregistrer**.

   ![Enregistrer les modifications](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Expérience des employés

Une fois que vous avez empêché les employés d’ajouter ou de modifier les coordonnées, ils peuvent voir les informations, mais ne peuvent pas les modifier.

Dans cet exemple, où les employés ne peuvent pas modifier les coordonnées **Professionnelles**, ils peuvent toujours voir les informations dans le libre-service des employés :

![Afficher les coordonnées professionnelles](./media/hr-employee-self-service-restrict-view.png)

Cependant, lorsqu’ils sélectionnent les coordonnées professionnelles, le volet **Modifier l’adresse** apparaît en lecture seule et ils ne peuvent modifier aucun des champs.

![Les coordonnées professionnelles s’affichent en lecture seule](./media/hr-employee-self-service-restrict-read-only.png)

De plus, s’ils sélectionnent **Ajouter** pour ajouter une nouvelle adresse, ils ne peuvent pas sélectionner **Professionnelle** dans la liste déroulante **But**.

![L’employé ne peut pas ajouter d’adresse professionnelle](./media/hr-employee-self-service-restrict-add.png)

Les employés bénéficient de la même expérience lorsqu’ils sélectionnent **Détails du contact** sur la page **Renseignements personnels** et ajoutent une nouvelle adresse. La liste déroulante **But** affiche uniquement les types d’informations qu’ils peuvent ajouter. 

![L’employé ne peut pas sélectionner l’entreprise dans la liste déroulante Objectif](./media/hr-employee-self-service-restrict-purpose.png)

**Détails du contact** montre maintenant **But** dans la grille.

![Le but s’affiche dans la grille des détails du contact](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Voir également :

[Vue d’ensemble du libre-service pour employés et pour responsables](hr-employee-manager-self-service-overview.md)<br>
[Configurer les paramètres de Human Resources](hr-setup-parameters.md)<br>
[Modifier les informations personnelles](hr-employee-manager-self-service-edit-personal-information.md)