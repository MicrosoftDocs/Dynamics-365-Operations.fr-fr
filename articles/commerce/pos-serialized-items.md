---
title: Utiliser des articles en séries dans le PDV
description: Cette rubrique explique comment gérer les articles en série dans l’application de point de vente (PDV).
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978361"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Utiliser des articles en séries dans le PDV

[!include [banner](includes/banner.md)]

De nombreux détaillants vendent des produits qui nécessitent un contrôle en série. Ces produits sont appelés *articles en série*. Certains détaillants peuvent souhaiter conserver des numéros de série en magasin ou dans le stocke de l’entrepôt à des fins de suivi. D’autres détaillants pourraient vouloir capturer des numéros de série pendant le processus de vente, à des fins de service et de garantie. Cette rubrique explique comment vous pouvez gérer les articles en série dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurations des numéros de série

Un article est considéré comme un article sérialisé s’il se voit attribuer un groupe de dimensions de suivi configuré pour autoriser les numéros de série. Au siège du Commerce, sur la page **Suivi des groupes de dimensions**, sélectionnez l’option **Actif** pour activer les numéros de série pour le processus de stock, ou sélectionnez l’option **Actif dans le processus de vente** permettant d’activer les numéros de série pour le processus de vente.

Dans le raccourci **Dimensions de suivi**, activez le paramètre **Réception nulle autorisée** pour autoriser le numéro de série à être une entrée facultative lors du processus de réception de l’inventaire d’un article sérialisé. La désactivation de ce paramètre impose au numéro de série d’être une entrée obligatoire. De même, le paramètre **Sortie nulle autorisée** contrôle si le numéro de série est requis pendant le processus d’expédition de l’inventaire.

> [!NOTE]
> Pour utiliser les opérations de PDV **Stock entrant** et **Stock sortant** pour enregistrer ou valider des numéros de série par rapport à un article en série, vous devez configurer cet article pour qu’il soit affecté à un groupe de dimensions de suivi configuré pour autoriser les numéros de série pour l’option **Actif** pas l’option **Actif dans le processus de vente**.

## <a name="serial-number-management-page"></a>Page de gestion des numéros de série

Dans les opérations de PDV **Stock entrant** et **Stock sortant**, si l’article sélectionné, reçu ou expédié est un article sérialisé, le volet **Détails** contient une option **Gérer le numéro de série** qui renvoie à la page **Gestion des numéros de série** sur laquelle vous pouvez enregistrer ou valider les numéros de série de l’article. Vous pouvez également ouvrir la page **Gestion des numéros de série** soit en sélectionnant l’action **Numéro de série** dans la barre d’application de la vue des détails de la commande ou en sélectionnant l’option **Gérer le numéro de série** dans la boîte de dialogue qui vous invite pendant le processus de réception ou d’expédition. 

La page **Gestion des numéros de série** répertorie toutes les lignes de numéros de série ouvertes en attente d’enregistrement ou de validation. Il peut y avoir deux onglets sur cette page : un pour l’article actuel et un autre pour tous les articles en série de la commande.

Le champ **Statut** sur la page **Gestion des numéros de série** fournit des informations sur l’étape actuelle dans laquelle se trouve chaque numéro de série :

- **Non enregistré** - Le numéro de série n’a pas été fourni ou le numéro de série préenregistré n’a pas encore été validé (dans le processus de réception).
- **Enregistrement** - Le numéro de série a été enregistré et sauvegardé localement dans la base de données des canaux du magasin, ou le numéro de série préenregistré a été validé. Seuls les numéros de série dont le statut est **Enregistrement** seront envoyés à Commerce Headquarters à la fin de la réception ou de l’achèvement.

## <a name="receive-serialized-items"></a>Recevoir des articles sérialisés

L’opération du PDV **Stock entrant** permet aux utilisateurs d’effectuer les tâches suivantes pour les articles en série :

- Enregistrez les numéros de série par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande.
- Validez les numéros de série pré-enregistrés par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande ou un ordre de transfert.

### <a name="register-serial-numbers-against-serialized-items"></a>Enregistrer des numéros de série par rapport aux articles en série

Dans le cadre d’une commande fournisseur, une boîte de dialogue vous invite avec l’option **Gérer le numéro de série** pendant le processus de réception d’un article en série. Vous pouvez sélectionner cette option pour ouvrir la page **Gestion des numéros de série** et commencer à enregistrer les numéros de série. Vous pouvez également ignorer cette étape pendant le processus de réception et fournir l’entrée plus tard, avant que le reçu ne soit publié.

Par défaut, l’onglet de l’élément actuel est affiché. Toutes les lignes de numéros de série ont une valeur de numéro de série vide et un état **Non enregistré**. Vous pouvez numériser les codes à barres du numéro de série ou sélectionner **Numéro de série** sur la barre d’application pour saisir en continu les numéros de série. Les numéros de série que vous saisissez apparaissent dans la liste et leur statut est modifié avec **Enregistrement**. Le nombre maximum de numéros de série que vous pouvez enregistrer dans la liste est égal à la quantité reçue. Si vous faites une erreur, vous pouvez sélectionner **Modifier** ou **Effacer** dans le volet **Détails** pour modifier les numéros de série que vous avez saisis.

