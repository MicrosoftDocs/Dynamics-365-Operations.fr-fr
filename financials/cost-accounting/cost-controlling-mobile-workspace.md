---
title: "Estimation de coût de contrôler l&quot;espace de travail mobile de Microsoft Dynamics 365 pour l&quot;application Opérations"
description: "Le coût contrôlant l&quot;espace de travail mobile, responsables de centre de coût peuvent voir les performances de centre de coût à tout moment et n&quot;importe où."
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

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Estimation de coût de contrôler l'espace de travail mobile de Microsoft Dynamics 365 pour l'application Opérations

Le coût contrôlant l'espace de travail mobile, responsables de centre de coût peuvent voir les performances de centre de coût à tout moment et n'importe où. 

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                         | description ;                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Disposer connaissances Microsoft Dynamics 365 pour la plateforme mobiles d'opérations | [Dynamics 365 pour plateforme mobile opérations] (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 pour les opérations                                          | Assurez-vous que vous utilisez un environnement avec Microsoft Dynamics 365 pour la version 1611 d'opérations et Microsoft Dynamics pour la mise à jour 3 de plateforme Opérations (novembre 2016). |
| Base de connaissances 3215650 de correctif                                                    | Installez le correctif pour activer des espaces de travail qui sont définis dans Microsoft Dynamics 365 pour les opérations.                                                                       |
| Appareil mobile qui a Dynamics 365 pour l'application Opérations installée | Téléchargez Dynamics 365 pour l'application Opérations de votre magasin portable d'application.                                                                                                      |

## <a name="introduction"></a>Introduction
Coût contrôlant l'espace de travail portable fournit une vue instantanée de la performance actuelle des centres de coût en comparant les coûts réels avec les coûts budgétés. Vous pouvez accéder aux statuts des éléments individuels de coût.

### <a name="example"></a>Exemple

Un employé reçoit une invitation à une conférence internationale. L'organisation doit couvrir toutes les dépenses de déplacement. L'employé demande son manger s'il peut former la conférence. Il ouvre rapidement le coût contrôlant l'espace de travail de passer à son téléphone portable de voir s'il a le budget qu'{{il:for}} {{faut:for}} que l'employé participe à une conférence.

### <a name="data-security"></a>Sécurité des données

Les données dans le coût contrôlant l'espace de travail sont sécurisées par les informations d'identification de l'utilisateur. Seule à un responsable de centre de coût pour consulter les données pour son propre centre de coût. La sécurité de niveau d'accès est gérée dans le module de contrôle de gestion. Les comptables de coût définissent le coût contrôlant la configuration portable de l'espace de travail du module Contrôle de gestion. Une fois l'espace de travail ne soit émis à Microsoft Dynamics 365 pour l'application Opérations, il est disponible dans Dynamics 365 pour l'application de portable d'opérations. Cela garantit que tous les responsables du centre de coût dans la recherche d'organisation aux données dans le même formatent.

### <a name="actions-views-and-links"></a>Actions, affichages, et liens

Coût contrôlant l'espace de travail mobile de Dynamics 365 pour l'application Opérations fournit des actions, des vues, et les liens suivants :

-   Actions 
    -   Sélectionnez ** configurations ** pour prélever une mise en page.
    -   Sélectionnez ** objets de coût ** pour prélever les centres de coût dans lesquels vous souhaitez des données de filtre. ** Remarque : ** La liste est affichée en fonction de l'accès accordé du module Contrôle de gestion.

<!-- -->

-   Selon ce qui est sélectionné sous ** des actions ** et qui est paramétré dans le module Contrôle de gestion, vous pouvez afficher les informations suivantes dans les cartes. Notez que le montant est affiché dans le même format : Niveau unique, budget, écart, et écart %. 
    -   Réel {{contre:vs}} le budget (période actuelle)
    -   Réel {{contre:vs}} le budget révisé (période actuelle)
    -   Réel {{contre:vs}} le budget (période précédente)
    -   Réel {{contre:vs}} le budget révisé (période précédente)
    -   Réel {{contre:vs}} le budget (Année en cours)
    -   Réel {{contre:vs}} le budget révisé (Année en cours)

<!-- -->

-   Liens
    -   Détails de la période actuelle.
    -   Détails de la période précédente.
    -   Détails de l'année jusqu'à présent.

Lorsque vous sélectionnez l'un des liens, une carte par élément de coût s'affiche. Montant dans les cartes est affiché dans le format suivant : Écart réel, de budget, de budget, écart % de budget, écart de budget révisé, de budget révisé, et écart % du budget révisé.  [![coût contrôlant] (. /media/cost-controlling.png)](. /media/cost-controlling.png)

## <a name="get-started"></a>Mise en route
Procédez comme suit pour obtenir commencé à l'aide de l'application mobile de contrôle des coûts sur votre périphérique mobile.

1.  Dans votre magasin portable d'application, chargez et installez Microsoft Dynamics 365 pour l'application Opérations.
2.  Démarrez l'application de votre périphérique.
3.  Permet d'entrer l'URL de Dynamics 365.
4.  Entrez la société pour signer dans en. Par exemple, entrez ** USMF **.
5.  La première fois que vous vous connectez, vous êtes invité à entrer le nom d'utilisateur et le mot de passe pour votre Microsoft Dynamics 365 pour le compte d'opérations. Entrez vos informations d'identification. Après avoir signer électroniquement dans, vous voyez des espaces de travail disponibles pour votre société.

Pour afficher des espaces de travail de votre application mobile, vous devez d'abord envoyer des espaces de travail souhaités à Dynamics 365 pour l'application Opérations.

1.  Début Dynamics 365 pour les opérations.
2.  Allez ** Administration du système ** &gt; ** au paramétrage ** &gt; ** des paramètres système **.
3.  Sélectionnez ** de gérer l'application mobile **.
4.  Sélectionnez l'espace de travail ** contrôler des coûts ** pour publier à la plateforme portable.
5.  Sélectionnez ** publiez l'espace de travail **.
6.  Permet d'actualiser le périphérique pour voir des espaces de travail émis.

## <a name="view-the-performance-of-your-cost-center"></a>Permet d'afficher les performances de votre centre de coût
1.  Dans votre périphérique mobile, sélectionnez ** contrôler des coûts ** l'espace de travail.
2.  Sélectionnez ** contrôler d'objet de coût **.
3.  Cliquez sur ** actions **.
4.  Cliquez sur ** sélectionnez la configuration ** pour sélectionner un coût contrôlant la mise en page.
5.  Click **Done**.
6.  Cliquez sur ** actions **.
7.  Cliquez sur ** sélectionnez l'objet de coût ** pour sélectionner les centres de coût dans lesquelles vous avez obtenu l'accès.
8.  Click **Done**.
9.  Permet d'afficher les performances générales de votre centre de coût.
10. Cliquez sur ** détails de la période actuelle **.
11. Permet d'afficher les performances des éléments individuels de coût.
12. Vous pouvez également rechercher les éléments spécifiques de coût.



