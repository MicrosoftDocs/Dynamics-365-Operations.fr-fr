---
title: Activités dans les processus
description: Cette rubrique fournit des informations sur les différents types d'activités qui peuvent être utilisés dans le processus de recrutement.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c975b95e4195c795ec4c816b1f3a50461715feea
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/12/2019
ms.locfileid: "989912"
---
# <a name="activities-in-the-hiring-processes"></a>Activités dans les processus de recrutement

[!include[banner](../includes/banner.md)]

Des activités peuvent être ajoutées dans le cadre du processus de recrutement dans Microsoft Dynamics 365 for Talent : Attract. Des activités peuvent être ajoutées à un modèle de processus, ou directement au processus de recrutement de la mission. Lorsqu'une mission est définie, un modèle de processus est sélectionné, et les activités incluses dans le modèle sont appliquées à la mission. Si un modèle n'est pas sélectionné, le modèle par défaut est utilisé. Le processus de recrutement peut également être modifié sur la mission une fois le modèle appliqué.

> [!NOTE] 
> Les modèles de processus sont disponibles avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Activité du prospect

L'activité du prospect contrôle si des prospects peuvent être ajoutés à une mission. Par défaut, des prospects peuvent être ajoutés à une mission. Pour désactiver l'activité du prospect, définissez l'option **Activer les prospects** sur **Désactivé**. Lorsque l'activité du prospect est activée, les responsables du recrutement peuvent ajouter et afficher des prospects, et l'onglet **Prospect** est affiché sur la mission.

## <a name="application-activity"></a>Activité de candidature

L'activité de candidature est requise dans le modèle de processus de recrutement. Pour envoyer un courrier électronique aux candidats lorsqu'ils soumettent leurs candidature ou sont ajoutés à la phase de candidature, définissez l'option **Envoyer l'e-mail au candidat** sur **Activé**.

## <a name="interview-schedule-and-feedback-activity"></a>Planification des entretiens et activité de rétroaction

