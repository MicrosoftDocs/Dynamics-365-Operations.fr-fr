---
title: Applications connectées
description: Cet article explique comment paramétrer les applications connectées dans la facturation électronique.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f908caa902e4747d324480e3a5108b443d385ea7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277329"
---
# <a name="connected-applications"></a>Applications connectées

[!include [banner](../includes/banner.md)]

Les applications connectées sont les instances de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management que vous souhaitez peut-être atteindre via Regulatory Configuration Service (RCS). Grâce aux applications connectées, vous pouvez configurer une partie de la fonction de globalisation dans Finance ou Supply Chain Management pour faire fonctionner l’ensemble du scénario de facturation électronique.

Lorsque vous déployez votre fonctionnalité de globalisation, les informations de configuration applicables à votre application Finance ou Supply Chain Management peuvent être publiées directement depuis RCS vers l’application connectée appropriée.

La disponibilité des paramètres Finance ou Supply Chain Management dans RCS est utile lorsque vous disposez de plusieurs environnements d’application, tels que des environnements de test d’acceptation utilisateur (UAT) et de production, et que vous souhaitez conserver la cohérence de la configuration en déployant les mêmes paramètres dans différents environnements.

## <a name="create-a-connected-application"></a>Créer une application connectée

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Configuration d’environnement**, dans le volet Actions, sélectionnez **Applications connectées**.
4. Sélectionnez **Nouveau** pour créer une application connectée.
5. Dans le champ **Nom**, entrez le nom de l’application à connecter.
6. Dans le champ **Type**, sélectionnez **Dynamics 365 Finance**.
7. Dans le champ **Application**, entrez l’URL de l’environnement à connecter.
8. Dans le champ **Client**, saisissez le client de l’environnement.
9. Cliquez sur **Enregistrer**.
10. Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l’environnement. Fermez ensuite la page.

## <a name="link-connected-applications-to-environments"></a>Lier les applications connectées aux environnements

1. Sur la page **Configuration d’environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.
2. Sélectionnez une application connectée dans le champ **Application connectée**.
3. Sélectionnez un environnement de service dans le champ **Environnement de service**.
4. Sélectionnez **Sauvegarder**, puis fermez la page.