Vous pouvez également enregistrer des numéros de série dans l’onglet **Tous les articles en série** de la page **Gestion des numéros de série**. Dans la liste, sélectionnez l’élément par rapport auquel vous souhaitez enregistrer les numéros de série.

### <a name="validate-serial-numbers-on-serialized-items"></a>Valider les numéros de série sur les articles en série

Pour un ordre de transfert, le côté sortant doit pré-enregistrer les numéros de série sur les articles en série pendant le processus d’expédition. Pour un bon de commande, le fournisseur peut fournir des informations sur le numéro de série par le biais d’un avis d’expédition préalable (ASN), et vous pouvez pré-enregistrer les numéros sur les articles qui seront expédiés. Dans les deux cas, les numéros de série sont connus avant la réception. Par conséquent, du côté entrant, il vous suffit de valider que vous avez reçu ce que vous étiez censé recevoir.

Pour valider les numéros de série, vous pouvez ouvrir la page **Gestion des numéros de série** pendant le processus de réception ou à tout moment avant la publication du reçu. Pour chaque article sérialisé qui a des numéros de série préenregistrés, tous les numéros de série sont automatiquement définis sur un état initial **Non enregistré** sur cette page. Pour valider les numéros de série, vous pouvez les numériser ou les saisir. Lorsque le numéro de série est entré, l’application valide si elles correspondent aux numéros de série préenregistrés. S’ils correspondent, leur statut passe à **Enregistrement**. Autrement, vous recevez un message d’erreur. Vous pouvez également sélectionner directement un numéro de série, puis sélectionner l’option **Valider le numéro de série** dans le volet **Détails** pour marquer rapidement ce numéro de série comme validé. Le nombre maximum de numéros de série que vous pouvez valider dans la liste est égal à la quantité reçue.

Vous pouvez également valider des numéros de série dans l’onglet **Tous les articles en série** de la page **Gestion des numéros de série**. Dans la liste, sélectionnez l’élément par rapport auquel vous souhaitez valider les numéros de série.

## <a name="ship-serialized-items"></a>Expédier les articles sérialisés

Vous pouvez utiliser l’opération de PDV **Stock sortant** pour enregistrer les numéros de série par rapport aux articles sérialisés lors de leur expédition hors du magasin actuel par le biais d’un ordre de transfert.

### <a name="register-serial-numbers-against-serialized-items"></a>Enregistrer des numéros de série par rapport aux articles en série

Dans le cadre d’un ordre de transfert, une boîte de dialogue vous invite avec l’option **Gérer le numéro de série** pendant le processus d’expédition d’un article en série. Vous pouvez sélectionner l’option pour ouvrir la page **Gestion des numéros de série** et commencer à enregistrer les numéros de série. Vous pouvez également ignorer cette étape pendant le processus d’expédition et fournir l’entrée plus tard, avant que l’expédition ne soit publié.

Par défaut, l’onglet de l’élément actuel est affiché. Toutes les lignes de numéros de série ont une valeur de numéro de série vide et un état **Non enregistré**. Vous pouvez numériser les codes à barres du numéro de série ou sélectionner **Numéro de série** sur la barre d’application pour saisir en continu les numéros de série. Les numéros de série que vous saisissez apparaissent dans la liste et leur statut est modifié avec **Enregistrement**. Le nombre maximum de numéros de série que vous pouvez enregistrer dans la liste est égal à la quantité expédiée. Si vous faites une erreur, vous pouvez sélectionner **Modifier** ou **Effacer** dans le volet **Détails** pour modifier les numéros de série que vous avez saisis.

Vous pouvez également enregistrer des numéros de série dans l’onglet **Tous les articles en série** de la page **Gestion des numéros de série**. Dans la liste, sélectionnez l’élément par rapport auquel vous souhaitez enregistrer les numéros de série.

Vous pouvez éventuellement activer la validation de la disponibilité du numéro de série lors de l’enregistrement du numéro de série par rapport à un ordre de transfert sortant. Avec cette validation, si vous tentez d’expédier un numéro de série qui n’est pas disponible dans le stock du magasin d’expédition, vous recevrez un message d’erreur et devrez fournir un numéro différent.

Pour activer cette validation, vous devez au préalable planifier l’exécution des tâches suivantes de manière récurrente :

- **Retail et Commerce** > **IT Retail et Commerce** > **Produits et stock** > **Disponibilité du produit avec dimensions de suivi**
- **Retail et commerce** > **Calendriers de distribution** > **1130** (**Disponibilité des produits**)

## <a name="additional-resources"></a>Ressources supplémentaires

[Opération de stock entrant dans le PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Opération de stock sortant dans le PDV](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
