---
title: Application Store Commerce pour les plateformes mobiles
description: Cet article explique comment commencer à utiliser l’application Store Commerce Microsoft Dynamics 365 Commerce pour Android et iOS.
author: stuharg
ms.date: 10/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: 1f07a130629863ebd9d036378436cf360e90ac26
ms.sourcegitcommit: 98231ff810f41f9fcdc6b536d87e453028aa6db8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "9642338"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Application Store Commerce pour les plateformes mobiles

[!include [banner](../includes/banner.md)]

Cet article explique comment commencer à utiliser les applications Store Commerce Microsoft Dynamics 365 Commerce pour Android et iOS.

Les applications mobiles Dynamics 365 Commerce pour Android et iOS rendent le processus de déploiement d’appareils de point de vente (POS) mobiles complets pour votre environnement de vente au détail simple et direct. Les applications mobiles Store Commerce offrent toutes les fonctionnalités et avantages de [l’application Store Commerce pour Windows](store-commerce.md) sur les facteurs de forme du téléphone et de la tablette. Les applications mobiles Store Commerce peuvent être installées directement à partir des magasins d’applications App Store et Google Play, et ne nécessitent pas qu’un développeur crée un package d’application pour les déployer ou les mettre à jour. 

Les applications mobiles Store Commerce conservent une parité fonctionnelle complète avec les applications hybrides Retail actuelles. De plus, Store Commerce pour iOS inclut la prise en charge d’une station matérielle dédiée, afin que les appareils iOS puissent communiquer avec des terminaux de paiement en réseau, des imprimantes de reçus et des tiroirs-caisses sans nécessiter le déploiement d’une station matérielle partagée. 

