---
title: "Accéder aux fonctionnalités d'aperçu dans Dynamics 365 for Talent"
description: "Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement activées pour le mode aperçu."
author: rschloma
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2e5dd8f852ac1a6c2997a50a60f03db6adfd218c
ms.openlocfilehash: 5500bfc1cdd1949d301ae82fad5506dfdbeb59f3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/01/2018

---

# <a name="access-preview-features-in-dynamics-365-for-talent"></a>Accéder aux fonctionnalités d'aperçu dans Dynamics 365 for Talent 

[!include[banner](../includes/banner.md)]

Dans le cadre de notre lancement continu de fonctionnalités du produit, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible. Les administrateurs peuvent afficher et utiliser les fonctionnalités d'aperçu dans leurs environnements. Ces fonctionnalités sont presque prêtes pour la mise à disposition générale et ont fait l'objet de tests étendus. Nous attendons les derniers commentaires et validations des clients avant leur mise à disposition générale.

Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement disponibles en mode aperçu. Cette liste sera mise à jour lorsque les fonctionnalités seront mises à la disposition générale et que de nouvelles fonctionnalités seront disponibles en mode aperçu. Aucune notification n'est fournie lorsque de nouvelles fonctionnalités sont disponibles en mode aperçu. Les utilisateurs commenceront simplement à voir les fonctionnalités.

## <a name="enable-or-disable-preview-features"></a>Activer ou désactiver les fonctionnalités d'aperçu

Vous pouvez utiliser le paramètre **Fonctionnalités d'aperçu** dans le centre d'administration Microsoft Dynamics 365 for Talent pour activer ou désactiver les fonctionnalités d'aperçu. Par défaut, le paramètre est désactivé. L'action d'activation et de désactivation des fonctionnalités d'aperçu est propre à l'environnement.

> [!IMPORTANT]
> En activant le paramètre **Fonctionnalités d'aperçu**, vous activez les fonctionnalités d'aperçu pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement. En désactivant le paramètre, vous désactivez les fonctionnalités d'aperçu et les rendez inaccessibles à vos utilisateurs. Les fonctionnalités d'aperçu ont une prise en charge limitée dans Talent. Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Talent. Vous ne devez pas utiliser les fonctionnalités d'aperçu pour traiter des données personnelles (c'est-à-dire, toute information susceptible de vous identifier), ou pour traiter d'autres données soumises à des exigences de conformité juridique ou réglementaire.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Activer ou désactiver les fonctionnalités d'aperçu pour votre organisation

#### <a name="attract"></a>Attract

1. Connectez-vous à Microsoft Dynamics 365 for Talent.
2. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Paramètres d'administration**.
3. Sous l'onglet **Gestion des fonctionnalités**, sélectionnez l'option en regard de **Fonctionnalités d'aperçu** afin qu'elle devienne bleu.
4. Actualisez votre navigateur pour commencer à voir les nouvelles fonctionnalités. (Les utilisateurs qui sont déjà connectés verront les fonctionnalités lors de leur prochaine connexion, ou ils peuvent actualiser leur navigateur pour voir les fonctionnalités immédiatement.)

#### <a name="core-hr"></a>Ressources humaines principales

1. Connectez-vous à Talent. L'espace de travail Ressources humaines principales s'ouvre pour vous permettre d'effectuer les étapes restantes. 
2. Sélectionnez **Administration système \> Paramètres système**.
3. Dans la page **Paramètres système**, sous l'onglet **Fonctionnalités d'aperçu**, définissez l'option **Activer le mode aperçu pour tous les utilisateurs** sur **Oui** pour rendre les fonctionnalités d'aperçu disponibles.

> [!NOTE]
> Pour désactiver les fonctionnalités d'aperçu, utilisez les mêmes étapes de base. Lorsque vous désactivez les fonctionnalités d'aperçu, elles deviennent inaccessibles aux utilisateurs, et des erreurs peuvent se produire dans les processus associés aux fonctionnalités.

## <a name="features-that-are-currently-in-preview"></a>Fonctionnalités actuellement en mode aperçu

### <a name="attract"></a>Attract

