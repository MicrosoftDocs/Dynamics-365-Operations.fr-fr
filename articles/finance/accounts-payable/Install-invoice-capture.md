---
title: Installer la solution Invoice Capture
description: Cet article fournit des informations sur la façon d’installer la solution Invoice Capture et de l’intégrer à Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691171"
---
# <a name="install-the-invoice-capture-solution"></a>Installer la solution Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Si vous avez installé la solution en version préliminaire privée, vous devez désinstaller l’ancienne solution avant de continuer.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir installer la solution Invoice Capture, vous devez remplir les conditions requises suivantes :

1. Enregistrez une application et ajoutez une clé secrète client à Microsoft Azure Active Directory (Azure AD) sous votre abonnement Azure. Pour plus d’informations, voir [Inscrire une application web avec AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Notez des valeurs des **ID de l’application (client)** , **Clé secrète client**, et **ID du locataire**, car vous en aurez besoin plus tard.

2. Enregistrez l’application Azure dans un environnement Dynamics 365 Finance. Pour plus d’informations, voir [Inscrire votre application externe](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Installer et configurer la solution

Pour installer la solution Invoice capture, accédez à AppSource, puis sélectionnez le lien de la version préliminaire de [Dynamics 365 Invoice capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). Une fois l’installation terminée, vous verrez la solution installée dans l’environnement sélectionné dans Power Apps.

Pour terminer le paramétrage, procédez comme suit.

1. Téléchargez la [solution d’assistant](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip) pour configurer les détails suivants :

    - La communication entre Microsoft Power Platform et l’environnement Finance
    - La référence de connexion pour Dataverse et Office 365 Outlook qui est utilisée par la chaîne

2. Dans Power Apps, accédez à votre environnement et sélectionnez **Importer la solution**.
3. Sélectionnez **Parcourir**, sélectionnez le package de solution de l’assistant que vous avez téléchargé, puis sélectionnez **Suivant**.
4. Cliquez sur **Suivant**.
5. Attribuez une connexion existante ou créez-en une en sélectionnant **Nouvelle connexion**.
6. Une fois le package importé avec succès, ouvrez **Dynamics 365 Invoice capture – Outils d’installation**.
7. Exécutez le flux Cloud pour configurer la connexion entre la solution Invoice capture dans Microsoft Power Platform et Finance.
8. Sélectionnez **Exécuter**, et spécifiez les paramètres suivants :

    - **URL Dynamics 365 Finance** – L’URL de l’environnement Finance auquel vous souhaitez vous intégrer.
    - **ID de client** : l’ID de client pour l’environnement Finance.
    - **ID client** – L’ID d’Azure Application qui a été enregistré.
    - **Clé secrète client** : clé secrète générée pour Azure Application.
