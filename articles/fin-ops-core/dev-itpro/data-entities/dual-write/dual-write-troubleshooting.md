---
title: Résolution générale des problèmes
description: Cette rubrique fournit des informations générales sur le dépannage de l’intégration de la double-écriture entre les applications Finance et Opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/07/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 8b5951f9f40179ca0bf31f5cccf1f05a0f968213
ms.sourcegitcommit: 1843235766b6f8cf950a13a310e9f4f2f53c59a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2022
ms.locfileid: "8554597"
---
# <a name="general-troubleshooting"></a>Résolution générale des problèmes

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations générales sur le dépannage de l’intégration de la double-écriture entre les applications Finance et Opérations et Dataverse.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur

Les journaux de suivi peuvent être utiles lors du dépannage de problèmes de synchronisation en direct à double écriture entre Finance & Operations et Dataverse. Les journaux peuvent fournir des détails spécifiques aux équipes qui assurent le support technique et d'ingénierie pour Dynamics 365. Cet article explique comment activer les journaux de suivi et comment les afficher. Les journaux de suivi sont gérés dans la page Paramètres de Dynamics 365 et nécessitent des privilèges de niveau administrateur pour être modifiés et affichés. 

**Rôle requis pour activer le journal de suivi et afficher les erreurs :** Administrateur système

### <a name="turn-on-the-trace-log"></a>Activer le journal de suivi
Pour activer le journal de suivi, procédez comme suit.

1.  Connectez-vous à Dynamics 365 et sélectionnez **Paramètres** dans la barre de navigation supérieure. Sur la page Systèmes, cliquez sur **Administration**.
2.  Sur la page Administration, sélectionnez **Paramètres système**.
3.  Sélectionnez l'onglet **Personnalisation** et le plug-in, puis dans la section de suivi des activités du workflow, changez le menu déroulant en **Tous**. Cela permettra de suivre toutes les activités et fournira un ensemble complet de données aux équipes qui doivent examiner les problèmes potentiels.

> [!NOTE]
> Si vous définissez la liste déroulante sur **Exception**, cela ne fournira d'informations de suivi que lorsque des exceptions (erreurs) se produiront.

Une fois activés, les journaux de suivi du plug-in continueront d'être collectés jusqu'à ce qu'ils soient désactivés manuellement en revenant à cet emplacement et en sélectionnant **Désactivé**.

### <a name="view-the-trace-log"></a>Afficher le journal de suivi
Pour afficher le journal de suivi, procédez comme suit.

1. Sur la page Paramètres de Dynamics 365, sélectionnez **Paramètres** dans la barre de navigation supérieure. 
2. Sélectionnez **Journal de suivi du plug-in** dans la section **Personnalisations** de la page.
3. Vous pouvez rechercher des entrées dans la liste des journaux de suivi, en fonction du nom du type et/ou du nom du message.
4. Ouvrez l'entrée souhaitée pour afficher le journal complet. Le bloc de message dans la section Exécution fournira les informations disponibles pour le plug-in. Si disponibles, les détails de l'exception seront également fournis. 

Vous pouvez copier le contenu des journaux de suivi et les coller dans une autre application comme le Bloc-notes ou d'autres outils pour afficher les journaux ou les fichiers texte pour voir plus facilement tout le contenu. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Activez le mode débogage pour résoudre les problèmes de synchronisation en direct dans les applications Finance et Opérations

**Rôle requis pour afficher les erreurs :** Administrateur système

Des erreurs de double écriture qui proviennent de Dataverse peuvent apparaître dans l’application Finance et Opérations. Pour activer la journalisation détaillée des erreurs, procédez comme suit :

