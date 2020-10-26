---
title: Configuration des types de congé et d'absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e6ca7d04b86232ba48474fcbe288a18995661ae
ms.sourcegitcommit: 6a89816f94c8cdcae6e56fa89843eb99c28b21fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "3969020"
---
# <a name="configure-leave-and-absence-types"></a>Configuration des types de congé et d'absence

Les types de congés dans Dynamics 365 Human Resources définissent les différents types d'absences que les employés peuvent signaler. Vous pouvez adapter les types de congés en fonction des besoins de votre organisation. Voici des exemples de types de congés :

- Congés payés
- Congés non payés
- Congés payés
- Congé maladie
- Congés maladie
- Congés parentaux
- Invalidité à court terme
- Congé de deuil

## <a name="add-a-leave-type"></a>Ajouter un type de congé

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Types de congé et d'absence**.

3. Sélectionnez **Nouveau**.

4. Entrez un nom pour le type de congé sous **Type**, sélectionnez un workflow dans **ID workflow** et entrez une description sous **Description**.

5. Dans **Général**, sélectionnez **Aucun**, **Planifié**, ou **non planifié** dans me menu déroulant **Catégorie**.

6. Sélectionnez un code de rémunération dans le menu déroulant **Code de rémunération**.

7. Sous **Code motif obligatoire**, choisissez si vous souhaitez exiger un code de motif. Si vous souhaitez exiger des codes de motif, vous devrez peut-être les ajouter. Sous **Codes motif**, sélectionnez **Ajouter**, sélectionnez un code de motif, puis cochez la case **Activé** à côté.

8. Sous **Restreindre l'accès aux rôles sélectionnés**, choisissez si vous souhaitez restreindre l'accès. Sélectionnez ensuite les rôles de sécurité sous **Rôles de sécurité pour ce type de congé**. Les rôles de sécurité sont définis dans le workflow que vous avez sélectionné sous **ID workflow**plus tôt dans cette procédure.

9. Sous **Couleur du calendrier**, choisissez la couleur à afficher sur les calendriers de congé et d'absence pour ce type de congé. 

10. En dessous de **Relations de suspension**, choisissez si vous souhaitez que ce type de congé suspende un autre type de congé ou soit suspendu par un autre type de congé. Lorsqu'une demande de congé est soumise pour le type de congé suspendu, une suspension de congé est automatiquement créée pour le type de congé suspendu. 

10. Sélectionnez **Enregistrer**.

## <a name="configure-leave-type-rules"></a>Configurer les règles de type de congé

1. Définissez les options d'arrondi pour le type de congé. Les options incluent **Aucun**, **Haut**, **Bas** et **Le plus proche**. Vous pouvez également définir la précision d'arrondi pour le type de congé.

2. Définissez **Correction des congés** pour le type de congés. Lorsque vous sélectionnez cette option, Human Resources utilise le nombre de congés qui tombent un jour ouvrable pour déterminer comment cumuler des congés pour le type de congé. Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.

   Vous définissez des congés dans le calendrier du temps de travail. Pour plus d'informations, voir [Création d'un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
   
 3. Définissez **Report de type de congé** pour le type de congé. Lorsque vous sélectionnez cette option, tous les soldes de report seront transférés vers le type de congé spécifié. Le report de type de congé doit également être inclus dans le plan de congé et d'absence. 
 
 4. Définissez **Règles d'expiration** pour le type de congé. Lorsque vous configurez cette option, vous pouvez choisir l'unité jours ou mois et définir la durée de l'expiration. Vous pouvez également définir la date d'entrée en vigueur de la règle d'expiration. Tout solde de congé existant au moment de l'expiration sera soustrait du type de congé et sera reflété dans le solde de congé. 
 
 
## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Créer un plan de congé et d'absence](hr-leave-and-absence-plans.md)
- [Créer un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
- [Suspendre les congés](hr-leave-and-absence-suspend-leave.md)

