---
title: Création manuelle de commandes de service
description: Vous pouvez créer des commandes de service manuellement à l’aide d’un accord de service ou de l’écran **Commandes de service**.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05c03cd07599c5ee2e739a785896888c8cfe8822e57529f7603783a2f011c97c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740645"
---
# <a name="create-service-orders-manually"></a>Création manuelle de commandes de service    

[!include [banner](../includes/banner.md)]


Vous pouvez créer des commandes de service manuellement à l’aide d’un accord de service ou de l’écran **Commandes de service**. Vous pouvez également créer une commande de service à partir d’un projet.

> [!TIP]
> <P>Vous pouvez utiliser des processus automatisés pour créer des commandes de service. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Création manuelle d’une commande de service à partir d’un accord de service

1.  Sélectionnez **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.

2.  Sélectionnez un accord de service ou créez-en un nouveau.

3.  Cliquez sur l’onglet **Livrer** et, dans le groupe **Créer**, sélectionnez **Commandes de service prévisionnelles** pour ouvrir le formulaire **Créer des commandes de service**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Création manuelle d’une commande de service dans l’écran Commandes de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Sélectionnez **Nouveau** pour créer un ordre de service.

3.  Créez les lignes d’ordre de service pour la commande de service.

> [!NOTE]
> <P>Si la case à cocher <STRONG>Autoriser sans accord de service</STRONG> de l’écran <STRONG>Paramètres de gestion des services</STRONG> est activée, vous pouvez valider les transactions à partir des lignes de commande de service sans lier la commande de service à un accord de service. Si la case à cocher est désactivée, vous devez au moins lier la commande de service créée manuellement à un projet avant de valider les lignes de commande de service.</P>

## <a name="create-a-service-order-from-a-project"></a>Création d’une commande de service à partir d’un projet

1.  Accédez à **Gestion et comptabilité des projets** \> **Commun** \> **Projets** \> **Tous les projets**.

2.  Dans le formulaire **Projets**, dans le volet **Actions**, cliquez sur l’onglet **Gérer** \> **Service** \> **Commandes de service**.

3.  Suivez la procédure précédente de création manuelle d’une commande de service dans l’écran **Commandes de service**. Le champ **ID projet** affiche la référence du projet.

> [!NOTE]
> <P>Si la case à cocher <STRONG>Autoriser sans accord de service</STRONG> de l’écran <STRONG>Paramètres de gestion des services</STRONG> est activée, vous pouvez valider les transactions à partir des lignes de commande de service sans lier la commande de service à un accord de service. Si la case à cocher est désactivée, vous devez au moins lier la commande de service créée manuellement à un projet avant de valider les lignes de commande de service.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Création d’une commande de service à partir de l’écran Commande client

Vous pouvez créer une commande de service dans l’écran **Commandes client** à l’aide de l’Assistant **Créer une nouvelle commande de service basée sur la commande client**.

1.  Accédez à **Ventes et marketing** \> **Commun** \> **Commandes client** \> **Toutes les commandes client**.

2.  Ouvrez les commandes clients concernées.

3.  Sous l’onglet **Commande client**, cliquez sur **Commande de service** pour démarrer l’Assistant **Créer une commande de service basée sur la commande client**.

4.  Cliquez sur **Suivant \>**, puis effectuez les étapes suivantes dans la page **Sélectionner l’accord pour la commande de service** :
    
      - Le champ **Accord de service** permet de sélectionner l’accord de service auquel la nouvelle commande de service doit être associée.
    
      - Facultatif : le champ **ID projet** permet d’associer cette commande de service à un projet particulier.

5.  Cliquez sur **Suivant \>**, puis effectuez les étapes suivantes dans la page **Créer une commande de service** :
    
      - Dans le champ **Durée de service préférée**, entrez une date et une heure pour le début de l’appel de service.
    
      - Facultatif : modifiez le texte dans le champ **Description**. Par défaut, ce champ contient la description de l’accord de service sélectionné dans la page précédente.
    
      - Dans le champ **Responsable**, sélectionnez l’ID de l’employé responsable de l’accord, puis, si vous le connaissez, entrez l’ID du technicien favori du client pour l’appel de service.
    
      - Dans le champ **ID contact**, sélectionnez la personne à contacter au sein de la société du client concernant cette commande de service.

6.  Sélectionnez **Suivant \>**, puis **Terminer**.


## <a name="see-also"></a>Voir également :

[Commandes de service](service-orders.md)

[Créer automatiquement des commandes de service](create-service-orders-automatically.md)

[Créer des commandes de service (écran classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]