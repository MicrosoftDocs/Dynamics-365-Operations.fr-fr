---
title: "Intégrer des fournisseurs"
description: "Cette rubrique décrit le processus d'intégration de nouveaux fournisseurs. Elle explique les actions requises par différents rôles au cours de ce processus."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationRequests,SysUserRequestListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: f831d986d7b534bf030bee0fa0c5dcb97af03289
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2018

---

# <a name="onboard-vendors"></a>Intégrer des fournisseurs
[!include [banner](../includes/banner.md)]

---

De nouveaux fournisseurs peuvent être intégrés et enregistrés comme fournisseurs dans Microsoft Dynamics 365 for Finance and Operations en fonction des informations collectées auprès d'un représentant du fournisseur.

Ce processus comprend les étapes suivantes, où différents rôles exécutent des actions dans le système.

1. **Gestion des données OData** – Importation d'entité - La demande initiale est la demande d'enregistrement du fournisseur potentiel. En général, cette demande émane d'une source telle qu'un site Web hébergé par un client qui autorise l'accès anonyme. Les fournisseurs peuvent s'inscrire en fournissant des informations de base, telles que le nom du fournisseur, la justification, le numéro de l'organisation et le nom et l'adresse e-mail de la personne à contacter. Les demandes sont importées via l'interface de gestion des données.
2. **Page de liste Demande d'enregistrement d'un fournisseur potentiel** - Sur la base des informations fournies dans la demande d'enregistrement du fournisseur potentiel, un professionnel de l'approvisionnement décide si le fournisseur doit être intégré. Le professionnel de l'approvisionnement affiche la demande entrante sur la page de liste **Demandes d'enregistrement d'un fournisseur potentiel** dans Finance and Operations.
3. **Workflow de mise en service de l'utilisateur** - Une fois qu'un professionnel de l'approvisionnement a vérifié les informations dans la demande entrante et décidé de poursuivre le processus d'intégration, le workflow de demande de l'utilisateur met en service le nouvel utilisateur et envoie un e-mail d'invitation pour accepter la personne à contacter en tant qu'utilisateur authentifié de Microsoft Dynamics 365.
4. **Assistant d'enregistrement du fournisseur** - La personne à contacter chez le fournisseur se connecte à Finance and Operations à l'aide du nouveau compte d'utilisateur. Elle exécute l'assistant d'enregistrement du fournisseur pour fournir des informations telles que les adresses, les informations sur l'entreprise, les catégories d'approvisionnement et les réponses au questionnaire.
5. **Workflow d'approbation** - Une demande fournisseur contenant les informations d'enregistrement est créée. Cette demande fournisseur est envoyée à un workflow, puis acheminée pour révision et approbation.
6. **Création des données principales du fournisseur et modification du rôle d'utilisateur** - Lorsque la demande fournisseur est approuvée, un enregistrement fournisseur est créé. Le compte d'utilisateur de la personne à contacter chez le fournisseur est autorisé à accéder à la collaboration fournisseur ou est désactivé.

Le tableau suivant présente les étapes et les rôles impliqués dans le processus.

| Rôle et « processus »       | Gestion des données OData – Importation d'entité | Page de liste Demande d'enregistrement d'un fournisseur potentiel | Workflow de mise en service de l'utilisateur | Assistant d'enregistrement du fournisseur | Workflow d'approbation | Création des données principales du fournisseur et modification du rôle d'utilisateur |
|--------------------------|---|---|---|---|---|---|
| Système                   | La demande d'un nouveau fournisseur est importée. | | | | | Une fois que la demande fournisseur est acceptée, l'enregistrement fournisseur est créé. |
| Professionnel de l'approvisionnement | | Lancez le processus d'intégration. | | | Examinez et acceptez ou rejetez la demande fournisseur. | |
| Administrator            | | | Créez un utilisateur dans Finance and Operations et Microsoft Azure. | | | |
| Personne à contacter chez le fournisseur    | | | Envoyez un e-mail à la personne à contacter. | Enregistrez les informations sur le fournisseur. | | |

Pour une démonstration rapide du processus d'intégration des fournisseurs, consultez cette courte vidéo YouTube : [Intégrer un nouveau fournisseur dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=0KUc3AGaTKk}.

## <a name="importing-the-prospective-vendor-registration-request"></a>Importation de la demande d'enregistrement du fournisseur potentiel

La demande d'enregistrement du fournisseur potentiel est une entité dans Finance and Operations. Vous pouvez paramétrer le système pour importer les données via cette entité. 

Le tableau suivant présente les informations contenues dans cette entité qui peuvent être importées.

