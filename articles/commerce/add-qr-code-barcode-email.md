---
title: Ajouter un code QR ou un code barres dans les e-mails transactionnels et de ticket de caisse
description: Cette rubrique explique comment insérer des codes QR et des codes barres qui représentent les ID de commande dans les e-mails transactionnels et de ticket de caisse dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5f7b349700a4b3b43f818b30bb479e630048e8b8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688963"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Ajouter un code QR ou un code barres dans les e-mails transactionnels et de ticket de caisse

[!include [banner](includes/banner.md)]

Cette rubrique explique comment insérer des codes QR et des codes barres qui représentent les ID de commande dans les e-mails transactionnels et de ticket de caisse dans Microsoft Dynamics 365 Commerce.

Vous pouvez facilement inclure des codes QR et des codes barres dans les e-mails transactionnels pour accélérer le processus de recherche de commande dans un environnement de vente au détail. Pour insérer des codes QR et des codes barres dans des e-mails, vous utilisez une balise HTML **\<img\>** qui demande un code QR ou une image de code barres à un service de génération et d’affichage. Microsoft ne fournit pas ce service. Cependant, il existe de nombreux services gratuits ou peu coûteux qui peuvent diffuser des codes QR ou des codes barres générés dynamiquement en fonction d’une valeur transmise dans une chaîne de requête.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Ajouter un code QR ou un code barres dans un e-mail transactionnel

Pour insérer un code QR ou un code barres dans un e-mail transactionnel envoyé dans le cadre d’un achat en ligne, procédez comme suit.

1. Ouvrez le HTML source du modèle d’e-mail transactionnel et ajoutez une balise HTML **\<img\>** qui pointe vers votre code QR ou votre service de code barres. Voici un exemple :

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Voici une explication de l’exemple précédent :

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** représente le domaine de votre service de code QR ou de code barres.
    - **data** représente le paramètre que le service de code QR ou de code barres utilise pour recevoir le contenu qui doit être affiché sous forme de code QR ou de code barres.

        La valeur **%salesid%** doit être affectée à ce paramètre. Dans cet exemple, notez que la valeur est également utilisée comme texte de remplacement pour l’image.

    - **param1** et **param2** représentent des paramètres facultatifs supplémentaires.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Modèles d’e-mail d’organisation** et téléchargez le code HTML mis à jour dans le modèle d’e-mail transactionnel approprié.

> [!NOTE]
> Les paramètres peuvent différer selon les fournisseurs de services de code QR et de code barres. Par conséquent, assurez-vous de contacter votre fournisseur de services pour confirmer les paramètres auxquels vous devez attribuer des valeurs.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Ajouter un code QR ou un code barres dans un e-mail de ticket de caisse 

Pour insérer un code QR ou un code barres dans un e-mail de ticket de caisse qui peut être envoyé après un achat effectué au point de vente (PDV), procédez comme suit.

1. Ouvrez le HTML source du modèle d’e-mail de ticket de caisse et ajoutez une balise HTML **\<img\>** qui pointe vers votre code QR ou votre service de code barres. Voici un exemple ci-dessous.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Voici une explication de l’exemple précédent :

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** représente le domaine de votre service de code QR ou de code barres.
    - **data** représente le paramètre que le service de code QR ou de code barres utilise pour recevoir le contenu qui doit être affiché sous forme de code QR ou de code barres.

        La valeur **%receiptid%** doit être affectée à ce paramètre. Dans cet exemple, notez que la valeur est également utilisée comme texte de remplacement pour l’image.

    - **param1** et **param2** représentent des paramètres facultatifs supplémentaires.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Modèles d’e-mail d’organisation** et téléchargez le code HTML mis à jour dans le modèle d’e-mail dont l’ID est **emailrecpt**.

> [!NOTE]
> Les paramètres peuvent différer selon les fournisseurs de services de code QR et de code barres. Par conséquent, assurez-vous de contacter votre fournisseur de services pour confirmer les paramètres auxquels vous devez attribuer des valeurs.

## <a name="additional-resources"></a>Ressources supplémentaires

[Envoyer des accusés de réception par e-mail depuis MPOS](email-receipts.md)

[Créer des modèles de messages électroniques pour les événements transactionnels](email-templates-transactions.md)
