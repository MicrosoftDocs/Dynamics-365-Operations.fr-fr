---
title: Créer un poste dans Attract
description: Cette rubrique décrit les éléments d'une mission dans Attract. Elle décrit également comment créer une mission.
author: hasrivas
manager: AnnBe
ms.date: 07/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9dcdbcea995285c879f91c0bff435103865cc10f
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124748"
---
# <a name="create-a-job-in-attract"></a>Créer un poste dans Attract

[!include [banner](includes/banner.md)]

Cette rubrique décrit les éléments d'une mission dans Microsoft Dynamics 365 Talent: Attract. Elle décrit également comment créer une mission.

## <a name="job-creation"></a>Création de tâches

Les administrateurs, les recruteurs et les responsables de l'embauche peuvent créer des missions. Lorsque vous créez une mission, vous êtes invité à sélectionner votre rôle dans le processus : responsable de l'embauche ou recruteur. Après avoir sélectionné un rôle, vous êtes invité à sélectionner un modèle de processus. Si vous sélectionnez **Ignorer**, le modèle par défaut est utilisé. Pour plus d'informations sur les modèles de processus, voir [Créer un modèle de processus dans Attract](./process-templates-attract.md).

Une mission dans Attract dispose de détails de mission, d'une équipe de recrutement, d'un processus de recrutement, de publications de mission, et d'analyses.

## <a name="job-details"></a>Détails de la mission

L'onglet **Détails de la mission** contient des détails sur les responsabilités et les attributs de la mission. Les champs de la fonction, de la description de la mission, et de l'emplacement de la mission sont obligatoires. Les autres champs sont facultatifs.

Par défaut, le champ **Nombre de postes à pourvoir** est défini sur **1**. Vous pouvez toutefois modifier la valeur. Lorsqu'une offre a été préparée pour une mission, la valeur du champ **Nombre de postes à pourvoir disponibles** est décrémentée.

Si la gestion des postes a été activée dans le centre d'administration, la recherche **Mettre à jour les postes** est disponible. Cette recherche parcourt l'entité JobPosition dans Common Data Service et retourne une liste des postes pouvant être sélectionnés pour la mission. Si le nombre de postes sélectionnés dépasse le nombre de postes à pourvoir, vous recevez un avertissement. Vous recevez également un avertissement si un poste est utilisé sur plusieurs missions.

> [!NOTE]
> La gestion des postes est disponible avec le Composant additionnel de recrutement complet.

En fonction des paramètres de l'activité Offre du processus de recrutement, un numéro de poste peut être utilisé deux fois dans une offre. Pour plus d'informations, voir [Activités des processus de recrutement](./activities-attract.md).

Attract comprend un ensemble par défaut de **Qualifications**. Ces qualifications s'affichent sous forme de suggestions à mesure que vous saisissez. Vous pouvez ajouter des qualifications supplémentaires en entrant le nouveau texte de qualification dans le champ et en appuyant sur la touche Entrée.

Attract comprend un ensemble par défaut de **Fonctions de la mission**. Vous pouvez ajouter jusqu'à trois fonctions de mission supplémentaires en entrant la nouvelle fonction de mission dans le champ et en appuyant sur la touche Entrée.

Attract comprend un ensemble par défaut de **Secteur de la société**. Vous pouvez ajouter jusqu'à trois secteurs de société supplémentaires en entrant le nouveau secteur de la société dans le champ et en appuyant sur la touche Entrée.

## <a name="hiring-team"></a>Équipe chargée du recrutement

L'onglet **Équipe chargée du recrutement** contient la liste des personnes qui sont impliquées dans la mission. Lorsque des utilisateurs sont ajoutés à une équipe chargée du recrutement, un rôle dans l'équipe chargée du recrutement doit leur être affecté. Le rôle détermine les données auxquelles les utilisateurs ont accès et les notifications qu'ils reçoivent. Les rôles qui peuvent être sélectionnés sont **Recruteur**, **Responsable de l'embauche**, **Délégué**, et **Intervieweur**. Pour plus d'informations sur les privilèges des rôles, voir le document intitulé « Gestion des rôles ». Les recruteurs et les responsables de l'embauche peuvent nommer un ou plusieurs délégués pour travailler en leur nom. Pour plus d'informations sur les délégués, voir [Gestion de la sécurité et des rôles dans Attract](./security-attract.md).

