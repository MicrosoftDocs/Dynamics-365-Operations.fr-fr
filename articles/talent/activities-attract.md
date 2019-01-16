---
title: "Activités dans les processus"
description: "Cette rubrique fournit des informations sur les différents types d'activités qui peuvent être utilisés dans le processus de recrutement."
author: 
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 4f59193991420fd9ec05a83049e569058bf81932
ms.contentlocale: fr-fr
ms.lasthandoff: 12/07/2018

---

# <a name="activities-in-the-hiring-processes"></a>Activités dans les processus de recrutement

[!include[banner](../includes/banner.md)]

Des activités peuvent être ajoutées dans le cadre du processus de recrutement dans Microsoft Dynamics 365 for Talent : Attract. Des activités peuvent être ajoutées à un modèle de processus, ou directement au processus de recrutement de la mission. Lorsqu'une mission est définie, un modèle de processus est sélectionné, et les activités incluses dans le modèle sont appliquées à la mission. Si un modèle n'est pas sélectionné, le modèle par défaut est utilisé. Le processus de recrutement peut également être modifié sur la mission une fois le modèle appliqué.

> [!NOTE] 
> Les modèles de processus sont disponibles avec le Composant additionnel de recrutement complet.

## <a name="prospect-activity"></a>Activité du prospect

L'activité du prospect contrôle si des prospects peuvent être ajoutés à une mission. Par défaut, des prospects peuvent être ajoutés à une mission. Pour désactiver l'activité du prospect, définissez l'option **Activer les prospects** sur **Désactivé**. Lorsque l'activité du prospect est activée, les responsables du recrutement peuvent ajouter et afficher des prospects, et l'onglet **Prospect** est affiché sur la mission.

## <a name="application-activity"></a>Activité de candidature

L'activité de candidature est requise dans le modèle de processus de recrutement. Pour envoyer un courrier électronique aux candidats lorsqu'ils soumettent leurs candidature ou sont ajoutés à la phase de candidature, définissez l'option **Envoyer l'e-mail au candidat** sur **Activé**.

## <a name="scheduler-activity"></a>Activité de planificateur

L'activité du planificateur est facultative. Cette activité a deux composants : Disponibilité du candidat et programme. Le composant Disponibilité du candidat permet d'utiliser des e-mails pour demander la disponibilité d'un candidat. Le composant Programme permet de programmer des entretiens avec le candidat et l'équipe de recrutement. Dans l'activité du planificateur, les options suivantes peuvent être configurées : **Demander la disponibilité du candidat**, **Réunion en ligne** et **Envoyer un e-mail au candidat**.

- Pour envoyer un e-mail aux candidats pour leur demander leur disponibilité, définissez l'option **Demander la disponibilité du candidat** sur **Activé**. Si vous définissez l'option sur **Désactivé**, cette étape n'est pas affichée dans le processus de recrutement sur la mission.
- Pour diffuser en continu ou faire une conférence téléphonique à l'aide de Skype Entreprise, définissez le champ **Réunion en ligne** sur **Skype Entreprise**. Le lien **Rejoindre la réunion de Skype** correct est alors ajouté à la demande de réunion d'entretien envoyées aux intervieweurs.
- Pour envoyer un e-mail aux candidats pour finaliser le programme, définissez l'option **Envoyer l'e-mail au candidat** sur **Activé**. Si vous définissez l'option sur **Désactivé**, les candidats recevront le programme d'entretien uniquement lorsqu'ils se connecteront au portail du candidat.

## <a name="feedback-activity"></a>Activité de rétroaction

L'activité de rétroaction est facultative. Cette activité permet aux participants à un entretien d'entrer des recommandations pour un candidat. Ils peuvent également entrer leurs commentaires de rétroaction. Si vous activez l'option **Hériter les participants aux commentaires de l'équipe de recrutement**, le recruteur, le responsable de l'embauche, et les intervieweurs sont automatiquement entrés dans l'activité de rétroaction. Les organisations peuvent permettre aux intervieweurs d'afficher les commentaires d'autres personnes avant d'envoyer leurs propres commentaires. Les organisations peuvent également autoriser les intervieweurs à modifier leur commentaire l'avoir envoyé.

## <a name="interview-activity"></a>Activité d'entretien

L'activité d'entretien est facultative. Cette activité a trois composants : Disponibilité du candidat, programme et commentaire. Le composant Disponibilité du candidat permet d'utiliser des e-mails pour demander la disponibilité d'un candidat. Le composant Programme permet de programmer des entretiens avec le candidat et l'équipe de recrutement. Dans l'activité du planificateur, les options suivantes peuvent être configurées : **Demander la disponibilité du candidat**, **Réunion en ligne** et **Envoyer un e-mail au candidat**.

- Pour envoyer un e-mail aux candidats pour leur demander leur disponibilité, définissez l'option **Demander la disponibilité du candidat** sur **Activé**. Si vous définissez l'option sur **Désactivé**, cette étape n'est pas affichée dans le processus de recrutement sur la mission.
- Pour diffuser en continu ou faire une conférence téléphonique à l'aide de Skype Entreprise, définissez le champ **Réunion en ligne** sur **Skype Entreprise**. Le lien **Rejoindre la réunion de Skype** correct est alors ajouté à la demande de réunion d'entretien.
- Pour envoyer un e-mail aux candidats pour finaliser le programme, définissez l'option **Envoyer l'e-mail au candidat** sur **Activé**. Si vous définissez l'option sur **Désactivé**, les candidats recevront le programme d'entretien uniquement lorsqu'ils se connecteront au portail du candidat.

