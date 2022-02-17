---
title: Collaborateurs sans emploi
description: Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent sur la page Collaborateurs sans emploi.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070549"
---
# <a name="workers-without-employment"></a>Collaborateurs sans emploi


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent sur la page **Collaborateurs sans emploi**. Les collaborateurs de ce type peuvent apparaître lorsque vous importez des collaborateurs qui n’ont pas de dossier ou lorsque vous supprimez l’emploi d’un collaborateur via **Collaborateur \> Historique des emplois**.

Par défaut, la page **Collaborateurs sans emploi** est disponible pour les postes suivants :

- Assistant des ressources humaines
- Directeur des ressources humaines
- Recruteur
- Gestionnaire de rémunération et avantages sociaux
- Administrateur de paie
- Responsable paie
- Responsable formation

Dans la liste **Collaborateurs sans emploi**, vous pouvez supprimer les individus répertoriés. Par défaut, ce privilège est accordé au poste d’Assistant des ressources humaines. Vous pouvez accorder ce privilège à d’autres postes en procédant comme suit :

1. Sélectionnez **Administration du système**, puis **Configuration de sécurité**.

2. Dans l’onglet **Privilèges**, filtrez la liste **Privilèges** sur **Tenir à jour les collaborateurs**.

   [![Liste des privilèges de filtrage.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. Dans la colonne **Références**, sélectionnez **Options du menu d’affichage**.

4. Dans **Options du menu d’affichage**, sélectionnez **HcmWorkersWithoutEmployment**.

   [![Sélectionner l’écran.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Définissez l’autorisation **Supprimer** sur **Accorder**.

6. Sélectionnez l’onglet **Objets non publiés**.

7. Sélectionnez **Publier tous**.

   [![Publier les modifications.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