L'équipe chargée du recrutement peut être mise à jour une fois la mission activée.

## <a name="process"></a>Processus

Les informations par défaut sur le processus de recrutement sont basés sur le modèle de processus sélectionné lors de la création de la mission. Si un modèle spécifique n'a pas été sélectionné à ce stade, le modèle par défaut est utilisé. Lorsque vous définissez le processus de recrutement, vous pouvez ajouter ou supprimer différents stades, sauf les stades Prospect, Candidature et Offre. Bien que le stade Prospect ne puisse pas être supprimé, il peut être désactivé. Dans chaque stade, vous pouvez ajouter ou supprimer une ou plusieurs activités prédéfinies.

Pour plus d'informations sur les activités qui peuvent être ajoutées au processus de recrutement, voir [Activités du processus de recrutement](./activities-attract.md).

> [!NOTE]
> Le processus de recrutement ne peut pas être mis à jour une fois une mission activée.

## <a name="postings"></a>Publications

Une fois la mission activée, elle peut être publiée. Seuls les recruteurs et les administrateurs peuvent publier des tâches. La mission peut être publiée dans Carrières Talent (site de carrières Dynamics 365 Talent) ou LinkedIn. L'équipe Attract travaille continuellement pour créer des partenariats avec des agrégateurs d'offres d'emploi. Cette liste se développera au fil du temps. Lorsqu'une offre d'emploi est publiée en interne seulement, les candidats ont besoin d'un compte AAD pour afficher l'offre et y postuler. Si l'offre est répertoriée comme publique, les candidats peuvent l'afficher et y postuler en utilisant toutes les options d'authentification. 

Pour plus d'informations sur les publications de postes, voir [Configurer votre site de carrière dans Microsoft Dynamics 365 Talent - Attract](career-site.md).

> [!NOTE]
> La fonctionnalité de publication de poste est disponible uniquement le Composant additionnel de recrutement complet pour Attract.

## <a name="activate"></a>Activer

Une fois la mission activée, elle peut être publiée, et des prospects et des candidats peuvent y être ajoutés. L'option pour ajouter des prospects à une mission est définie dans l'activité Prospect du processus de recrutement.

> [!NOTE]
> Le processus de recrutement ne peut pas être mis à jour une fois une mission activée.

## <a name="prospects-and-applicants"></a>Prospects et candidats

L'option pour ajouter des prospects à une mission est définie dans [Activités du processus de recrutement](./activities-attract.md#prospect-activity) du processus de recrutement. Cette option doit être définie avant d'activer la mission. Une fois la mission activée, des prospects et des candidats peuvent y être ajoutés.

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

Les approbations peuvent être envoyées à tous les utilisateurs de Microsoft Azure Active Directory (Azure AD) de la société. Les approbations sont envoyées simultanément à toutes les personnes qui sont répertoriées comme approbateurs. Tous les approbateurs doivent approuver l'offre avant qu'elle puisse passer à l'étape suivante. Si un seul approbateur rejette l'offre d'emploi, elle affiche l'état **Rejeté**. Une fois une mission approuvée, elle peut être activée.

Si un utilisateur modifie l'offre d'emploi après qu'elle a été approuvée, mais pas activée, le statut de l'offre est redéfini sur **Brouillon**, puis l'offre doit être à nouveau soumise à l'approbation. Une fois l'offre d'emploi approuvée activée, vous ne pouvez pas la modifier.

Les personnes répertoriées comme approbateurs reçoivent une notification dans Attract et un e-mail pour les informer qu'elles doivent approuver un élément.  Dans l'e-mail, les approbateurs peuvent cliquer sur le lien pour ouvrir l'offre d'emploi, en examiner les détails, puis l'approuver ou la rejeter. Une fois le statut de la tâche défini sur **Approuvé** ou **Rejeté**, le soumettant en est informé dans Attract et reçoit un e-mail. En outre, les approbateurs reçoivent un e-mail de rappel s'ils n'ont pas répondu à la demande d'approbation dans les 24 heures.

> [!NOTE]
> Vous pouvez créer des modèles d'e-mail personnalisés pour les e-mails d'approbation. Pour plus d'informations, voir [Création et gestion des modèles d'e-mail](https://docs.microsoft.com/dynamics365/unified-operations/talent/email-templates).

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
