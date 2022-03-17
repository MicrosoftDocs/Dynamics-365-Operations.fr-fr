---
title: Installer le module complémentaire pour les microservices dans Lifecycle Services
description: Cette rubrique explique comment installer le complément Facturation électronique dans Microsoft Dynamics Lifecycle Services (LCS).
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a575f3e26489607dc2143ba05c941240969a0feb
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371719"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installer le module complémentaire pour les microservices dans Lifecycle Services

[!include [banner](../includes/banner.md)]

L’authentification dans le service de facturation électronique nécessite que vous enregistriez votre environnement Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management dans la plate-forme de services en installant le complément pour votre environnement dans Microsoft Dynamics Lifecycle Services (LCS).

Pour enregistrer un environnement, procédez comme suit.

1. Connectez-vous à votre compte LCS.
2. Sur le tableau de bord Projet, sélectionnez un projet LCS.
2. Dans le projet, sur le tableau de bord **Environnements**, sélectionnez environnement déployé. L’environnement que vous sélectionnez doit être en cours d’exécution.
3. Dans l’onglet **Intégration Power Platform**, dans la section **Compléments d’environnement**, sélectionnez **Installer un nouveau complément**.
4. Sélectionnez **Facturation électronique**.
5. Dans le champ **ID d’application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Cette valeur est une valeur fixe. Veillez à saisir uniquement un identificateur global unique (GUID). N’incluez aucun autre symbole, tel que des espaces, des virgules, des points ou des guillemets.
6. Dans le champ **ID client AAD**, entrez l’ID client de votre compte d’abonnement Azure. Le client Azure Active Directory (Azure AD) que vous spécifiez doit être le même que celui utilisé pour Regulatory Configuration Service (RCS).
7. Passez en revue les conditions générales, puis cochez la case.
8. Sélectionnez **Installer**. Après quelques minutes, le statut devrait passer de **Installation** à **Installé**. Vous devrez peut-être actualiser la page pour voir cette modification.

La facturation électronique est maintenant prête à être utilisée.

> [!NOTE]
> Les entreprises disposent généralement de plusieurs environnements Finance ou Supply Chain Management. Ces environnements comprennent des environnements de production, des environnements de test d’acceptation utilisateur (UAT) et des environnements de développement (sandbox). Vous devez exécuter la procédure précédente pour tous les environnements auxquels vous souhaitez connecter la fonctionnalité de Facturation électronique.
