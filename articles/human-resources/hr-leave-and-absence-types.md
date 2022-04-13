---
title: Configuration des types de congé et d’absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d834b2cd162d361cd913dda14bfacf5efe1dcd3c
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509275"
---
# <a name="configure-leave-and-absence-types"></a>Configuration des types de congé et d’absence

> [!Important]
> La fonctionnalité indiquée dans cette rubrique est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les types de congés dans Dynamics 365 Human Resources définissent les différents types d’absences que les employés peuvent signaler. Vous pouvez adapter les types de congés en fonction des besoins de votre organisation. Voici des exemples de types de congés :

- Congés payés
- Congés non payés
- Congés payés
- Congé maladie
- Congés maladie
- Congés parentaux
- Invalidité à court terme
- Congé de deuil

## <a name="add-a-leave-type"></a>Ajouter un type de congé

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Types de congé et d’absence**.

3. Sélectionnez **Nouveau**.

4. Entrez un nom pour le type de congé sous **Type**, sélectionnez un workflow dans **ID workflow** et entrez une description sous **Description**.

5. Dans **Général**, sélectionnez **Aucun**, **Planifié**, ou **non planifié** dans me menu déroulant **Catégorie**.

6. Sélectionnez un code de rémunération dans le menu déroulant **Code de rémunération**.

7. Sous **Code motif obligatoire**, choisissez si vous souhaitez exiger un code de motif. Si vous souhaitez exiger des codes de motif, vous devrez peut-être les ajouter. Sous **Codes motif**, sélectionnez **Ajouter**, sélectionnez un code de motif, puis cochez la case **Activé** à côté.

8. Sous **Restreindre l’accès aux rôles sélectionnés**, choisissez si vous souhaitez restreindre l’accès. Sélectionnez ensuite les rôles de sécurité sous **Rôles de sécurité pour ce type de congé**. Les rôles de sécurité sont définis dans le workflow que vous avez sélectionné sous **ID workflow** plus tôt dans cette procédure.

9. Sous **Couleur du calendrier**, choisissez la couleur à afficher sur les calendriers de congé et d’absence pour ce type de congé. 

10. En dessous de **Relations de suspension**, choisissez si vous souhaitez que ce type de congé suspende un autre type de congé ou soit suspendu par un autre type de congé. Lorsqu’une demande de congé est soumise pour le type de congé suspendu, une suspension de congé est automatiquement créée pour le type de congé suspendu. 

10. Sélectionnez **Enregistrer**.

## <a name="configure-leave-type-rules"></a>Configurer les règles de type de congé

1. Définissez les options d’arrondi pour le type de congé. Les options incluent **Aucun**, **Haut**, **Bas** et **Le plus proche**. Vous pouvez également définir la précision d’arrondi pour le type de congé.

2. Définissez **Correction des congés** pour le type de congés. Lorsque vous sélectionnez cette option, le nombre de congés qui tombent un jour ouvrable est utilisé pour déterminer comment cumuler des congés pour le type de congé. Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.

   Vous définissez des congés dans le calendrier du temps de travail. Pour plus d’informations, voir [Création d’un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md).
   
 3. Définissez **Report de type de congé** pour le type de congé. Lorsque vous sélectionnez cette option, tous les soldes de report seront transférés vers le type de congé spécifié. Le report de type de congé doit également être inclus dans le plan de congé et d’absence. 
 
4. Définissez **Règles d’expiration** pour le type de congé. Lorsque vous configurez cette option, vous pouvez choisir l’unité jours ou mois et définir la durée de l’expiration. La date d’effet de la règle d’expiration est utilisée pour déterminer quand démarrer l’exécution du traitement par lots qui traite l’expiration du congé, ou la date à laquelle la règle entre en vigueur. L’expiration elle-même se produira toujours à la date de début de la période de régularisation. Par exemple, si la date de début de la période de régularisation est le 3 août 2021 et que la règle d’expiration a été fixée à 6 mois, la règle sera traitée en fonction du décalage de l’expiration par rapport à la date de début de la période de régularisation ; elle sera donc exécutée le 3 février 2022. Tout solde de congé existant au moment de l’expiration sera soustrait du type de congé et sera reflété dans le solde de congé.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Configurer la pièce jointe requise par type de congé

> [!NOTE]
> Pour utiliser le champ **Pièce jointe requise**, vous devez d’abord activer la fonctionnalité **Configurer la pièce jointe requise pour les demandes de congé** dans la Gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

1. Sur la page **Congés et absences**, sur l’onglet **Liens**, sous **Paramétrage**, sélectionnez **Types de congés et d’absences**.

2. Sélectionnez un type de congé et d’absence dans la liste. Ensuite, dans la section **Général**, utilisez le champ **Pièce jointe requise** pour spécifier si une pièce jointe doit être chargée lorsqu’un employé soumet une nouvelle demande de congé pour le type de congé sélectionné. 

Les employés devront charger une pièce jointe lorsqu’ils soumettront une nouvelle demande de congé d’un type où le champ **Pièce jointe requise** est activé. Pour afficher la pièce jointe qui a été chargée dans le cadre d’une demande de congé, les approbateurs de la demande de congé peuvent utiliser l’option **Pièces jointes** pour les éléments de travail qui leur sont affectés. Si une demande de congé est consultée à l’aide de l’application Human Resources dans Microsoft Teams, l’option **Afficher les détails** de la demande de congé peut être utilisée pour afficher ses détails et ses éventuelles pièces jointes.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Configurer les unités de congé (heures/jours) par type de congé

> [!NOTE]
> Pour utiliser la fonctionnalité d’unités de congé par type de congé, vous devez d’abord activer la fonctionnalité **Configurer les unités de congé par type de congé** dans la Gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

> [!IMPORTANT]
> Par défaut, les types de congé d’une entité juridique utilisent les unités de congé de la configuration des paramètres de congé au niveau de l’entité juridique.
> 
> L’unité de congé d’un type de congé et d’absence ne peut être modifiée que s’il n’y a pas de transactions de congé pour ce type de congé.
> 
> La fonctionnalité ne peut pas être désactivée une fois qu’elle a été activée.

1. Sur la page **Congés et absences**, sur l’onglet **Liens**, sous **Paramétrage**, sélectionnez **Types de congés et d’absences**.

2. Sélectionnez un type de congé et d’absence dans la liste. Ensuite, dans la section **Général**, dans le champ **Unité**, sélectionnez l’unité de congé. Vous pouvez sélectionner **Heures** ou **Jours**.

3. Facultatif : si vous avez sélectionné **Heures** dans le champ **Unité**, vous pouvez utiliser le champ **Activer la définition d’une demi-journée** pour spécifier si les employés peuvent sélectionner la première demi-journée ou la deuxième demi-journée de congé s’ils demandent une demi-journée de congé.

Les employés qui soumettent une nouvelle demande de congé peuvent sélectionner différents types de congés pour construire leur demande de congé. Cependant, tous les types de congés sélectionnés dans le cadre d’une seule demande de congé doivent avoir la même unité de congé. Les employés peuvent afficher l’unité de congé pour chaque type de congé dans le formulaire **Demander un congé**.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Créer un plan de congé et d’absence](hr-leave-and-absence-plans.md)
- [Créer un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
- [Suspendre les congés](hr-leave-and-absence-suspend-leave.md)
- [Créer un workflow de demande d’achat et de vente de congés](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
