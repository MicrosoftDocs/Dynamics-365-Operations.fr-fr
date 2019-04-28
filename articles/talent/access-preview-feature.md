---
title: Accéder aux fonctions d'aperçu de Talent
description: Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement activées pour le mode aperçu.
author: andreabichsel
manager: AnnBe
ms.date: 04/17/2018
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
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 060a36185641d5bb7912631b7c857c5c4331c8b7
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856322"
---
# <a name="access-preview-features-in-talent"></a>Accéder aux fonctions d'aperçu de Talent

[!include[banner](../includes/banner.md)]

Dans le cadre de notre lancement continu de fonctionnalités du produit, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible. Les administrateurs peuvent afficher et utiliser les fonctionnalités d'aperçu dans leurs environnements. Ces fonctionnalités sont presque prêtes pour la mise à disposition générale et ont fait l'objet de tests étendus. Nous attendons les derniers commentaires et validations des clients avant leur mise à disposition générale.

Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement disponibles en mode aperçu. Cette liste sera mise à jour lorsque les fonctionnalités seront mises à la disposition générale et que de nouvelles fonctionnalités seront disponibles en mode aperçu. Aucune notification n'est fournie lorsque de nouvelles fonctionnalités sont disponibles en mode aperçu. Les utilisateurs commenceront simplement à voir les fonctionnalités.

## <a name="enable-or-disable-preview-features"></a>Activer ou désactiver les fonctionnalités d'aperçu

Vous pouvez utiliser le paramètre **Fonctionnalités d'aperçu** dans le centre d'administration Microsoft Dynamics 365 for Talent pour activer ou désactiver les fonctionnalités d'aperçu. Par défaut, le paramètre est désactivé. L'action d'activation et de désactivation des fonctionnalités d'aperçu est propre à l'environnement.

> [!IMPORTANT]
> En activant le paramètre **Fonctionnalités d'aperçu**, vous activez les fonctionnalités d'aperçu pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement. En désactivant le paramètre, vous désactivez les fonctionnalités d'aperçu et les rendez inaccessibles à vos utilisateurs. Les fonctionnalités d'aperçu ont une prise en charge limitée dans Talent. Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Talent. Vous ne devez pas utiliser les fonctionnalités d'aperçu pour traiter des données personnelles (c'est-à-dire, toute information susceptible de vous identifier), ou pour traiter d'autres données soumises à des exigences de conformité juridique ou réglementaire.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Activer ou désactiver les fonctionnalités d'aperçu pour votre organisation

#### <a name="attract"></a>Attract

1. Connectez-vous à Microsoft Dynamics 365 for Talent : Attract.
2. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Paramètres d'administration**.
3. Sous l'onglet **Gestion des fonctionnalités**, sélectionnez l'option en regard de **Fonctionnalités d'aperçu** afin qu'elle devienne bleu.
4. Vous pouvez éventuellement contrôler certaines fonctionnalités en activant/désactivant des fonctionnalités spécifiques sur cette page.
5. Actualisez votre navigateur pour commencer à voir les nouvelles fonctionnalités. (Les utilisateurs qui sont déjà connectés verront les fonctionnalités lors de leur prochaine connexion, ou ils peuvent actualiser leur navigateur pour voir les fonctionnalités immédiatement.)

#### <a name="core-hr"></a>Core HR

1. Connectez-vous à Talent. L'espace de travail Ressources humaines principales s'ouvre pour vous permettre d'effectuer les étapes restantes. 
2. Sélectionnez **Administration système \> Paramètres système**.
3. Dans la page **Paramètres système**, sous l'onglet **Fonctionnalités d'aperçu**, définissez l'option **Activer le mode aperçu pour tous les utilisateurs** sur **Oui** pour rendre les fonctionnalités d'aperçu disponibles.

> [!NOTE]
> Pour désactiver les fonctionnalités d'aperçu, utilisez les mêmes étapes de base. Lorsque vous désactivez les fonctionnalités d'aperçu, elles deviennent inaccessibles aux utilisateurs, et des erreurs peuvent se produire dans les processus associés aux fonctionnalités.

## <a name="features-that-are-currently-in-preview"></a>Fonctionnalités actuellement en mode aperçu

### <a name="attract"></a>Attract

- **Candidats correspondant à une mission** : Les recruteurs et les responsables de l'embauche peuvent aisément voir les candidats pouvant être les plus pertinents pour la mission parmi tous les candidats. Les 5 principaux candidats sont affichés selon la pertinence de leur CV/profil par rapport la description de la mission.
- **Missions pertinentes** : Les candidats voient maintenant une liste d'autres missions qui leur correspondent selon leur CV/profil et les descriptions de mission.  Actuellement les candidats sont affichés une fois qu'ils postulent comme suggestion pour d'autres opportunités.
- **Prise en charge d'Égalité des chances d'emploi/Bureau des programmes fédéraux de conformité des contrats** : De nouveaux types d'activités permettent l'utilisation d'un écran prédéfini pour la collecte de données relatives à l'Égalité des chances d'emploi/Bureau des programmes fédéraux de conformité des contrats du candidat.  Il s'agit d'un écran prédéfini qui peut pas être modifié.

    > [!NOTE]
    > Les postes publiés sont visibles uniquement par les clients qui se sont abonnés à un ou plusieurs produits de la liste des postes sur LinkedIn. Sinon, les clients voient un poste uniquement s'ils effectuent une recherche explicite. Les postes sont publiés sur LinkedIn avec du retard. L'affichage d'un poste peut prendre quelques heures après sa publication depuis Attract.

- **Postulant** – Les candidats internes et externes peuvent désormais postuler directement depuis la page des postes sur le site de carrière.
- **Gestion des offres** – Les utilisateurs peuvent désormais créer des lettres d'offre à partir de modèles qui incluent des espaces réservés. Lorsque les candidats passent à l'étape Offre, les recruteurs et les responsables du recrutement peuvent utiliser l'outil Offre pour préparer l'offre formelle d'un candidat à l'aide de modèles, envoyer l'offre pour approbation interne et enfin envoyer l'offre au candidat pour signature. De nombreuses fonctionnalités seront ajoutées à l'outil Offre au fil du temps, et la fonctionnalité d'aperçu sera mise à jour avec ces fonctionnalités dès que nous serons prêts à les publier en mode aperçu.

### <a name="core-hr"></a>Core HR

- **Inscription en cours** – L'inscription en cours aux avantages offre aux employés une expérience simple de sélection de leurs avantages en libre service. Les administrateurs des ressources humaines peuvent configurer le processus d'inscription en cours aux avantages pour leur organisation, et l'expérience d'inscription des employés en utilisant une solution guidée facile à suivre.

## <a name="feedback"></a>Commentaire

Que vos commentaires soient positifs ou négatifs, nous souhaitons en savoir plus sur votre utilisation des fonctionnalités d'aperçu. Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d'autres.

- [Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d'utilisation, poser des questions et obtenir l'aide de la communauté.
- Utilisez les sites suivants pour proposer des idées de produit. Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit, ainsi que les modifications qui, selon vous, doivent être apportées aux fonctionnalités.

    - [Idées pour Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

N'ajoutez pas des données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d'évaluation du produit. Les informations collectées peuvent être analysées davantage, et elles ne seront pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité. Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Marquez cette rubrique et consultez-la régulièrement pour rester informé des nouvelles fonctionnalités d'aperçu dès leur parution.