> [!IMPORTANT]
> Les applications Store Commerce pour Windows, Android et iOS sont la prochaine génération d’applications de point de vente pour Dynamics 365 Commerce. L’application Modern POS (MPOS) actuelle et les [applications hybrides Retail](hybridapp.md) pour mobile seront obsolètes en octobre 2023. Microsoft vous recommande d’utiliser Store Commerce ou Cloud POS (CPOS) pour tous les nouveaux déploiements POS. Les clients existants doivent prévoir de migrer de l’application hybride Retail vers Store Commerce. Pour plus d’informations sur le calendrier d’obsolescence de MPOS et des applications hybrides Retail, consultez [Moderniser la pile technologique en magasin Dynamics 365 Commerce](https://www.microsoft.com/download/details.aspx?id=103896). 

## <a name="app-architecture"></a>Architecture de l’application

Les applications mobiles Store Commerce utilisent la même topologie que l’application Store Commerce pour Windows quand elle est déployée en mode hybride. Les applications mobiles Store Commerce sont des applications d’interpréteur de commandes qui restituent le CPOS directement à partir de la Commerce Scale Unit (CSU) et se connectent au siège du commerce administré à distance et Commerce headquarters via la CSU. Le modèle d’application d’interpréteur de commandes permet aux applications Store Commerce de prendre en charge une station matérielle dédiée pour une intégration directe avec un terminal de paiement, une imprimante, un tiroir-caisse et d’autres périphériques. Il n’est pas nécessaire de configurer une station matérielle partagée pour utiliser des périphériques matériels. 

Pour mettre à jour une application mobile Store Commerce, il suffit de mettre à jour la CSU. Toutes les nouvelles fonctionnalités et fonctionnalités du point de vente seront automatiquement récupérées par l’application. Pour plus d’informations sur la façon de mettre à jour la CSU, voir [Appliquer les mises à jour et les extensions à Commerce Scale Unit (cloud)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Les applications d’interpréteur de commandes sont desservies via les mises à jour du magasin d’applications. Quand une version mineure atteint la disponibilité générale (DG), Microsoft la publie dans les magasins d’applications. Microsoft peut également publier des correctifs entre les mises à jour de versions mineures pour publier des correctifs de bogues hautement prioritaires.

## <a name="prerequisites"></a>Logiciels requis

Les applications mobiles Store Commerce nécessitent Dynamics 365 Commerce, en particulier Commerce headquarters et les composants CSU. Le tableau suivant répertorie les versions minimales du système d’exploitation (SE) et de la CSU requises par les applications mobiles Android et iOS. 

| Logiciel requis | Android      | iOS  |
| ------------ | ------------ | ---- |
| Version du système d’exploitation   | 7,0          | 15.0 |
| Version de la CSU  | 9.38.22266.8 | À CALCULER  |

## <a name="install-the-app"></a>Installer l’application

Vous pouvez installer les applications mobiles Store Commerce directement depuis Google Play Store ou l’App Store Apple. 

- [Application Store Commerce pour Android](https://aka.ms/storecommerceandroid)
- Application Store Commerce pour iOS (bientôt disponible)

L’application Android (.apk) et les packages d’application Apple (.ipa) peuvent également être téléchargés à partir de la bibliothèque de ressources partagées dans Lifecycle Services Microsoft Dynamics. 

## <a name="device-and-register-setup"></a>Paramétrage de caisse enregistreuse et de périphérique

Avant qu’un registre puisse être activé sur les applications mobiles Store Commerce, vous devez configurer un appareil et une caisse enregistreuse dans Commerce headquarters. Pour plus d’informations, voir [Caisses enregistreuses et périphériques](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Paramètres de périphérique

Pour créer et paramétrer un périphérique, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration de canal \> Configuration du PDV \> Périphériques**. 
1. Créez un appareil et sélectionnez **Modern POS – Android** ou **Modern POS – iOS** comme type d’application, selon l’application mobile que vous déployez. 

    > [!NOTE] 
    > Les types d’application **Modern POS – Android** et **Modern POS – iOS** sont également utilisés pour déployer les applications hybrides actuelles pour Android et iOS. Après l’abandon de MPOS, les libellés de ces types d’application seront mis à jour pour **Store Commerce – Android** et **Modern POS – iOS**. 

### <a name="register-setup"></a>Paramétrage du registre

Vous pouvez créer une caisse enregistreuse et l’associer au périphérique que vous avez créé, ou vous pouvez associer une caisse enregistreuse existante à votre nouveau périphérique. Pour plus d’informations sur les caisses enregistreuses, voir [Créer et associer des caisses enregistreuses](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Configuration de la disposition de l’écran

Si vous réaffectez une disposition d’écran incluse dans les données de démonstration fournies avec votre licence Dynamics 365 Commerce, l’application Store Commerce sélectionnera automatiquement la disposition compacte incluse si la résolution d’écran de votre appareil est inférieure à 480 &times; 853 pixels en orientation portrait. Toutefois, si vous créez une disposition d’écran à partir de rien ou si votre appareil mobile utilise une résolution supérieure à celle prise en charge par la disposition compacte, assurez-vous de créer une résolution et des grilles de boutons associées adaptées au téléphone ou à la tablette que vous prévoyez d’utiliser pour le déploiement. Pour plus d’informations sur les configurations de disposition d’écran, voir [Configurations visuelles de l’interface utilisateur du PDV](../pos-screen-layouts.md). 

Une fois les appareils et les caisses enregistreuses configurés, dans Commerce headquarters, accédez à **Vente au détail et commerce \> ID de vente au détail et commerce \> Horaires de distribution**, et exécutez la tâche des caisses enregistreuses.

## <a name="activate-a-device"></a>Activer un périphérique

Pour activer un périphérique sur une application mobile Store Commerce, procédez comme suit.

1. Ouvrez l’application sur l’appareil mobile.
1. Entrez l’URL CPOS, que vous pouvez trouver sur la page des détails de l’environnement dans Lifecycle Services, ou sur la page **Profils de canal** dans Commerce headquarters (**Vente au détail et commerce \> Configuration du canal \> Profils de canal**).
1. Connectez-vous en utilisant les informations d’identification d’un collaborateur autorisé à gérer les appareils.
1. Sélectionnez le magasin associé à la caisse enregistreuse que vous avez créée ou réutilisée dans Commerce headquarters.
1. Sélectionnez la caisse enregistreuse associée au périphérique créé dans Commerce headquarters.
1. Votre appareil devrait maintenant être activé. Vous pouvez vous connecter à la caisse enregistreuse en utilisant l’ID opérateur et le mot de passe du collaborateur associé au magasin que vous avez sélectionné. 

Pour plus d’informations sur l’activation de l’appareil, voir [Activation de l’appareil au point de vente (PDV)](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Parité des fonctionnalités avec Store Commerce pour Windows

Le tableau suivant compare les fonctionnalités de l’application Store Commerce sur les plateformes Windows, Android et iOS.

| Fonction                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Station matérielle dédiée                                                            | Oui     | Oui     | Oui |
| Station matérielle partagée                                                               | Oui     | Oui     | Oui |
| Communication avec des périphériques en réseau (terminal de paiement, imprimante et tiroir-caisse) | Oui     | Oui     | Oui |
| Périphériques OLE pour point de vente (OPOS) via une station matérielle locale             | Oui     | Non      | Non  |
| Mode hors connexion                                                                          | Oui     | Non      | Non  |

## <a name="additional-resources"></a>Ressources supplémentaires

[Application Store Commerce](store-commerce.md)

[Choisir entre Store Commerce et Cloud POS](../mpos-or-cpos.md)

[Résoudre les problèmes de configuration et d’installation de Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
