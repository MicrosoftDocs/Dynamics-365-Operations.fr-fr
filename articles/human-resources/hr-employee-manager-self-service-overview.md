---
title: Vue d’ensemble du libre-service pour employés et pour responsables
description: Cet article fournit une vue d’ensemble de l’espace de travail libre-service pour employés et pour responsables.
author: andreabichsel
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 116c85c53b0ec2fe1e1fd2d1fbc2738f5b6351fb
ms.sourcegitcommit: 1fdca917e01470fbd5d3051adb85fd63e8624b47
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4418582"
---
# <a name="employee-and-manager-self-service-overview"></a>Vue d’ensemble du libre-service pour employés et pour responsables

Cet article fournit une vue d’ensemble de l’espace de travail libre-service pour employés et pour responsables.

## <a name="edit-personal-details"></a>Modifier les détails personnels

Si vous devez ajouter ou modifier des informations personnelles, voir [Modifier les informations personnelles](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Utilisateur non affecté à un enregistrement de collaborateur

Si vous n’avez pas associé votre utilisateur à un enregistrement **Collaborateur** dans la page **Utilisateurs**, le message suivant s’affiche :

**Votre ID utilisateur n’est pas associé à votre enregistrement employé dans le système. Vous ne pourrez pas afficher ou mettre à jour vos informations tant qu’il ne le sera pas. Contactez votre responsable ou équipe de support pour obtenir de l’aide.**

Pour associer un utilisateur à un enregistrement **Collaborateur**, accédez à **Utilisateurs** et sélectionnez l’utilisateur. Sélectionnez **Modifier**, ajoutez le collaborateur correspondant dans le champ **Personne** du formulaire et sélectionnez **Enregistrer**. Vous devriez maintenant avoir accès au libre service des employés.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Exigences de sécurité pour le libre service des employés et des gestionnaires

Le libre service des employés et des gestionnaires nécessite deux rôles de sécurité :

- Les employés ont besoin du rôle d’employé.
- Les responsables ont besoin des rôles d’employé et de responsable.

>[!NOTE]
>Vous pouvez également utiliser des rôles personnalisés pour accéder au libre service Employé et Responsable tant qu’ils ont obtenu l’accès aux espaces de travail Employé et Responsable.<br>
>L’accès du gestionnaire aux informations sur les employés est basé sur la hiérarchie de ligne de poste actuelle définie dans Human Resources.

## <a name="employee-self-service"></a>Libre-service employé

L’onglet **Mes informations** affiche les informations suivantes pour le libre-service pour employés.  

### <a name="summary"></a>Synthèse

**Éléments de travail qui m’ont été attribués** affiche toutes les approbations et les éléments de workflow attribués à l’employé. Vous pouvez configurer les éléments de workflow pour envoyer des e-mails à l’utilisateur.

**Questionnaires qui m’ont été attribués** affiche tous les questionnaires planifiés attribués directement à l’employé ou au groupe.

**Annuaire d’entreprises** permet aux employés de rechercher des informations relatives aux individus de l’organisation. Les coordonnées publiques sont accessibles à tous les employés. Le répertoire de l’entreprise est limité à l’entreprise à laquelle l’employé s’est connecté.

**Calendrier d’équipe** affiche les informations de calendrier de votre équipe. Pour plus d’informations, voir [Afficher les calendriers des équipes et des sociétés](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Mes informations de carrière

La section **Mes informations de carrière** du libre-service des employés contient des cartes sur les congés et les absences, la gestion des performances, les compétences, les avantages sociaux, les tâches et les pièces jointes.

La carte **Soldes des congés** affiche les soldes de tous les plans souscrits. Cette carte prévoit votre solde en fonction de votre méthode de régularisation. Vous pouvez saisir et soumettre des demandes de congés, qui passeront ensuite par un processus de workflow d’approbation. Pour plus d’informations sur la gestion des congé et des absences, voir [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md).

La carte **Tâches** affiche les tâches qui vous sont assignées et vous permet de les visualiser et de les gérer.

La carte **Prochain cours enregistré** affiche le prochain cours auquel vous êtes inscrit. Vous pouvez voir et vous inscrire aux cours actifs. Tous les cours, qui sont ouverts à l’inscription, sont définis sur le statut **Commencé** et qui permettent aux employés de s’inscrire automatique, s’affichent sur cette carte. Selon les paramètres de votre organisation, votre inscription à un cours peut passer par un processus d’approbation.

La carte **Certificats** affiche le certificat et la date d’expiration du certificat dont la date d’expiration est la plus proche de la date actuelle. Vous pouvez mettre à jour, ajouter ou supprimer des certificats. Selon les paramètres de votre organisation, les mises à jour de certificat peuvent passer par un processus d’approbation.

La carte **Prochain examen prévu** affiche votre prochaine évaluation des performances. Vous pouvez commencer un nouvel examen à partir de cette carte. Votre responsable ou votre représentant RH peut également lancer des évaluations. Selon les paramètres de votre organisation, vous pouvez également être en mesure d’afficher, de mettre à jour et de soumettre des avis de sortie à partir de cette carte.

Vous pouvez gérer vos objectifs avec la carte **Objectifs de performance**. Cette carte affiche le nombre d’objectifs que vous avez dans chaque statut (**Pas commencé**, **En cours**, et **À améliorer**). Vous pouvez créer, mettre à jour et supprimer des objectifs, selon la sécurité basée sur les rôles qui vous est attribuée. Si vous le souhaitez, vous pouvez ajouter de nouveaux objectifs à partir de groupes ou de modèles. Les responsables et les RH peuvent également créer des objectifs au nom des employés et déterminer dans quelle mesure chaque objectif sera détaillé. Les responsables et les employés peuvent collaborer sur les objectifs et mettre à jour les activités, les mesures et le statut. Vous pouvez également inclure des pièces jointes.

Vous pouvez consulter vos compétences existantes sur la carte **Compétences**. Vous pouvez mettre à jour des compétences, en ajouter de nouvelles ou supprimer celles qui ne sont plus pertinentes. Selon les paramètres de votre organisation, les modifications de vos compétences pourraient passer par un processus d’approbation.

Vous pouvez consulter votre rémunération actuelle via la carte **Rémunération**. Sélectionnez **Afficher** pour voir votre salaire annuel et le montant de votre dernière augmentation. Si vous êtes employé dans plusieurs entreprises, chaque montant annuel s’affiche sur la carte. Pour afficher votre historique de rémunération détaillé, sélectionnez le montant du salaire annuel pour ouvrir le formulaire **Historique des rémunérations fixes et variables**. La future rémunération ne s’affiche pas dans ce formulaire. Si vous avez plusieurs emplois, vous pouvez basculer entre les entreprises dans ce formulaire pour afficher votre historique de rémunération sans vous connecter à chaque entreprise.

Affichez et gérez des documents avec la carte **Pièces jointes**. Vous pouvez gérer toutes les pièces jointes **Externes**. Les RH et les employés peuvent ajouter des pièces jointes via le libre-service des employés ou le formulaire **Collaborateur**. Les pièces jointes sont définies sur **Externe** par défaut.

### <a name="additional-information"></a>Informations supplémentaires

Cette section fournit des liens vers d’autres zones de libre-service pour les employés, similaires à la section **Mes informations de carrière**.

Inscrivez-vous aux avantages via le lien **Avantages**. Pour plus d’informations sur la gestion des avantages, voir [Vue d’ensemble des avantages](hr-benefits-management-overview.md).

Sous **Performance**, vous pouvez sélectionner **Journaux de performances** pour créer des entrées de journal de performance à utiliser à la fois sur les objectifs de performance et les évaluations. Vous pouvez sélectionner **Envoyer des commentaires** pour fournir des commentaires aux autres employés de votre organisation. Selon les paramètres de votre organisation, des e-mails peuvent être envoyés au destinataire, à l’expéditeur et aux responsables. Vous pouvez envoyer des commentaires à tous les employés de l’organisation. L’envoi de commentaires n’est pas limité par l’entreprise.

Sous **Compétences**, vous pouvez apporter des modifications à **Cours**, **Éducation**, **Postes de confiance** et **Expérience professionnelle**. Selon les paramètres de votre organisation, les mises à jour de ces compétences peuvent passer par un processus d’approbation.

Vous pouvez voir les détails du travail sous **Organisation**. Les détails de l’emploi incluent les compétences, les certificats et les domaines de responsabilité de votre poste principal. Vous pouvez également consulter tout équipement prêté. Selon les paramètres de votre organisation, les modifications de l’équipement prêté pourraient passer par un processus d’approbation.

Sous **Questionnaire**, vous pouvez voir les questionnaires remplis. Vous pouvez également voir des questionnaires à l’échelle de l’entreprise qui n’ont pas été remplis. Vous pouvez choisir de remplir un questionnaire à tout moment. L’auteur du questionnaire peut déterminer le délai et pour qui le questionnaire est applicable.

Vous pouvez configurer des liens définis par l’utilisateur dans **Paramètres de Human Resources**. Par exemple, vous pouvez définir des liens vers des relevés de paie, une documentation de fin d’exercice ou des solutions externes. Ces liens s’affichent au bas de cette section, mais vous pouvez les déplacer en utilisant la personnalisation.

Vous pouvez également créer des onglets supplémentaires en intégrant Power Apps dans l’espace de travail libre-service des employés. Utilisez le menu **Paramètres** pour personnaliser la page avec Power Apps. Dans le menu **Paramètres**, vous pouvez choisir d’ajouter une Power App, de compléter les détails et d’insérer l’application. Par défaut, Power Apps apparaît comme le premier onglet de la séquence. Vous pouvez changer l’ordre avec la personnalisation standard.

## <a name="my-team"></a>Mon équipe

L’onglet **Mon équipe** affiche les informations suivantes pour le libre-service des responsables. Seuls les responsables peuvent accéder à l’onglet **Mon équipe**.

### <a name="personnel-actions"></a>Actions liées au personnel

Les actions du personnel s’affichent en fonction des options de configuration dans **Paramètres partagés de Human Resources** et **Paramètres de Human Resources**. Lorsqu’elles sont activées pour les **Collaborateurs**, les actions du personnel permettent de nouvelles options de menu, notamment :

- **Demander un nouvel employé**
- **Demander un nouveau fournisseur**
- **Demander la réaffectation d’un collaborateur**
- **Demander une fin de contrat**
- **Demander une modification de rémunération**

Vous pouvez configurer ces options pour passer par un flux de travail de révision et d’approbation facultatif.

L’activation des **Actions liées aux postes** permet les options suivantes :

- **Demander un nouveau poste**
- **Demander une modification des détails du poste**

Vous pouvez également configurer ces options pour passer par un worfklow d’approbation et une révision facultative.

### <a name="summary"></a>Synthèse

Les informations de la section **Synthèse** dépend des options sélectionnées par Human Resources dans **Paramètres de Human Resources**. Sur l’onglet **Responsable en libre-service** de la page **Paramètres de Human Resources**, vous pouvez configurer les options d’affichage des enregistrements arrivant à expiration et des postes ouverts. L’activation de ces options détermine ce que les responsables peuvent voir dans la section **Synthèse**.

Vous pouvez configurer les vignettes suivantes pour les responsables :

- **Certificats expirant pour mon équipe**
- **Numéros d’identification arrivant à expiration pour mon équipe**
- **Essais arrivant à expiration pour mon équipe**
- **Filtrages arrivant à expiration pour mon équipe**
- **Tests arrivant à expiration pour mon équipe**
- **Postes ouverts aux subordonnés directs et/ou étendus**
- **Demandes de congés en attente pour mon équipe**
- **Évaluation des qualifications de l’équipe**
- **Analyse des écarts de qualifications**
- **Journal des performances de l’équipe**
- **Objectifs de performance de l’équipe**
- **Révisions des performances de l’équipe**
- **Collaborateurs sur le départ**

Vous pouvez configurer les options suivantes pour que les responsables apportent des modifications ou ajoutent des demandes de congé au nom de leurs subordonnés directs :

- Certificats
- Cours
- Articles empruntés
- Compétences
- Demandes de congé et d’absence

### <a name="my-team-information"></a>Mes informations d’équipe

Les informations de mon équipe permettent aux responsables de visualiser et de mettre à jour des subordonnés directs et étendus. Pour accéder aux subordonnés étendus, sélectionnez l’employé qui a des subordonnés, puis choisissez **Voir l’équipe** sur la carte. Toutes les mêmes options s’appliquent aux subordonnés étendus comme aux subordonnés directs. 

#### <a name="summary-tab"></a>Onglet Synthèse

L’onglet **Synthèse** offre une vue rapide de vos subordonnés directs. Si un subordonné direct a également des collaborateurs, la carte affiche le nombre de subordonnés directs dans la section supérieure, ainsi qu’un bouton **Voir l’équipe**. Les options au-dessus de chaque carte s’appliquent à l’employé sélectionné. Par exemple, si vous souhaitez saisir une demande de congé au nom d’un employé, vous sélectionnez l’employé, puis choisissez **Demander un congé** au-dessus des cartes. 

Si vous sélectionnez **Détails** après avoir sélectionné un employé, les options suivantes s’affichent :

- **Certificats**
- **Rémunération**
- **Cours**
- **Révisions**
- **Congés**
- **Articles empruntés**
- **Objectifs de performance**
- **Cours enregistrés**
- **Compétences**
- **Envoyer des commentaires**

Selon les paramètres de votre organisation, vous pouvez soit apporter des modifications ou les afficher uniquement.

#### <a name="position-tab"></a>Onglet Poste

L’onglet **Postes** fournit une vue récapitulative des employés dans leur poste principal. Le nom, la vignette et le département s’affichent dans la zone d’en-tête de chaque carte. Cette carte comprend :

- **Date d’ancienneté** - Affichée à partir de la section récapitulative du collaborateur du formulaire de collaborateur
- **Années de service** - Calculées en fonction de la date de début d’emploi de l’employé
- **Nombre de postes précédents** - En fonction de l’historique des postes, si vous sélectionnez ce numéro, vous ouvrez la vue détaillée de tous les postes précédemment occupés
- **Date de naissance** - Le mois et le jour de la date de naissance de l’employé

Vous pouvez afficher les données de poste pour les subordonnés directs et étendus.

#### <a name="compensation-tab"></a>Onglet Rémunération

L’onglet **Rémunération** affiche le salaire annuel de l’employé. Un identifiant d’entreprise s’affiche sous le montant du salaire. Si un employé a plusieurs emplois et est payé par plusieurs entités juridiques, l’employé aura plusieurs plans de rémunération. Pour voir tous les plans de rémunération des entités juridiques sans changer d'entreprise, vous devez activer la rémunération croisée sous **Human Resources > Paramètres partagés > Accès avancé > Activer la rémunération intersociétés**.

Pour afficher l’historique des rémunérations, sélectionnez le montant du salaire pour ouvrir le formulaire **Détails**. Seuls les enregistrements de rémunération fixes et variables actuels et historiques s’affichent dans le formulaire **Rémunération**. Si un employé a plusieurs emplois, vous pouvez basculer entre les sociétés pour afficher l'historique de rémunération dans chaque société ou activer la rémunération intersociétés dans les paramètres partagés de Human Resources pour afficher tous les plans de rémunération.

Vous pouvez afficher la rémunération pour les subordonnés directs et étendus.

#### <a name="leave-and-absence-tab"></a>Onglet Congé et absence

L’onglet **Congé et absence** affiche les premiers soldes pour les employés qui ont une activité. Pour prendre des mesures ou afficher une liste complète des activités, sélectionnez **Détails**, puis sélectionnez **Congés**. Sur le formulaire **Congés**, vous pouvez afficher les soldes, les demandes, les congés approuvés et les soldes prévisionnels pour aider les employés à mieux gérer leur temps. Selon les paramètres de votre organisation, vous pouvez également demander des congés pour vos subordonnés directs et étendus.

#### <a name="performance-goals-tab"></a>Onglet Objectifs de performance

L’onglet **Objectifs de performance** résume les objectifs de performance par statut. Sélectionnez un nombre pour un statut ou sélectionnez des objectifs de performance dans les **Détails** pour voir tous les objectifs d’un employé. Les responsables et les employés peuvent mettre à jour les objectifs au besoin pendant la durée de l’objectif.

Les responsables peuvent voir tous les objectifs de leur équipe via la vignette **Objectifs de performance de l’équipe** dans la section **Synthèse** de **Mon équipe**.

#### <a name="reviews-tab"></a>Onglet Révisions

L’onglet **Révisions** récapitule les révisions du collaborateur selon chaque état : **En cours**, **Prêt pour la révision** et **Révision finale**. Pour accéder à la révision d’un employé, sélectionnez le bouton **Détails**, puis sélectionnez les révisions sur lesquelles collaborer. En fonction de l’emplacement de la révision dans le processus de workflow, vous pouvez voir si la révision est disponible pour la mise à jour. 

Vous pouvez voir toutes les révisions de votre équipe via la vignette **Révisions des performances de l’équipe** dans la section **Synthèse** de **Mon équipe**.