---
title: Configurer les informations sur la société dans Microsoft Dynamics 365 Talent - Attract
description: Cette rubrique explique comment configurer des informations sur la société et la marque pour Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
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
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 7013065a9494cb407020de2ebcad4058dd57c6c4
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551593"
---
# <a name="configure-company-information-in-microsoft-dynamics-365-talent---attract"></a>Configurer les informations sur la société dans Microsoft Dynamics 365 Talent - Attract
[!include[banner](../includes/banner.md)]

Le centre d'administrateur dans Microsoft Dynamics 365 Talent: Attract contient des paramètres de configuration, des options d'intégration, et des options de paramétrage pour l'application Attract.

## <a name="company-information"></a>Informations sur la société

Entrez un nom d'affichage pour la société, puis ajoutez un logo de la société. Le nom et le logo d'affichage peuvent ensuite être utilisés dans les offres d'emploi et à l'expérience d'intégration.

## <a name="linkedin-integration"></a>Intégration de LinkedIn

Paramétrage de l'intégration avec LinkedIn Recruiter System Connect(RSC). Une fois connecté à LinkedIn à l'aide de vos informations d'identification LinkedIn, vous pouvez synchroniser le profil LinkedIn, les candidatures, les commentaires d'entretien et les notes de l'équipement de recrutement d'un candidat. Une licence recruteur LinkedIn complète est requise. Pour plus d'informations sur LinkedIn Recruiter, voir [Recruiter System Connect (RSC) – FAQ](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Autorisations utilisateur

Affectation de rôles aux utilisateurs dans votre organisation. Les rôles suivants sont disponibles : **Administrateur**, **Recruteur**, **Responsable de l'embauche**, et **Lecture seule**. Pour plus d'informations sur les autorisations des utilisateurs, voir [Gestion de la sécurité et des rôles dans Attract](./security-attract.md).

## <a name="feature-management"></a>Gestion des fonctionnalités

À mesure que de nouvelles fonctionnalités sont ajoutées, elles peuvent être publiées dans une version préliminaire publique. Les fonctionnalités de version préliminaire publique ne répondent pas toutes aux besoins de service. En les obtenant, vous acceptez de partager vos données avec des systèmes externes. Vous pouvez vous rendre compte que votre organisation n'a pas besoin de toutes les nouvelles fonctionnalités publiées. Vous pouvez activer et désactiver les fonctionnalités de la version préliminaire publique en fonction des besoins de votre organisation.

## <a name="template-management"></a>Gestion des modèles

Un modèle de processus contient toutes les activités qui doivent être incluses dans le cadre du processus de recrutement d'une mission. Votre organisation peut autoriser tous les membres de l'équipe ou uniquement les administrateurs à créer des modèles de processus de recrutement. Pour autoriser des membres de l'équipe à créer leurs propres modèles de processus de recrutement, activez la fonctionnalité Gestion des modèles. Pour plus d'informations sur les modèles de processus, voir [Modèles de processus dans Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Paramètres du modèle d'e-mail

Les organisations peuvent créer des modèles d'e-mails pour différents scénarios. Vous pouvez sélectionner l'image d'en-tête pour l'inclure dans les modèles d'e-mails. L'en-tête sélectionné s'affiche ensuite dans tous les modèles d'e-mails. Dans le modèle de pied de page, vous pouvez ajouter un lien vers la déclaration de confidentialité et les conditions d'utilisation de votre organisation concernant les communications. Pour plus d'informations, voir [Modèles d'e-mails dans Attract](./email-templates.md).

## <a name="offer-process"></a>Processus d'offre

Vous pouvez configurer le processus d'approbation pour les offres d'emploi. Par exemple, vous pouvez spécifier si une offre doit être approuvée avant d'être envoyée à un candidat. Vous pouvez également imposer que les approbateurs laissent un commentaire avec leur décision relative à l'offre.

Deux workflows d'approbation sont disponibles : **Parallèle** et **Séquentiel**.

- **Parallèle** : Les approbations sont envoyées à tous les approbateurs simultanément.
- **Séquentiel** : Les approbations sont envoyées aux approbateurs dans un ordre spécifique.

Vous pouvez également configurer des options relatives à l'expérience du candidat. Par exemple, une option vous permet de spécifier si les candidats peuvent refuser une offre sans discussion supplémentaire. Si vous définissez l'option **Autoriser les candidats à refuser une offre sans discussion supplémentaire** sur **Non**, le bouton **Refuser l'offre** est disponible pour les candidats. Si vous définissez cette option sur **Oui**, les candidats peuvent refuser l'offre en sélectionnant un motif, puis **Refuser l'offre**.

Vous pouvez également définir et appliquer une date d'expiration aux offres. Si vous définissez l'option **Une date d'expiration est obligatoire pour toutes les offres** sur **Oui**, les offres expirent après le nombre d'heures ou de jours spécifiés.

Pour plus d'informations sur la gestion des offres, voir [Paramétrer la gestion des offres](./offer-setup.md).
