---
title: Configuration des types de congé et d’absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39e4c4b9c83ca648c21ac20bd20b739af8a6b9ed
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271125"
---
# <a name="configure-leave-and-absence-types"></a>Configuration des types de congé et d’absence

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

2. Définissez **Correction des congés** pour le type de congés. Lorsque vous sélectionnez cette option, Human Resources utilise le nombre de congés qui tombent un jour ouvrable pour déterminer comment cumuler des congés pour le type de congé. Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.

   Vous définissez des congés dans le calendrier du temps de travail. Pour plus d’informations, voir [Création d’un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
   
 3. Définissez **Report de type de congé** pour le type de congé. Lorsque vous sélectionnez cette option, tous les soldes de report seront transférés vers le type de congé spécifié. Le report de type de congé doit également être inclus dans le plan de congé et d’absence. 
 
4. Définissez **Règles d’expiration** pour le type de congé. Lorsque vous configurez cette option, vous pouvez choisir l’unité jours ou mois et définir la durée de l’expiration. La date d’effet de la règle d’expiration est utilisée pour déterminer quand démarrer l’exécution du traitement par lots qui traite l’expiration du congé, ou la date à laquelle la règle entre en vigueur. L’expiration elle-même se produira toujours à la date de début de la période de régularisation. Par exemple, si la date de début de la période de régularisation est le 3 août 2021 et que la règle d’expiration a été fixée à 6 mois, la règle sera traitée en fonction du décalage de l’expiration par rapport à la date de début de la période de régularisation ; elle sera donc exécutée le 3 février 2022. Tout solde de congé existant au moment de l’expiration sera soustrait du type de congé et sera reflété dans le solde de congé.
 
## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Créer un plan de congé et d’absence](hr-leave-and-absence-plans.md)
- [Créer un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
- [Suspendre les congés](hr-leave-and-absence-suspend-leave.md)
- [Créer un workflow de demande d’achat et de vente de congés](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
