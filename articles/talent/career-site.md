---
title: "Fonctionnalité de site de carrière dans Attract"
description: "Cet article fournit une vue d'ensemble de la fonctionnalité de site de carrière côté candidat dans Microsoft Dynamics 365 for Talent - Attract. Il décrit également la procédure de paramétrage de cette fonctionnalité."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: fr-fr
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>Fonctionnalité de site de carrière dans Attract

[!include [banner](includes/banner.md)]

Cet article fournit une vue d'ensemble de la fonctionnalité de site de carrière côté candidat dans Microsoft Dynamics 365 for Talent : Attract. Il décrit également la procédure de paramétrage de cette fonctionnalité.

## <a name="overview"></a>Vue d'ensemble

Attract fournit un site de carrière pour chaque environnement dans un locataire. Par exemple, si une organisation a un environnement de développement et un environnement de test, un site de carrière est mis en service pour l'environnement de développement, et un autre site de carrière est mis en service pour l'environnement de test. Chaque site de carrière est **complètement isolé** et possède son propre mécanisme d'authentification. Les postes et les profils de candidats ne sont pas partagés entre les sites de carrière.

Par défaut, le site de carrière est public. Par conséquent, les candidats peuvent afficher tous les postes marqués comme étant externes sans avoir à se connecter. Toutefois, toutes les autres actions demandent que les candidats se connectent.

## <a name="career-site-management"></a>Gestion du site de carrière

Les éléments suivants du site de carrière sont contrôlés par des paramètres :

- **Nom de l'organisation :** Le nom de l'organisation s'affiche dans la barre de navigation en haut du site de carrière. Si vous sélectionnez le nom de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.
- **Logo de l'organisation :** Une image du logo de l'organisation s'affiche dans la partie supérieure gauche du site de carrière. Si vous sélectionnez le logo de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.

Pour définir des valeurs pour le nom et le logo de l'organisation, connectez-vous à Attract en tant qu'administrateur, sélectionnez **Centre d'administration** dans le menu **Paramètres** (symbole d'engrenages), puis sélectionnez l'onglet **Informations sur la société**.

> [!NOTE]
> L'image du logo qui s'affiche sur le site de carrière a une hauteur fixe de 20 pixels (px). L'image ajoutée au centre d'administration est mise à l'échelle. Par conséquent, en fonction de l'image, la largeur peut varier.

## <a name="career-site-url"></a>URL du site de carrière

Lorsque vous [publiez un poste externe](./Creating-jobs-Attract.md#postings) pour la première fois, vous pouvez copier le lien **Postuler** dans l'application Attract. L'URL de ce lien est au format suivant : `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

L'URL du site de carrière est une sous-chaîne de l'URL **Postuler**. Elle est composée de tout jusqu'au nom de la société. Par conséquent, pour l'URL **Postuler** précédente, l'URL du site de carrière est `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Options d'authentification

Les candidats disposent des options de connexion suivantes pour un site de carrière Attract :

- Compte personnel :

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Compte professionnel ou scolaire :

    - Microsoft Azure Active Directory (Azure AD)

La connexion Azure AD est prévue uniquement pour les candidats internes. Par conséquent, elle fonctionne uniquement pour les candidats internes qui utilisent leurs informations d'identification Azure AD de société. Par exemple, un candidat actuellement employé par Contoso Ltd souhaite postuler à un poste dans une société indépendante, Alpine Ski House. Dans ce cas, la connexion sera infructueuse si l'employé essaie d'utiliser ses informations d'identification Azure AD de Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Création et tenue à jour d'un profil

Une fois que les candidats se connectent au site de carrière, ils peuvent sélectionner **Mon profil** dans la barre de navigation en haut de la page pour créer et tenir à jour leur profil. Le profil inclut des informations personnelles, des informations sur l'expérience professionnelle, des détails sur leur formation, des documents, des liens, ainsi que des informations sur des ensembles de qualifications. Une fois un profil créé, il peut être utilisé pour postuler à des postes qui intéressent le candidat. Les profils permettent également à Attract de recommander des postes adéquats aux candidats.

## <a name="find-the-right-job"></a>Rechercher le poste adéquat

Sur la page de la liste des postes, les candidats peuvent rechercher un poste spécifique en entrant des conditions de recherche. La fonctionnalité de recherche recherche des conditions de recherche dans les titres et les descriptions de postes, affiche les postes appropriés comme résultats. Les candidats peuvent filtrer les résultats à tout moment, selon l'emplacement du poste ou la fonction.

Les candidats peuvent également afficher un ensemble de postes recommandés sur le site de carrière. Les postes recommandés à un candidat sont basés sur les candidatures précédentes, le profil, et les CV du candidat.

> [!NOTE]
> Les recommandations de postes sont affichées uniquement si au moins 10 postes sont validés sur le site de carrière, et si le candidat a terminé son profil.

## <a name="apply-for-jobs"></a>Soumission d'une candidature à des emplois

Une fois que les candidats trouvent le poste adéquat, ils peuvent postuler à l'aide du bouton **Postuler** sur la page des détails du poste. À ce stade, les candidats peuvent créer un profil tout nouveau ou réviser les informations de leur profil existant. Les candidats peuvent également charger un CV, au besoin, puis soumettre la candidature au poste.

## <a name="check-application-status"></a>Consulter le statut de la candidature

Une fois que les candidats postulent à un ou plusieurs postes, ils peuvent sélectionner **Candidatures** dans la barre de navigation en haut de la page pour afficher leur candidatures en cours et clôturées. Lorsque les candidats ouvrent l'une de leurs candidatures, ils voient le stade actuel et toutes les actions en cours qu'ils doivent compléter. Par exemple, si un candidat doit fournir des dates potentielles pour un entretien en personne, la page lui présente ses options.

## <a name="internal-jobs"></a>Postes internes

Actuellement, les postes marqués comme internes et publiés sur le site de carrière Attract n'apparaissent pas sur le site de carrière. Ils sont accessibles uniquement via l'URL **Postuler** directe qui peut être copiée sur l'application Attract.