| Champ                        | Description |
|------------------------------|-------------|
| Nom du fournisseur                  | Nom du fournisseur. |
| Justification de la demande       | Motif(s) de la demande fournisseur. |
| Numéro d'organisation          | Numéro d'enregistrement officiellement connu. |
| Activité             | Secteur d'activité du fournisseur. |
| Prénom de la personne à contacter.  | Prénom de la personne qui est invitée à enregistrer les informations sur le fournisseur. |
| Autres prénoms de la personne à contacter. | Autres prénoms de la personne qui est invitée à enregistrer les informations sur le fournisseur. |
| Nom de la personne à contacter   | Nom de la personne qui est invitée à enregistrer les informations sur le fournisseur. |
| E-mail de la personne à contacter       | Adresse e-mail utilisée pour créer un utilisateur dans Finance and Operations, qui est enregistrée dans le compte Azure Active Directory (Azure AD) du locataire. |
| Date de soumission               | Date de création de la demande dans un système externe. |
| Entité juridique                 | Entité juridique dans laquelle le fournisseur souhaite devenir un fournisseur. Cette valeur doit être un code d'entité juridique qui a été enregistré dans Finance and Operations. Si aucune valeur n'est reçue via le processus d'importation, une valeur issue des paramètres d'approvisionnement est appliquée. |
| Type de fournisseur                  | Le fournisseur peut être une organisation ou une personne. Le type de fournisseur détermine la manière dont le fournisseur est créé. |

Une fois que la demande d'enregistrement du fournisseur potentiel est importée, elle apparaît sur la page de liste **Demande d'enregistrement d'un fournisseur potentiel**. Dans cette page de liste, un professionnel de l'approvisionnement peut inviter l'utilisateur. Une demande de mise en service de l'utilisateur est envoyée à un workflow.

## <a name="submitting-a-prospective-vendor-user-request"></a>Envoi de la demande d'un utilisateur fournisseur potentiel

La demande d'un utilisateur fournisseur potentiel a pour but de mettre en service la personne qui a envoyé la demande initiale, afin qu'elle puisse se connecter à Finance and Operations à l'aide du compte de messagerie fourni dans la demande d'enregistrement du fournisseur potentiel.

La demande de l'utilisateur fournisseur potentiel est traitée par le workflow de demande de l'utilisateur. Ce workflow communique via la collaboration Azure AD B2B. Il crée un utilisateur dans Finance and Operations avec les paramètres de sécurité appropriés.

Les nouveaux utilisateurs paramétrés ont les rôles de sécurité suivants :

- Utilisateur système externe
- Fournisseur potentiel (externe)

Le nouvel utilisateur reçoit un e-mail généré par le workflow de demande de l'utilisateur. Cet e-mail invite l'utilisateur à se connecter au système.