- **Modèles de poste** – Vous pouvez désormais créer des modèles de processus de recrutement. Les utilisateurs peuvent déjà personnaliser le processus de recrutement pour un poste spécifique. Toutefois, ils peuvent maintenant créer des modèles pour le processus et sélectionner le modèle approprié lorsqu'un poste spécifique est créé. Par conséquent, cette fonctionnalité permet de rationnaliser le processus de paramétrage des postes.
- **Site de carrière** – La version actuelle du site de carrière répertorie tous les postes vacants. Toutefois, d'autres fonctionnalités seront ajoutées au site ultérieurement. Les postes peuvent être marqués comme internes ou externes. Les utilisateurs internes qui se connectent au site voient les postes internes et externes. Toutefois, les utilisateurs qui ne sont pas internes et les utilisateurs qui ne sont pas connectés ne voient que les postes externes.
- **Annonce d'emploi** – Vous pouvez maintenant publier des postes sur le site de carrière.
- **Annonce d'emploi LinkedIn** – Vous pouvez maintenant publier des postes sur LinkedIn.

    > [!NOTE]
    > Les postes publiés sont visibles uniquement par les clients qui se sont abonnés à un ou plusieurs produits de la liste des postes sur LinkedIn. Sinon, les clients voient un poste uniquement s'ils effectuent une recherche explicite. Les postes sont publiés sur LinkedIn avec du retard. L'affichage d'un poste peut prendre quelques heures après sa publication depuis Attract.

- **Postulant** – Les candidats internes et externes peuvent désormais postuler directement depuis la page des postes sur le site de carrière.
- **Évaluations** – Dans le cadre du processus de recrutement configurable, pour un poste spécifique ou lorsqu'un modèle de poste est utilisé, les utilisateurs ont désormais accès à un nouveau type d'activité **Évaluation**. Ils peuvent ensuite utiliser l'application Projet : « Gauge » dans Talent pour créer des évaluations de base qu'ils peuvent envoyer aux candidats. L'application Projet : « Gauge » est également en mode aperçu public. D'autres fournisseurs seront ajoutés ultérieurement.
- **Projet : « Gauge »** – Projet : « Gauge » est une application dans Talent qui permet aux utilisateurs de créer des évaluations ou enquêtes simples.
- **Gestion des offres** – Les utilisateurs peuvent désormais créer des lettres d'offre à partir de modèles qui incluent des espaces réservés. Lorsque les candidats passent à l'étape Offre, les recruteurs et les responsables du recrutement peuvent utiliser l'outil Offre pour préparer l'offre formelle d'un candidat à l'aide de modèles, envoyer l'offre pour approbation interne et enfin envoyer l'offre au candidat pour signature. De nombreuses fonctionnalités seront ajoutées à l'outil Offre au fil du temps, et la fonctionnalité d'aperçu sera mise à jour avec ces fonctionnalités dès que nous serons prêts à les publier en mode aperçu.

### <a name="core-hr"></a>Ressources humaines principales

- **Inscription en cours** – L'inscription en cours aux avantages offre aux employés une expérience simple de sélection de leurs avantages en libre service. Les administrateurs des ressources humaines peuvent configurer le processus d'inscription en cours aux avantages pour leur organisation, et l'expérience d'inscription des employés en utilisant une solution guidée facile à suivre.

## <a name="feedback"></a>Commentaire

Que vos commentaires soient positifs ou négatifs, nous souhaitons en savoir plus sur votre utilisation des fonctionnalités d'aperçu. Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d'autres.

- [Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d'utilisation, poser des questions et obtenir l'aide de la communauté.
- Utilisez les sites suivants pour proposer des idées de produit. Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit, ainsi que les modifications qui, selon vous, doivent être apportées aux fonctionnalités.

    - [Idées pour Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Ressources humaines principales](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

N'ajoutez pas des données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d'évaluation du produit. Les informations collectées peuvent être analysées davantage, et elles ne seront pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité. Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/en-us/privacystatement).

> [!TIP]
> Marquez cette rubrique et consultez-la régulièrement pour rester informé des nouvelles fonctionnalités d'aperçu dès leur parution.

