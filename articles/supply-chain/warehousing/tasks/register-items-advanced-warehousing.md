---
title: Enregistrer des articles pour un article activé pour l'entreposage avancé à l'aide d'un journal des arrivées d'articles
description: Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 392884d2a87c10a5f38bf6f51967f879c68c1ca6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355493"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Enregistrer des articles pour un article activé pour l'entreposage avancé à l'aide d'un journal des arrivées d'articles

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts. Cette opération est généralement effectuée par la personne qui s'occupe de la réception. 

Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Vous devez avoir une commande fournisseur confirmée avec une ligne de commande fournisseur en cours avant de lancer ce guide. L'article de la ligne doit être stocké et il ne doit ni utiliser les variantes de produit ni avoir des dimensions de suivi. Et l'article doit être associé à un groupe de dimensions de stockage compatible avec les processus de gestion des entrepôts. L'entrepôt utilisé doit être activé pour les processus de gestion des entrepôts et l'emplacement que vous utilisez pour la réception doit être contrôlé par un contenant. Si vous utilisez USMF, vous pouvez utiliser le Compte société 1001, l'entrepôt 51 et l'article M9200 pour créer la CF. 

Notez le numéro de la commande fournisseur que vous créez, et notez également le numéro d'article et le site que vous avez utilisé pour la ligne de commande fournisseur.


## <a name="create-an-item-arrival-journal-header"></a>Créer un en-tête du journal des arrivées d'articles
1. Accédez à Arrivée d'articles.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
    * Si vous utilisez USMF, vous pouvez taper WHS. Si vous utilisez d'autres données, le journal dont vous choisissez le nom doit avoir les propriétés suivantes : Vérifier l'emplacement de prélèvement doit être définie sur Non et Gestion des contrôles doit être définie sur Non.  
4. Tapez une valeur dans le champ Nombre.
5. Tapez une valeur dans le champ Site.
    * Sélectionnez le site que vous avez utilisé pour votre ligne de commande fournisseur. Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal. Si vous avez utilisé l'entrepôt 51 dans USMF, choisissez le site 5.  
6. Tapez une valeur dans le champ Entrepôts.
    * Sélectionnez un entrepôt valide pour le site sélectionné. Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal. Si vous utilisez les valeurs d'exemple de USMF, sélectionnez 51.  
7. Dans le champ Emplacement, tapez une valeur.
    * Sélectionnez un emplacement valide dans l'entrepôt sélectionné. L'emplacement doit être associé à un profil d'emplacement, qui est contrôlé par le contenant. Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal. Si vous utilisez les valeurs d'exemple de USMF, sélectionnez Bulk-008.  
8. Cliquez avec le bouton droit sur la flèche de déroulement dans le champ Contenant, puis sélectionnez Afficher les détails.
9. Cliquez sur Nouveau.
10. Tapez une valeur dans le champ Contenant.
    * Notez la valeur.  
11. Cliquez sur Enregistrer.
12. Fermez la page.
13. Tapez une valeur dans le champ Contenant.
    * Entrez la valeur du conteneur que vous venez de créer. Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal.  
14. Cliquez sur OK.

## <a name="add-a-line"></a>Ajouter une ligne
1. Cliquez sur Ajouter une ligne.
2. Tapez une valeur dans le champ Numéro d'article.
    * Entrez le numéro d'article que vous avez utilisé dans la ligne de commande fournisseur.  
3. Dans le champ Quantité, entrer un numéro.
    * Entrez la quantité que vous souhaitez enregistrer.  
    * Le champ Date détermine la date à laquelle la quantité disponible de cet article sera enregistrée dans le stock.  
    * L'ID de lot sera renseigné par le système s'il peut être identifié de manière unique à partir des informations fournies. Sinon, vous devrez l'ajouter manuellement. Il s'agit d'un champ obligatoire, qui lie cet enregistrement à une ligne spécifique d'un document source.  

## <a name="complete-the-registration"></a>Terminer l'enregistrement
1. Cliquez sur Valider.
    * Cela vérifie que le journal est prêt à être validé. Si la validation échoue, vous devrez corriger les erreurs avant de pouvoir valider le journal.  
2. Cliquez sur OK.
    * Après avoir cliqué sur OK, vérifiez le message. Il doit y avoir un message indiquant que le journal est OK.  
3. Cliquez sur Valider.
4. Cliquez sur OK.
    * Après avoir cliqué sur OK, vérifiez la barre des messages. Il doit y avoir un message indiquant que l'opération a réussi.  
5. Fermez la page.

