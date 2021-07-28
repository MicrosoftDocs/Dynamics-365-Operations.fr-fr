---
title: Configurer les paramètres de Human Resources
description: Cette rubrique décrit comment définir les paramètres spécifiques à la société dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 24d30aa06805b530cc069be0517279a11dff9ed4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356534"
---
# <a name="configure-human-resources-parameters"></a>Configurer les paramètres de Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les réglages de certains paramètres des Ressources humaines sont partagés entre des sociétés, alors que les réglages d’autres paramètres sont spécifiques à la société. Cette rubrique décrit comment définir les paramètres Human Resources spécifiques à la société.

Deux pages permettent de définir les paramètres de Human Resources. Pour les paramètres communs à des sociétés, vous utilisez la page **Paramètres partagés de ressources humaines**. Pour les paramètres qui sont spécifiques à une société (en d’autres termes, les paramètres s’appliquent à une seule société), vous utilisez la page **Paramètres de ressources humaines**.

![Accéder aux paramètres de Human resources.](./media/hr-employee-self-service-human-resources-parameters.png)

Sur la page **Paramètres de Ressources humaines**, les paramètres sont répartis sur six onglets :

- **Généralités**
- **Recrutement** (cet onglet n’est pas inclus dans Dynamics 365 Human Resources)
- **Rémunération**
- **Souches de numéros**
- **Congé FMLA**
- **Libre-service employé**
- **Responsable en libre-service**
- **Gestion des avantages**
- **Congé et absence**
- **Modes de paiement**

Chaque onglet contient les informations qui concernent une seule société.

## <a name="general"></a>Généralités

Les paramètres de l’onglet **Général** définissent l’apparence des informations relatives à l’absence, la blessure ou la maladie, et les nouvelles embauches. Les paramètres sous cet onglet définissent également certains entrées par défaut qui s’affichent au fur et à mesure que vous travaillez. Plus précisément, cet onglet vous permet :

- Permet de sélectionner la couleur à appliquer aux transactions d’absence en cours.
- Spécifiez la feuille de style à utiliser pour les rapports.
- Permettre l’intégration entre les formations et l’enregistrement des absences.
- Sélectionnez le code d’absence utilisé pour contrôler cette intégration.
- Indiquez combien de temps il faut conserver les incidents de blessures et de maladies.
- Spécifiez le numéro d’identification par défaut affiché lorsqu’un nouveau travailleur est embauché.
- Spécifiez la date utilisée pour calculer les années de service. 

