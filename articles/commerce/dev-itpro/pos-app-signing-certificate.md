---
title: Signer le fichier .appx MPOS avec un certificat de signature de code
description: Cet article explique comment signer MPOS avec un certificat de signature de code.
author: mugunthanm
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 28021
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-09-2019
ms.openlocfilehash: 7e998514081cad1c7302aacb1cd74373f896f2d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865967"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Signer le fichier .appx MPOS avec un certificat de signature de code

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Pour installer Modern POS (MPOS), vous devez signer l’application MPOS avec un certificat de signature de code d’un fournisseur de confiance et installer le même certificat sur toutes les machines où MPOS est installé sous le dossier racine de confiance pour l’utilisateur actuel.

Pour signer l’application MPOS avec un certificat, utilisez l’une de ces options via **Kit de développement logiciel (SDK) Retail\\Outil de génération\\Customization.settings** :

- Ajoutez la partie de tâche de fichier sécurisé des étapes de génération Azure DevOps et télécharger le certificat pour sécuriser la tâche de fichier. Utilisez la variable de chemin de sortie de tâche de fichier sécurisé comme paramètre dans le fichier Customization.settings.

    > [!NOTE]
    > La tâche Sécuriser le fichier ne prend pas en charge un certificat protégé par mot de passe. Vous devez supprimer le mot de passe avant de télécharger cette tâche. Étant donné que le certificat est chargé dans la tâche de système de fichiers sécurisé dans Azure, vous ne pouvez supprimer le mot de passe que pour cette étape. Cependant, vous devez discuter de la suppression du mot de passe avec vos experts en sécurité pour déterminer s’il s’agit de la bonne action pour votre projet. Ne supprimez pas le mot de passe du certificat pour les autres scénarios.
- Utilisez un certificat qui se trouve dans le système de fichiers. Pour ce faire, téléchargez ou générez un certificat et placez-le dans le système de fichiers où la génération est en cours d’exécution. L’agent hébergé par Microsoft ou l’utilisateur de génération doit avoir accès à ce chemin et à ce fichier.
- Utilisez l’empreinte digitale pour rechercher le certificat dans le magasin et connectez-vous avec ce certificat.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Utiliser une tâche de fichier sécurisé pour la signature d’applications de la plateforme Windows universelle

