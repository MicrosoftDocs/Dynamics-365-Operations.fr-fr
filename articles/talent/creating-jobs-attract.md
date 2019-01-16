---
title: "Créer, approuver et publier des missions dans Attract"
description: "Cette rubrique décrit les éléments d'une mission dans Attract. Elle décrit également comment créer une mission."
author: josaw
manager: AnnBe
ms.date: 12/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 95031534c43dc0578e258bc3e5376c429d72b0ab
ms.openlocfilehash: 6c5daa4050d63303f1ac10c24901e5b1182cb62b
ms.contentlocale: fr-fr
ms.lasthandoff: 12/23/2018

---

# <a name="create-approve-and-post-jobs-in-attract"></a>Créer, approuver et publier des missions dans Attract

[!include [banner](includes/banner.md)]

Cette rubrique décrit les éléments d'une mission dans Microsoft Dynamics 365 for Talent - Attract. Elle décrit également comment créer une mission.

## <a name="job-creation"></a>Création de missions

Les administrateurs, les recruteurs et les responsables de l'embauche peuvent créer des missions. Lorsque vous créez une mission, vous êtes invité à sélectionner votre rôle dans le processus : responsable de l'embauche ou recruteur. Après avoir sélectionné un rôle, vous êtes invité à sélectionner un modèle de processus. Si vous sélectionnez **Ignorer**, le modèle par défaut est utilisé. Pour plus d'informations sur les modèles de processus, voir [Créer un modèle de processus dans Attract](./process-templates-attract.md).

Une mission dans Attract dispose de détails de mission, d'une équipe de recrutement, d'un processus de recrutement, de publications de mission, et d'analyses.

## <a name="job-details"></a>Détails de la mission

L'onglet **Détails de la mission** contient des détails sur les responsabilités et les attributs de la mission. Les champs de la fonction, de la description de la mission, et de l'emplacement de la mission sont obligatoires. Les autres champs sont facultatifs.

Par défaut, le champ **Nombre de postes à pourvoir** est défini sur **1**. Vous pouvez toutefois modifier la valeur. Lorsqu'une offre a été préparée pour une mission, la valeur du champ **Nombre de postes à pourvoir disponibles** est décrémentée.

Si la gestion des postes a été activée dans le centre d'administration, la recherche **Mettre à jour les postes** est disponible. Cette recherche parcourt l'entité JobPosition dans Common Data Service pour les applications et retourne une liste des postes pouvant être sélectionnés pour la mission. Si le nombre de postes sélectionnés dépasse le nombre de postes à pourvoir, vous recevez un avertissement. Vous recevez également un avertissement si un poste est utilisé sur plusieurs missions.

> [!NOTE]
> La gestion des postes est disponible avec le Composant additionnel de recrutement complet.

En fonction des paramètres de l'activité Offre du processus de recrutement, un numéro de poste peut être utilisé deux fois dans une offre. Pour plus d'informations, voir la rubrique [Processus de recrutement](./activities-attract.md).

Attract comprend un ensemble par défaut de **Qualifications**. Ces qualifications s'affichent sous forme de suggestions à mesure que vous saisissez. Vous pouvez ajouter des qualifications supplémentaires en entrant le nouveau texte de qualification dans le champ et en appuyant sur la touche Entrée.

Attract comprend un ensemble par défaut de **Fonctions de la mission**. Vous pouvez ajouter jusqu'à trois fonctions de mission supplémentaires en entrant la nouvelle fonction de mission dans le champ et en appuyant sur la touche Entrée.

Attract comprend un ensemble par défaut de **Secteur de la société**. Vous pouvez ajouter jusqu'à trois secteurs de société supplémentaires en entrant le nouveau secteur de la société dans le champ et en appuyant sur la touche Entrée.

## <a name="hiring-team"></a>Équipe chargée du recrutement

L'onglet **Équipe chargée du recrutement** contient la liste des personnes qui sont impliquées dans la mission. Lorsque des utilisateurs sont ajoutés à une équipe chargée du recrutement, un rôle dans l'équipe chargée du recrutement doit leur être affecté. Le rôle détermine les données auxquelles les utilisateurs ont accès et les notifications qu'ils reçoivent. Les rôles qui peuvent être sélectionnés sont **Recruteur**, **Responsable de l'embauche**, **Délégué**, et **Intervieweur**. Pour plus d'informations sur les privilèges des rôles, voir le document intitulé « Gestion des rôles ». Les recruteurs et les responsables de l'embauche peuvent nommer un ou plusieurs délégués pour travailler en leur nom. Pour plus d'informations sur les délégués, voir [Gestion de la sécurité et des rôles dans Attract](./security-attract.md).

