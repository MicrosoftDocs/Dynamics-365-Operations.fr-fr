---
title: Utiliser des articles en séries dans le PDV
description: Cette rubrique explique comment gérer les articles en série dans l’application de point de vente (PDV).
author: boycezhu
manager: annbe
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 0431ffa45eceac5c12d8ed991b00730c50ca62f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972553"
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

## <a name="sell-serialized-items-in-pos"></a>Vendre des articles sérialisés dans le PDV

Bien que l'application de PDV ait toujours pris en charge la vente d'articles sérialisés, dans Commerce version 10.0.17 et ultérieure, les organisations peuvent activer des fonctionnalités qui améliorent la logique métier déclenchée lors de la vente de produits configurés pour le suivi du numéro de série.

Quand la fonction **Validation améliorée du numéro de série dans la capture des commandes du PDV et l'exécution des commandes** est activée, les configurations de produit suivantes sont évaluées lors de la vente de produits sérialisés dans le PDV :

- **Type de série** configuré pour le produit (**actif** ou **actif dans les ventes**).
- Paramètres **Sortie nulle autorisée** pour le produit.
- Paramètres **Stock physique négatif** pour le produit et/ou l'entrepôt de vente.

### <a name="active-serial-configurations"></a>Configurations en série actives

Lorsque des articles sont vendus dans des PDV configurés avec une dimension de suivi du numéro de série **Active**, le PDV lance une logique de validation qui empêche les utilisateurs de terminer la vente d'un article sérialisé avec un numéro de série introuvable dans l'inventaire actuel de l'entrepôt de vente. Il existe deux exceptions à cette règle de validation :

- Si l'élément est également configuré avec l'option **Sortie nulle autorisée** activée, les utilisateurs peuvent ignorer l'entrée du numéro de série et vendre l'article sans désignation de numéro de série.
- Si l'article et/ou l'entrepôt de vente est configuré avec l'option **Stock physique négatif** activée, l'application accepte et vend un numéro de série qui ne peut pas être confirmé comme étant en stock dans l'entrepôt auquel il est vendu. Cette configuration permet à la transaction d'inventaire pour cet article/ce numéro de série spécifique d'être négatif et, par conséquent, le système autorisera les ventes de numéros de série inconnus.

> [!IMPORTANT]
> Pour s'assurer que l'application PDV peut valider correctement que les numéros de série vendus pour les articles de type série **actifs** sont bien en stock dans l'entrepôt de vente, il est nécessaire que les organisations exécutent la tâche **Disponibilité du produit avec dimensions de suivi** dans Commerce Headquarters et la tâche de distribution de disponibilité des produits **1130** associée via Commerce Headquarters sur une base fréquente. Au fur et à mesure que le nouvel inventaire sérialisé est reçu dans les entrepôts de vente, pour que le PDV valide la disponibilité en stock des numéros de série vendus, le stock principal doit fréquemment mettre à jour la base de données des canaux avec les données de disponibilité les plus à jour. La tâche **Disponibilité du produit avec dimensions de suivi** prend un instantané du stock principal, y compris les numéros de série, pour tous les entrepôts de l'entreprise. La tâche de distribution **1130** prend cet instantané du stock et le partage avec toutes les bases de données de canaux configurées.

### <a name="active-in-sales-process-serial-configurations"></a>Configurations en série Actif dans le processus de vente

Les articles configurés avec la dimension de série **Actif dans le processus de vente** ne passent par aucune logique de validation de l'inventaire, car cette configuration implique que les numéros de série d'inventaire ne sont pas pré-enregistrés en stock et que les numéros de série ne sont capturés qu'au moment de la vente.  

Si l'option **Sortie nulle autorisée** est également configurée pour les éléments configurés **Actif dans le processus de vente**, l'entrée du numéro de série peut être ignorée. Si l'option **Sortie nulle autorisée** n'est pas configurée, l'application demande à l'utilisateur de saisir un numéro de série, même s'il ne sera pas validé par rapport à l'inventaire disponible.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Appliquer les numéros de série lors de la création des transactions du PDV

L'application du PDV invite immédiatement les utilisateurs à saisir le numéro de série lors de la vente d'un article sérialisé, mais l'application permet aux utilisateurs d'ignorer la saisie de numéros de série jusqu'à un certain point du processus de vente. Lorsque l'utilisateur commence à capturer le paiement, l'application applique et exige la saisie du numéro de série pour tous les articles qui ne sont pas configurés pour être traités par des expéditions ou des collectes futures. Tous les articles sérialisés configurés pour le cash and carry et le report exigent que l'utilisateur saisisse le numéro de série (ou accepte de le laisser vide si la configuration de l'article le permet) avant de conclure la vente.

Pour les articles sérialisés vendus pour un retrait ou une expédition future, les utilisateurs du PDV peuvent ignorer la saisie initiale du numéro de série et terminer la création de la commande client.   

> [!NOTE]
> Lors de la vente ou de l'exécution de produits sérialisés via l'application du PDV, une quantité de « 1 » est appliquée pour les articles sérialisés sur la transaction de vente. Cela résulte de la manière dont les informations du numéro de série sont suivies sur la ligne de vente. Lors de la vente ou de l'exécution d'une transaction pour plusieurs articles sérialisés via le PDV, chaque ligne de vente doit être configurée uniquement avec une quantité de « 1 ». 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Appliquer les numéros de série lors de l'exécution ou du retrait de la commande client

Lors du traitement des lignes de commande client pour les produits sérialisés à l'aide de l'opération **Exécution des commandes** dans le PDV, le PDV applique la capture du numéro de série avant l'exécution finale. Par conséquent, si un numéro de série n'a pas été fourni lors de la capture initiale de la commande, il doit être capturé lors des processus de retrait, d'emballage ou d'expédition dans le PDV. Une validation est effectuée à chaque étape et l'utilisateur ne sera invité à saisir les données du numéro de série que si elles sont manquantes ou ne sont plus valides. Par exemple, si un utilisateur ignore les étapes de retrait ou d'emballage et lance immédiatement un envoi, et qu'un numéro de série n'a pas été enregistré pour la ligne, le PDV exigera que le numéro de série soit entré avant la fin de l'étape de facturation finale. Lors de la capture du numéro de série lors des opérations de traitement des commandes dans le PDV, toutes les règles mentionnées précédemment dans cette rubrique s'appliquent toujours. Seuls les éléments sérialisés configurés comme **Actif** passent par une validation de stock d'inventaire de numéro de série. Les éléments configurés comme **Actif dans le processus de vente** ne seront pas validés. Si **Stock physique négatif** est autorisé pour les produits **Actif**, tout numéro de série est accepté, quelle que soit la disponibilité des stocks. Pour les articles **Actif** et **Actif dans le processus de vente**, si **Sortie nulle autorisée** est configuré, un utilisateur peut laisser les numéros de série vides s'il le souhaite pendant les étapes de retrait, d'emballage et d'expédition.

Les validations des numéros de série se produiront également lorsqu'un utilisateur effectue les opérations de retrait sur les commandes des clients dans le PDV. L'application de PDV ne permet pas de finaliser un retrait de produit sérialisé sauf s'il obtient les validations mentionnées précédemment. Les validations sont toujours basées sur la dimension de suivi du produit et la vente de configurations d'entrepôt. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Opération de stock entrant dans le PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Opération de stock sortant dans le PDV](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)


[!INCLUDE[footer-include](../includes/footer-banner.md)]