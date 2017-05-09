---
title: "Espace de travail mobile Contrôle des coûts pour l&quot;application Microsoft Dynamics 365 for Operations"
description: "Avec l&quot;espace de travail mobile Contrôle des coûts, les responsables des centres de coût peuvent consulter les performances du centre de coût à tout moment et n&quot;importe où."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espace de travail mobile Contrôle des coûts pour l'application Microsoft Dynamics 365 for Operations

Avec l'espace de travail mobile Contrôle des coûts, les responsables des centres de coût peuvent consulter les performances du centre de coût à tout moment et n'importe où. 

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                         | Description                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| En savoir plus sur la plateforme mobile Microsoft Dynamics 365 for Operations | [Plateforme mobile Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Assurez-vous d'utiliser un environnement disposant de la version 1611 de Microsoft Dynamics 365 for Operations et de la mise à jour 3 de Microsoft Dynamics for Operations (novembre 2016). |
| Correctif de la Base de connaissances 3215650                                                    | Installez le correctif pour activer les espaces de travail fournis dans Microsoft Dynamics 365 for Operations.                                                                       |
| Appareil mobile sur lequel l'application Dynamics 365 for Operations est installée | Téléchargez l'application Dynamics 365 for Operations à partir de votre magasin d'application mobile.                                                                                                      |

## <a name="introduction"></a>Introduction
L'espace de travail mobile Contrôle des coûts fournit une vue instantanée des performances actuelles des centres de coût en comparant les coûts réels aux coûts budgétés. Vous pouvez accéder aux statuts des éléments de coût individuels.

### <a name="example"></a>Exemple

Un employé reçoit une invitation à une conférence internationale. L'organisation doit couvrir tous les frais de déplacement. L'employé demande à son responsable s'il peut assister à la conférence. Le responsable ouvre rapidement l'espace de travail Contrôle des coûts sur son téléphone portable de voir s'il dispose du budget nécessaire.

### <a name="data-security"></a>Sécurité des données

Les données de l'espace de travail Contrôle des coûts sont sécurisées par les informations d'identification de l'utilisateur. Un responsable de centre de coût est uniquement autorisé à consulter les données de son propre centre de coût. La sécurité au niveau de l'accès est gérée dans le module Contrôle de gestion. Les contrôleurs de gestion définissent la configuration de l'espace de travail mobile Contrôle des coûts dans le module Contrôle de gestion. Une fois que l'espace de travail est publié sur l'application Microsoft Dynamics 365 for Operations, il est disponible dans l'application mobile Dynamics 365 for Operations. Ainsi, tous les responsables de centre de coût de l'organisation consultent les données au même format.

### <a name="actions-views-and-links"></a>Actions, vues et liens

L'espace de travail mobile Contrôle des coûts pour l'application Dynamics 365 for Operations fournit les actions, les vues et les liens suivants :

-   Actions 
    -   Sélectionnez **Configurations** pour sélectionner une mise en page.
    -   Sélectionnez **Objets de coût** pour sélectionner les centres de coût dans lesquels vous souhaitez filtrer les données. **Remarque :** la liste est affichée en fonction de l'accès accordé dans le module Contrôle de gestion.

<!-- -->

-   Selon la sélection sous **Actions** et la configuration du module Contrôle de gestion, vous pouvez afficher les informations suivantes dans les cartes. Notez que le montant est affiché au même format : réel, budget, écart et écart en %. 
    -   Réel/Budget (période actuelle)
    -   Réel/Budget révisé (période actuelle)
    -   Réel/Budget (période précédente)
    -   Réel/Budget révisé (période précédente)
    -   Réel/Budget (année en cours)
    -   Réel/Budget révisé (année en cours)

<!-- -->

-   Liens
    -   Détails pour la période actuelle.
    -   Détails pour la période précédente.
    -   Détails pour l'année en cours.

Lorsque vous sélectionnez l'un des liens, une carte par élément de coût s'affiche. Le montant des cartes est affiché au format suivant : réel, budget, écart budgétaire, écart budgétaire en %, budget révisé, écart budgétaire révisé et écart budgétaire révisé en %.  [![cost-controlling](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Mise en route
Suivez les étapes ci-après pour commencer à utiliser l'application mobile de contrôle des coûts sur votre appareil mobile.

1.  Dans votre magasin d'application mobile, téléchargez et installez l'application Microsoft Dynamics 365 for Operations.
2.  Démarrez l'application sur votre appareil.
3.  Entrez votre URL Dynamics 365.
4.  Entrez la société à laquelle vous vous connectez. Par exemple, entrez **USMF**.
5.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer le nom d'utilisateur et le mot de passe de votre compte Microsoft Dynamics 365 for Operations. Entrez vos informations d'identification. Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.

Pour afficher les espaces de travail sur votre application mobile, vous devez d'abord publier les espaces de travail souhaités sur l'application Dynamics 365 for Operations.

1.  Démarrez Dynamics 365 for Operations.
2.  Accédez à **Administration système** &gt; **Paramétrage** &gt; **Paramètres système**.
3.  Sélectionnez **Gérer l'application mobile**.
4.  Sélectionnez l'espace de travail **Contrôle des coûts** pour le publier sur la plateforme mobile.
5.  Sélectionnez **Publier l'espace de travail**.
6.  Actualisez votre appareil pour afficher les espaces de travail publiés.

## <a name="view-the-performance-of-your-cost-center"></a>Afficher les performances de votre centre de coût
1.  Sur votre appareil mobile, sélectionnez l'espace de travail **Contrôle des coûts**.
2.  Sélectionnez **Contrôle des objets de coût**.
3.  Cliquez sur **Actions**.
4.  Cliquez sur **Sélectionner une configuration** pour sélectionner une mise en page de contrôle des coûts.
5.  Cliquez sur **Terminé**.
6.  Cliquez sur **Actions**.
7.  Cliquez sur **Sélectionner un objet de coût** pour sélectionner les centres de coût auxquels vous êtes autorisé à accéder.
8.  Cliquez sur **Terminé**.
9.  Affichez les performances globales de votre centre de coût.
10. Cliquez sur **Détails pour la période actuelle**.
11. Affichez les performances des éléments de coût individuels.
12. Vous pouvez également rechercher des éléments de coût spécifiques.