> [!NOTE]
> Vous pouvez également utiliser Azure Key Vault pour stocker le certificat et utiliser l’outil de signature Azure pour signer le fichier .appx de Modern POS et les programmes d’installation en libre-service. Pour obtenir des exemples de scripts de pipeline et des informations supplémentaires, consultez [Configurer un pipeline de build dans Azure DevOps pour générer des packages en libre-service Retail](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

L’utilisation d’une tâche de fichier sécurisé est l’approche recommandée pour la signature d’applications de la plateforme Windows universelle (UWP). Pour plus d’informations sur la signature de package, consultez [Configurer la signature de package](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Ce processus est illustré dans l’image suivante.

![Flux de signature d’application MPOS.](media/POSSigningFlow.png)

> [!NOTE]
> Actuellement, le packaging OOB prend uniquement en charge la signature du fichier .appx, les différents programmes d’installation en libre-service tels que MPOIS, RSSU et HWS ne sont pas signés par ce processus. Vous devez le signer manuellement à l’aide de SignTool ou d’autres outils de signature. Le certificat utilisé pour signer le fichier .appx doit être installé sur la machine sur laquelle Modern POS est installé.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Étapes de configuration du certificat pour la journalisation dans Azure Pipelines

### <a name="certificate-in-the-file-systemsecure-location"></a>Certificat dans le système de fichiers/emplacement sécurisé

Téléchargez la [Tâche DownloadFile](/visualstudio/msbuild/downloadfile-task) et ajoutez-la comme première étape du processus de génération. L’avantage de l’utilisation de la tâche Sécuriser le fichier est que le fichier est chiffré et placé sur le disque pendant la génération, que le pipeline de génération réussisse, échoue ou soit annulé. Le fichier est supprimé de l’emplacement de téléchargement une fois le processus de génération terminé.

1. Téléchargez et ajoutez la tâche Sécuriser le fichier comme première étape du pipeline de build Azure. Vous pouvez télécharger la tâche Fichier sécurisé à partir de [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Chargez le certificat dans la tâche Fichier sécurisé et définissez le nom de référence sous Variables de sortie, comme illustré dans l’image suivante.
    > [!div class="mx-imgBorder"]
    > ![Tâche Fichier sécurisé.](media/SecureFile.png)
1. Créez une nouvelle variable dans Azure Pipelines en sélectionnant **Nouvelle variable** sous l’onglet **Variables**.
1. Indiquez un nom pour la variable dans le champ de valeur, par exemple, **MySigningCert**.
1. Enregistrez la variable.
1. Ouvrez le fichier **Customization.settings** de **RetailSDK\\BuildTools** et mettez à jour **ModernPOSPackageCertificateKeyFile** avec le nom de variable créé dans le pipeline (étape 3). Par exemple :

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Cette étape est obligatoire si le certificat n’est pas protégé par un mot de passe. Si le certificat est protégé par un mot de passe, continuez avec les étapes suivantes.
    
1. Si vous souhaitez horodater le fichier .appx MPOS lors de sa signature avec un certificat, ouvrez le fichier **Kit de développement logiciel (SDK) Retail\\Outil de création\\Customization.settings** et effectuez une mise à jour de la variable **ModernPOSPackageCertificateTimestamp** avec le fournisseur d’horodatage (par exemple, `http://timestamp.digicert.com`).
1. Sur l’onglet **Variables** du pipeline, ajoutez une nouvelle variable de texte sécurisée. Définissez le nom sur **MySigningCert.secret** et définissez la valeur du mot de passe pour le certificat. Sélectionnez l’icône de verrouillage pour sécuriser la variable.
1. Ajoutez une tâche **Script Powershell** au pipeline (après l’étape Télécharger le fichier sécurisé et avant l’étape Générer). Fournissez le nom **Affichage** et définissez le Type comme **En ligne**. Copiez et collez ce qui suit dans la section de script.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Ouvrez le fichier **Customization.settings** de **RetailSDK\\BuildTools** et mettez à jour **ModernPOSPackageCertificateThumbprint** avec la valeur d’empreinte de certificat.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Pour plus d’informations sur l’obtention de l’empreinte numérique d’un certificat, voir [récupérer l’empreinte d’un certificat](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Téléchargez ou générez un certificat pour signer manuellement l’application MPOS à l’aide de msbuild dans le SDK

Si un certificat téléchargé ou généré est utilisé pour signer l’application MPOS, la mise à jour du nœud **ModernPOSPackageCertificateKeyFile** dans le fichier **BuildTools\\Customization.settings** pour pointer vers l’emplacement du fichier pfx (**$(SdkReferencesPath)\\appxsignkey.pfx**). Par exemple :

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

Dans ce cas, le nom du fichier de certificat est **appxsignkey.pfx**, situé dans le dossier **Kit de développement logiciel (SDK) Retail\\Référence**.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Utiliser l’empreinte pour signer l’application MPOS

Si vous utilisez l’empreinte numérique pour signer l’application MPOS, installez le certificat localement. Actualisez la valeur d’empreinte dans le nœud **ModernPOSPackageCertificateThumbprint** au sein du fichier **BuildTools\\Customization.settings**.

Cette option fonctionnera si l’utilisateur de construction est un utilisateur local. Cependant, si vous utilisez les agents Azure DevOps pour générer le build, l’agent n’aura peut-être pas l’autorisation d’accéder au magasin de certificats pour utiliser le certificat pour la signature ou la machine de génération n’aura pas le certificat installé. Dans ce cas, la solution consiste à changer l’utilisateur de construction en utilisateur local et à installer le certificat dans la boîte. Cependant, cette option ne fonctionnera pas si vous n’avez pas d’accès administrateur à la zone.

> [!NOTE]
> Si le fichier .pfx ou l’option de tâche Fichier sécurisé est utilisé pour signer l’application, laissez le nœud **ModernPOSPackageCertificateThumbprint** dans **Customization.settings** vide. Si l’option d’empreinte digitale est utilisée, laissez **ModernPOSPackageCertificateKeyFile** vide. Si les deux valeurs sont mises à jour, la génération échouera.

### <a name="certification-renewal"></a>Renouvellement de la certification

### <a name="renew-a-certificate-from-trusted-ca"></a>Renouveler un certificat d’une autorité de certification approuvée

Contactez votre autorité de certification (CA) pour le processus de renouvellement de certificat. Pour un certificat approuvé, aucune action n’est requise du côté MPOS.

### <a name="renew-a-self-signed-certificate"></a>Renouveler un certificat auto-signé

N’utilisez pas l’exemple de certificat disponible dans le SDK Retail pour la production. Il ne peut être utilisé que pour les fins de développement. L’exemple de certificat Contoso ne peut pas être renouvelé et l’exemple de certificat inclus dans Retail SDK version 10.0.16 ou antérieure expirera le 31 décembre 2020. Si ce certificat, ou un certificat auto-signé, a été utilisé pour signer un Modern POS personnalisé, il est fort possible que Modern POS ne fonctionne pas correctement après cette date.
 
### <a name="impact"></a>Impact
 
Si ce qui précède est vrai pour vous, le problème que vous rencontrerez est que le programme d’installation ne pourra pas s’exécuter après le 31 décembre 2020. Selon les politiques informatiques de l’entreprise utilisées, Modern POS peut ne pas être en mesure de fonctionner. Il est essentiel que vous testiez cela en modifiant temporairement la date à une date ultérieure, afin de déterminer l’impact sur votre organisation.
 
### <a name="steps-to-determine-the-issue"></a>Étapes pour déterminer le problème
 
1.  Utilisez les paramètres Windows pour régler l’horloge de l’ordinateur sur une date et une heure en 2021.
2.  Vérifiez que Modern POS peut être ouvert, que la connexion peut avoir lieu et qu’une transaction peut être effectuée.
3.  Vérifiez que le programme d’installation de Modern POS Self-service peut être exécuté et, le cas échéant, que l’installation se terminera avec succès.
4.  Remettez les paramètres d’horloge de Windows à la date et à l’heure correctes.
 
Si vous pouvez effectuer toutes ces étapes sans problème, vous pourrez alors utiliser le certificat actuel après le 31 décembre 2020.  
 
### <a name="steps-going-forward"></a>Étapes à suivre 

Il est fortement recommandé de renouveler le certificat précédemment utilisé. Nous vous recommandons fortement d’obtenir un nouveau certificat. Pour ce faire, vous devez effectuer l’une des actions suivantes :
 
- **Préféré** - Obtenez un certificat de signature de code auprès d’une autorité de certification de confiance.

- **Non préféré** - Générer un certificat de signature de code auto-signé à utiliser. Ceci est généralement utilisé uniquement à des fins de développement au sein d’un domaine et n’est pas recommandé pour la production. 

- **Disponible en tant que solution temporaire** - Utilisez le certificat de signature de code Contoso renouvelé. Ceci est généralement utilisé à des fins de test, il n’est donc pas recommandé de le déployer en production.
 
Ensuite, générez un nouveau package Modern POS personnalisé qui est signé à l’aide de ce certificat obtenu à partir de l’une des actions ci-dessus. Selon le certificat, une des étapes suivantes doit être suivie :
 
- Si vous utilisez un nouveau certificat de confiance (ou un nouveau certificat auto-signé), vous devrez installer un nouveau certificat sur chaque appareil. Après cela, vous devez prendre le package Modern POS nouvellement créé (programme d’installation), désinstaller l’application existante, puis réinstaller le nouveau package Modern POS. Vous devrez effectuer une activation de l’appareil de Modern POS sur chaque appareil.

- Si vous utilisez le certificat Contoso renouvelé, vous devrez installer le nouveau certificat sur chaque appareil et installer le package Modern POS (programme d’installation). Vous n’êtes pas obligé de désinstaller, mais vous devez réinstaller sur l’appareil. Notez que l’activation de l’appareil de Modern POS ne sera pas nécessaire. Cette option est une solution temporaire. N’utilisez cette option que pour éviter la réactivation et résoudre le problème avant d’obtenir un nouveau certificat de confiance.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