L'équipe chargée du recrutement peut être mise à jour une fois la mission activée.

## <a name="process"></a>Processus

Les informations par défaut sur le processus de recrutement sont basés sur le modèle de processus sélectionné lors de la création de la mission. Si un modèle spécifique n'a pas été sélectionné à ce stade, le modèle par défaut est utilisé. Lorsque vous définissez le processus de recrutement, vous pouvez ajouter ou supprimer différents stades, sauf les stades Prospect, Candidature et Offre. Bien que le stade Prospect ne puisse pas être supprimé, il peut être désactivé. Dans chaque stade, vous pouvez ajouter ou supprimer une ou plusieurs activités prédéfinies.

Pour plus d'informations sur les activités qui peuvent être ajoutées au processus de recrutement, voir [Activités du processus d'embauche dans Attract](./activities-attract.md).

> [!NOTE]
> Le processus de recrutement ne peut pas être mis à jour une fois une mission activée.

## <a name="postings"></a>Publications

Une fois la mission activée, elle peut être publiée. Seuls les recruteurs et les administrateurs peuvent publier des tâches. La mission peut être publiée dans Carrières Talent (site de carrières de Microsoft Dynamics 365 for Talent) ou LinkedIn. 

> [!NOTE]
> Il existe trois éléments importantes à noter sur le processus de publications de mission dans LinkedIn.
> 1. Les missions publiées dans LinkedIn sont publiées comme des « offres d'emploi limitées ». Les offres d'emploi limitées ne peuvent pas être promues sur le site de LinkedIn. Si vous souhaitez promouvoir les offres d'emploi limitées publiées sur LinkedIn à partir d'Attract, vous devez utiliser LinkedIn pour activer la « diffusion automatique des offres d'emploi ». Consultez les liens ci-dessous et contactez le support technique de LinkedIn pour plus de détails.
>
>    [Offres d'emploi limitées et job slots Premium pour la diffusion automatique des offres d'emploi](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping)
>
>    [FAQ sur la diffusion automatique des offres d'emploi](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions)
>
> 1. Lors de la publication de mission sur LinkedIn, Attract transmet le nom de l'organisation Microsoft 365 à la mission. LinkedIn lie les missions à une société côté LinkedIn selon le nom de l'organisation transmise. Si votre mission est référencée selon la mauvaise société dans LinkedIn, vérifiez que votre nom d'organisation Microsoft 365 correspond à celui de la société sur LinkedIn.  
>
>    [Modifier le contact d'adresse et plus encore](https://docs.microsoft.com/en-us/office365/admin/manage/change-address-contact-and-more)
>
>    Si vous rencontrez des problèmes après cette étape, contactez le support LinkedIn. 
> 
> 1. Les missions publiées sur LinkedIn peuvent prendre jusqu'à 24 heures pour être visibles aux candidats à partir de LinkedIn, en raison du processus actuel de publication par traitement par lots de LinkedIn.

L'équipe Attract travaille continuellement pour créer des partenariats avec des agrégateurs d'offres d'emploi. Cette liste se développera au fil du temps.

Pour plus d'informations sur les publications de postes, voir [Fonctionnalité de site de carrière dans Attract](./career-site.md).

> [!NOTE]
> La fonctionnalité de publication de poste est disponible uniquement le Composant additionnel de recrutement complet pour Attract.

## <a name="activate"></a>Activer

Une fois la mission activée, elle peut être publiée, et des prospects et des candidats peuvent y être ajoutés. L'option pour ajouter des prospects à une mission est définie dans l'activité Prospect du processus de recrutement.

> [!NOTE]
> Le processus de recrutement ne peut pas être mis à jour une fois une mission activée.

## <a name="prospects-and-applicants"></a>Prospects et candidats

L'option pour ajouter des prospects à une mission est définie dans l'[activité Prospect](./activities-attract.md#prospect-activity) du processus de recrutement. Cette option doit être définie avant d'activer la mission. Une fois la mission activée, des prospects et des candidats peuvent y être ajoutés.

## <a name="approvals"></a>Approbations

Les missions Attract peuvent être soumises pour approbation. Toutes les missions ne nécessitent pas d'approbation. Ce besoin est défini au niveau du modèle. Par défaut, les approbations sont désactivées sur le modèle. Pour paramétrer des approbations, accédez à un modèle de processus, puis définissez le champ **Approbation** sur Par défaut. Sélectionnez ensuite ce modèle lorsque vous créez la mission.

Une fois une mission enregistrée, elle peut être soumise pour approbation. Le tableau suivant répertorie les statuts d'un document qui utilise des approbations.

| Statut   | État                                                               |
|----------|---------------------------------------------------------------------|
| Brouillon    | La mission a été enregistrée, mais n'a pas été envoyée au workflow. |
| En attente  | La mission a été soumise aux approbateurs.                            |
| Approuvée | La mission a été approuvée, mais n'a pas été activée.            |
| Rejetée | La mission a été rejetée, et elle ne peut pas être activée.               |
| Active   | La mission a été approuvée et activée.                            |

Dans la liste des postes, vous pouvez filtrer les statuts des missions.

Des approbations peuvent être envoyées à tout utilisateur Microsoft Azure Active Directory (Azure AD) de la société. Les approbations sont envoyées simultanément à toutes les personnes qui sont répertoriées comme approbateurs. Une fois une mission approuvée, elle peut être activée.

Les personnes répertoriées comme approbateurs reçoivent une notification dans Attract pour les informer qu'ils doivent approuver un élément. Un élément d'approbation s'affiche également dans la section **Affecté à vous** sur le tableau de bord. Une fois que quelqu'un accepte ou approuve une mission, l'équipe chargée du recrutement reçoit une notification. Enfin, l'équipe chargée du recrutement reçoit une notification lorsque la mission est approuvée.

## <a name="create-a-job"></a>Créer une mission

Pour créer une mission, procédez comme suit.

1. Accédez à **Postes**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Fonction**, entrez la fonction. Dans le champ **Rôle**, entrez votre rôle.
4. Dans le champ **Modèle**, sélectionnez un modèle. Sinon, sélectionnez **Ignorer**. Si vous sélectionnez **Ignorer**, le modèle marqué comme modèle par défaut est utilisé.

    Si le document doit passer par un processus d'approbation, sélectionnez un modèle dans lequel le champ **Processus d'approbation** est défini sur **Par défaut**.

5. Sous l'onglet **Détails**, entrez les détails de la mission. Les champs **Titre**, **Description de la mission** et **Lieu** sont obligatoires.
6. Sélectionnez **Enregistrer**.
7. Sous l'onglet **Équipe chargée du recrutement**, ajoutez un responsable de l'embauche, un recruteur ou un intervieweur.
8. Sélectionnez **Enregistrer**.
9. Sous l'onglet **Processus**, ajoutez ou supprimez les stades comme vous le voulez :

    - Pour ajouter un stade, sélectionnez **+ Nouveau stade**.
    - Pour supprimer un stade, placez le curseur sur le stade à supprimer, puis sélectionnez le bouton de poubelle qui s'affiche.

        > [!NOTE]
        > Les stades Prospect, Candidature et Offre ne peuvent pas être supprimés.

10. Ajoutez ou supprimez des activités comme vous le voulez :

    - Pour ajouter une activité, faites-la glisser depuis la liste de droite sur le stade approprié. Sinon, double-cliquez sur l'activité, puis sélectionnez le stade auquel l'ajouter.
    - Pour supprimer une activité, développez l'activité, puis sélectionnez le bouton de poubelle dans l'en-tête de l'activité.

11. Sélectionnez **Enregistrer**.
12. Si vous avez choisi d'utiliser un processus d'approbation, procédez comme suit :

    1. Sélectionnez **+ Ajouter un approbateur**, puis entrez un utilisateur disposant d'un compte Azure AD. Vous pouvez ajouter plusieurs approbateurs.
    2. Sélectionnez **Envoyer aux approbateurs**.

    Le champ **Statut de la mission** de la mission est défini sur **En attente**. Une fois que la valeur du champ **Statut de la mission** passe à **Approuvée**, la mission peut être activée.

13. Pour activer la mission, sélectionnez **Activer**.
14. Pour publier la mission, accédez à **Publications**, puis sélectionnez **Publier maintenant** sous le site Carrières Talent ou LinkedIn.

