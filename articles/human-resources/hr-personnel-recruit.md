---
title: Recruter des candidats à un poste
description: Cet article explique comment recruter des candidats dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 743c78d3526db2707630229d4cf21531f9641dd6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879248"
---
# <a name="recruit-job-candidates"></a>Recruter des candidats à un poste


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources vous aide à gérer les demandes de recrutement. Il vous aide également à faire la transition transparente des candidats aux employés. Si votre organisation utilise une application de recrutement distincte, votre processus de recrutement peut inclure les étapes suivantes :<!--note from editor: Should this be a numbered list? These steps do seem to follow a particular order.-->

- Saisissez votre demande de recrutement dans Human Resources.
- Recevez des références de candidats dans Human Resources à partir de l’application de recrutement.
- Terminez le processus d’approbation des candidats dans Human Resources.

Si vous n’utilisez pas d’application de recrutement distincte, vous pouvez également gérer manuellement les candidats dans Human Resources.

> [!NOTE]
> Si vous êtes administrateur ou développeur et souhaitez intégrer Human Resources à une application de recrutement tierce, accédez à [Configurer l’intégration de Dataverse](hr-admin-integration-common-data-service.md) et [Configurer les tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> Vous pouvez également trouver des applications d’intégration de recrutement sur [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
## <a name="enable-recruiting-requests-on-the-merged-infrastructure"></a>Activer les demandes de recrutement sur l’infrastructure fusionnée

Si vous souhaitez soumettre des demandes de recrutement dans le recrutement RH, vous devez d’abord activer les fonctionnalités **Expérience utilisateur RH** et **Gestion du processus de recrutement**.

Une fois les fonctionnalités activées, sélectionnez la fonctionnalité en procédant comme suit : 
1. Accédez à **Ressources humaines** > **Paramétrage** > **Paramètres des ressources humaines**.
2. Dans l’onglet  **Recrutement** , définissez le champ **Recrutement activé** sur **Oui**.
3. Dans la liste déroulante **Expérience de recrutement** , sélectionnez **Recrutement RH**.  
4. Cliquez sur **Enregistrer**. 

> [!Note] 
> Une fois que **Recrutement RH** est sélectionné, **Projets de recrutement** (hérité) ne sera pas disponible. 


## <a name="add-a-recruiting-request-location"></a>Ajouter un emplacement de demande de recrutement

Si votre organisation possède plusieurs emplacements, vous pouvez les ajouter afin que les demandeurs puissent sélectionner un emplacement où la nouvelle recrue travaillera. L’emplacement sera inclus dans l’offre d’emploi.

1. Dans la barre de recherche, saisissez **Emplacement de la demande de recrutement**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Emplacement de la demande de recrutement**, entrez le nom de l’emplacement.

    ![Ajouter un emplacement de demande de recrutement.](./media/hr-recruit-0a-add-location.png)

4. Pour **Description**, entrez une description de l’emplacement.
5. Sous **Emplacement**, sélectionnez **Ajouter**. Si la boîte de dialogue **Nouvelle adresse** apparaît, entrez l’adresse de l’emplacement.<!--note from editor: Please make the address in this image less plausible. Via the fictitious guidelines on CELAweb: For street addresses, you should use sequential numbers, common street names, and incorrect zip codes (e.g., 4567 Main St Buffalo, NY 98052). (See https://microsoft.sharepoint.com/sites/CELAWeb-Copyrights-Trademarks-And-Patents/SitePages/trademarks-fictitious-names.aspx)-->

    ![Entrer l’adresse.](./media/hr-recruit-0b-address.png)

6. Sous **Informations de contact**, entrez les informations du contact du lieu.
7. Sélectionnez **Enregistrer**.

## <a name="add-a-recruiting-request"></a>Ajouter une demande de recrutement

Les managers peuvent soumettre des demandes de recrutement dans Human Resources. Si vous utilisez une application de recrutement distincte, ces étapes enverront une demande de recrutement et lancera le processus de recrutement dans cette candidature. Sinon, suivez cette procédure pour lancer le workflow de votre propre processus de recrutement interne.

1. Sélectionnez **Libre service employé**.
2. Sélectionnez l’onglet **Mon équipe**.
3. Sélectionnez **Demande de recrutement**.

    ![Démarrer une demande de recrutement.](./media/hr-recruit-1-request-to-recruit.png)

4. Remplissez les champs **Description**, **Poste** et **Estimation de la date de début**.

    ![Remplissez la demande de recrutement.](./media/hr-recruit-2-request-to-recruit.png)

5. Sélectionnez **Continuer**. La demande de recrutement pour votre poste apparaît.
6. Sous **Général**, sélectionnez un recruteur dans la liste déroulante **Recruteur**, puis sélectionnez un emplacement dans la liste déroulante **Emplacement de la demande de recrutement**.
7. Sous **Emploi**, modifiez les informations selon vos besoins, puis sélectionnez **Créer des détails à partir du poste**.

    ![Créer des détails à partir de la tâche.](./media/hr-recruit-3-create-details-from-job.png)

    Le reste de la demande de recrutement sera rempli avec les informations par défaut pour l’emploi que vous avez entré.

8. Sous **Description externe**, saisissez une description de poste externe.
9. Sous **Postes**, sélectionnez **Ajouter**, puis sélectionnez un poste pour cette demande de recrutement.<!--note from editor: In all of these images, are they approved fictitious names, or do they come from sample data included with the app?-->

    ![Ajouter un poste.](./media/hr-recruit-4-select-position.png)

10. Sous **Compétences**, sélectionnez **Ajouter**, puis sélectionnez une compétence.
11. Sous **Exigences scolaires**, sélectionnez **Ajouter**, puis sélectionnez des valeurs dans les listes déroulantes **Éducation** et **Niveau d’instruction requis**.

    ![Ajouter des exigences scolaires.](./media/hr-recruit-5-select-educational-requirements.png)

12. Sous **Commentaire**, ajoutez des commentaires si nécessaire.
13. Sous **Rémunération**, sélectionnez un niveau dans la liste déroulante **Niveau**, puis ajustez **Plancher**, **Point de contrôle**, et **Plafond** le cas échéant.
14. Lorsque votre demande de recrutement est terminée et que vous êtes prêt à démarrer le processus de recrutement, sélectionnez **Activer** dans la barre de menus.

    ![Activer la demande de recrutement.](./media/hr-recruit-6-activate-recruit-request.png)

15. Sélectionnez **Enregistrer**.

## <a name="view-and-edit-your-recruiting-requests"></a>Consultez et modifiez vos demandes de recrutement

Si vous êtes un responsable et souhaitez consulter vos propres demandes :

1. Sélectionnez **Libre service employé**.
2. Sélectionnez l’onglet **Mon équipe**.
3. Sous **Informations sur mon équipe**, sélectionnez l’onglet **Demandes de recrutement**.

    ![Sélectionnez l’onglet Demandes de recrutement.](./media/hr-recruit-7-recruiting-requests.png)

4. Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.

Si vous êtes un professionnel des RH et que vous souhaitez consulter toutes les demandes de recrutement :

1. Sélectionnez **Gestion du personnel**.
2. Sélectionnez **Demandes de recrutement**.

    ![Afficher les demandes de recrutement dans Gestion du personnel.](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Pour afficher ou modifier une demande de recrutement, sélectionnez-la dans la grille.

## <a name="add-or-edit-a-candidate-profile"></a>Ajouter ou modifier un profil de candidat

Si votre organisation s’est intégrée à une autre application pour gérer les demandes de recrutement, les demandes de recrutement sont transmises à cette application. La candidature de recrutement renvoie ensuite les informations du candidat à Human Resources. Sinon, vous pouvez suivre vos propres processus de recrutement internes et saisir manuellement les informations sur le candidat.

1. Sélectionnez **Gestion du personnel**.
2. Sélectionnez **Liens**.
3. Sous **Recrutement**, sélectionnez **Candidats**.

    ![Afficher les candidats.](./media/hr-recruit-9-candidates.png)

4. Pour ajouter un candidat, sélectionnez **Nouveau**. Pour modifier un candidat existant, sélectionnez le candidat dans la liste, puis sélectionnez **Modifier**. Le profil du candidat apparaît.
5. Sous **Résumé du candidat**, entrez ou modifiez les informations sur le candidat si nécessaire.
6. Sous **Demande de recrutement**, sélectionnez une demande de recrutement à laquelle associer le candidat. Puis complétez les champs **Estimation de date de début estimée**, **Responsable du recrutement**, **Poste** et **Description** le cas échéant.

    ![Lien vers une demande de recrutement.](./media/hr-recruit-10-link-to-recruiting-request.png)

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

1. Sur la page **Candidat**, sélectionnez **Embaucher**.

    ![Engager un candidat.](./media/hr-recruit-11-hire.png)

2. Sur la page **Embaucher un nouveau collaborateur**, sous **Détails**, remplissez tous les champs.

    ![Entrez les détails de la nouvelle recrue.](./media/hr-recruit-12-hire-new-worker.png)

3. Sous **Détails du poste**, vérifiez et modifiez les informations si nécessaire.
4. Sous **Listes de contrôle de l’intégration**, sélectionnez les listes de contrôle d’intégration pertinentes pour cet employé.
5. Sélectionnez **Continuer** pour créer la fiche de l’employé.

    > [!NOTE]
    > En fonction des workflows de votre organisation, l’enregistrement de candidat peut passer par des étapes d’approbation supplémentaires avant de devenir un enregistrement d’employé.

## <a name="decide-not-to-hire-a-candidate"></a>Décider de ne pas embaucher de candidat

Si vous décidez de ne pas embaucher un candidat, suivez cette procédure pour le retirer du processus de vérification. 

1. Sur la page **Candidat**, sélectionnez **Ne pas embaucher**.

    ![Ne pas engager un candidat.](./media/hr-recruit-13-do-not-hire.png)

2. Sélectionnez un **Code motif** et incluez vos commentaires.
3. Cliquez sur **OK**.

## <a name="dismiss-a-candidate"></a>Ignorer un candidat

Si nécessaire, vous pouvez ignorer un candidat après l’avoir embauché. Par exemple, un candidat peut rejeter votre offre ou ne pas se présenter le premier jour.

- Sur la page **Candidat**, sélectionnez **Ignorer un candidat**.

    ![Ignorer le candidat.](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Voir également :

[Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organisation du personnel](hr-personnel-departments-jobs-positions.md)<br>
[Paramétrer les composants d’une tâche](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
