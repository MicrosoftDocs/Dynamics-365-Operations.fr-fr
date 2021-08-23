---
title: Collaborateurs sans emploi
description: Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent dans le formulaire Collaborateurs sans emploi.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45841c35780960f524cc232dad16f94dbc8ec1c2df75fa2a5c2520e5522d4e3a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724962"
---
# <a name="workers-without-employment"></a>Collaborateurs sans emploi

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les collaborateurs sans emploi futur, actuel ou passé au sein de votre organisation apparaissent dans le formulaire **Collaborateurs sans emploi**. Les collaborateurs ayant ce statut peuvent apparaître lorsque vous importez des collaborateurs sans dossier ou lorsque vous supprimez l’emploi d’un collaborateur via **Collaborateur > Historique des emplois**.

Par défaut, le formulaire **Collaborateurs sans emploi** est disponible pour les postes suivants :

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