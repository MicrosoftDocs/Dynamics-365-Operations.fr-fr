---
title: Activer les notifications d’enregistrement des clients dans le point de vente (PDV)
description: Cette rubrique décrit comment activer les notifications d’enregistrement des clients dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 95b4e3a1750cf072db919492f7445e87654701da
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983159"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Activer les notifications d’enregistrement des clients dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment activer les notifications d’enregistrement des clients dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.

Dans leurs e-mails « commande prête à être ramassée », les organisations peuvent fournir un lien ou un bouton permettant aux clients d’informer le magasin qu’ils sont sur place et qu’ils attendent que leur colis leur soit apporté. Les clients reçoivent ensuite une confirmation d’enregistrement et le magasin reçoit une notification en tant que tâche dans son application de point de vente. Cette tâche permet à un vendeur de livrer la commande au véhicule du client. Par conséquent, le client n’a pas à entrer dans le magasin.

Le workflow d’enregistrement des clients peut également être configuré pour collecter des informations supplémentaires, telles que le numéro de place de parking du client, la marque, le modèle et la couleur de son véhicule et les instructions de livraison. Le préposé au magasin peut utiliser ces informations pour faciliter l’exécution des commandes.

## <a name="enable-customer-check-in"></a>Activer l’enregistrement client

Lorsque la fonction d’enregistrement client est activée, Commerce génère un ID de confirmation de commande (également appelé ID de référence de canal). Il génère également des ID de confirmation de commande pour les commandes créées via des points de vente (PDV) ou des canaux de centre d’appels. 

Pour activer la fonctionnalité d’enregistrement des clients dans Commerce Headquarters, procédez comme suit :

1. Accédez à **Espaces de travail \> Gestion des fonctionnalités**.
2. Recherchez la fonctionnalité **Générer un format d’identifiant de référence de canal cohérent sur tous les canaux**. 
3. Sélectionnez la fonctionnalité, puis, dans le volet des propriétés, sélectionnez **Activer maintenant**. 

## <a name="create-a-check-in-confirmation-page"></a>Créer une page de confirmation d’enregistrement

Sur votre site de commerce électronique, vous devez créer une nouvelle page qui servira pour confirmer l’enregistrement. Grâce à une configuration supplémentaire, la page peut également inclure un formulaire qui recueille d’autres informations auprès des clients pour faciliter l’exécution des commandes. Pour plus d’informations sur la configuration de la page et du module, voir [Module d’enregistrement client](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Configurer le modèle d’e-mail transactionnel

Vous devez ajouter un lien ou bouton **Je suis là** vers le modèle pour l’e-mail transactionnel que les clients reçoivent lorsque leur commande est prête pour le retrait. Les clients utiliseront ce lien ou bouton pour informer le magasin qu’ils sont là pour récupérer leur commande. 

Ajoutez le lien ou le bouton au modèle mappé sur le type de notification **Emballage terminé** et le mode de livraison que vous utilisez pour l’exécution des commandes en retrait à un point-relais. Dans le modèle, créez un lien ou un bouton HTML qui pointe vers l’URL de la page de confirmation d’enregistrement que vous avez créée et qui inclut les noms et les valeurs des paramètres, comme illustré dans l’exemple suivant.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Pour plus d’informations sur la configuration des modèles d’e-mail, consultez [Personnaliser les e-mails transactionnels par mode de livraison](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Une tâche de confirmation d’enregistrement est créée dans le PDV

Une fois qu’un client a informé le magasin qu’il est présent pour le retrait, la page d’enregistrement affiche un message de confirmation et un code QR facultatif contenant l’ID de confirmation de commande du client. Dans le même temps, une tâche est créée dans la liste des tâches du point de vente pour le magasin où le client récupère la commande. Cette tâche contient toutes les informations sur le client et la commande nécessaires pour exécuter la commande. Le champ d’instructions de la tâche affiche toutes les informations collectées auprès du client via le formulaire d’informations supplémentaires.

## <a name="end-to-end-testing"></a>Tests de bout en bout

L’enregistrement du client nécessite que des paramètres et des valeurs spécifiques soient transmis à la page d’enregistrement, puis à l’API d’enregistrement du client. Par conséquent, l’approche la plus simple consiste à tester la fonctionnalité dans un environnement où une commande de test peut être créée et conditionnée. De cette façon, un e-mail de type « Commande prête pour l’enlèvement » peut être généré avec une URL contenant les noms et valeurs des paramètres requis.

Pour tester la fonction d’enregistrement des clients, procédez comme suit.

1. Créez la page d’enregistrement des clients, puis ajoutez et configurez le module d’enregistrement des clients. Pour plus d’informations, voir [Module Enregistrement pour retrait](check-in-pickup-module.md). 
1. Enregistrez la page, mais ne la publiez-la.
1. Ajoutez le lien suivant à un modèle d’e-mail invoqué par le type de notification Emballage terminé pour un mode de livraison Retrait. Pour plus d’informations, voir [Créer des modèles d’e-mail pour les événements transactionnels](email-templates-transactions.md).

    - **Pour les environnements de pré-production (UAT) :** Ajoutez l’extrait de code de la section [Configurer le modèle d’email transactionnel](#configure-the-transactional-email-template) plus haut dans cette rubrique.
    - **Pour les environnements de production :** Ajoutez le code commenté suivant afin que les clients existants ne soient pas affectés.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Créez une commande où le mode de livraison Retrait est spécifié.
1. Lorsque vous recevez l’e-mail déclenché par le type de notification Emballage terminé, testez le flux d’enregistrement en ouvrant la page d’enregistrement contenant l’URL que vous avez ajoutée précédemment. Étant donné que l’URL inclut l’indicateur `&preview=inprogress`, vous serez invité à vous authentifier avant de pouvoir afficher la page.
1. Entrez les informations supplémentaires nécessaires pour configurer le module.
1. Vérifiez que la vue de confirmation d’enregistrement s’affiche correctement.
1. Ouvrez un terminal de PDV pour le magasin où la commande sera récupérée.
1. Sélectionnez la vignette **Commandes à retirer** et vérifiez que la commande apparaît.
1. Vérifiez que toute information supplémentaire qui a été configurée dans le module d’enregistrement apparaît dans le volet de détails.

Après avoir vérifié que la fonction d’enregistrement des clients fonctionne de bout en bout, procédez comme suit.

1. Publiez la page d’enregistrement.
1. Si les tests s’effectuent dans un environnement de production, décommentez l’URL dans le modèle d’e-mail « Commande prête pour l’enlèvement », afin que le lien ou le bouton **Je suis là** s’affiche. Ensuite, réimportez le modèle.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Enregistrement pour retrait](check-in-pickup-module.md)

[Personnalisez les e-mails transactionnels par mode de livraison](customize-email-delivery-mode.md)

[Créer des modèles de messages électroniques pour les événements transactionnels](email-templates-transactions.md)
