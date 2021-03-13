---
title: Recruter des candidats à un poste
description: Cette rubrique montre comment recruter des candidats dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f615584785ba48a140e4e97991a4594047fea8ee
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112445"
---
# <a name="recruit-job-candidates"></a>Recruter des candidats à un poste

[!include [banner](includes/preview-feature.md)]

Dynamics 365 Human Resources vous aide à gérer les demandes de recrutement. Il vous aide également à faire la transition transparente des candidats aux employés. Si votre organisation utilise une application de recrutement distincte, votre processus de recrutement peut inclure les étapes suivantes :

- Saisissez votre demande de recrutement dans Human Resources.
- Recevez des références de candidats dans Human Resources à partir de l'application de recrutement.
- Terminez le processus d'approbation des candidats dans Human Resources.

Si vous n'utilisez pas d'application de recrutement distincte, vous pouvez également gérer manuellement les candidats dans Human Resources.

>[!NOTE]
>Si vous êtes administrateur ou développeur et souhaitez intégrer Human Resources à une application de recrutement tierce, consultez [Configurer l'intégration de Dataverse](hr-admin-integration-common-data-service.md) et [Configurer les tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> Vous pouvez également trouver des applications d'intégration de recrutement sur [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
> Pour essayer notre fonctionnalité d'évaluation pour l'intégration avec LinkedIn Talent Hub, voir [Intégrer avec LinkedIn Talent Hub](hr-admin-integration-linkedin.md).

## <a name="enable-recruiting-requests"></a>Activer les demandes de recrutement

Si vous souhaitez soumettre des demandes de recrutement dans Human Resources, vous devez d'abord activer la fonctionnalité dans **Paramètres partagés de Human Resources**.

1. Dans l'espace de travail **Gestion du personnel**, sélectionnez **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres partagés des ressources humaines**.

3. Sur l'onglet **Recrutement**, sous **RECRUTEMENT**, définissez **Activer les demandes de recrutement** sur **Oui**.

## <a name="add-a-recruiting-request-location"></a>Ajouter un emplacement de demande de recrutement

Si votre organisation possède plusieurs emplacements, vous pouvez les ajouter afin que les demandeurs puissent sélectionner un emplacement où la nouvelle recrue travaillera. L'emplacement sera inclus dans l'offre d'emploi.

1. Dans la barre de recherche, saisissez **emplacement de la demande de recrutement**.

2. Sélectionnez **Nouveau**.

3. Dans le champ **Emplacement de la demande de recrutement**, entrez le nom de l'emplacement.

   ![Ajouter un emplacement de demande de recrutement](./media/hr-recruit-0a-add-location.png)

4. Dans **Description**, entrez une description de l'emplacement.

5. Sous **Emplacement**, sélectionnez **Ajouter**. Si la fenêtre contextuelle **Nouvelle adresse** apparaît, entrez l'adresse de l'emplacement.

   ![Entrer l'adresse](./media/hr-recruit-0b-address.png)

6. Sous **Informations de contact**, entrez les informations du contact du lieu.

7. Sélectionnez **Enregistrer**.

## <a name="add-a-recruiting-request"></a>Ajouter une demande de recrutement

Les managers peuvent soumettre des demandes de recrutement dans Human Resources. Si vous utilisez une application de recrutement distincte, ces étapes enverront une demande de recrutement et lancera le processus de recrutement dans cette candidature. Sinon, suivez cette procédure pour lancer le workflow de votre propre processus de recrutement interne.

1. Sélectionnez **Libre service employé**.

2. Sélectionnez l'onglet **Mon équipe**.

3. Sélectionnez **Demande de recrutement**.

   ![Démarrer une demande de recrutement](./media/hr-recruit-1-request-to-recruit.png)

4. Remplissez les champs **Description**, **Poste** et **Estimation de la date de début**.

   ![Remplissez la demande de recrutement](./media/hr-recruit-2-request-to-recruit.png)

5. Sélectionnez **Continuer**. La demande de recrutement pour votre poste apparaît.

6. Sous **Général**, sélectionnez un recruteur dans la liste déroulante **Recruteur**, puis sélectionnez un emplacement dans le menu déroulant **Emplacement de la demande de recrutement**.

7. Sous **Emploi**, modifiez les informations selon vos besoins, puis sélectionnez **Créer des détails à partir du poste**.

   ![Créer des détails à partir de la tâche](./media/hr-recruit-3-create-details-from-job.png)

   Le reste de la demande de recrutement sera rempli avec les informations par défaut pour l'emploi que vous avez entré.

8. Sous **Description externe**, saisissez une description de poste externe.

9. Sous **Postes**, sélectionnez **Ajouter**, puis sélectionnez un poste pour cette demande de recrutement.

   ![Ajouter un poste](./media/hr-recruit-4-select-position.png)

10. Sous **Compétences**, sélectionnez **Ajouter**, puis sélectionnez une compétence.

11. Sous **Exigences scolaires**, sélectionnez **Ajouter**, puis sélectionnez des valeurs dans les listes déroulantes **Éducation** et **Niveau d'instruction requis**.

   ![Ajouter des exigences scolaires](./media/hr-recruit-5-select-educational-requirements.png)

12. Sous **Commentaire**, ajoutez des commentaires si nécessaire.

13. Sous **Rémunération**, sélectionnez un niveau dans la liste déroulante **Niveau**, puis ajustez **Plancher**, **Point de contrôle**, et **Plafond** le cas échéant.

14. Lorsque votre demande de recrutement est terminée et que vous êtes prêt à démarrer le processus de recrutement, sélectionnez **Activer** dans la barre de menus.

   ![Activer la demande de recrutement](./media/hr-recruit-6-activate-recruit-request.png)

15. Sélectionnez **Enregistrer**.

## <a name="view-and-edit-your-recruiting-requests"></a>Consultez et modifiez vos demandes de recrutement

Si vous êtes un responsable et souhaitez consulter vos propres demandes :

1. Sélectionnez **Libre service employé**.

2. Sélectionnez l'onglet **Mon équipe**.

3. Sous **Informations sur mon équipe**, sélectionnez l'onglet **Demandes de recrutement**.

   ![Sélectionnez l'onglet Demandes de recrutement](./media/hr-recruit-7-recruiting-requests.png)

4. Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.

Si vous êtes un professionnel des RH et que vous souhaitez consulter toutes les demandes de recrutement :

1. Sélectionnez **Gestion du personnel**.

2. Sélectionnez **Demandes de recrutement**.

   ![Afficher les demandes de recrutement dans Gestion du personnel](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.

## <a name="add-or-edit-a-candidate-profile"></a>Ajouter ou modifier un profil de candidat

Si votre organisation s'est intégrée à une autre application pour gérer les demandes de recrutement, les demandes de recrutement sont transmises à cette application. La candidature de recrutement renvoie ensuite les informations du candidat à Human Resources. Sinon, vous pouvez suivre vos propres processus de recrutement internes et saisir manuellement les informations sur le candidat.

1. Sélectionnez **Gestion du personnel**.

2. Sélectionnez **Liens**.

3. Sous **Recrutement**, sélectionnez **Candidats**.

   ![Afficher les candidats](./media/hr-recruit-9-candidates.png)

4. Pour ajouter un candidat, sélectionnez **Nouveau**. Pour modifier un candidat existant, sélectionnez le candidat dans la liste, puis sélectionnez **Modifier**. Le profil du candidat apparaît.

5. Sous **Résumé du candidat**, entrez ou modifiez les informations sur le candidat si nécessaire.

6. Sous **Demande de recrutement**, sélectionnez une demande de recrutement à laquelle associer le candidat. Puis complétez les champs **Estimation de date de début estimée**, **Responsable du recrutement**, **Poste** et **Description** le cas échéant.

   ![Lien vers une demande de recrutement](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Complétez toutes les informations dans les domaines suivants que vous souhaitez inclure dans le dossier du candidat :
   - **Commentaires**
   - **Expérience professionnelle**
   - **Informations sur le contact**
   - **Formation**
   - **Compétences**
   - **Certificats**
   - **Présélections**

8. Sélectionnez **Enregistrer**.

## <a name="hire-a-candidate"></a>Engager un candidat

Lorsque vous êtes prêt à embaucher un candidat, suivez cette procédure pour transformer le candidat en employé.

1. Sur le formulaire de candidature, sélectionnez **Embaucher**.

   ![Engager un candidat](./media/hr-recruit-11-hire.png)

2. Sur le formulaire **Embaucher un nouveau collaborateur**, sous **Détails**, remplissez tous les champs.

   ![Entrez les détails de la nouvelle recrue](./media/hr-recruit-12-hire-new-worker.png)

3. Sous **Détails du poste**, vérifiez et modifiez les informations si nécessaire.

4. Sous **Listes de contrôle de l'intégration**, sélectionnez les listes de contrôle d'intégration pertinentes pour cet employé.

5. Sélectionnez **Continuer** pour créer la fiche de l'employé.

   >[!NOTE]
   >En fonction des workflows de votre organisation, l'enregistrement de candidat peut passer par des étapes d'approbation supplémentaires avant de devenir un enregistrement d'employé.

## <a name="decide-not-to-hire-a-candidate"></a>Décider de ne pas embaucher de candidat

Si vous décidez de ne pas embaucher un candidat, suivez cette procédure pour le retirer du processus de vérification. 

1. Sur le formulaire de candidature, sélectionnez **Ne pas embaucher**.

   ![Ne pas engager un candidat](./media/hr-recruit-13-do-not-hire.png)

2. Sélectionnez un **Code motif** et incluez vos commentaires.

3. Cliquez sur **OK**.

## <a name="dismiss-a-candidate"></a>Ignorer un candidat

Si nécessaire, vous pouvez ignorer un candidat après l'avoir embauché. Par exemple, un candidat peut rejeter votre offre ou ne pas se présenter le premier jour.

- Sur le formulaire de candidature, sélectionnez **Ignorer un candidat**.

  ![Ignorer le candidat](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Voir également :

[Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organisation du personnel](hr-personnel-departments-jobs-positions.md)<br>
[Paramétrer les composants d’une tâche](hr-personnel-jobs.md)
