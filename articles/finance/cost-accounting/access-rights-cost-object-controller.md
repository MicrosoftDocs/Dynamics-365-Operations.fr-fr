---
title: Droits d’accès pour les contrôleurs d’objet de coût
description: Cette rubrique fournit des informations sur les droits d’accès pour les contrôleurs d’objet de coût.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c30a7c2765647aad17a475ba8705b8e688d166593adf242fcd15d90e49334189
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733027"
---
# <a name="access-rights-for-cost-object-controllers"></a>Droits d’accès pour les contrôleurs d’objet de coût

[!include [banner](../includes/banner.md)]

L’espace de travail **Contrôle des coûts** est un point central où les responsables peuvent afficher les performances de leurs objets de coût. Cet espace de travail permet aux responsables d’utiliser les données de contrôle de gestion même si elles ne concernent pas les comptables. Pour des raisons de sécurité, les responsables doivent être autorisés à voir les données de contrôle de gestion liées aux objets de coût spécifiques dont ils sont responsables.

Il existe quatre rôles uniques dans le contrôle de gestion.

| Nom de rôle               | Licence      |
|-------------------------|--------------|
| Gestionnaire de contrôle de gestion | Activité     |
| Contrôleur de gestion         | Operations   |
| Commis contrôleur de gestion   | Operations   |
| Contrôleur d’objet de coût  | Membres de l’équipe |

Cette rubrique explique comment affecter le rôle **Contrôleur d’objet de coût** à un responsable.

Lorsque le rôle **Contrôleur d’objet de coût** est affecté à un responsable, le responsable peut effectuer les tâches suivantes :

- Accéder à l’espace de travail **Contrôle des coûts** (dans le client).

    - Extraire et avoir accès aux pages qui prennent en charge l’expérience d’extraction.

- Accéder à l’espace de travail **Contrôle des coûts** (dans l’application mobile).

> [!NOTE]
> Le rôle **Contrôleur d’objet de coût** ne contrôle pas les objets de coût auxquels l’utilisateur peut accéder et dont il peut afficher les données. La sécurité au niveau de la ligne est fournie via les hiérarchies de dimensions et la hiérarchie de liste d’accès.

## <a name="grant-access-rights"></a>Accorder des droits d’accès
L’exemple suivant montre ce à quoi une hiérarchie de dimensions peut ressembler.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension    | Nom du type de hiérarchie des dimensions      | Hiérarchie de la liste d’accès |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Centres de coût | Hiérarchie de classification de dimension | **Oui**               |

Vous pouvez utiliser l’organisateur **Utilisateurs** dans le concepteur de hiérarchie pour ajouter un ou plusieurs ID utilisateur dans chaque nœud.

|             Nœuds                 | Utilisateurs            | Membre de la dimension de départ     |   Membre de la dimension de fin   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| Organisation                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Admin                 | Avril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finances   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Production            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Emballage | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblage  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> Les comptables doivent être affectés au niveau supérieur de la hiérarchie, de sorte qu’ils puissent visualiser toutes les écritures du contrôle de gestion.

Avant que les paramètres de la hiérarchie de la liste d’accès et ses paramètres de sécurité puissent être appliqués, l’option **Activer l’affichage pour les membres de dimension d’objet de coût** doit être définie sur **Oui** dans l’onglet **Général** de la page **Paramètres de contrôle de gestion** (**Contrôle de gestion** > **Paramétrage** > **Paramètres**).

Les paramètres de la hiérarchie de la liste d’accès sont utilisés pour contrôler les données affichées dans les sections suivantes :

- Espace de travail **Contrôle des coûts** (dans le client) :

    - Données dans les pages utilisées pour l’extraction

- Espace de travail **Contrôle des coûts** (dans l’application mobile) :

    - Soldes dans les cartes

- Microsoft Power BI :

    - Données qui sont affichées dans une visualisation Power BI
    - Visualisations des données Power BI intégrées dans le client Dynamics 365 Finance

> [!IMPORTANT]
> - Avant que la hiérarchie de la liste d’accès puisse affecter des données Power BI, la hiérarchie de la liste d’accès et la sécurité au niveau de la ligne dans Power BI doivent être jumelées. Pour plus d’informations, voir [Paramétrer la sécurité pour le pack de contenu de gestion des coûts](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Cette rubrique affiche les paramétrages qui doivent être effectués pour utiliser l’espace de travail **Contrôle des coûts**.

Ressources supplémentaires

- [Espace de travail de contrôle des coûts](cost-control-workspace.md)
- [Hiérarchie des dimensions](dimension-hierarchy.md)
- [Paramétrer la sécurité du pack de contenu Contrôle de gestion](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
