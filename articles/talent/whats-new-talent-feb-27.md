---
title: Nouveautés ou modifications dans Dynamics 365 Talent (27 février 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: afa1044c8adc9566149e20ade57e771b50d9c53f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529136"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (27 février 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2163.

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Ajouter un élément du menu Champs personnalisés dans l'administration du système

La navigation jusqu'au menu **Champs personnalisés** a été ajoutée à l'espace de travail **Administration du système**.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Masquer les options de création et d'importation de nouvelles applications mobiles

Actuellement, il est impossible de créer de nouvelles applications mobiles dans Talent. L'option permettant de créer de nouvelles expériences mobiles a été supprimée du menu **Application mobile**.

### <a name="variable-compensation-award-dmf-entity"></a>Prime de rémunération variable (entité d'infrastructure de gestion des données)

Dans cette version, une entité d'infrastructure de gestion des données de type **Prime de rémunération variable** est désormais disponible pour exportation.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Les adresses britanniques s'affichent sur la page d'analyse de gestion du personnel à l'instar des adresses suisses.

Dans cette version, les adresses sont affichées par ville. Cette version corrige les problèmes où les visualisations représentaient de façon erronée l'emplacement d'un employé.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>L'état Power BI sur la main-d'œuvre affiche une erreur lorsque la date d'ancienneté du collaborateur est un jour intercalaire.

Un correctif a été apporté à Microsoft Power BI pour les dates d'ancienneté qui tombent le 29 février.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>La rémunération fixe des employés, les primes variables des employés, les plans variables des employés (embauches) sont compatibles avec les champs personnalisés.

Les champs personnalisés peuvent désormais être ajoutés à la rémunération fixe des employés, aux primes variables des employés ainsi qu'aux plans variables des employés (embauches). Vous pouvez désormais suivre plus d'informations concernant les plans de rémunération fixe et variable des employés, en sus des informations disponibles par défaut. Les champs personnalisés peuvent être saisis et mis à jour via l'interface utilisateur ou via les entités fournies.

### <a name="other-miscellaneous-bug-fixes"></a>Autres correctifs de bogues divers

Cette version comprend d'autres correctifs de bogues mineurs.

## <a name="coming-soon"></a>Prochainement

### <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)

Nombreuses sont les organisations où les responsables des bénéfices et de la rémunération ne peuvent accéder qu'à des enregistrements spécifiques en termes de rémunération. Ces enregistrements peuvent concerner des cadres ou des employés régionaux. Cette modification permet aux ressources humaines (RH) de gérer et de tenir à jour les plans de rémunération pour différentes populations d'employés au sein de l'organisation. Les rôles de sécurité qui peuvent être attribués à des plans fixes et variables déterminent l'accès à ces plans et les données des employés qui y sont liées (par exemple, les informations sur les salaires et les enregistrements des primes). Seuls les rôles bénéficiant de l'accès spécifié sont en mesure de traiter la rémunération pour ces employés.

### <a name="platform-update-24-for-finance-and-operations"></a>Mise à jour de la plateforme 24 pour Finance and Operations

Pour en savoir plus sur Platform Update 24 pour Microsoft Dynamics 365 Finance and Operations (mars 2019), voir [Fonctionnalités d'aperçu dans Finance and Operations Platform Update 24 (mars 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Mettre à disposition la rémunération fixe des employés pour des futures affectations de poste

Généralement, les employés qui rejoignent une organisation ont un date de début à venir. Cette modification vous permet de définir la rémunération fixe pour les employés ayant des affectations de poste ultérieures.

## <a name="known-issues"></a>Problèmes connus

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>Modifications apportées au modèle d'intégration Core HR (Talent Common Data Service vers Finance)
Le modèle pour Core HR a été mis à jour vers un « modèle de requête avancé ». Par conséquent, par défaut, la requête avancée est disponible pour les projets créés à l'aide de ce modèle. En outre, les fonctions de mise en correspondance par défaut sont visibles uniquement dans l'éditeur de requête avancé. (Les fonctions de mise en correspondance par défaut s'affichent comme « FN » dans les mises en correspondance.)

Pour en savoir plus sur les erreurs de mise en correspondance, voir [Nouveautés ou modifications dans Dynamics 365 Talent: Core HR (14 décembre 2018)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Pour utiliser le nouveau modèle, créez un projet et sélectionnez le nouveau modèle d'intégration Talent.

Pour mettre à jour votre modèle existant, procédez comme suit.

1. Mettez à jour les mises en correspondance suivantes :

    - **Postes d'une mission aux postes :** supprimez cette mise en correspondance.
    - **Attribution des postes d'une mission au poste parent des missions :** supprimez cette mise en correspondance.
    - **Postes d'une mission au poste de base :** ajoutez une nouvelle mise en correspondance depuis l'entité **Postes d'une mission** Common Data Service à l'entité **Poste de base** de Finance and Operations. Déplacez-le au poste 7 dans la séquence.

        [![Mise en correspondance des postes d'une mission avec le poste de base](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Détails des postes d'une mission au poste de base :** ajoutez une nouvelle mise en correspondance depuis l'entité **Détails des postes d'une mission** Common Data Service à l'entité **Poste de base** de Finance and Operations. Déplacez-le au poste 8 dans la séquence.

        [![Mise en correspondance des postes d'une mission avec les détails du poste](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Durées des postes d'une mission au poste de base :** ajoutez une nouvelle mise en correspondance depuis l'entité **Durées des postes d'une mission** Common Data Service à l'entité **Poste de base** de Finance and Operations.

        [![Mise en correspondance des postes d'une mission avec les durées du poste](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Hiérarchies des postes d'une mission au poste de base :** ajoutez une nouvelle mise en correspondance depuis l'entité **Hiérarchies des postes d'une mission** Common Data Service à l'entité **Poste de base** de Finance and Operations. Sélectionnez **Requête avancée** pour rendre la requête avancée disponible pour votre projet.

       [![Bouton de requête avancée](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Ajoutez les mises en correspondance suivantes.
    
    [![Mise en correspondance](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Sélectionnez le lien **Requête et filtrage avancés** en regard du champ **Recherche**.  

    3. Recherchez la colonne **cdm_parentjobpositionid.cdm_jobpositionnumber** et sélectionnez le bouton de la flèche en bas à droite.

    4. Dans la boîte de dialogue qui apparaît, sélectionnez **Supprimer colonne vide**.

    5. Sélectionnez **Ajouter une colonne \> Ajouter une colonne conditionnelle** pour ajouter une transformation de valeur par défaut pour HIERARCHYTYPENAME.

        [![Ajouter une commande de colonne conditionnelle](./media/Add-column.png)](./media/Add-column.png)

    6. Dans la boîte de dialogue **Ajouter une colonne conditionnelle**, saisissez **HIERARCHYTYPENAME** comme nom de nouvelle colonne.
    7. Dans la partie **Si** de la condition, sélectionnez n'importe quel champ, utilisez **égal à** comme relation, puis saisissez n'importe quelle valeur. Dans les parties **Puis** et **Sinon** de la condition, spécifiez la valeur par défaut. Dans ce cas, saisissez **Ligne** dans les deux parties.

        [![Boîte de dialogue Ajouter une colonne conditionnelle](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Sélectionnez **OK** pour fermer la boîte de dialogue **Requête et filtrage avancés**.
    9. Sur la page **Tâche de mise en correspondance**, sélectionnez la nouvelle colonne comme source pour créer une autre mise en correspondance pour HIERARCHYTYPENAME.

        [![Mise en correspondance](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