Pour plus d'informations sur la configuration de l'e-mail et du workflow en général, consultez la description d'un workflow de demande de l'utilisateur dans [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Enregistrement des fournisseurs

Un utilisateur fournisseur potentiel qui se connecte à Finance and Operations verra la première page de l'assistant d'enregistrement du fournisseur, où il peut entrer les informations sur le fournisseur.

L'assistant reflète la configuration de la demande fournisseur. Le pays ou la région où le fournisseur exerce des activités détermine les informations demandées dans l'assistant et les informations obligatoires.

Pour plus d'informations sur la configuration de la demande fournisseur, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md). Le tableau suivant offre une vue d'ensemble des pages de l'assistant et de l'objet de chaque page.

| Page                       | Description |
|----------------------------|-------------|
| Pays/région             | Le pays ou la région détermine la configuration de la demande fournisseur qui est appliquée aux autres pages de l'assistant. Il détermine également les valeurs de la recherche **État de la taxe**. |
| Conditions générales       | Cette page peut être disponible, selon la configuration de la demande fournisseur. Si elle est disponible, l'utilisateur doit accepter les conditions générales pour continuer. |
| Informations fournisseur         | Cette page contient le nom du fournisseur, qui est automatiquement saisi à partir de la demande initiale d'enregistrement du fournisseur potentiel. Elle contient également le numéro de l'organisation, le numéro de téléphone du fournisseur, le numéro de télécopie, l'adresse e-mail et les adresses du fournisseur à différentes fins. |
| Informations sur la personne à contacter | Cette page contient le nom de la personne à contacter, qui est automatiquement saisi à partir de la demande initiale d'enregistrement du fournisseur potentiel. Elle contient également le numéro de téléphone et l'adresse e-mail de la personne à contacter, ainsi que les adresses de la personne à contacter à différentes fins. |
| Informations professionnelles       | Cette page contient les numéros d'identification fiscale (pour différents pays ou régions) et les numéros des employés. Elle indique également si l'entreprise appartient à une minorité. |
| Catégories d'approvisionnement     | Cette page contient les catégories d'approvisionnement pour lesquelles le fournisseur demande une approbation. L'utilisateur peut sélectionner des catégories dans la hiérarchie des catégories d'approvisionnement. Vous pouvez configurer le nombre de niveaux affichés dans la hiérarchie en accédant à &gt; **Paramètres d'approvisionnement** **Collaboration du fournisseur**, sous &gt; **Approvisionnements** **Paramétrage**. |
| Questionnaires             | L'assistant peut inclure un série de questionnaires pour le fournisseur. Les questionnaires qui s'affichent dans l'assistant sont configurés dans la demande fournisseur ou par catégorie d'approvisionnement. Si les questionnaires sont configurés par catégorie d'approvisionnement, les catégories d'approvisionnement pour lesquelles l'utilisateur demande une approbation déterminent les questionnaires qui apparaissent dans l'assistant. Sur la page **Catégories d'approvisionnement**, vous pouvez ajouter un questionnaire sous la catégorie appropriée et définir le type d'activité sur **Intégration du fournisseur**. |

Lorsque l'utilisateur fournisseur potentiel exécute l'assistant d'enregistrement du fournisseur, une demande fournisseur est créée.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Envoi manuel ou automatique d'une demande fournisseur

Une demande fournisseur peut être créée comme brouillon et être envoyée manuellement à un workflow. La demande fournisseur peut également être automatiquement envoyée à un workflow lorsque l'assistant d'enregistrement du fournisseur est exécuté. Une demande peut être envoyée manuellement si, par exemple, un professionnel de l'approvisionnement souhaite évaluer si la demande doit être acheminée via un processus d'approbation avant d'être envoyée au workflow.

- Sélectionnez **Paramètres d'approvisionnement** &gt; **Collaboration du fournisseur**, puis sélectionnez **Envoyer automatiquement l'enregistrement du fournisseur potentiel au workflow** pour configurer la demande fournisseur afin qu'elle soit envoyée automatiquement à un workflow lorsque l'assistant d'enregistrement du fournisseur est exécuté.

## <a name="vendor-requests"></a>Demandes fournisseur

Les demandes fournisseur sont disponibles sur la page **Demandes d'utilisateur de la fonctionnalité Collaboration du fournisseur**.

Une demande fournisseur contient les informations saisies par l'utilisateur fournisseur potentiel dans l'assistant d'enregistrement du fournisseur.

La demande vous permet d'examiner les informations sur le fournisseur et de décider si le fournisseur doit devenir un fournisseur enregistré dans Finance and Operations.

La demande fournisseur doit être envoyée à un workflow, puis acheminée vers les réviseurs et approbateurs appropriés. Pour obtenir des informations de base sur le paramétrage des workflows, voir [Workflows d'approvisionnement](procurement-sourcing-workflows.md).

Le tableau suivant indique les statuts des demandes fournisseur.

| État                     | Description |
|----------------------------|-------------|
| Brouillon                      | La demande fournisseur n'a pas encore été envoyée. |
| Demande soumise          | La demande fournisseur a été envoyée, et la première étape du workflow est en cours de traitement. |
| Révision en attente             | Si une tâche de workflow contient plusieurs réviseurs, un réviseur peut accepter la tâche de révision de la demande fournisseur et procéder à la révision. S'il n'y a qu'un seul réviseur, ce participant peut procéder à la révision en sélectionnant **Terminé** dans l'action de workflow. Il n'est pas nécessaire d'accepter au préalable l'élément de travail. |
| Approbation en attente de la demande   | La demande fournisseur a été acheminée vers les participants pour approbation, et il existe une option de demande d'informations supplémentaires. Une demande d'informations supplémentaires entraîne le réacheminement de l'élément de travail vers l'expéditeur. La demande fournisseur peut également être approuvée ou refusée lorsqu'elle se trouve dans ce statut. |
| Demande de modification de l'application | Des informations supplémentaires ont été demandées par l'approbateur, et la demande fournisseur a été acheminée vers la personne qui a envoyé la demande fournisseur. L'expéditeur peut ajouter les informations requises, puis renvoyer la demande fournisseur. Si une demande fournisseur est renvoyée, le statut passe à **Approbation en attente de la demande**. |
| Demande approuvée           | Ce statut est un état final. |
| Demande rejetée           | Ce statut est un état final. |

## <a name="approving-a-vendor-request"></a>Approbation d'une demande fournisseur

Lorsqu'une demande fournisseur est approuvée, un compte fournisseur est créé et le statut **Approuvé** s'affiche dans la demande initiale d'enregistrement du fournisseur potentiel et dans la demande fournisseur.

Avant d'approuver une demande fournisseur, sur la page **Nouveau fournisseur**, sous l'organisateur **Général**, sélectionnez **Groupe de fournisseurs** pour sélectionner un groupe de fournisseurs.

Si l'utilisateur fournisseur potentiel doit avoir accès à Finance and Operations en tant qu'utilisateur de la collaboration fournisseur qui représente le fournisseur, définissez l'autorisation d'accès à la collaboration fournisseur sur **Oui**. Pour désactiver le compte d'utilisateur utilisé par le fournisseur potentiel pour s'enregistrer, définissez cette autorisation sur **Non**.

Si l'autorisation d'accès à la collaboration fournisseur est définie sur **Oui**, lorsque la demande fournisseur est approuvée, une demande est envoyée pour modifier les rôles de l'utilisateur afin qu'il dispose des rôles définis pour le type **Fournisseur** dans **Rôles externes**. Si cette autorisation est définie sur **Non**, lorsque la demande fournisseur est approuvée, une demande est envoyée pour désactiver l'utilisateur. Dans ce cas, le workflow permettant de désactiver une demande de l'utilisateur doit être paramétré.

Pour créer un compte fournisseur lorsque la demande fournisseur est approuvée, la séquence de numéros permettant de créer des fournisseurs à partir des demandes fournisseur doit être définie sur **Automatique**.

Pour obtenir une vue d'ensemble des autorisations d'accès d'un utilisateur de la collaboration fournisseur, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Rejet d'une demande fournisseur

Si une demande fournisseur est rejetée, un motif de rejet doit être sélectionné dans la demande fournisseur.

Lorsqu'une demande fournisseur est rejetée, une demande est envoyée pour désactiver l'utilisateur. Dans ce cas, le workflow permettant de désactiver une demande de l'utilisateur doit être paramétré. Pour plus d'informations, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md).

Lorsqu'une demande fournisseur est rejetée, le statut **Rejeté** s'affiche dans la demande initiale d'enregistrement du fournisseur potentiel et dans la demande fournisseur.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Suppression de la demande d'enregistrement d'un fournisseur potentiel avec différents statuts

Les différents statuts de la demande d'enregistrement d'un fournisseur potentiel donnent un aperçu de la progression de la demande.

À l'aide de l'action **Supprimer** de la demande d'enregistrement du fournisseur potentiel, vous pouvez nettoyer et supprimer la chaîne d'enregistrements qui ont été créés, et vous pouvez désactiver le compte d'utilisateur. Le résultat de l'action **Supprimer** varie, selon le statut de la demande d'enregistrement du fournisseur potentiel, comme indiqué dans le tableau suivant.


|          État          |                                                                                     Description du statut                                                                                      |                                                                                                                                                            Résultat de l'action Supprimer                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nouveau            |                                                                         Aucune action n'a été effectuée sur la demande.                                                                          |                                                                                                                                              La demande d'enregistrement du fournisseur potentiel est supprimée.                                                                                                                                               |
|      Utilisateur demandé      | Lorsque vous sélectionnez <strong>Inviter l'utilisateur</strong>, le statut devient <strong>Utilisateur demandé</strong>, et une demande de l'utilisateur potentiel est créée et envoyée au workflow de demande de l'utilisateur. |                                                                                                          Vous ne pouvez pas supprimer la demande d'enregistrement d'un fournisseur potentiel ayant ce statut, car le workflow de demande de l'utilisateur n'est pas terminé.                                                                                                          |
|       Utilisateur invité       |                                                               Le workflow de demande de l'utilisateur est approuvé, et l'utilisateur est créé.                                                               |                                                                                                                      Une demande de désactivation de l'utilisateur est créée, et la demande d'enregistrement du fournisseur potentiel est supprimée.                                                                                                                      |
| Enregistrement en cours |                                                         Le nouvel utilisateur s'est connecté et a démarré l'assistant d'enregistrement du fournisseur.                                                          |                                                                                     Une demande de désactivation de l'utilisateur est créée, et la demande d'enregistrement du fournisseur potentiel et les données saisies dans l'assistant d'enregistrement du fournisseur sont supprimées.                                                                                      |
|  Demande fournisseur créée  |                                                                     L'assistant d'enregistrement du fournisseur a été exécuté.                                                                      | Une demande de désactivation de l'utilisateur est créée, et la demande d'enregistrement du fournisseur potentiel, les données saisies dans l'assistant d'enregistrement du fournisseur et la demande fournisseur sont supprimées.<blockquote>[!NOTE]<br>Vous ne pouvez pas utiliser l'action <strong>Supprimer</strong> lorsque la demande fournisseur est en cours de révision dans le workflow.</blockquote> |
|         Approbation         |                                                                               La demande fournisseur est approuvée.                                                                               |                                                                                                   La demande d'enregistrement du fournisseur potentiel, les données saisies dans l'assistant d'enregistrement du fournisseur et la demande fournisseur sont supprimées.                                                                                                    |
|         Rejeté         |                                                                               La demande fournisseur est rejetée.                                                                               |                                                                                                   La demande d'enregistrement du fournisseur potentiel, les données saisies dans l'assistant d'enregistrement du fournisseur et la demande fournisseur sont supprimées.                                                                                                    |


