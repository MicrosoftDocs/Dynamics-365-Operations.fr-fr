---
title: "Numéros de série de la caisse enregistreuse dans le processus de vente"
description: "Cette rubrique explique comment vous pouvez enregistrer des numéros de série sur des bons de livraison ou des factures pendant le processus de vente. Cette fonctionnalité est utile si une société souhaite capturer des numéros de série à des fins de service et de garantie, sans avoir à mettre à jour des numéros de série dans le stock de la réception à la sortie."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 23683ff3b232d485d0e4386963b3dcf37cd96c6f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="register-serial-numbers-in-the-sales-process"></a>Numéros de série de la caisse enregistreuse dans le processus de vente

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Cette rubrique explique comment vous pouvez enregistrer des numéros de série sur des bons de livraison ou des factures pendant le processus de vente. Cette fonctionnalité est utile si une société souhaite capturer des numéros de série à des fins de service et de garantie, sans avoir à mettre à jour des numéros de série dans le stock de la réception à la sortie.

De nombreuses sociétés souhaitent simplement capturer des numéros de série à des fins de service et de garantie, et ne doivent pas mettre à jour des numéros de série dans le stock (de la réception à la sortie). Dans ces scénarios, Microsoft Dynamics 365 for Finance and Operations permet d'enregistrer les numéros de série sur les bons de livraison ou les factures lorsque les produits sont vendus. Si des produits sont ultérieurement renvoyés, vous pouvez ensuite suivre un produit sur une facture pour déterminer si vous avez vendu le produit, et si le service ou les obligations de garantie sont valides.
Y-a-t-il une configuration requise ?
----------------------------

