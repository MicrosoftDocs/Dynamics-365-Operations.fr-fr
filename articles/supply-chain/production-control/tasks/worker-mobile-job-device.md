---
title: Configurer un collaborateur à l’aide du périphérique mobile
description: Cette rubrique explique comment affecter des rôles corrects au compte utilisateur d’un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d’atelier.
author: ShylaThompson
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe4e195763f5329ee7732a2f087094acbad595a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810940"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurer un collaborateur à l’aide du périphérique mobile

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment affecter des rôles corrects au compte utilisateur d’un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d’atelier.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Vérifier qu’un certain rôle est affecté à un collaborateur

Pour cet exemple, vérifiez que le rôle Opérateur est affecté à l’utilisateur « SHANNON » avant de configurer le compte du collaborateur.

1. Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.
2. Recherchez un utilisateur dans le filtre rapide. Pour cet exemple, entrez `shannon`.
3. Sélectionnez le lien dans la colonne **ID utilisateur** du compte d’utilisateur qui s’affiche.
4. Dans l’arborescence **Rôles de l’utilisateur**, sélectionnez **Rôles > Opérateur**.
5. Fermez les pages **détails sur l’utilisateur** et **utilisateurs** pour revenir à la page d’accueil.

## <a name="configure-worker-account"></a>Paramétrer le compte du collaborateur
1. Allez dans **Volet de navigation > Modules > Ressources humaines > Collaborateurs > Collaborateurs**.
2. Recherchez un utilisateur dans le filtre rapide. Pour cet exemple, entrez `shannon`.
3. Sélectionnez le lien dans la colonne **Nom** du compte d’utilisateur qui s’affiche.
4. Sélectionnez l’onglet **Enregistrement du temps**.
5. Sélectionnez **Activer sur les terminaux d’enregistrement**.
6. Entrez ou sélectionnez des valeurs dans les champs suivants :  

    - **Groupe de calcul**  
    - **Groupe de calcul par défaut**  
    - **Groupe d’approbation**  
    - **Profil standard**  
    - **Groupe de profils**  

7. Cliquez sur **OK**.
8. Sélectionnez **Modifier** pour saisir un numéro de badge pour le nouveau collaborateur qualifié pour l’enregistrement des heures. Entrez une valeur dans le champ **ID badge**.
9. Sélectionnez **Enregistrer**.
10. Fermez les pages **Détails du collaborateur** et **Collaborateurs**.

## <a name="assign-worker-to-device-group"></a>Affecter le collaborateur au groupe de périphériques
1. Accédez à **Contrôle de la production > Paramétrage > Contrôle et suivi de la production > Configurer le bon de travail pour les périphériques**.
2. Sélectionnez **Ajouter**.
3. Dans la liste, sélectionnez le collaborateur souhaité. Pour cet exemple, sélectionnez **SHANNON**.
4. Cliquez sur **OK**.
5. Sélectionnez **Modifier**.
6. Dans le champ **Unité de production**, vous pouvez définir le filtre par défaut pour le collaborateur. Cela garantit que seules les tâches de production pour l’unité de production sélectionnée sont affichées lorsque le collaborateur se connecte au périphérique. Entrez la valeur souhaitée.
7. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]