1. Pour toutes les configurations de projet dans l’application Finance et Opérations, il y a un indicateur **IsDebugMode** sur la table **DualWriteProjectConfiguration**.
2. Ouvrez la table **DualWriteProjectConfiguration** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance et Opérations et ajoutez **DualWriteProjectConfiguration** à la fiche. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
3. Définissez **IsDebugMode** sur **Oui** sur le projet.
4. Exécutez le scénario qui génère des erreurs.
5. Les journaux détaillés sont disponibles dans la table **DualWriteErrorLog**.
6. Pour rechercher des données sur le navigateur de table, utilisez le lien suivant : `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, remplaçant `999` comme requis.
7. Mettez à jour à nouveau après [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), qui est disponible pour les mises à jour de plate-forme 37 et versions ultérieures. Si vous avez installé ce correctif, le mode de débogage capturera plus de journaux.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Vérifier les erreurs de synchronisation sur la machine virtuelle pour l’application Finance et Opérations

**Rôle requis pour afficher les erreurs :** Administrateur système

1. Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).
2. Ouvrez le projet LCS que vous avez choisi pour effectuer le test de double écriture.
3. Sélectionnez la vignette **Environnements hébergés dans le cloud**.
4. Utilisez Remote Desktop pour vous connecter à la machine virtuelle pour l’application Finance et Opérations. Utilisez le compte local affiché dans LCS.
5. Ouvrez l’observateur d’événements.
6. Sélectionnez **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**.
7. Consultez la liste des erreurs récentes.

## <a name="dual-write-ui-landing-page-showing-blank"></a>Page de destination de l'interface utilisateur à double écriture vide
Lors de l'ouverture de la page à double écriture dans le navigateur Microsoft Edge ou Google Chrome, la page d'accueil ne se charge pas et vous voyez une page vierge ou une erreur telle que « Une erreur s'est produite ».
Dans Devtools, vous voyez une erreur dans les journaux de la console :

>bundle.eed39124e62c58ef34d2.js:37 DOMException : Impossible de lire la propriété 'sessionStorage' depuis 'Window' : l'accès à ce document est refusé. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) at new t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) at ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) at Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) at jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) at Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) at Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) at Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) at vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) at hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

L'interface utilisateur utilise le « stockage de session » du navigateur pour stocker certaines valeurs de propriété pour le chargement de la page d'accueil. Pour que cela fonctionne, les cookies tiers doivent être autorisés dans le navigateur du site. L'erreur indique que l'interface utilisateur ne peut pas accéder au stockage de session. Il peut y avoir deux scénarios dans lesquels ce problème est rencontré :

1.  Vous ouvrez l'interface utilisateur en mode navigation privée d'Edge/Chrome et les cookies tiers en navigation privée sont bloqués.
2.  Vous avez complètement bloqué les cookies tiers dans Edge/Chrome.

### <a name="mitigation"></a>Atténuation
Les cookies tiers doivent être autorisés dans les paramètres du navigateur.

### <a name="google-chrome-browser"></a>Navigateur Google Chrome
1ère option :
1.  Accédez aux paramètres en entrant chrome://settings/ dans la barre d'adresse, puis accédez à Confidentialité et sécurité -> Cookies et autres données de site.
2.  Sélectionnez « Autoriser tous les cookies ». Si vous ne souhaitez pas le faire, optez pour la deuxième option.

2ème option :
1.  Accédez aux paramètres en entrant chrome://settings/ dans la barre d'adresse, puis accédez à Confidentialité et sécurité -> Cookies et autres données de site.
2.  Si « Bloquer les cookies tiers en mode navigation privée » ou « Bloquer les cookies tiers » est sélectionné, accédez à « Sites qui peuvent toujours utiliser des cookies » et cliquez sur **Ajouter**. 
3.  Ajoutez le nom de votre site d'applications Finance & Operations - https://<votre_instance_FinOp>.cloudax.dynamics.com. Assurez-vous de cocher la case « Tous les cookies, sur ce site uniquement ». 

### <a name="microsoft-edge-browser"></a>Navigateur Microsoft Edge
1.  Accédez à Paramètres -> Autorisations du site -> Cookies et données de site.
2.  Désactivez « Bloquer les cookies tiers ».  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Supprimer un lien et lier un autre environnement Dataverse avec une application Finance et Opérations

**Rôle requis pour dissocier l’environnement :** Administrateur système pour l’application Finance et Opérations ou Dataverse.

1. Connectez-vous à l’application Finance et Opérations.
2. Accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**.
3. Sélectionnez toutes les mises en correspondance en cours d’exécution et sélectionnez **Arrêter**.
4. Cliquez sur **Supprimer le lien avec l’environnement**.
5. Sélectionnez **Oui** pour confirmer l’opération.

Vous pouvez maintenant lier un nouvel environnement.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Impossible d’afficher le formulaire d’informations de ligne de la commande client 

Lorsque vous créez une commande client dans Dynamics 365 Sales, cliquer sur **+ Ajouter des produits** peut vous rediriger vers le formulaire de ligne de commande Dynamics 365 Project Operations. Il n’y a aucun moyen à partir de ce formulaire pour afficher le formulaire de ligne de commande client **Informations**. L’option pour **Informations** n’apparaît pas dans la liste déroulante sous **Nouvelle ligne de commande**. Cela se produit car Project Operations a été installé dans votre environnement.

Pour réactiver l’option de formulaire **Informations**, procédez comme suit :

1. Accédez à la table **Ligne de commande**.
2. Recherchez le formulaire **Informations** sous le nœud de formulaires.
3. Sélectionnez le formulaire **Informations** et cliquez sur **Activer les rôles de sécurité**.
4. Modifiez le paramètre de sécurité sur **Afficher pour tout le monde**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Comment activer et enregistrer le suivi du réseau afin que le suivi puisse être joint aux tickets de support

L’équipe du support technique peut avoir besoin d’examiner le suivi du réseau pour résoudre certains problèmes. Pour créer un suivi du réseau, procédez comme suit :

### <a name="google-chrome-browser"></a>Navigateur Google Chrome

1. Dans l’onglet ouvert, appuyez sur **F12** ou choisissez **Outils de développement** pour ouvrir les outils de développement.
2. Ouvrez l’onglet **Réseau** et saisissez **entier** dans la zone de texte du filtre.
3. Exécutez votre scénario et observez les demandes enregistrées.
4. Faites un clic droit sur les entrées et sélectionnez **Enregistrer tout en tant que HAR avec contenu**.

### <a name="microsoft-edge-browser"></a>Navigateur Microsoft Edge

1. Dans l’onglet ouvert, appuyez sur **F12** ou choisissez **Outils de développement** pour ouvrir les outils de développement.
2. Ouvrez l’onglet **Réseau**.
3. Exécutez votre scénario.
4. Sélectionnez **enregistrer** pour exporter les résultats au format HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