Vous devez activer les numéros de série pour le processus de vente en sélectionnant l'option **Actif dans le processus de vente** sur la page **Groupes de dimension de suivi**. Les événements suivants se produisent dans Microsoft Dynamics 365 for Finance and Operations :
-   Sur l'organisateur **Numéros de série**, l'option **Contrôle des numéros de série** est sélectionnée. Si cette option est sélectionnée, vous devez enregistrer un numéro de série pour chaque article figurant sur le bon de livraison ou sur la facture.
-   Toutes les sélections effectuées dans le groupe de dimensions de suivi pour les numéros de série sont désactivées, hormis l'option **Sortie nulle autorisée**. Vous pouvez activer l'option **Sortie nulle autorisée** pour remplacer le contrôle des numéros de série et autoriser l'emballage et la facturation des produits sans enregistrer les numéros de série.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>Quand dois-je enregistrer les numéros de série dans le processus de vente ?
Vous pouvez enregistrer les numéros de série sur le bon de livraison pour une commande client, ou sur la facture. Lorsque vous préparez une facture pour un article fabriqué en série envoyé avec un bon de livraison, vous pouvez sélectionner les numéros de série sur le bon de livraison à facturer. Le nombre de numéros de série enregistrés ne doit pas être supérieur à la quantité d'articles expédiés. Si vous créez une facture partielle, vous pouvez sélectionner moins d'articles fabriqués en série que ce qui est enregistré sur le bon de livraison. Lorsque vous imprimez un bon de livraison ou une facture, les numéros de série qui ont été enregistrés sont inclus.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>Est-ce que je peux entrer des numéros de série en les scannant, ou je dois les taper ?
Vous pouvez numériser ou saisir les numéros de série. Lorsque vous utilisez un scanner, le mode d'analyse détermine s'il est nécessaire d'ajouter ou de supprimer des numéros de série de la liste des numéros de série figurant sur la facture ou sur le bon de livraison. Si vous souhaitez scanner les numéros de série, par exemple à l'aide d'un scanneur de codes-barres portable, configurez le scanneur pour envoyer une commande Entrer ou la commande TAB après le numéro de série. Cette commande indique la fin du flux de données. Sinon, vous devez appuyer sur Entrer ou TAB sur le clavier après avoir scanné chaque numéro de série.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Si j'active les numéros de série pour le processus de vente, dois-je enregistrer tous les numéros de série pour tous les articles ?
L'enregistrement des numéros de série pour tous les articles sur un bon de livraison ou une facture dépend du paramétrage du groupe de dimensions de suivi affecté au produit. Lorsque vous activez les numéros de série pour le processus de vente, l'option **Contrôle des numéros de série** est automatiquement activée. Vous devez ensuite enregistrer un numéro de série, ou un enregistrement vide pour un numéro illisible, pour chaque article sur le bon de livraison ou la facture. Si vous ne souhaitez pas exiger un numéro de série pour chaque article, sélectionnez l'option **Sortie nulle autorisée** dans le groupe de dimensions de suivi affecté à l'article. Vous pouvez ensuite enregistrer moins de numéros de série que la quantité d'articles expédiés. Si vous enregistrez plus de numéros de série que la quantité d'articles expédiés, vous ne pourrez pas valider le bon de livraison ou la facture.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>Est-ce que je peux enregistrer des numéros de série pour des factures partielles et des expéditions partielles ?
Vous pouvez créer des factures partielles et des bons de livraison partiels pour des commandes client, et n'enregistrer que les numéros de série pour les articles que ces factures et ces bons de livraison incluent. Si vous souhaitez créer une facture partielle et si vous avez plusieurs bons de livraison pour la commande client, vous pouvez inclure des numéros de série de plusieurs bons de livraison. Toutefois, il ne peut y avoir qu'un bon de livraison dans lequel tous les numéros de série ne sont pas inclus. Par exemple, si vous avez trois bons de livraison, et que chacun inclut deux articles fabriqués en série, vous ne pouvez pas créer une facture partielle pour un article de chaque bon de livraison.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>Que faire si un numéro de série n'est pas lisible ?
Si un numéro de série ne peut pas être lu ou scanné, vous pouvez créer une ligne vide pour l'article en cliquant sur la page **Non lisible** sur la page **Numéros de série**. Si le numéro de série devient disponible ultérieurement, vous pourrez mettre à jour la facture ou le bon de livraison. Pour plus d'informations, voir la section suivante, « Puis-je corriger ou modifier les numéros de série que j'ai enregistrés pour une commande client » ?

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>Puis-je corriger ou modifier les numéros de série que j'ai enregistrés pour une commande client ?
Oui, vous pouvez modifier les numéros de série si les conditions suivantes sont remplies :
-   **Factures** – Vous pouvez modifier les numéros de série pour les articles que vous n'avez pas encore facturés. Le bon de livraison est ensuite également mis à jour. Toutefois, si une ligne de commande client a été corrigée en enregistrant une quantité négative, vous ne pouvez pas modifier les numéros de série de la ligne de commande client.
-   **Bons de livraison** – Vous pouvez corriger partiellement une ligne de bon de livraison qui contient des articles fabriqués en série. Vous devez contrepasser la totalité de la quantité pour la ligne. Si un bon de livraison a été annulé ou corrigé, vous ne devez pas enregistrer à nouveau les numéros de série contrepassés lors de la création d'un bon de livraison pour les mêmes articles fabriqués en série. Les numéros qui ont été enregistrés seront utilisés.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>Puis-je afficher les numéros de série qui ont été expédiés avec un bon de livraison spécifique, ou qui étaient inclus dans une facture ?
Oui, vous pouvez effectuer une recherche sur la ligne de journal des bons de livraison ou la ligne de journal des factures pour afficher une liste de tous les numéros de série qui ont été inclus dans le document.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>Puis-je afficher les articles fabriqués en série disponibles ?
Non, vous ne pouvez pas afficher les articles fabriqués en série disponibles, car les numéros de série ne sont pas enregistrés pour les articles tant qu'ils ne sont pas vendus.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>Est-ce que je peux enregistrer les numéros de série pour les articles de poids variable ?
Non, vous ne pouvez pas enregistrer des numéros de série pour les articles de poids variable dans le processus de vente. Vous ne pouvez pas non plus affecter un produit défini comme article de poids variable à un groupe de dimensions de suivi paramétré pour utiliser des numéros de série uniquement lors du processus de vente.
Puis-je enregistrer les numéros de série au point de vente au détail ?
------------------------------------------------

Oui, le point de vente au détail invitera l'utilisateur à saisir un numéro de série lorsque l'utilisateur vend un article affecté un groupe de dimensions de suivi paramétré pour utiliser des numéros de série uniquement lors du processus de vente.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Quels rôles de sécurité sont nécessaires afin d'enregistrer des numéros de série lors du processus de vente ?
Cette fonction est disponible pour tous les rôles pouvant tenir à jour des bons de livraison et des factures. Les responsabilités suivantes permettent aux collaborateurs de corriger les numéros de série, et d'enregistrer des entrées vides pour les numéros de série qui ne peuvent pas être affichés ou scannés :
-   Tenir à jour les corrections des numéros
-   Tenir à jour l'enregistrement des numéros de série illisibles






