---
title: Utiliser des articles en séries dans le PDV
description: Cette rubrique explique comment gérer les articles en série dans l'application de point de vente (PDV).
author: boycezhu
manager: annbe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 1e0d6aa7cd5576578378e70c6ee808833314aff3
ms.sourcegitcommit: 919620b4aca425e6a1248ee12f50a622d2531e58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290768"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Utiliser des articles en séries dans le PDV

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

De nombreux détaillants vendent des produits qui nécessitent un contrôle en série. Ces éléments sont appelés *articles en série*. Certains détaillants peuvent souhaiter conserver des numéros de série à des fins de suivi. D'autres détaillants pourraient vouloir capturer des numéros de série pendant le processus de vente, à des fins de service et de garantie. Cette rubrique explique comment vous pouvez gérer les articles en série dans l'application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurations des numéros de série

Un article est considéré comme un article sérialisé s'il se voit attribuer un groupe de dimensions de suivi configuré pour autoriser les numéros de série. Dans Commerce Headquarters, sur la page **Groupes de dimensions de suivi**, sélectionnez l'option **Actif** pour activer des numéros de série dans le cadre du processus d'inventaire. Pour activer les numéros de série pour le processus de vente, sélectionnez l'option **Actif dans le processus de vente**.

Dans le raccourci **Dimensions de suivi**, si l'option **Réception nulle autorisée** est activée, le numéro de série est une entrée facultative lors du processus de réception de l'inventaire. Si l'option est désactivée, le numéro de série est requis.

Dans le raccourci **Numéros de série**, si l'option **Contrôle du numéro de série** est activée, le numéro de série doit être unique par unité. En d'autres termes, les numéros de série dupliqués ne sont pas autorisés.

## <a name="serialized-items-in-the-receiving-process"></a>Articles en série dans le processus de réception

L'opération **Stock entrant** dans l'application PDV permet aux utilisateurs d'effectuer les tâches suivantes pour les articles en série :

- Enregistrez les numéros de série par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande.
- Validez les numéros de série pré-enregistrés par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande ou un ordre de transfert.

> [!NOTE]
> Pour utiliser l'opération **Stock entrant** pour enregistrer ou valider un article en série, l'article doit être affecté à un groupe de dimensions de suivi configuré pour autoriser les numéros de série pour l'option **Actif** pas l'option **Actif dans le processus de vente**.

Pour commencer le processus de réception, dans l'opération **Stock entrant**, vous pouvez commencer dans la vue **Recevoir maintenant** en scannant le code à barres de l'article ou en entrant l'ID de l'article. Sinon, vous pouvez commencer dans la vue **Liste complète des commandes** en sélectionnant manuellement l'élément.

Si l’élément sélectionné ou reçu est un élément en série, le volet **Détails** de l'élément contient un lien **Gérer le numéro de série** qui ouvre la page **Gestion des numéros de série**. Vous pouvez également ouvrir la page **Gestion des numéros de série** soit en sélectionnant **Numéro de série** dans la barre d'application de la vue des détails de la commande ou en sélectionnant **Gérer le numéro de série** dans la boîte de dialogue qui vous invite pendant le processus de réception. La page **Gestion des numéros de série** répertorie toutes les lignes de numéros de série ouvertes en attente d'enregistrement ou de validation. Il peut y avoir deux onglets sur cette page : un pour l'article actuel et un pour tous les articles en série de la commande.

Le champ **Statut** sur la page **Gestion des numéros de série** fournit des informations sur l'étape actuelle dans laquelle se trouve chaque numéro de série :

- **Non enregistré** - Le numéro de série n'a pas été fourni ou le numéro de série préenregistré n'a pas encore été validé.
- **Enregistrement** - Le numéro de série a été enregistré et sauvegardé localement dans la base de données des canaux du magasin, ou le numéro de série préenregistré a été validé. Seuls les numéros de série dont le statut est **Enregistrement** seront envoyés à Commerce Headquarters à la fin de la réception.

### <a name="register-serial-numbers-against-serialized-items"></a>Enregistrer des numéros de série par rapport aux articles en série

Dans le cadre d'une commande fournisseur, une boîte de dialogue vous invite pendant le processus de réception d'un article en série et propose l'option **Gérer le numéro de série**. Vous pouvez sélectionner cette option pour ouvrir la page **Gestion des numéros de série** et commencer à enregistrer les numéros de série. Vous pouvez également ignorer cette étape pendant le processus de réception et fournir l'entrée plus tard, avant que le reçu ne soit publié.

Par défaut, l'onglet de l'élément actuel est affiché. Toutes les lignes de numéros de série ont une valeur de numéro de série vide et un état **Non enregistré**. Vous pouvez numériser les codes à barres du numéro de série ou sélectionner **Numéro de série** sur la barre d'application pour saisir en continu les numéros de série dans la boîte de dialogue. Les numéros de série que vous saisissez apparaissent dans la liste et le statut des lignes de numéro de série est modifié en **Enregistrement**. Le nombre maximum de numéros de série que vous pouvez enregistrer dans la liste est égal à la quantité reçue. Si vous faites une erreur, vous pouvez sélectionner **Modifier** ou **Effacer** dans le volet **Détails** pour modifier les numéros de série que vous avez saisis.

Vous pouvez également enregistrer des numéros de série dans l'onglet **Tous les articles en série** de la page **Gestion des numéros de série**. Dans la liste, sélectionnez l'élément par rapport auquel vous souhaitez enregistrer les numéros de série.

Lors de l'enregistrement du numéro de série sur cette page, la validation de la duplication se produit. Si vous essayez d'entrer un numéro de série en double par rapport à un élément pour lequel le contrôle du numéro de série est activé, vous recevez un message d'erreur et devez fournir un numéro différent.

### <a name="validate-serial-numbers-on-serialized-items"></a>Valider les numéros de série sur les articles en série

Pour un ordre de transfert, le côté sortant doit pré-enregistrer les numéros de série sur les articles en série pendant le processus d'expédition. Pour un bon de commande, le fournisseur peut fournir des informations sur le numéro de série par le biais d'un avis d'expédition préalable (ASN), et vous pouvez pré-enregistrer les numéros sur les articles qui seront expédiés. Dans les deux cas, les numéros de série sont connus avant la réception. Par conséquent, du côté entrant, il vous suffit de valider que vous avez reçu ce que vous étiez censé recevoir.

Pour valider les numéros de série, vous pouvez ouvrir la page **Gestion des numéros de série** pendant le processus de réception ou à tout moment avant la publication du reçu. Pour chaque article sérialisé qui a des numéros de série préenregistrés, tous les numéros de série sont automatiquement définis sur un état initial **Non enregistré** sur cette page. Pour valider les numéros de série, vous pouvez les numériser ou les saisir. Lorsque le numéro de série est entré, l'application valide si elles correspondent aux numéros de série préenregistrés. S'ils correspondent, leur statut passe à **Enregistrement**. Autrement, vous recevez un message d'erreur. Le nombre maximum de numéros de série que vous pouvez valider dans la liste est égal à la quantité reçue.

Vous pouvez également valider des numéros de série dans l'onglet **Tous les articles en série** de la page **Gestion des numéros de série**. Dans la liste, sélectionnez l'élément par rapport auquel vous souhaitez valider les numéros de série.

## <a name="additional-resources"></a>Ressources supplémentaires

[Opération de stock entrant dans le PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