![Onglet Général.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Recrutement

Les paramètres sur l’onglet **Recrutement** définit les types de documents utilisés pour la correspondance envoyée automatiquement aux candidats. Vous pouvez également indiquer le projet de recrutement utilisé pour les candidatures spontanées.

La période définie pour le projet de recrutement âgé détermine les projets de recrutement inclus dans la vignette **Projets âgés** de l’espace de travail **Gestion des recrutements**. La période définie pour l’avertissement de la date limite de candidature est utilisée pour afficher les projets de recrutement qui approchent leur date limite de candidature dans la vignette **Date limite de candidature qui approche** de l’espace de travail **Recrutement**.

Pour plus d’informations sur le recrutement, consultez [Recruter des candidats](hr-personnel-recruit.md).

## <a name="compensation"></a>Rémunération

Dans Dynamics 365 Finance, les paramètres de l’onglet **Rémunération** définissent si les utilisateurs doivent confirmer qu’ils souhaitent enregistrer des informations pour un régime de rémunération fixe ou variable. Si vous activez **Activer le contrôle de l’enregistrement**, l’utilisateur reçoit un message lui demandant sil souhaite enregistrer l’enregistrement quand il utilise une page associée à la rémunération. Certaine pages de Gestion des rémunérations ne permettent pas aux utilisateurs de supprimer les informations. En invitant les utilisateurs à confirmer qu’ils souhaitent enregistrer les informations, vous pouvez restreindre la quantité d’informations enregistrées sans possibilité de suppression ultérieure. Si vous décochez **Activer le contrôle de l’enregistrement**, les enregistrements sont sauvegardés immédiatement, peut-être avant que l’utilisateur soit prêt. Si vous utilisez la Gestion des performances, l’onglet **Rémunération** vous permet de sélectionner un modèle de classement à utiliser à la place du modèle affecté aux régimes de rémunération lors du classement des performances.

Dans Human Resources, vous pouvez utiliser l’onglet **Rémunération** pour choisir de restreindre l’accès aux plans de rémunération et de définir une devise par défaut.

Pour plus d’informations sur les plans de rémunération, voir [Vue d’ensemble des régimes de rémunération](hr-compensation-overview.md).

![Onglet Rémunération.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Souches de numéros

Les paramètres sur l’onglet **Souche de numéros** détermine les souches utilisées pour attribuer automatiquement des identifiants aux éléments dans les Human Resources, tels que :

- Applications
- Enregistrements d’absences
- Résultats du traitement de la rémunération
- Numéros de cas
- Formations
- Emploi du temps du cours

Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros** (cliquez sur **Administration d’organisation > Souches de numéros > Souches de numéros**).

Pour plus d’informations, voir [Vue d’ensemble des souches de numéros](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> Le nombre d’heures travaillées ne peut pas dépasser 1 250, et la durée de l’emploi ne peut pas dépasser 12 mois. Ces valeurs maximales sont conformes à la législation fédérale des États-Unis.

![Onglet Souches de numéros.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

Dans l’onglet FMLA, vous définissez les conditions d’éligibilité FMLA et les heures de droit FMLA. Pour plus d’informations, voir [Configurer les paramètres de congé et d’absence](hr-leave-and-absence-parameters.md).

![Onglet FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Espace collaborateur

Les paramètres sur l’onglet **Libre-service des employés** affecte la façon dont le libre-service des employés apparaît aux employés. Sur cet onglet, vous pouvez :

- Entrer le nom de l’employé pour l’espace de travail du libre-service pour employés
- Sélectionnez les informations qu’un responsable peut saisir pour les employés
- Ajouter des liens utiles pour les employés
- Empêcher les employés d’ajouter ou de modifier leurs coordonnées professionnelles. Pour plus d’informations, consultez [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md).

Pour plus d’informations sur la configuration du libre-service des employés, voir [Aperçu du libre-service des employés et des gestionnaires](hr-employee-manager-self-service-overview.md).

![Onglet Libre-service employé.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Responsable en libre-service

Les paramètres sur l’onglet **Gestionnaire libre-service** affecte ce que les gestionnaires voient dans le libre-service pour responsables. Sur cet onglet, vous pouvez configurer les options suivantes :

- La plage des enregistrements expirant
- Les gestionnaires de l’information peuvent afficher dans les enregistrements expirant
- Indique si les managers peuvent afficher les postes ouverts pour des rapports étendus
- Vues des collaborateurs sortants
- Liens utiles pour les gestionnaires

Pour plus d’informations sur la configuration du libre-service des responsables, voir [Aperçu du libre-service des employés et des gestionnaires](hr-employee-manager-self-service-overview.md).

![Onglet Responsable en libre-service.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Gestion des avantages

Dans l’onglet Gestion des avantages, vous pouvez configurer les options de messagerie pour la gestion des avantages. Pour plus d’informations sur la configuration et l’utilisation de la gestion des avantages, voir [Présentation de la gestion des avantages](hr-benefits-management-overview.md).

![Onglet Gestion des avantages.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Congé et absence

Pour plus d’informations sur la configuration et l’utilisation des congés et des absences, voir [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Modes de paiement

Sur l’onglet **Méthodes de payement**, vous pouvez sélectionner les modes de paiement pris en charge par votre organisation. Pour plus d’informations sur la configuration de la rémunération, voir [Vue d’ensemble des régimes de rémunération](hr-compensation-overview.md).

![Onglet Modes de paiement.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