Cette activité a trois composants : Demande de disponibilité du candidat, programme et commentaire. Utilisez l'activité d'entretien dans le modèle de poste si vous souhaitez inclure la demande de disponibilité du candidat, le programme et les commentaires dans le cadre du processus plutôt que de les utiliser de manière individuelle dans le cadre du processus de recrutement. Pour en savoir plus, consultez la rubrique [Planification et commentaires sur les entretiens](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>Activité PowerApps

L'activité PowerApps vous permet d'intégrer une application Microsoft PowerApps à votre processus de recrutement. L'application peut être nécessaire pour tous les candidats, les candidats internes uniquement, les candidats externes uniquement, ou aucun candidat. Si l'application est marquée comme requise, elle doit être terminée avant que la phase puisse être avancée. Pour être considéré comme terminé, le champ **JobApplicationStatus** doit être défini sur **Terminé**. Ce champ est situé dans l'entité JobApplicationActivity, si bien que l'application PowerApps doit mettre à jour ce champ avant de passer à l'étape suivante. Si l'application n'est pas marquée comme requise, l'activité est une étape facultative, et la phase peut être avancée même si l'application n'est pas terminée.

Pour enregistrer l'activité PowerApps dans le processus de recrutement, vous devez entrer un ID PowerApps. Pour trouver l'ID PowerApps, accédez à [PowerApps](https://web.powerapps.com), sélectionnez **Applications**, puis **Détails**.

Par défaut, l'activité PowerApps est à la disposition du responsable du recrutement, du recruteur et de leurs délégués. Si vous sélectionnez l'option **Autoriser l'ajout de participants à cette activité**, des participants supplémentaires de l'équipe de recrutement peuvent être ajoutés pour une application qui utilise l'activité PowerApps. Par exemple, une organisation a créé une application PowerApps qui est une bibliothèque des questions d'entretien pour des rôles techniques. L'organisation recrute à présent un nouveau développeur logiciel et a ajouté l'activité PowerApps au processus de recrutement pour le rôle de développeur logiciel. Si l'option **Autoriser l'ajout de participants à activité** est activée, un recruteur ou un responsable de l'embauche qui consulte un candidat pour le rôle de développeur logiciel peut ajouter des interviewers à l'activité PowerApps. Ces personnes qui peuvent ensuite afficher l'application comportant les questions d'entretien.

> [!NOTE]
> L'activité PowerApps n'est disponible qu'avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Activité YouTube

L'activité YouTube vous permet de partager une vidéo YouTube dans le cadre de votre processus de recrutement. Pour enregistrer l'activité YouTube dans le processus de recrutement, vous devez spécifier l'URL de la vidéo YouTube. Vous pouvez choisir d'afficher le contenu à l'**Équipe de recrutement**, aux **Candidats internes uniquement**, aux **Candidats externes uniquement**, ou à **Tous les candidats**. Comme pour l'activité PowerApps, vous pouvez autoriser l'ajout de participants de l'équipe de recrutement à l'activité. Si vous choisissez d'afficher le contenu aux candidats, la vidéo ne s'affiche que dans le cadre de l'expérience du candidat et pas dans le processus de recrutement.

> [!NOTE]
> L'activité YouTube n'est disponible qu'avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Activité de contenu web

L'activité de contenu web vous permet d'incorporer du contenu en ligne dans votre processus de recrutement. Pour enregistrer l'activité de contenu web dans le processus de recrutement, vous devez spécifier l'URL du contenu. Vous pouvez choisir d'afficher le contenu à l'**Équipe de recrutement**, aux **Candidats internes uniquement**, aux **Candidats externes uniquement**, ou à **Tous les candidats**. Comme pour les activités PowerApps et YouTube, vous pouvez autoriser l'ajout de participants de l'équipe de recrutement à l'activité. Si vous choisissez d'afficher le contenuaux candidats, le contenu Web ne s'affiche que dans le cadre de l'expérience du candidat et pas dans le processus de recrutement. Vous pouvez choisir la taille du contenu affiché.

> [!NOTE]
> L'activité de contenu web n'est disponible qu'avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Activité Microsoft Forms

L'activité Microsoft Forms vous permet d'intégrer une activité Microsoft Forms à votre processus de recrutement. Microsoft Forms vous permet de créer des jeux-concours, d'études, et des sondages. Pour enregistrer l'activité Microsoft Forms dans le processus de recrutement, vous devez spécifier l'URL de l'écran. Vous pouvez choisir d'afficher le contenu à l'**Équipe de recrutement**, aux **Candidats internes uniquement**, aux **Candidats externes uniquement**, ou à **Tous les candidats**. Comme pour les activités PowerApps, YouTube et de contenu Web, vous pouvez autoriser l'ajout de participants de l'équipe de recrutement à l'activité. Si vous choisissez d'afficher le contenu, aux candidats, l'écran ne s'affiche que dans le cadre de l'expérience du candidat et pas dans le processus de recrutement.

Dans Microsoft Forms, les auteurs peuvent modifier leurs paramètres pour permettre aux utilisateurs extérieurs à leur organisation de répondre à leur étude ou jeu-concours. Dans ce cas, les utilisateurs soumettent leurs réponses de façon anonyme. Si vous souhaitez voir qui a répondu à votre étude ou jeu-concours, vous pouvez demander que les personnes interrogées entrent leur nom dans le cadre de l'étude ou du jeu-concours.

> [!NOTE]
> L'activité Microsoft Forms n'est disponible qu'avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Activité d'offre

Le modèle de processus de recrutement requiert l'activité Offre. Pour utiliser l'application intégrée de gestion des offres, définissez **Lancer l'application Offer Management lors de la préparation de l'offre** sur **Activé**. Si ce paramètre est désactivé, le candidat n'apparaîtra pas dans l'application Offre. Vous devrez donc suivre manuellement l'activité d'offre des candidats. Pour définir si les responsables du recrutement peuvent préparer une offre pour le candidat dans l'application Offre, définissez **Les responsables du recrutement peuvent préparer l'offre** sur **Activé**. Si l'emploi a plusieurs postes associés, vous pouvez décider de préparer plusieurs offres avec le même numéro de poste. Si vous souhaitez n'autoriser qu'une offre par poste et par emploi, définissez **Autoriser les postes à être réutilisés pour l'emploi** sur **Désactivé**.

> [!NOTE]
> L'application intégrée Gestion des offres n'est disponible qu'avec le Composant additionnel de recrutement complet. Pour plus d'informations, voir [Fonctionnalités complémentaires complètes de recrutement dans Attract](./attract-comprehensive-hiring.md).


