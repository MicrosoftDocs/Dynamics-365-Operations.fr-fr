---
title: Résoudre les problèmes de configuration et d'installation de Store Commerce
description: Cet article explique comment résoudre les problèmes de configuration et d'installation dans l'application Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 92d4a9d78485b681b4e802f695d54f44ecd7c5de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870464"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Résoudre les problèmes de configuration et d'installation de Store Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article explique comment résoudre les problèmes de configuration et d'installation dans l'application Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Je ne peux pas activer l'application et je reçois un message d'erreur de connectivité

Après avoir saisi l'URL Cloud Point of Sale (CPOS) valide, vous pouvez recevoir un message d'erreur de connectivité ressemblant à l'exemple suivant :

> Une erreur de connectivité s'est produite et votre appareil ne peut pas se connecter au CPOS. L'URL CPOS saisie peut présenter des problèmes.

Dans ce cas, vérifiez si l'URL contient des erreurs typographiques ou déterminez si CPOS n'est pas accessible car il est hors ligne.

En outre, vérifiez que la version Cloud Scale Unit (CSU) est 10.0.25 (9.35.\*.\*) ou version ultérieure. La version 10.0.25 ou ultérieure de CPOS est requise pour utiliser l'application Store Commerce.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Je ne peux pas installer l'application car Modern POS est déjà installé

Lors de l'installation, vous pouvez recevoir un message d'erreur tel que l'exemple suivant :

> Une variante (9.\*.\*.\*) de ce produit (Modern POS) a déjà été installée via l'ancien programme d'installation.

Pour corriger l'erreur, vous devez désinstaller l'application Modern Point of Sale (MPOS) pour tous les utilisateurs de la machine, puis réessayer. Vous pouvez vérifier si MPOS a été supprimé pour tous les utilisateurs en exécutant la commande PowerShell suivante.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Je ne peux pas activer l'application en raison d'une URL invalide ou d'un état d'erreur

Si l'URL CPOS que vous avez saisie n'est pas valide et que vous souhaitez la modifier, ou si l'application Store Commerce est en état d'erreur lors de l'activation, vous pouvez redémarrer le processus en réinitialisant l'application. L'application Store Commerce n'enregistrera qu'une URL CPOS valide.

Pour réinitialiser l'application Store Commerce, procédez comme suit.

1. Dans le menu **Démarrer** de Windows, sélectionnez et maintenez (ou cliquez avec le bouton droit) sur l'application, puis sélectionnez **Plus \> Paramètres de l'application**.
2. Faites défiler la page des paramètres de l'application jusqu'à ce que vous trouviez le bouton **Réinitialiser**.
3. Sélectionnez **Réinitialiser**. Ensuite, lorsque vous y êtes invité, confirmez que vous souhaitez réinitialiser l'application.
