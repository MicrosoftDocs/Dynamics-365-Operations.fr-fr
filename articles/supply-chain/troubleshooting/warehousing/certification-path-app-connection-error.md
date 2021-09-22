---
title: Erreur de chemin de certification lors de la configuration de la connexion à l'application
description: Si l'application Warehouse Management affiche l'erreur « Ancre de confiance pour le chemin de certification introuvable », utilisez cette page pour résoudre ou contourner le problème.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476339"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Ancre de confiance pour le chemin de certification introuvable lors de la configuration de la connexion à l'application

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de vous connecter à Supply Chain Management, l'application Warehouse Management peut afficher le message d'erreur suivant :

> java.security.cert.certPathValidatorException : L’ancre validé pour le chemin de certification est introuvable.

Ce problème peut affecter les appareils avec les propriétés suivantes :

- **Version du système d'exploitation** : Android 4.4.x (comme Zebra TC55). Ce problème ne concerne pas les version Android récentes.
- **Emplacement de Supply Chain Management** : cloud
- **Mode de connexion** : Secret client ou certificat

## <a name="possible-cause"></a>Raison possible

Microsoft a peut-être mis à jour les certificats SSL du serveur utilisés par Supply Chain Management. Par conséquent, le certificat racine et/ou l'un des certificats intermédiaires peuvent avoir changé, de sorte que le nouveau certificat ne figure pas sur la liste des certificats système de confiance pour l'appareil mobile. Les versions plus récentes de Android mettent à jour automatiquement les listes de certificats de confiance, mais Android 4.4.x ne le fait pas.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, exécutez l'une des opérations suivantes :

- Utilisez la solution de contournement décrite dans la section suivante pour mettre à jour chaque appareil concerné.
- Il *peut* être possible de contacter Zebra ou Google pour obtenir une mise à jour des certificats de l'autorité de confiance de certification (CA) du système. Nous ne l'avons cependant pas vérifié.
- Si possible, envisagez de remplacer les appareils plus anciens par des appareils exécutant une version plus récente de Android (où les certificats de confiance CA sont mis à jour automatiquement).

### <a name="workaround"></a>Solution de contournement

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Étape 1 : exportez le nouveau certificat racine depuis Supply Chain Management

Téléchargez manuellement le nouveau certificat racine à l'aide de votre navigateur Internet en procédant comme suit :

1. Connectez-vous à Dynamics Supply Chain Management et ouvrez la page d'accueil.

1. Dans la barre d'adresse de votre navigateur, sélectionnez l'icône de verrouillage pour ouvrir la boîte de dialogue **L'emplacement est sécurisé**.
1. Dans la boîte de dialogue, sélectionnez **Certificat (valide)** pour ouvrir la fenêtre **Certificat** pour ce certificat.
1. Ouvrez l'onglet **Chemin de certification** de la fenêtre **Certificat**.
1. Sélectionnez le certificat qui s'affiche en haut de la hiérarchie. (il s'agit du certificat racine).
1. Ouvrez l'onglet **Détails** de la fenêtre **Certificat**.
1. Sélectionnez le bouton **Copier dans un fichier** en bas de l'onglet **Détails**.
1. L'**Assistant d'exportation de certificat** s'ouvre. Sélectionnez **Suivant** pour continuer.
1. La page **Format de fichier d'exportation** s'ouvre. Sélectionnez **Binaire codé DER X.509 (.CER)**. Sélectionnez ensuite **Suivant** pour continuer.
1. La page **Fichiers à exporter** s'ouvre ; spécifiez un nom de fichier et un emplacement. Sélectionnez ensuite **Suivant** pour continuer.
1. La page **Exécution de l'assistant d'exportation de certificat** s'ouvre, affichant le résultat de votre exportation. Sélectionnez **Terminer**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Étape 2 : Installez le certificat téléchargé sur les appareils concernés

Installez le certificat téléchargé en procédant comme suit :

1. Transférez le certificat que vous avez téléchargé à l'étape précédente à l'appareil que vous souhaitez mettre à jour. Par exemple, vous pouvez utiliser une carte SD ou une connexion réseau pour rendre le fichier disponible sur votre appareil.
1. Ouvrez les paramètres de sécurité de votre appareil et choisissez l'option de menu pour installer un certificat à partir d'un fichier. (Les étapes exactes varient en fonction de l'appareil et de la version du système d'exploitation.)
1. Le nouveau certificat devrait maintenant apparaître sur l'onglet **Utilisateur** des certificats de confiance.
1. Répétez cette procédure pour chaque appareil concerné.
