---
title: Activer les notifications d’enregistrement des clients dans le point de vente (PDV)
description: Cette rubrique décrit comment activer les notifications d’enregistrement des clients dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
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
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271423"
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

Ajoutez le lien ou le bouton au modèle mappé sur le type de notification **Emballage terminé** et le mode de livraison que vous utilisez pour l’exécution des commandes en retrait à un point-relais. Dans le modèle, créez un lien ou un bouton HTML qui pointe vers l’URL de la page de confirmation d’enregistrement que vous avez créée. Voici un exemple :

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Pour plus d’informations sur la configuration des modèles d’e-mail, consultez [Personnaliser les e-mails transactionnels par mode de livraison](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Une tâche de confirmation d’enregistrement est créée dans le PDV

Une fois qu’un client a informé le magasin qu’il est présent pour le retrait, il reçoit une notification de confirmation d’enregistrement et une tâche est créée dans la liste des tâches dans le PDV du magasin où le client récupère la commande. La tâche contient toutes les informations sur le client et la commande nécessaires pour exécuter la commande. Dans la tâche, le champ d’instructions affiche toutes les informations collectées auprès du client via le formulaire d’informations supplémentaires. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Enregistrement pour retrait](check-in-pickup-module.md)
