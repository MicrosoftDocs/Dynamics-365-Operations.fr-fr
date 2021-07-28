---
title: Saisir les compétences
description: Les collaborateurs et les responsables peuvent saisir des compétences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8a6b36314d9d98f971cd1619dd3604f20a3770b3
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360518"
---
# <a name="enter-skills"></a>Saisir les compétences

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez saisir des compétences cibles ou des compétences réelles pour les collaborateurs, les candidats ou les contacts dans Dynamics 365 Human Resources. Une compétence cible est une compétence que la personne envisage d’acquérir. Une compétence réelle est une compétence qu’une personne possède actuellement.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Créer un flux de travail pour approuver automatiquement les compétences

Pour saisir des compétences sans nécessiter d’approbation, vous devez créer un flux de travail pour approuver automatiquement les compétences.

> [!NOTE]
> Les compétences saisies par les collaborateurs nécessitent toujours l’approbation du responsable. Ce flux de travail n’approuve automatiquement que les compétences saisies par les responsables au nom de leurs collaborateurs.

1. Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**.

2. Sous **Configuration**, sélectionnez **Flux de travail des ressources humaines**.

3. Sélectionnez **Nouveau**.

4. Dans le volet **Créer un flux de travail**, sélectionnez **Compétences du collaborateur**.

   [![Sélectionner le flux de travail des compétences du collaborateur.](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. Dans la boîte de dialogue **Ouvrir ce fichier ?**, sélectionnez **Ouvrir**. Lorsque vous y êtes invité, entrez vos informations d’identification.

6. Dans l’éditeur de flux de travail, sélectionnez l’élément de flux de travail **Approuver les compétences** et faites-le glisser sur le canevas.

   [![Sélectionner l’élément de flux de travail Approuver les compétences.](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Connectez l’élément **Début** à l’élément **Approuver les compétences 1**, puis connectez l’élément **Approuver les compétences 1** à l’élément **Fin**. Vous devrez peut-être faire défiler vers le bas pour voir l’élément **Fin**. Vous pouvez le faire glisser plus près des autres éléments.

   [![Connecter les éléments du flux de travail.](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Double-cliquez sur l’élément de flux de travail **Approuver les compétences 1**, puis cliquez avec le bouton droit sur l’élément **Étape 1**. Cliquez avec le bouton droit sur l’élément **Étape 1**, puis sélectionnez **Propriétés**.

9. Dans la fenêtre **Propriétés**, sélectionnez **Condition** dans la barre de navigation de gauche.

10. Sélectionnez **Exécuter cette étape uniquement si la condition suivante est remplie**.

11. Sélectionnez **Ajouter une condition**. Après **Où**, sélectionnez **Compétences du libre-service des employés**, puis sélectionnez **Compétences du libre-service des employés**. Après **est**, sélectionnez **champ**, puis sélectionnez **Relation utilisateur/personne**.

    [![Spécifier la condition.](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Sélectionnez **Affectation** dans la barre de navigation de gauche.

13. Dans l’onglet **Type d’affectation**, sélectionnez **Hiérarchie**.

14. Dans l’onglet **Sélection de la hiérarchie**, dans le champ **Type de hiérarchie :**, sélectionnez **Hiérarchie managériale**.

    [![Spécifier la hiérarchie managériale.](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Sélectionnez **Fermer**, sélectionnez **Flux de travail** dans la barre de navigation du canevas, puis sélectionnez **Enregistrer et fermer**.

Pour plus d’informations sur la création de flux de travail, consultez [Vue d’ensemble du système de flux de travail](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Saisir les compétences d’un collaborateur

1. Sélectionnez un collaborateur.

2. Dans la barre d’actions de la page **Collaborateur**, sélectionnez **Personne**, puis sélectionnez **Compétences**.

3. Dans la page **Compétences**, complétez les champs suivants pour chaque compétence :

   - **Compétence** : sélectionnez une compétence.
   - **Type de niveau** : sélectionnez **Réel** pour une compétence que le collaborateur possède déjà, ou sélectionnez **Cible** pour une compétence que le collaborateur souhaite acquérir.
   - **Niveau** : sélectionnez un niveau pour la compétence du collaborateur.
   - **Date du niveau** : sélectionnez une date dans l’outil de calendrier.
   - **Examinateur** : le cas échéant, sélectionnez un examinateur dans la liste. Vous pouvez filtrer votre recherche.
   - **Années d’expérience** : entrez les années d’expérience.
   - **Vérifiée** : si la compétence est vérifiée, cochez la case.
   - **Vérifiée par** : entrez le nom du vérificateur.

4. Lorsque vous avez terminé de saisir les compétences, sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

[Configurer les compétences](hr-develop-skills.md)<br>
[Mettre en correspondance les compétences](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]