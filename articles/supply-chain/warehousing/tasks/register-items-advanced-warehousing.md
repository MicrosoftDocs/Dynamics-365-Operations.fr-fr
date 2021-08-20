---
title: Enregistrer des articles pour un article activé pour l’entreposage avancé à l’aide d’un journal des arrivées d’articles
description: Cette rubrique présente un scénario montrant comment enregistrer des articles à l’aide des journaux d’arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9f7a4df39fbf6e2bbdba16f953fa519b239dd9debef6efe55cd6b85d10e36b9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741187"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Enregistrer des articles pour un article activé pour l’entreposage avancé à l’aide d’un journal des arrivées d’articles

[!include [banner](../../includes/banner.md)]

Cette rubrique présente un scénario montrant comment enregistrer des articles à l’aide des journaux d’arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts. Cette opération est généralement effectuée par la personne qui s’occupe de la réception.

## <a name="enable-sample-data"></a>Activer les exemples de données

Pour exécuter ce scénario à l’aide des exemples d’enregistrements et des valeurs spécifiés dans cette rubrique, vous devez utiliser un système sur lequel les données de démonstration standard sont installées et vous devez sélectionner l’entité juridique *USMF* avant de commencer.

Vous pouvez aussi explorer ce scénario en substituant des valeurs à partir de vos propres données, à condition que vous disposiez des données suivantes :

- Vous devez avoir une commande fournisseur confirmée avec une ligne de commande ouverte.
- L’article de la ligne doit être stocké. Elle ne doit pas utiliser de variantes de produit et ne doit pas avoir de dimensions de suivi.
- L’article doit être associé à un groupe de dimensions de stockage pour lequel les processus de gestion des entrepôts ont activés.
- L’entrepôt utilisé doit être activé pour les processus de gestion des entrepôts et l’emplacement que vous utilisez pour la réception doit être contrôlé par un contenant.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Créer un en-tête de journal des arrivées d’articles qui utilise la gestion de l’entrepôt

Le scénario suivant montre comment créer un en-tête de journal des arrivées d’articles qui utilise la gestion de l’entrepôt :

1. Assurez-vous que votre système contient une commande fournisseur confirmée qui remplit les conditions décrites dans la section précédente. Ce scénario utilise une commande fournisseur pour l’entreprise *USMF*, compte fournisseur *1001*, entrepôt *51*, avec une ligne de commande pour *10 PL* (10 palettes) du numéro d’article *M9200*.
1. Prenez note du numéro de la commande fournisseur que vous utiliserez.
1. Accédez à **Gestion des stocks\> Entrées de journal \> Arrivée d’articles \> Arrivée d’articles**.
1. Sélectionnez **Nouveau** dans le volet Actions.
1. La boîte de dialogue **Créer un journal de gestion d’entrepôt** s’ouvre. Sélectionnez un nom de journal dans le champ **Nom**.
    - Si vous utilisez les données de démonstration *USMF*, sélectionnez *WHS*.
    - Si vous utilisez vos propres données, le journal que vous choisissez doit avoir **Vérifier l’emplacement de prélèvement** défini sur *Non* et **Gestion des contrôles** défini sur *Non*.
1. Définissez **Référence** sur *Commande fournisseur*.
1. Définissez **Numéro de compte** sur *1001*.
1. Définissez **Numéro** sur le numéro de la commande fournisseur que vous avez identifiée pour cet exercice.

    ![Journal des arrivées d’articles.](../media/item-arrival-journal-header.png "Journal des arrivées d’articles")

1. Sélectionnez **OK** pour créer l’en-tête du journal.
1. Dans la section **Lignes de journal**, sélectionnez **Ajouter une ligne** et entrez les données suivantes :
    - **Numéro d’article** : défini sur *M9200*. Les éléments **Site**, **Entrepôt** et **Quantité** seront définis en fonction des données de transaction d’inventaire pour les 10 palettes (1000 unités chaque).
    - **Emplacement** : défini sur *001*. Cet emplacement spécifique ne suit pas les contenants.

    ![Ligne du journal des arrivées d’articles.](../media/item-arrival-journal-line.png "Ligne du journal des arrivées d’articles")

    > [!NOTE]
    > Le champ **Date** détermine la date à laquelle la quantité disponible de cet article sera enregistrée dans le stock.  
    >
    > L’**ID de lot** sera renseigné par le système s’il peut être identifié de manière unique à partir des informations fournies. Sinon, vous devrez le saisir manuellement. Il s’agit d’un champ obligatoire, qui lie cet enregistrement à une ligne spécifique d’un document source.  

1. Dans le volet Action, sélectionnez **Valider**. Cela vérifie que le journal est prêt à être validé. Si la validation échoue, vous devrez corriger les erreurs avant de pouvoir valider le journal.  
1. La boîte de dialogue **Vérifier le journal** s’ouvre. Cliquez sur **OK**.
1. Examinez la barre de messages. Il doit y avoir un message indiquant que l’opération a abouti.  
1. Sélectionnez **Valider** dans le volet Actions.
1. La boîte de dialogue **Valider le journal** s’ouvre. Cliquez sur **OK**.
1. Examinez la barre de messages. Il doit y avoir un message indiquant que l’opération a réussi.
1. Sélectionnez **Fonctions> Accusé de réception des produits** dans le volet Actions pour mettre à jour la ligne de commande fournisseur et valider un accusé de réception de marchandises.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