>[!NOTE]
> - Pour tous les entretiens individuels, des rappels sont envoyés aux interviewers toutes les 24 heures si l'interviewer n'a pas répondu (accepté ou refusé) à la demande d'entretien.
> - Pour tous les entretiens collectifs, il n'existe aucun rappel automatisé auquel répondre à une demande d'entretien. Pour déclencher un rappel manuellement, modifiez l'entretien et utilisez l'option **Mettre à jour et envoyer** pour renvoyer la demande aux interviewers.

Le composant de commentaire permet aux personnes d'entrer des recommandations sur un candidat. Ils peuvent également entrer leurs commentaires de rétroaction. Si vous activez l'option **Hériter les participants aux commentaires de l'équipe de recrutement**, le recruteur, le responsable de l'embauche, et les intervieweurs sont automatiquement entrés dans le composant de rétroaction. Les organisations peuvent permettre aux intervieweurs d'afficher les commentaires d'autres personnes avant d'envoyer leurs propres commentaires. Les organisations peuvent également autoriser les intervieweurs à modifier leur commentaire l'avoir envoyé.

## <a name="powerapps-activity"></a>Activité PowerApps

L'activité PowerApps vous permet d'intégrer une application Microsoft PowerApps à votre processus de recrutement. L'application peut être nécessaire pour tous les candidats, les candidats internes uniquement, les candidats externes uniquement, ou aucun candidat. Si l'application est marquée comme requise, elle doit être terminée avant que la phase puisse être avancée. Si l'application n'est pas marquée comme requise, l'activité est une étape facultative, et la phase peut être avancée même si l'application n'est pas terminée.

Pour enregistrer l'activité PowerApps dans le processus de recrutement, vous devez entrer un ID PowerApps. Pour trouver l'ID PowerApps, accédez à [PowerApps](https://web.powerapps.com), sélectionnez **Applications**, puis **Détails**.

Si vous sélectionnez l'option **Autoriser l'ajout de participants à cette activité**, des contributeurs supplémentaires peuvent être ajoutés pour une application qui utilise l'activité PowerApps. Par exemple, une organisation a créé une application PowerApps qui est une bibliothèque des questions d'entretien pour des rôles techniques. L'organisation recrute à présent un nouveau développeur logiciel et a ajouté l'activité PowerApps au processus de recrutement pour le rôle de développeur logiciel. Si l'option **Autoriser l'ajout de participants à activité** est activée, un recruteur ou un responsable de l'embauche qui consulte un candidat pour le rôle de développeur logiciel peut ajouter des personnes à l'activité PowerApps. Ces personnes qui peuvent ensuite afficher l'application comportant les questions d'entretien.

> [!NOTE]
> L'activité PowerApps n'est disponible qu'avec le Composant additionnel de recrutement complet.

## <a name="youtube-activity"></a>Activité YouTube

L'activité YouTube vous permet de partager une vidéo YouTube dans le cadre de votre processus de recrutement. Pour enregistrer l'activité YouTube dans le processus de recrutement, vous devez spécifier l'URL de la vidéo YouTube. Comme pour l'activité PowerApps, vous pouvez autoriser l'ajout de participants à l'activité. Si vous sélectionnez l'option **Afficher uniquement au candidat**, la vidéo est affichée uniquement dans le cadre de l'expérience du candidat. Elle n'est pas affichée dans le processus de recrutement d'Attract.

> [!NOTE]
> L'activité YouTube n'est disponible qu'avec le Composant additionnel de recrutement complet.

## <a name="web-content-activity"></a>Activité de contenu web

L'activité de contenu web vous permet d'incorporer du contenu en ligne dans votre processus de recrutement. Pour enregistrer l'activité de contenu web dans le processus de recrutement, vous devez spécifier l'URL du contenu. Comme pour les activités PowerApps et YouTube, vous pouvez autoriser l'ajout de participants à l'activité. Si vous sélectionnez l'option **Afficher uniquement au candidat**, le contenu est affiché uniquement dans le cadre de l'expérience du candidat. Elle n'est pas affichée dans le processus de recrutement d'Attract. Vous pouvez sélectionner la taille du contenu affiché.

> [!NOTE]
> L'activité de contenu web n'est disponible qu'avec le Composant additionnel de recrutement complet.

## <a name="microsoft-forms-activity"></a>Activité Microsoft Forms

L'activité Microsoft Forms vous permet d'intégrer un écran Microsoft Forms à votre processus de recrutement. Microsoft Forms vous permet de créer des jeux-concours, d'études, et des sondages. Pour enregistrer l'activité Microsoft Forms dans le processus de recrutement, vous devez spécifier l'URL de l'écran. Comme pour les activités PowerApps, YouTube et de contenu web vous pouvez autoriser l'ajout de participants à l'activité. Si vous sélectionnez l'option **Afficher uniquement au candidat**, l'écran est affiché uniquement dans le cadre de l'expérience du candidat. Elle n'est pas affichée dans le processus de recrutement d'Attract.

Dans Microsoft Forms, les auteurs peuvent modifier leurs paramètres pour permettre aux utilisateurs extérieurs à leur organisation de répondre à leur étude ou jeu-concours. Dans ce cas, les utilisateurs soumettent leurs réponses de façon anonyme. Si vous souhaitez voir qui a répondu à votre étude ou jeu-concours, vous pouvez demander que les personnes interrogées entrent leur nom dans le cadre de l'étude ou du jeu-concours.

> [!NOTE]
> L'activité Microsoft Forms n'est disponible qu'avec le Composant additionnel de recrutement complet.

