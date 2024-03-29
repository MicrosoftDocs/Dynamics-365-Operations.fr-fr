---
title: Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen
description: Cet article fournit des conseils de résolution des problèmes qui peuvent vous aider à obtenir de l’aide lorsque vous rencontrez des problèmes avec le connecteur de paiement Microsoft Dynamics 365 pour Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 687f2fdff5e29cc25fae911b015164f0d90aee88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268863"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent vous aider à obtenir de l’aide lorsque vous rencontrez des problèmes avec le connecteur de paiement Microsoft Dynamics 365 pour Adyen.

## <a name="description"></a>Description

Vous rencontrez des problèmes avec le connecteur de paiement Dynamics 365 pour Adyen dans les domaines suivants et vous avez besoin de l’assistance de l’équipe Adyen :

- Configuration du point de vente (PDV), du point de vente moderne (MPOS), du centre d’appels ou de Dynamics 365 Commerce
- Numéro de référence du fournisseur de services de paiement Adyen (par exemple, si vous avez des questions sur les refus, y compris les refus \[MKE\] de saisie manuelle avec les touches)
- Tout ce qui ne fonctionne pas dans les environnements de test ou de prestataires en direct

## <a name="resolution"></a>Résolution

Utilisez le modèle d’e-mail suivant pour démarrer le processus d’assistance avec l’équipe Adyen. Pour accélérer la résolution des problèmes, assurez-vous que l’e-mail contient tous les détails requis.

| Champ        | Valeur |
|--------------|-------|
| Destination           | `support@adyen.com` |
| Cc           | |
| Ligne d’objet | Microsoft Dynamics Support Request |
| Corps         | <p>Chers membres du support,</p><p>Merci de nous aider concernant le problème suivant :</p><ul><li>Compte de marchand</li><li>Environnement (Test/Prod)</li><li>Canal (PDV/Centre d’appels/e-commerce Commerce)</li><li>Numéro de référence PSP, si le problème concernait une transaction spécifique (vous pouvez trouver le numéro de référence PSP sur le reçu, dans l’Espace client Adyen ou dans le menu des transactions du terminal de PDV.)</li><li>Capture d’écran ou photo du message d’erreur, le cas échéant</li><li>Journaux de l’Observateur d’événements (au format .txt)</li><li>Description du problème et étapes de résolution des problèmes que vous avez essayées</li></ul> |

## <a name="additional-resources"></a>Ressources supplémentaires

[Accepter les paiements avec le connecteur Adyen pour Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Connecteur de paiement Dynamics 365 pour Adyen](../dev-itpro/adyen-connector.md)

[Configurer le connecteur de paiement Adyen pour Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
