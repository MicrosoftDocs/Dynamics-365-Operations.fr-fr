---
title: Activer Power BI pour la comptabilité globale des stocks
description: Cette rubrique décrit comment activer Microsoft Power BI pour la comptabilité globale des stocks.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273155"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Activer Power BI pour la comptabilité globale des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Vous pouvez épingler des vignettes, des tableaux de bord et des rapports provenant de votre compte [PowerBI.com](https://powerbi.com/) à votre espace de travail de l’application Microsoft Dynamics 365.

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être satisfaites avant de pouvoir activer la génération de rapports Power BI :

- Vous devez être un administrateur système dans l’application Dynamics 365.
- Vous devez avoir un compte [PowerBI.com](https://powerbi.com/).
- Vous devez avoir au moins un tableau de bord et un rapport dans votre compte Power BI.
- Vous devez être administrateur de votre compte Azure Active Directory (Azure AD).
- Le domaine Azure AD doit être le même que celui que vous avez utilisé pour votre compte [PowerBI.com](https://powerbi.com/).

## <a name="setup"></a>Paramétrage

Pour configurer l’intégration de Power BI, procédez comme suit.

1. Connectez-vous à [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Accédez à **Bibliothèque d’actifs partagés**, sélectionnez **Modèle de rapport Power BI** comme type d’actif et téléchargez le package **Comptabilité globale des stocks**. 
1. Connectez-vous à [PowerBI.com](https://app.powerbi.com/) et chargez le fichier de rapport Power BI **Comptabilité globale des stocks** en suivant ces étapes :

    1. Sélectionnez **Nouveau**.
    1. Sélectionnez **Charger un fichier**.
    1. Sélectionnez le fichier de rapport Power BI **Comptabilité globale des stocks**.

1. Configurez le rapport Power BI **Comptabilité globale des stocks** en suivant ces étapes :

    1. Accédez à **Mon espace de travail**, recherchez le jeu de données pour la comptabilité globale des stocks puis, dans le menu **Options**, sélectionnez **Paramètres**.
    1. Dans **Paramètres de la comptabilité globale des stocks**, développez **Paramètres** et mettez à jour tous les paramètres si nécessaire.

1. Enregistrez l’application comme décrit dans [Configurer l’intégration PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Intégrez le fichier de rapport Power BI **Comptabilité globale des stocks** dans Dynamics 365 Supply Chain Management en suivant les étapes ci-après :

    1. Accédez à **Administration système \> Paramétrage \> Configuration PowerBI.com**.
    1. Sélectionnez **Modifier**.
    1. Sélectionnez **Activer l’intégration PowerBI.Com**.
    1. Dans le champ **ID application**, entrez l’ID d’application.
    1. Dans le champ **Clé d’application**, entrez la clé d’application.
    1. Sélectionnez **Enregistrer**.

1. Rafraîchissez la page pour que la boîte de dialogue de connexion Power BI s’affiche.
1. Sur l’onglet **Options**, sélectionnez **Ouvrir le catalogue de rapports**, puis sélectionnez le fichier de rapport Power BI **Comptabilité globale des stocks** que vous avez téléchargé précédemment.
1. Actualisez la page. Vous devriez voir que votre rapport a été ajouté.
1. Sous **Rapports Power BI**, sélectionnez le lien **Comptabilité globale des stocks**.

Pour plus d’informations, voir [Configuration de l’intégration PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
