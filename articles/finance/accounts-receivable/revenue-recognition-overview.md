---
title: Présentation de la prise en compte de revenu (contient une vidéo)
description: Cet article fournit des informations sur la fonctionnalité de prise en compte de revenu. Elle offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l’échéancier de produit pour les commandes comportant plusieurs éléments.
author: bking
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5bf07356b5613f438034f8dabac7db197e69a6c8
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644028"
---
# <a name="revenue-recognition-overview"></a>Vue d’ensemble de la fonctionnalité de prise en compte de revenu

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Cette fonctionnalité sera obsolète en octobre 2023, les nouveaux utilisateurs doivent utiliser la facturation de l’abonnement.

Les sociétés qui ont de multiples prestations (comme des produits, des services, des abonnements, etc.), doivent pouvoir éclater les commandes comportant plusieurs éléments afin que le produit puisse être identifié selon un ensemble d’instructions spécifiques et propres au secteur.

La fonctionnalité de prise en compte de revenu (y compris la fonctionnalité groupée), n’est pas prise en charge pour une utilisation dans les canaux commerciaux (commerce électronique, PDV, centre d’appels). Les articles configurés avec la fonctionnalité de prise en compte de revenu ne doivent pas être ajoutés aux commandes ou aux transactions créées dans les canaux commerciaux.

En général le processus de prise en compte de revenu peut être utilisé pour réaliser les tâches suivantes :

* Répartir le produit, pour aider à garantir que le prix approprié est bien constaté en fonction de la valeur des composants sur les commandes à plusieurs éléments.
* Différer le produit, selon un échéancier de produit qui représente le calendrier et les pourcentages contractuels pour constater le produit au fil du temps.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

La vidéo [Utilisation de la constatation du produit dans Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (affichée ci-dessus) est incluse dans la [liste de lecture des applications de finances et d’opérations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

La fonctionnalité de constatation du produit offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l’échéancier de produit.

Les produits lancés permettent de prendre en charge la prise en compte de revenu dans les documents de commande client. Les produits lancés contiennent le paramétrage requis pour déterminer le prix et l’échéancier de produit. La commande client peut provenir d’un projet en régie.

Les sociétés peuvent utiliser la fonctionnalité d’échéancier de produit sans utiliser la fonctionnalité de prix du produit. Par conséquent, le prix sur les lignes de commande client est utilisé comme produit ou comme produit différé. Si un échéancier de produit existe sur la ligne de commande client, le prix sur la ligne de commande client est différé. S’il n’existe pas d’échéancier de produit dans la ligne de commande client, le prix est validé dans un compte de produit au moment de la facturation.

Le prix du produit est calculé lors de la confirmation de la commande client ou lors de la validation de la facture. Pour afficher un aperçu du prix du produit avant la validation de la facture, vous devez confirmer la commande client.

Lorsque la commande client est confirmée, un échéancier de produit prévu est également créé si une ligne de commande comporte un échéancier de produit. Lorsque la commande client est facturée, l’échéancier de produit prévu est supprimé et remplacé par l’échéancier de prise en compte de revenu réels.

Les détails de l’échéancier de prise en compte de revenu sont conservés pour chaque ligne de commande client. Par conséquent, le responsable de prise en compte de revenu peut afficher les détails et peut libérer des lignes du produit une fois l’obligation contractuelle accomplie. À la fin de chaque période, le responsable de prise en compte de revenu peut créer un journal de produit pour débloquer toutes les lignes de l’échéancier qui arrivent à échéance à cette date ou avant une date qu’il a définie. Ce journal de produit n’est pas validé immédiatement. Par conséquent, le responsable de prise en compte de revenu peut vérifier que des montants corrects sont bien émis entre le produit différé et le produit réel.

Si une modification contractuelle entraîne l’ajout d’une nouvelle ligne de commande client à la commande client existante ou à une nouvelle commande client, un processus de redistribution peut être exécuté pour corriger le prix du produit dans toutes les lignes des commandes client.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

