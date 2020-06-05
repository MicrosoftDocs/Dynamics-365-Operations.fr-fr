---
title: Désactiver la collecte d'événements d'activité Web
description: Cette rubrique explique comment vous pouvez autoriser les visiteurs de votre site Web à désactiver la collecte d'événements d'activité Web dans Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b0e48307527a8fea729d8dfdcdbc6337be0faf1
ms.sourcegitcommit: 8058db089b8768076ff1250be77d42a6e2b3f570
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378990"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Désactiver la collecte d'événements d'activité Web
[!include [banner](includes/banner.md)]

Cette rubrique explique comment vous pouvez laisser les clients désactiver la collecte d'événements d'activité Web dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce permet aux administrateurs de site d'analyser l'activité Web des utilisateurs de leurs sites de commerce électronique. De cette façon, ils peuvent mieux comprendre comment leurs sites sont utilisés et les optimiser pour offrir une expérience utilisateur améliorée et répondre aux objectifs commerciaux.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Méthodes de mise en œuvre d'une expérience de désinscription côté administrateurs

Les administrateurs disposent de 3 méthodes pour mettre en œuvre d'une expérience de désinscription.

### <a name="opt-out-on-behalf-of-users"></a>Refus pour le compte des utilisateurs

Dans la gestion de compte dans Commerce Headquarters (HQ), les administrateurs peuvent refuser au nom des utilisateurs.

1. Dans le client HQ, sur la page **Tous les clients**, recherchez et sélectionnez un client.
1. Sur la page des détails du client, sur le raccourci **Retail**, dans la section **Confidentialité**, définissez l'option **Ne pas suivre l'activité Web** sur **Oui**.

    ![Paramètres de confidentialité](media/Disablepersonalizationpart2.png)

1. Sélectionnez **Sauvegarder**, puis fermez la page.

### <a name="module-based-opt-out-experience"></a>Expérience de désinscription basée sur les modules

Les administrateurs peuvent laisser les utilisateurs authentifiés désactiver eux-mêmes la collecte d'événements d'activité Web. Pour proposer cette expérience de désinscription, ajoutez le module de refus utilisateur aux pages du profil de compte client.

### <a name="custom-extensions"></a>Extensions personnalisées

Les administrateurs peuvent créer leurs propres extensions pour gérer l'expérience de désinscription pour les utilisateurs. Pour plus d'informations, voir [Appeler les API Retail Server](e-commerce-extensibility/call-retail-server-apis.md) et [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).
