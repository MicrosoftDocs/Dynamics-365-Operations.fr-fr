---
title: FAQ sur l’évaluation des coûts de stock
description: Cette rubrique répond à des questions fréquentes sur l’évaluation des coûts de stock dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45f65bd4a5cfb9bd0c4eb03ceb56eca452f6ec95
ms.sourcegitcommit: cbe9493d479f96f271d94599ec1b85131b26169f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809286"
---
# <a name="inventory-costing-faq"></a>FAQ sur l’évaluation des coûts de stock

[!include [banner](../includes/banner.md)]

Cette rubrique répond à des questions fréquentes sur l’évaluation des coûts de stock dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Clôture, ajustements et recalcul du stock

### <a name="is-the-inventory-close-required"></a>La clôture des stocks est-elle obligatoire ?

Si vous prévoyez d’utiliser la fonctionnalité d’archivage de stock, la clôture de stock est requise. Si vous ne prévoyez pas d’utiliser la fonctionnalité d’archivage de stock, nous vous recommandons fortement de toujours exécuter la clôture de stock, quels que soient les modèles d’évaluation des coûts que vous utilisez.

### <a name="how-often-should-the-inventory-close-be-run"></a>À quelle fréquence la clôture de stock doit-elle être exécutée ?

La clôture de stock doit être exécutée au moins une fois par période comptable. Par exemple, si votre grand livre est défini sur un calendrier fiscal basé sur un mois calendaire, vous devez exécuter la clôture de stock une fois par mois.

### <a name="is-the-inventory-recalculation-required"></a>Un nouveau calcul de stock est-il obligatoire ?

Non, un nouveau calcul de stock n’est pas requis. Si vous utilisez un modèle d’évaluation des coûts périodiques tel que premier entré, premier sorti (FIFO), dernier entré, premier sorti (LIFO) ou moyenne pondérée, vous devez soigneusement déterminer si vous allez exécuter le recalcul du stock. Il peut fournir des coûts plus précis dans les modèles heuristiques que vous avez sélectionnés.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>À quelle fréquence le recalcul du stock doit-il être exécuté ?

Si vous prévoyez d’exécuter le recalcul du stock, nous vous recommandons de l’exécuter quotidiennement en tant que traitement par lots. Si votre organisation n’a pas besoin de rapports fréquents sur les valeurs de stock pour les modèles d’évaluation des coûts périodiques, vous pouvez exécuter le calcul de stock moins souvent.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>Quand dois-je utiliser l’ajustement des stocks disponibles sur la page Clôture et ajustements ?

L’ajustement du stock disponible peut uniquement être exécuté une fois le stock clôturé. Il est généralement exécuté après la dernière clôture. L’ajustement disponible peut uniquement ajuster le stock qui est toujours disponible à la date à laquelle vous exécutez l’ajustement.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>Quand dois-je utiliser l’ajustement des transactions de stock sur la page Clôture et ajustements ?

Vous devez utiliser l’ajustement des transactions de stock avant d’exécuter une clôture de stock. Il est généralement utilisé pour corriger une réception incorrecte. Vous ne pouvez pas valider l’ajustement de transaction de stock après l’exécution d’une clôture de stock et le règlement de la transaction.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>Les retours de bons de commande sont-ils traités comme les autres problèmes lors de la clôture des stocks ?

Oui. Une réception de bon de commande est un problème qui est réglé sur une réception dans le modèle heuristique que vous sélectionnez pour l’article. Si vous utilisez un modèle d’évaluation des coûts périodique, vous pouvez utiliser le marquage pour remplacer le coût heuristique.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>Qu’advient-il des retours de commande client pendant la clôture des stocks ?

Lorsque vous exécutez la clôture du stock, un retour de commande client est traité comme une réception dans le stock. Les problèmes sont résolus par rapport au stock, en fonction du modèle heuristique que vous sélectionnez pour l’élément.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Quel prix de revient est utilisé sur un retour de commande client ?

Lorsque vous créez un retour lié à une commande client, la valeur du champ **Prix unitaire** est copiée à partir de la commande client d’origine, et le champ **Prix de vente de retour** est défini sur le prix de revient ajusté de la transaction de stock d’origine pour la ligne de commande client qui fait l’objet d’un retour. Si l’option **Valeur en cours** pour la transaction de stock associée est définie sur *Oui*, la clôture de stock peut entraîner des mises à jour du coût de sortie sur la commande client d’origine. Le champ **Prix de vente de retour** n’est pas mis à jour dans ce scénario. Cependant, lorsque vous validez un bon de livraison d’ordre de retour, le système vérifie le prix de revient et utilise le coût mis à jour sur la transaction de retour de stock.

Pour le retour d’un article de coût standard lié à une commande client, le système utilisera le coût standard appliqué au moment de la commande client d’origine, même si un nouveau coût standard est actif pour l’article.

Lorsque vous créez un retour qui n’est pas lié à une commande client, le champ **Prix de vente de retour** est défini sur le prix appliqué à l’article sur le site pour lequel vous créez l’ordre de retour. Si vous n’avez pas de prix de revient actif dans une version d’évaluation des coûts pour l’article, la valeur sera 0 (zéro). Si vous laissez la valeur sur 0 (zéro), vous recevrez un avertissement indiquant que l’ID de lot de retour ou le prix de revient de retour n’est pas spécifié.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Quelle est la performance attendue de la clôture des stocks ?

De nombreux facteurs peuvent affecter les performances de la clôture des stocks. Ces facteurs incluent le nombre total d’articles, le nombre total de transactions au cours de la période, les modèles de stock que vous utilisez et le nombre d’assistants de lot que vous configurez dans les paramètres de gestion des stocks et des entrepôts. Vous pouvez vous attendre à ce que la clôture prenne seulement quelques minutes ou quelques heures. Il n’y a pas d’indications spécifiques sur la durée d’exécution de la clôture. Vous devez définir vos exigences commerciales non fonctionnelles concernant les performances de la clôture de stock et travailler en étroite collaboration avec votre partenaire pour définir le calendrier d’exécution du processus de clôture de stock. Si vous constatez une baisse inattendue des performances du processus de clôture de stock, vous devez ouvrir un ticket de support.

## <a name="costing-sheet-and-indirect-costs"></a>Feuille de coûts et coûts indirects

### <a name="which-costing-models-support-the-costing-sheet"></a>Quels modèles d’évaluation des coûts prennent en charge la feuille de coûts ?

Bien que la feuille de coûts soit généralement utilisée dans les organisations qui utilisent l’évaluation des coûts standard, vous pouvez l’utiliser avec n’importe quel modèle d’évaluation des coûts disponible dans Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Puis-je avoir plusieurs feuilles de coûts pour différentes parties de mon organisation ?

Non Vous ne pouvez avoir qu’une seule feuille de coûts par entité juridique.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Puis-je avoir des feuilles de coûts différentes pour chaque site ?

Non, vous ne pouvez pas avoir de feuilles de coûts différentes pour chaque site. Vous ne pouvez créer qu’une seule feuille de coûts pour chaque entité juridique. Cependant, vous pouvez configurer le nombre total de nœuds, les groupes de coûts ou les nœuds de coûts indirects par site. Cette configuration est un processus manuel et vous devez gérer la hiérarchie et les affectations d’articles sur la feuille de calcul des coûts lorsque des modifications organisationnelles ou opérationnelles se produisent. Si un seul article est produit ou acheté sur plusieurs sites, aucun mécanisme ne vous permet de traiter l’article différemment sur la feuille de coûts de chaque site. De plus, notez que tous les codes de coûts indirects ont un taux ou un supplément qui est défini dans votre version d’évaluation des coûts. Les coûts que vous définissez sont toujours spécifiques au site.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Puis-je désactiver et activer des versions de la feuille de coûts ?

Bien qu’aucun historique détaillé des versions ne soit conservé pour la feuille de coûts, vous pouvez apporter des modifications à la feuille de coûts, puis, lorsque vous êtes prêt, l’enregistrer et la valider. Aucun mécanisme ne vous permet de revenir à une ancienne version de la feuille de coûts ou de visualiser les modifications qui y sont apportées. Si vous lancez des modifications et que vous ne souhaitez pas qu’elles prennent effet, vous pouvez fermer la page sans enregistrer ni valider les modifications. Vous serez invité à annuler les modifications.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Puis-je créer des coûts indirects pour chaque article ?

Sur votre feuille de coûts, vous pouvez créer des codes de coûts indirects où le champ **Type de nœud** est défini sur *Supplément*, *Taux*, ou *Basé sur l’unité de sortie*. Vous pouvez ensuite définir le tarif ou le supplément afin qu’il soit spécifique à un numéro d’article. Sur le raccourci **Taux** ou **Supplément**, ajoutez une ligne à la grille. Définissez le champ **Valide pour** sur *Table* et le champ **Relation** sur le numéro d’article spécifique.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Puis-je créer un coût indirect qui n’est pas lié à un élément spécifique ?

Oui. Vous pouvez créer un code de coût indirect où le champ **Type de nœud** est défini sur *Basé sur l’unité de sortie*. Vous pouvez ensuite définir le champ **Sous-type** sur *Quantité*, *Poids*, ou *Volume* pour spécifier la quantité, le poids ou le volume de l’article que vous produisez. Le taux que vous indiquez sur le raccourci **Taux** sera appliqué au sous-type que vous avez sélectionné. Par exemple, vous pouvez définir le champ **Sous-type** sur *Quantité* et le champ **Taux** sur *1,00 USD*, puis créer un lot de commandes ou un ordre de fabrication pour une quantité de 10. Dans ce cas, le coût indirect qui sera ajouté au produit fini est 10,00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Puis-je utiliser la feuille de coûts pour répartir mes coûts de production par heures et matériaux ?

Oui. Vous pouvez créer des nœuds **Total** sur votre feuille de coûts pour séparer les coûts selon le regroupement que vous choisissez. Par exemple, vous pouvez en créer un nœud **Total** nommé *Heures* et un autre nommé *Matériaux*. Sous le nœud **Heures**, ajoutez chaque groupe de codes lié à vos heures. Sous le nœud **Matériaux**, ajoutez chaque groupe de coûts lié à vos matériaux.

## <a name="dimension-groups"></a>Groupes de dimensions

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Puis-je gérer les coûts au niveau du lot ou du numéro de série ?

Oui, si vous utilisez un modèle d’évaluation des coûts périodique tel que FIFO, LIFO, Date LIFO, moyenne pondérée ou date moyenne pondérée, vous pouvez activer l’option **Stock financier** pour la dimension **Lot** ou **Numéro de série** dans le groupe de dimensions de suivi pour suivre les coûts à un niveau détaillé.

### <a name="can-i-manage-costs-at-the-location-level"></a>Puis-je gérer les coûts au niveau de l’emplacement ?

Non, vous ne pouvez pas activer l’option **Stock financier** pour la dimension **Emplacement** dans le groupe de dimensions de stockage. Si votre organisation doit suivre les coûts à un niveau plus détaillé, déterminez si vous pouvez créer des entrepôts virtuels, puis sélectionnez l’option **Stock financier** pour la dimension **Entrepôt** dans votre groupe de dimensions de stockage.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Dois-je activer l’option Utiliser les processus de gestion des entrepôts pour le groupe de dimensions de stockage ?

Si vous estimez que vous allez peut-être utiliser les fonctionnalités avancées de gestion des entrepôts par la suite, vous devez activer l’option **Utiliser les processus de gestion des entrepôts**. Après avoir enregistré un groupe de dimensions de stockage, vous ne pouvez plus modifier le paramètre de l’option **Utiliser les processus de gestion des entrepôts** pour celui-ci. Si vous décidez d’utiliser les processus de gestion des entrepôts ultérieurement, vous devrez créer un nouvel entrepôt où l’option est activée. Il n’existe aucun processus automatisé à utiliser pour déplacer tout le stock d’un entrepôt vers un autre entrepôt ou pour copier les configurations associées vers un nouvel entrepôt.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>Puis-je activer l’option Utiliser les processus de gestion des entrepôts pour le groupe de dimensions de stockage même si je ne prévois pas d’utiliser la gestion d’entrepôt avancée ?

Oui, même si vous ne prévoyez pas d’utiliser les fonctionnalités avancées de gestion des entrepôts, vous pouvez activer l’option **Utiliser les processus de gestion des entrepôts** pour le groupe de dimensions de stockage. Pour créer et traiter des transactions, vous devrez compléter la configuration minimale, telle que les hiérarchies de réservation et les groupes de séquences d’unités. Cependant, les paramètres d’entreposage avancé sont généralement ignorés lorsque vous traitez manuellement des listes de prélèvement, des bons de livraison et des accusés de réception de marchandises (par exemple, sur les pages de commande client et de commande fournisseur).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quand dois-je activer l’option Stock physique pour un groupe de dimensions de suivi ou de stockage ?

Vous devez activer l’option **Stock physique** pour les groupes de dimensions de stockage et de suivi lorsque vous devez conserver des enregistrements de stock détaillés basés sur cette dimension. En règle générale, toute dimension active sera également suivie physiquement. Par conséquent, toute réception, sortie ou mouvement de stock sera suivi par la dimension sélectionnée. Si une dimension n’est pas obligatoire (par exemple, la plaque d’immatriculation), vous pouvez activer les options **Réception nulle autorisée** et **Sortie nulle autorisée** pour permettre aux utilisateurs de recevoir, d’émettre ou de déplacer le stock même lorsque la dimension n’est pas spécifiée.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quand dois-je activer l’option Stock financier pour un groupe de dimensions de suivi ou de stockage ?

Vous devez activer l’option **Stock financier** pour les groupes de dimensions de stockage et de suivi lorsque vous devez conserver des enregistrements financiers détaillés basés sur cette dimension. Les dimensions **Site** font toujours l’objet d’un suivi financier, tandis que ce suivi est facultatif pour les autres dimensions. Si vous utilisez un modèle d’évaluation des coûts périodique tel que FIFO, LIFO ou moyenne pondérée, l’activation de l’option **Stock financier** pour une dimension indique que vous effectuerez des règlements uniquement dans les cas où la réception et la sortie ont les mêmes valeurs de dimension. Par exemple, si vous activez l’option **Stock financier** pour la dimension **Entrepôt**, vous aurez un coût différent dans chaque entrepôt, et les réceptions et les sorties de différents entrepôts ne pourront pas être réglées.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Puis-je apporter des modifications à un produit, un stockage ou un groupe de dimensions de suivi s’il existe des transactions ?

Après avoir créé un groupe de modèles d’article, vous pouvez modifier le paramètre des champs **Plan de couverture par dimension**, **Prix d’achat**, et **Prix de vente** si la case à cocher **Actif(ve)** est sélectionnée pour une dimension dans le groupe de modèles d’article. Aucune autre modification n’est autorisée. Par exemple, vous ne pouvez pas activer ou désactiver les options **Actif(ve)**, **Sortie nulle autorisée**, **Réception nulle autorisée**, **Stock physique** et **Stock financier**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Puis-je modifier le produit, le stockage ou le groupe de dimensions de suivi pour un produit lancé ?

Si le stock disponible d’un produit est de 0 (zéro) et que l’option **Valeur en cours** est définie sur *Non* pour toutes les transactions de stock, vous pouvez modifier les groupes de dimensions de stockage et de suivi sur la page de production lancée. Vous ne pouvez pas modifier le groupe de dimensions de produit. après avoir créé l’enregistrement.

## <a name="item-model-groups"></a>Groupes de modèles d’article

### <a name="when-should-i-enable-the-stocked-product-option"></a>Quand dois-je activer l’option Produit stocké ?

Vous devez activer l’option **Produit stocké** pour tout article qui fera l’objet d’un suivi dans votre stock. Lorsque cette option est activée, des transactions de stock détaillées sont conservées pour suivre la réception et la sortie de l’article. Cette option est généralement activée pour tout actif corporel que vous conservez dans votre entrepôt, par exemple. Vous devez également activer cette option si vous envisagez d’ajouter un actif incorporel, tel qu’un élément de service, à vos nomenclatures ou formules. Si vous n’activez pas l’option **Produit stocké**, aucune transaction de stock ne fait l’objet d’un suivi dans la comptabilité auxiliaire du stock et le coût des articles est généralement passé en charges dans votre grand livre général. Cette option est souvent utilisée, par exemple, pour les fournitures d’atelier ou les services qui ne sont pas inclus dans vos nomenclatures ou vos formules.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>Quand dois-je activer l’option Valider le stock physique ?

L’option **Valider le stock physique** est généralement activée lorsque l’option **Produit stocké** est activée. Lorsque vous activez cette option, le système suit la mise à jour physique de l’article sur la transaction de stock. Cette option est utilisée en coordination avec les paramètres de Comptabilité fournisseur, Comptabilité client et Contrôle de la production qui spécifient que la mise à jour physique doit créer un justificatif. Vous devez généralement activer cette option lorsque vous souhaitez que la comptabilité soit mise à jour chaque fois que vous mettez le stock physiquement à jour. Si Supply Chain Management n’est pas votre système d’enregistrement financier, vous pouvez désactiver cette option.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>Quand dois-je activer l’option Valider le stock financier ?

L’option **Valider le stock financier** est généralement activée lorsque l’option **Produit stocké** est activée. Cette option est utilisée en coordination avec les paramètres de Comptabilité fournisseur, Comptabilité client et Contrôle de la production qui spécifient que la mise à jour financière doit créer un justificatif. Vous devez généralement activer cette option lorsque vous souhaitez que la comptabilité soit mise à jour chaque fois que vous mettez à jour financièrement le stock (par exemple, en facturant des commandes client et des bons de commande, ou en mettant fin à un ordre de fabrication). Si Supply Chain Management n’est pas votre système d’enregistrement financier, vous pouvez désactiver cette option.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>Quand dois-je activer l’option Valider sur le compte de produit différé dans la livraison des ventes ?

Vous devez utiliser l’option **Valider sur le compte de produit différé dans la livraison des ventes** pour indiquer si vous souhaitez comptabiliser le produit dans le grand livre lorsque vous validez un bon de livraison pour une commande client. Cette option est généralement utilisée lorsqu’il y a un long délai entre le bon de livraison et la facture d’une commande client, ou lorsqu’il n’est pas possible de facturer toutes les commandes client de la période. En règle générale, vous devez désactiver cette option si vous validez vos factures de commande client immédiatement après avoir validé le bon de livraison. De cette manière, vous évitez de générer des écritures comptables supplémentaires qui seront immédiatement annulées lorsque vous allez facturer une commande client.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>Quand dois-je activer l’option Provisionner le passif sur l’accusé de réception de marchandises ?

Dans la plupart des organisations, vous allez activer l’option **Provisionner le passif sur l’accusé de réception de marchandises** pour tous les groupes de modèles d’articles, que vous ayez un produit stocké ou un produit non stocké. Cette option est utilisée pour comptabiliser une provision dans le grand livre, en fonction du prix de l’accusé de réception de marchandises. Étant donné qu’il y a généralement un délai entre la validation de la réception de marchandises pour un bon de commande et la validation de la facture, la plupart des organisations doivent comptabiliser le passif sur le bilan pour se conformer aux réglementations locales telles que les principes comptables généralement acceptées (GAAP). Si Supply Chain Management n’est pas votre système d’enregistrement financier, vous pouvez désactiver cette option. Si votre organisation utilise des catégories d’approvisionnement sur les bons de commande, vous pouvez contrôler les exigences des provisions en activant l’option **Provisionner les dépenses d’achat à la réception** pour la règle de stratégie de catégorie sur la page **Politiques d’achat**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Comment puis-je empêcher un utilisateur de valider un accusé de réception de marchandises si un enregistrement de réception n’a pas encore été publié ?

Vous pouvez empêcher un utilisateur de valider un accusé de réception de marchandises si un enregistrement de bon de commande n’a pas encore eu lieu en activant l’option **Spécifications d’inscription** pour le groupe de modèles d’article. Cette option est généralement utilisée dans les organisations qui utilisent un processus de réception en deux étapes, ou dans les scénarios où vous devez enregistrer un lot ou un numéro de série, par exemple, sur les articles que vous recevez. L’option **Spécifications d’inscription** s’applique à *toutes* les réceptions de stock pour un article, pas seulement pour les bons de commande. Par exemple, cela s’applique à un journal de stock qui a une quantité positive et un état d’ordre de fabrication déclaré comme journal terminé.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Comment puis-je empêcher un utilisateur de valider une facture de commande fournisseur un accusé de réception de marchandises n’a pas encore été validé ?

Vous pouvez empêcher un utilisateur de valider une facture de commande fournisseur si un accusé de réception de marchandises des commandes fournisseur n’a pas encore eu lieu en activant l’option **Conditions préalables à la réception** pour le groupe de modèles d’article. Cette option est généralement utilisée dans les organisations qui exigent que les réceptions soient physiquement reconnues dans le grand livre général pour les provisions. L’option **Conditions préalables à la réception** s’applique à *toutes* les réceptions de stock pour un article, pas seulement pour les bons de commande. Par exemple, cela s’applique à un journal de stock qui a une quantité positive et un état d’ordre de fabrication déclaré comme journal terminé. Si votre organisation utilise des catégories d’approvisionnement sur les bons de commande, vous pouvez contrôler les exigences pour une réception en activant l’option **Conditions préalables à la réception** pour la règle de stratégie de catégorie sur la page **Politiques d’achat**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Comment puis-je empêcher un utilisateur de valider un bon de livraison de commande client si une liste de prélèvement de commande client n’est pas encore validée ?

Vous pouvez empêcher un utilisateur de valider un bon de livraison de commande client ou une facture si un prélèvement de commande client n’a pas encore eu lieu en activant l’option **Conditions de prélèvement** pour le groupe de modèles d’article. Cette option est généralement utilisée dans les organisations qui effectuent un processus de prélèvement physique dans l’entrepôt (par exemple, en utilisant l’appareil mobile de l’entrepôt pour effectuer le prélèvement). L’option **Conditions de prélèvement** s’applique à *toutes* les sorties de stock pour un article, pas seulement pour les commandes client. Par exemple, elle s’applique à un journal de stock qui a une quantité négative et un journal des prélèvements d’ordres de fabrication.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Comment puis-je empêcher un utilisateur de valider une facture de commande client si le bon de livraison de commande client n’est pas encore validé ?

Vous pouvez empêcher un utilisateur de valider une facture de commande client si un bon de livraison de commande client n’a pas encore eu lieu en activant l’option **Conditions de déduction** pour le groupe de modèles d’article. Cette option est généralement utilisée dans les organisations qui effectuent un processus d’emballage physique dans l’entrepôt (par exemple, en utilisant l’application mobile Warehouse Management pour effectuer l’emballage ou en générant un document qui sera inclus avec les articles expédiés). L’option **Conditions de déduction** s’applique à *toutes* les sorties de stock pour un article, pas seulement pour les commandes client. Par exemple, elle s’applique à un journal de stock qui a une quantité négative et un journal des prélèvements d’ordres de fabrication.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Puis-je empêcher la vente d’articles enregistrés ?

Lorsqu’un article est enregistré dans votre stock dans Supply Chain Management, la quantité est physiquement disponible pour être émise dans le système. Si des articles qui ont été enregistrés mais pas encore reçus ne doivent *pas* être disponibles pour être émis pour les commandes client ou les ordres de production, par exemple, pensez à utiliser le statut de stock, le blocage de stock, les ordres de qualité, les ordres de contrôle ou les fonctionnalités de réservation pour gérer le processus d’entreprise.

## <a name="production-costing"></a>Évaluation des coûts de production

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Puis-je utiliser un modèle d’établissement des coûts pour les matières premières et un modèle d’établissement des coûts différent pour les produits finis ?

Oui, vous pouvez utiliser différents modèles d’établissement des coûts pour chaque article. Il n’est pas rare que les fabricants utilisent un modèle d’établissement des coûts périodique pour les matières premières et un coût standard pour les produits semi-finis et finis.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Comment puis-je réduire les frais généraux des coûts de la machine ?

Pour réduire les frais généraux de vos machines, vous devez créer des ressources et des groupes de ressources pour chaque machine, en fonction des besoins de votre entreprise. Chaque ressource ou groupe de ressources peut être affecté à des catégories de coûts pour contrôler le coût de la machine. Chaque catégorie de coûts peut être liée à un groupe de coûts, et chaque groupe de coûts peut être utilisé comme base pour le calcul des coûts indirects sur la feuille de coûts.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Comment reconnaître les coûts liés à la consommation d’énergie (par exemple, la consommation d’eau, d’énergie ou de gaz) sur la feuille de coûts ?

Vous pouvez généralement comptabiliser les coûts liés à la consommation d’énergie de l’une des deux manières suivantes :

- Créez une ligne dans votre nomenclature ou formule. En règle générale, cette ligne est créée en tant qu’article de service et vous pouvez spécifier l’unité de mesure que vous consommez par rapport à la quantité que vous produisez. De cette façon, l’utilisateur peut consommer une quantité différente au cours du processus de production. Vous pouvez consommer automatiquement les éléments en fonction de la valeur que vous sélectionnez dans le champ **Principe d’effacement**.
- Créez un coût indirect sur votre feuille de coûts. Généralement, cette approche est utilisée pour répartir le coût total de votre consommation d’énergie sur l’ensemble de votre processus de production. Vous pouvez utiliser le groupe de coûts et la base d’absorption pour mettre à l’échelle la consommation en fonction des matériaux ou de la main-d’œuvre dans votre gamme, par exemple.

Vous devez sélectionner la meilleure option, en fonction de vos exigences en matière de génération d’états, de rapprochement et d’exploitation.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Puis-je capturer les détails des ressources dans la nomenclature ou la formule ?

Les détails des ressources peuvent être capturés uniquement dans une opération de gamme. Bien que vous puissiez créer un article de service pour représenter une ressource et affecter un coût pour augmenter le calcul du coût d’un produit fini, nous ne recommandons généralement pas cette approche. Au lieu de cela, nous vous recommandons de créer une gamme simple comportant une ligne pour suivre les coûts des ressources et de configurer l’opération de sorte qu’elle soit automatiquement consommée au début ou à la fin de l’ordre de fabrication.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Puis-je voir les détails du calcul si le coût est entré manuellement ?

Non Si vous entrez manuellement le prix sur la page **Prix de l’article**, les bouton **Afficher les détails du calcul du coût** et **Exposer les détails du calcul** ne sont pas disponibles. Si vous sélectionnez le bouton **Repositionnement des coûts par groupe de coûts** pour un prix de revient saisi manuellement, une ligne récapitulative s’affiche et tous les coûts sont regroupés jusqu’au produit fini.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>Le système calcule-t-il les écarts sur un ordre de fabrication lorsque je saisis manuellement le coût ?

Oui, le système calcule les écarts lorsque vous saisissez manuellement un coût standard. Toutefois, lorsque vous saisissez manuellement un coût standard au lieu de le calculer, toutes les consommations de matières, de gammes et de coûts indirects dans l’ordre de fabrication sont considérées comme un écart de remplacement. S’il existe des écarts supplémentaires, tels que la consommation de matériaux ou de main-d’œuvre supplémentaires, ils seront également enregistrés en tant qu’écarts par rapport à la nomenclature de production. Par conséquent, nous vous recommandons vivement de toujours exécuter un calcul pour les articles ayant une nomenclature, une gamme ou des coûts indirects.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Comment reporter les écarts d’un ordre de sous-production à l’ordre de fabrication parent ?

Lorsque vous utilisez un modèle de coût périodique tel que FIFO, LIFO ou moyenne pondérée, les coûts d’une sous-production seront reconnus dans le modèle heuristique que vous avez sélectionné pour les articles. Si vous avez besoin d’un calcul du coût de revient réel, pensez à utiliser le principe de marquage pour indiquer quelle sous-production est émise pour un ordre de fabrication parent. Sinon, pensez à utiliser l’option **Stock financier** pour la dimension **Lot** ou **Numéro de série** dans le groupe de dimensions de suivi, par exemple.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>Comment le principe d’effacement affecte-t-il la consommation ?

Le principe d’effacement d’une nomenclature, d’une formule ou d’une ligne de gamme contrôle l’échéance et la technique utilisées pour consommer l’article ou la main-d’œuvre. Si vous sélectionnez *Commencer*, l’article ou la main-d’œuvre est automatiquement consommé lorsque vous démarrez l’ordre de fabrication. Si vous sélectionnez *Terminer*, l’article ou la main-d’œuvre est automatiquement consommé lorsque vous déclarez l’ordre de fabrication comme terminé. Si vous sélectionnez *Manuel*, un utilisateur doit sélectionner manuellement les matériaux ou enregistrer l’heure dans un journal de fiches de travail ou de gamme. Les nomenclatures et les formules ont également une option *Disponible à l’emplacement*. Si vous sélectionnez cette option, les articles sont automatiquement consommés après leur transfert vers l’emplacement de l’atelier de production.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Comment dois-je exécuter des calculs de coût si j’ai des nomenclatures ou des formules à plusieurs niveaux ?

En général, nous vous recommandons de commencer le calcul au niveau le plus bas de vos nomenclatures ou formules. Pour faciliter le filtrage lorsque vous effectuez des calculs de coûts en masse, vous pouvez utiliser des groupes de calcul pour faciliter la séparation des produits. Nous vous recommandons également d’exécuter la tâche périodique *Recalculer les niveaux de nomenclature* avant de commencer les calculs de coûts en masse. Chaque organisation doit tenir compte de la gamme de produits et définir une stratégie qui répond aux besoins spécifiques de votre produit et de vos structures de nomenclature ou de formule.

## <a name="transfer-order-costing"></a>Évaluation des coûts d’ordre de transfert

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>Existe-t-il un moyen d’affecter le fret au coût d’un ordre de transfert ?

Vous pouvez ajouter des frais à un ordre de transfert pour ajouter des coûts. Le code frais définit le débit et le crédit pour les frais que vous ajoutez. Vous devez d’abord créer des codes frais dans le module **Gestion des stocks**. Pour ajouter des frais à un ordre de transfert, sélectionnez **Frais** sur la ligne d’ordre de transfert à laquelle vous souhaitez ajouter des frais.

## <a name="variances"></a>Écarts

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>Puis-je traiter les écarts différemment, en fonction du site ou de l’entrepôt ?

Il n’y a pas d’option pour configurer les comptes d’écart par site. Lorsque vous utilisez le coût standard pour un produit lancé, vous pouvez sélectionner le compte principal utilisé pour les écritures d’écart de coût standard sur la page **Validation**. Vous pouvez choisir de configurer les comptes pour un élément, un groupe d’éléments ou tous les éléments. Vous pouvez également configurer un groupe de coûts, un groupe de groupes de coûts ou tous les groupes de coûts.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Puis-je séparer les écarts résultant des taux de change des autres types d’écarts ?

Si un écart est le résultat d’une différence de taux de change entre le prix de la commande fournisseur et le coût standard d’un article, il n’existe aucun moyen de séparer la différence de taux de change des autres écarts.

## <a name="reporting"></a>Génération d’états

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Combien de configurations de rapport sur la valeur de stock puis-je créer et utiliser ?

Il n’y a pas de limite au nombre de configurations de rapport de valeur de stock que vous pouvez créer. Vous devez évaluer vos exigences spécifiques en matière de création de rapports et créer le nombre de configurations dont vous avez besoin pour répondre à ces exigences. Vous aurez besoin d’au moins une configuration de rapport de valeur de stock pour exécuter le rapport ou l’option de stockage de rapport.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>Puis-je utiliser le rapport sur la valeur des stocks pour analyser le coût d’un article dans chaque entrepôt ?

Oui. Vous pouvez activer l’option **Afficher** ou **Total** pour chaque dimension **Entrepôt** dans la configuration de rapport de valeur de stock. Toutefois, l’état va afficher uniquement les valeurs pour les dimensions où l’option **Stock financier** est activée pour le groupe de dimensions de stockage. Les autres dimensions n’afficheront que des colonnes vides. Pour plus d’informations, voir [Exemples et logique de l’état de valeur des stocks](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Comment puis-je afficher la quantité de stock à une date spécifique avec la moyenne pondérée ?

Vous pouvez utiliser l’état **Balance âgée**, qui comprend une colonne **Coût unitaire moyen** qui indique la valeur du stock à une date précise. Pour plus d’informations, voir [Exemples et logique Stock - Balance âgée](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Comment puis-je voir quelles transactions de réception sont réglées par rapport à une transaction de sortie ?

Vous pouvez afficher les règlements pour un mouvement de stock en sélectionnant **Règlements** ou **Explorateur de coût** sur l’onglet **Stock** du volet Actions de la page **Mouvement de stock** ou **Détails des transactions de stock**. Si vous sélectionnez une réception pour afficher les sorties liés à la transaction, l’explorateur de coûts n’affiche pas les détails. Les détails sont affichés uniquement si vous sélectionnez une transaction de sortie.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>Comment l’état de valeur de stock affiche-t-il les articles qui ont une quantité physique positive et une valeur financière négative ?

L’état de valeur de stock sépare les quantités et les montants physiques et financiers dans leurs propres colonnes. Les valeurs affichées sur l’état correspondent à la plage de dates que vous avez sélectionnée lors de l’exécution de l’état. Le niveau de synthèse affiché dépend des paramètres que vous avez sélectionnés. Si un article a des transactions qui ont été physiquement reçues et émises financièrement, les quantités et les valeurs sont additionnées indépendamment. Si vous avez choisi d’afficher le niveau de détail en tant que transactions, les lignes de chaque réception et sortie sont affichées séparément, et les quantités et montants physiques et financiers sont affichés, respectivement. Pour plus d’informations, voir [Exemples et logique de l’état de valeur des stocks](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Quel est l’impact des groupes de dimensions de stockage et de suivi sur l’état de valeur de stock ?

Si vous activez l’option **Valeur financière** pour une dimension dans un groupe de dimensions de stockage ou de suivi, vous pouvez sélectionner l’option **Afficher** ou **Total** pour la dimension dans la configuration de l’état sur la valeur de stock. Si vous sélectionnez l’option **Afficher** ou **Total** pour une dimension où l’option **Valeur financière** n’est pas sélectionnée, la colonne sera vide dans la sortie de l’état. Si vous avez activé l’option **Valeur financière** pour une dimension dans un groupe de dimensions de stockage ou de suivi, et si vous ne sélectionnez pas l’option **Afficher** ou **Total** sur la configuration du rapport de valeur de stock, le système résumera les valeurs pour les dimensions sélectionnées où elles sont suivies financièrement.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Puis-je personnaliser les états Power BI Embedded pour l’évaluation des coûts ?

Oui, les utilisateurs disposant des autorisations de sécurité appropriées peuvent mettre à jour le canevas de conception d’état pour n’importe quel état Power BI Embedded dans Supply Chain Management. Pour plus d’informations, voir [Personnaliser les états intégrés dans les espaces de travail analytiques](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Où puis-je consulter le relevé d’analyse d’écart ?

Vous pouvez accéder au relevé d’analyse d’écart en allant dans **Gestion des coûts \> Recherches et états \> Comptabilité de stock – états d’analyse** ou **Gestion des coûts \> Recherches et états \> Comptabilité de fabrication - états d’analyse**. Les deux options ouvrent le même état et l’état a le même comportement.

## <a name="item-prices-and-default-costs"></a>Prix des articles et coûts par défaut

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Puis-je tenir à jour le coût pour chaque variante de produit ?

Oui. Vous pouvez activer l’option **Utiliser le prix de revient par variante** du raccourci **Gérer les coûts** de la page **Produit lancé** pour activer la tarification par variante de produit. (Cette option n’est disponible que pour les produits génériques.) Ensuite, sur la page **Prix de l’article** (que vous pouvez ouvrir depuis la page **Version d’évaluation des coûts** ou la page **Produit lancé**), vous pouvez sélectionner **Affichage des dimensions** pour spécifier si vous souhaitez afficher la dimension **Configuration**, **Taille**, **Couleur** ou **Style**. Pour enregistrer la configuration et utiliser les dimensions sélectionnées à chaque fois que vous ouvrez la page, activez l’option **Enregistrer le paramétrage**, puis cliquez sur **OK**. Vous ne pouvez saisir les dimensions que pour les articles dont les dimensions sont actives dans le groupe de dimensions de produit.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Puis-je tenir à jour le coût pour chaque entrepôt ?

Non, vous ne pouvez pas gérer le prix des articles par entrepôt. Cependant, vous pouvez gérer des accords commerciaux pour les prix d’achat ou les prix de vente par magasin. Tout d’abord, sélectionnez l’option **Prix d’achat** ou **Prix de vente** pour la dimension sur la page **Groupe de dimensions de stockage**. Ensuite, lorsque vous créez le journal des accords commerciaux et ouvrez les lignes pour les dimensions, sélectionnez **Stock \> Afficher les dimensions** pour sélectionner la dimension à afficher dans la grille. Pour enregistrer la configuration et utiliser les dimensions sélectionnées à chaque fois que vous ouvrez la page, activez l’option **Enregistrer le paramétrage**, puis cliquez sur **OK**. Vous ne pouvez saisir les dimensions que pour les articles dont les dimensions sont actives dans le groupe de dimensions de produit.

### <a name="what-are-price-charges"></a>Que représentent les frais sur les prix ?

Les frais sur les prix permettent d’ajouter un montant fixe au prix unitaire du prix de l’article ou de l’accord commercial. Lorsque vous entrez un montant dans le champ **Frais sur le prix**, vous pouvez également entrer une valeur dans le champ **Quantité de frais**. Les frais sur les prix sont amortis sur la quantité de frais que vous spécifiez. Activez l’option **Inclus dans le prix unitaire** si vous souhaitez inclure les frais sur le prix dans le prix unitaire de l’article. Cette option est toujours activée pour un coût standard.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Comment dois-je configurer le prix des articles achetés dans plusieurs devises ?

Si vous entrez un prix par défaut dans le champ **Prix d’achat** sur la page **Produit lancé**, il est supposé être dans la devise comptable de la comptabilité de l’entité juridique dans laquelle vous vous trouvez. De même, si vous saisissez un prix d’achat dans une version d’évaluation où le champ **Type de prix** est défini sur *Achat*, le prix est supposé être dans la devise comptable de votre entité juridique. Lorsque vous créez un bon de commande pour un fournisseur qui a une devise différente, le système convertit automatiquement la devise du montant en devise comptable dans la devise de la transaction en utilisant le taux de change que vous spécifiez dans le champ **Type de taux de change de la devise comptable** de votre comptabilité.

Lorsque vous créez un journal des accords commerciaux, vous pouvez spécifier la devise dans laquelle vous exprimez le prix sur chaque ligne. Vous pouvez créer des accords commerciaux pour plusieurs devises, des fournisseurs spécifiques et de nombreuses autres combinaisons de facteurs. Si vous créez un bon de commande pour lequel un accord commercial existe pour la devise que vous avez sélectionnée, le système utilisera l’accord commercial ayant la devise correspondante. Lorsque vous validez des transactions telles que des accusés de réception de marchandises ou des factures, le montant est converti dans la devise comptable en utilisant le taux de change de la devise comptable que vous spécifiez dans la comptabilité.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Comment dois-je configurer le coût des articles achetés dans plusieurs devises ?

Les coûts peuvent être configurés dans plusieurs devises. Le coût que vous spécifiez pour le prix de l’article ou les coûts par défaut que vous entrez dans le champ **Prix** du raccourci **Gérer les coûts** de la page **Produit lancé** sont toujours exprimés dans la devise comptable de la comptabilité pour l’entité juridique que vous avez sélectionnée.

Si votre organisation utilise des coûts standard, vous devez définir une stratégie pour définir les coûts lorsqu’il existe plusieurs devises. Vous devez également définir un processus de mise à jour régulière du coût afin de réduire le nombre d’écarts validés.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>Puis-je utiliser le paramètre Bénéfice sur la page Groupe de coûts pour calculer les prix de vente ?

Oui, vous pouvez utiliser le paramètre **Bénéfice** sur la page **Groupe de coûts** pour ajouter un pourcentage lorsque les prix de vente sont calculés à l’aide d’un calcul de coût. Pour plus d’informations, voir [Calculs de nomenclature](bom-calculations.md).

## <a name="marking"></a>Marquage

### <a name="how-does-marking-affect-periodic-costing-models"></a>Comment le marquage affecte-t-il les modèles d’évaluation des coûts périodiques ?

Si vous utilisez un modèle d’évaluation des coûts périodiques tel que FIFO, LIFO ou moyenne pondérée, et que vous avez marqué une transaction de réception par rapport à une transaction de sortie, le modèle heuristique de l’article est ignoré lors du processus de clôture de stock. Au lieu de cela, le système utilisera le coût réel de la réception pour le coût de la sortie.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>Que se passe-t-il lors de la clôture des stocks lorsque j’utilise le marquage ?

Lorsque vous marquez des réceptions et des sorties, la clôture de stock réglera les transactions qui sont marquées ensemble. Lorsque le marquage est utilisé pour créer le règlement, le champ **Principe** de la page **Règlement** sera défini sur *Marquage*. Si une transaction est marquée avant d’être physiquement ou financièrement mise à jour, la sortie utilisera le coût de la réception marquée au lieu du coût moyen en vigueur. Si les transactions sont marquées après la mise à jour financière, le processus de clôture et d’ajustement de stock va ajuster le coût de la sortie pour qu’il corresponde au coût de la réception.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Puis-je marquer manuellement les transactions lorsque j’utilise le coût standard ou la moyenne mobile ?

Non, vous ne pouvez pas marquer manuellement les réceptions ou les sorties lorsque vous utilisez le coût standard ou la moyenne mobile. Si des transactions (par exemple, une livraison directe ou des commandes intersociétés) sont automatiquement marquées, le marquage des enregistrements restera et agira comme une réservation fixe. Toutefois, lorsque vous utilisez le coût standard ou la moyenne mobile, le marquage des enregistrements n’a aucun effet sur le coût des articles.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>Comment le marquage affecte-t-il le compte de résultat ?

Lorsque vous marquez une transaction de sortie par rapport à une réception, le coût de la sortie correspondra à la réception sélectionnée. Lorsque vous publiez physiquement et financièrement la sortie, la validation affectera les comptes **Coût des marchandises vendues, livrées** et **Coût des marchandises vendues, facturées** que vous spécifiez dans le profil de validation de stock. Si une transaction est marquée après la mise à jour physique ou financière, le processus *Clôture et ajustement des stocks* créera un ajustement ayant un justificatif correspondant qui ajuste le compte **Coût des marchandises vendues, facturées** et les contreparties du compte que vous spécifiez pour **Coût des unités, facturé** (stock).

### <a name="how-does-marking-affect-master-planning"></a>Comment le marquage affecte-t-il la planification générale ?

L’onglet **Mise à jour standard** de la page **Paramètres de planification** inclut un champ nommé **Mettre à jour le marquage**. L’option que vous sélectionnez ici est utilisée lorsque vous confirmez un ordre planifié généré par la planification générale. Les options suivantes sont disponibles :

- *Non* : Le système n’effectue aucun marquage.
- *Standard* : Le système marque les réceptions par rapport aux sorties en fonction de l’origine des besoins. Une demande est marquée par rapport à une offre. Si une certaine quantité reste à exécuter sur l’offre, cette dernière n’est pas marquée.
- *Développé* : Le système marque à la fois les demandes et les offres, indépendamment de la quantité restant ouverte dans l’offre.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Stock négatif

### <a name="when-should-i-allow-physical-negative-inventory"></a>Quand dois-je autoriser un stock physique négatif ?

En général, nous vous déconseillons d’autoriser un stock physique négatif, car il n’est pas possible d’avoir moins de 0 (zéro) d’un actif corporel dans votre entrepôt. Cependant, les processus métier de certains secteurs et scénarios métier peuvent restreindre les opérations nécessitant que le stock soit autorisé à devenir physiquement négatif. Par exemple, les détaillants peuvent ne pas vouloir empêcher la vente d’un article présenté en caisse, même lorsque le système indique qu’aucun article n’est disponible. Les fabricants de procédés fournissent un autre exemple. Pour ces fabricants, la quantité consommée peut dépasser ce qui est recommandé dans la formule. Il risque sinon d’y avoir une estimation de la consommation et un manque de précision, et la consommation pourrait dépasser la quantité dans un emplacement spécifique, tel qu’un réservoir.

Dans la mesure du possible, vous devez évaluer votre processus d’entreprise et essayer de l’améliorer pour vous assurer que le stock ne peut pas être négatif. Si vous devez autoriser un stock négatif, vous devez disposer d’un processus d’entreprise clair pour corriger le stock négatif, car cela peut avoir un impact négatif sur les coûts.

### <a name="when-should-i-allow-financial-negative-inventory"></a>Quand dois-je autoriser un stock financier négatif ?

En général, nous recommandons à la plupart des organisations d’autoriser un stock financier négatif. (Dans la plupart des cas, les factures de bon de commande ne sont pas traitées avant que vous puissiez expédier les articles.) Vous devez activer cette option lorsque vous avez des processus métier spécifiques qui exigent que le prix de vente reflète le coût final d’un bon de commande. Par exemple, cette exigence peut s’appliquer dans le secteur de la fabrication sur commande ou dans des régions spécifiques où la loi l’exige.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>Qu’advient-il du coût de mes sorties lorsque le stock est négatif ?

Lorsque le stock de votre article est négatif et que vous sortez plus d’articles que vous n’en avez physiquement, le système utilise le prix de l’article par défaut pour calculer le coût moyen en vigueur si vous utilisez un modèle d’établissement des coûts périodiques tel que FIFO, LIFO ou la moyenne pondérée. Si aucun prix par défaut n’est spécifié pour l’article, le système va publier le stock avec une valeur de 0 (zéro). Ce comportement peut rendre inexacts les futurs calculs de votre coût moyen en vigueur ou de votre moyenne mobile.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Puis-je empêcher le retrait, l’emballage ou la vente d’articles sur des bons de commande et des ordres de production s’il n’y a pas suffisamment de stock disponible ?

Oui. Nous vous recommandons de désactiver l’option **Physique négatif** pour le groupe de modèles d’article afin d’empêcher le retrait, l’emballage ou la vente d’articles sur des commandes client et des ordres de fabrication.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Puis-je empêcher la facturation d’articles sur une commande client si aucun bon de commande n’a été facturé pour le même article ?

Oui. Nous vous recommandons de désactiver l’option **Financier négatif** pour le groupe de modèles d’article pour empêcher la facturation d’articles sur une commande client si aucun bon de commande n’a été facturé pour le même article.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>Comment les stocks négatifs affectent-ils les ratios financiers tels que la marge bénéficiaire brute ?

Lorsque vous autorisez votre stock à devenir négatif, la valeur de stock dans votre bilan et le coût des marchandises vendues dans votre compte de résultat peuvent être sous-estimés, surtout si aucun prix par défaut n’est configuré pour vos articles. Par conséquent, la génération d’états financiers et les ratios tels que les marges bénéficiaires brutes peuvent être surestimés, car le coût est incorrect. Si vous utilisez un modèle d’évaluation des coûts périodique tel que FIFO, LIFO ou la moyenne pondérée, la valeur des sorties peut être ajustée lorsque vous exécutez le processus de clôture et d’ajustement du stock une fois que les quantités de stock négatives ont été corrigées. Cependant, si vous utilisez la moyenne mobile, il n’y a aucun moyen de réévaluer les transactions individuelles.

### <a name="how-should-i-correct-negative-inventory"></a>Comment corriger un stock négatif ?

Nous vous recommandons de surveiller et de corriger fréquemment le stock négatif lorsque les exigences de votre organisation ou de votre entreprise autorisent à laisser le stock devenir négatif. Vous pouvez corriger les valeurs de stock en effectuant un stock tournant, en enregistrant un ajustement ou un journal des mouvements. Si vous devez reconnaître les gains de stock inattendus dans un compte de grand livre spécifique, vous devez prévoir d’utiliser un journal des mouvements. Sinon, lorsque vous utilisez le processus de stock tournant ou d’ajustement des stocks, le système impute l’ajustement des stocks au compte **Réception de stock** et effectue la compensation sur les comptes **Dépense de stock, profit** que vous spécifiez sur le profil de validation de stock.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Dois-je créer un nouvel article si mon stock est devenu négatif et que j’utilise la moyenne mobile ?

Non Si votre organisation permet au stock de devenir physiquement négatif et que vous utilisez la moyenne mobile comme modèle de stock, le système utilisera la séquence de coût de secours qui est attribuée sur la page **Paramètres de gestion des stocks et des entrepôts** pour déterminer comment le coût sera attribué à vos sorties. En général, nous vous recommandons d’éviter de laisser votre stock devenir physiquement négatif. Pour plus d’informations, voir les autres questions dans la section [Stock négatif](#negative-inventory) de cette rubrique.

## <a name="not-stocked-products"></a>Produits non stockés

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Puis-je valider des listes de prélèvements de commande client pour des produits non stockés ?

Lorsque vous générez une liste de prélèvement pour une commande client qui inclut des articles qui se trouvent dans un groupe de modèles d’article qui n’est pas stocké, vous ne verrez aucune ligne pour ces articles non stockés. Puis-je utiliser l’application mobile Warehouse Management pour traiter les articles non stockés.

Lorsque vous générez un bon de livraison pour une commande client qui inclut des articles qui se trouvent dans un groupe de modèles d’article qui n’est pas stocké, définissez le champ **Quantité** sur *Produits prélevés et non inventoriés* pour inclure les articles non stockés dans la génération du document. Si vous sélectionnez *Tous*, seuls les articles stockés seront inclus dans le bon de livraison.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Dois-je utiliser un produit non stocké ou une catégorie (catégorie de vente ou catégorie d’approvisionnement) ?

Le choix entre un produit non stocké et une catégorie dépend des besoins spécifiques de votre entreprise. Les produits non stockés offrent généralement plus de contrôle sur les valeurs par défaut, telles que les quantités et les prix sur les commandes fournisseur et les commandes client. Par conséquent, les produits non stockés sont à privilégier dans les scénarios où le même produit ou service est acheté ou vendu plus d’une fois. Les catégories sont utiles dans les scénarios où le prix, les articles, les descriptions, etc. sont incohérents d’une transaction à l’autre. Les catégories peuvent également être utilisées sur n’importe quel produit pour aider à classer le type de produit vendu ou acheté.

## <a name="service-items"></a>Articles de service

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Quelle est la différence entre un article de service et un produit non stocké ?

Un article de service est un type de produit. Lorsque vous créez un nouveau produit, vous pouvez définir le champ **Type de produit** sur *Article* ou *Service*. *Article* est généralement sélectionné pour indiquer que l’article est un produit corporel, alors que *Service* est généralement sélectionné pour indiquer que l’article est un produit incorporel.

Tout produit lancé, qu’il s’agisse d’un article ou d’un produit de service, peut être stocké ou non stocké. Le paramètre stocké ou non stocké est contrôlé par le groupe de modèles d’article que vous sélectionnez pour le produit lancé. Lorsque vous sélectionnez un groupe d’articles qui n’est pas stocké, le système ne crée pas de mouvements de stock pour la commande client ou la commande fournisseur associée, par exemple.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Puis-je inclure des articles non stockés dans une nomenclature ?

Non, vous ne pouvez pas inclure un produit lancé qui est lié à un groupe de modèles d’articles où l’option **Stocké** est désactivée dans une nomenclature ou une formule. Peu importe que le champ **Type de produit** soit défini sur *Article* ou *Service*. Seuls les articles stockés peuvent être inclus dans les lignes de nomenclature ou de formule.

## <a name="costing-modelspecific-questions"></a>Questions spécifiques au modèle d’évaluation des coûts

### <a name="which-costing-model-should-i-use"></a>Quel modèle d’évaluation des coûts dois-je utiliser ?

Les modèles d’évaluation des coûts que vous devez sélectionner dépendent des besoins de votre entreprise. Avant de sélectionner un modèle d’évaluation des coûts à utiliser dans Supply Chain Management, vous devez vérifier que le modèle est autorisé par vos réglementations locales. Nous vous recommandons de valider votre choix auprès d’un comptable agréé de votre région.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Puis-je utiliser plusieurs modèles d’évaluation des coûts dans mon organisation ?

Oui. Il n’y a pas de limite au nombre de groupes de modèles d’article ou de modèles d’évaluation des coûts que vous pouvez sélectionner dans Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Puis-je utiliser plusieurs modèles d’évaluation des coûts pour chaque article ?

Non Vous ne pouvez sélectionner qu’un seul modèle d’évaluation des coûts pour chaque produit lancé. Ce comportement est contrôlé par le groupe de modèles d’éléments. Si vous devez utiliser plusieurs modèles d’évaluation des coûts pour générer des rapports sur les valeurs de stock, vous devez utiliser le complément Global Inventory Accounting.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>Lorsque j’utilise l’exécution de la fabrication, quelle méthodologie d’évaluation des coûts dois-je utiliser ?

Les modèles d’évaluation des coûts que vous devez sélectionner dépendent des besoins de votre entreprise. Il n’y a aucun avantage ou inconvénient spécifique à utiliser un modèle d’évaluation des coûts lorsque votre organisation utilise également l’exécution de la fabrication.

### <a name="when-is-fefo-used"></a>Quand le FEFO est-il utilisé ?

Premier expiré, premier sorti (FEFO) n’est pas une méthode d’évaluation des coûts. Au lieu de cela, il s’agit d’une technique de réservation souvent utilisée dans les organisations de fabrication. Vous pouvez activer les réservations FEFO pour un groupe de modèles d’article en activant l’option **Contrôlé par date FEFO**, puis en sélectionnant une valeur dans le champ **Critères de prélèvement**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Y a-t-il des avantages en termes de performances à choisir un modèle d’établissement des coûts plutôt qu’un autre ?

En général, le modèle d’établissement des coûts que vous sélectionnez pour un article a un impact minimal sur les performances globales du système. Toutefois, le temps nécessaire à l’exécution du processus de clôture ou de recalcul du stock peut être affecté par le modèle d’évaluation des coûts de stock que vous sélectionnez. Par exemple, si vous utilisez le coût standard ou la moyenne mobile, le processus de clôture de stock a un impact minimal sur le système, car il ne met pas à jour chaque transaction de stock et ne crée pas de règlements. Cependant, un modèle d’établissement des coûts périodiques tel que FIFO, LIFO ou la moyenne pondérée peut augmenter le temps nécessaire pour terminer le processus de clôture du stock. Plus précisément, le processus de clôture peut être plus long lorsque vous entrez un chiffre élevé dans le champ **Nombre maximum d’itérations autorisé par article** ou un chiffre peu élevé dans le champ **Montant minimal autorisé** pour le processus *Clôturer le stock*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>Quand dois-je utiliser l’option Prix fixe de réception ?

Lorsque vous sélectionnez la case à cocher **Prix fixe de réception** sur la page **Groupe de modèles d’article** pour un article, le système va utiliser le prix de réception comme coût standard pour la réception de stock. En cas de différence entre le prix d’achat et le prix de revient de l’article par défaut configurés pour un produit, la différence sera imputée au compte **Profit sur prix fixe de réception** ou **Perte sur prix fixe de réception** et déduite du compte **Contrepartie de prix fixe de réception**. (Tous ces comptes sont spécifiés sur la page **Validation**.)

Vous devez sélectionner la case à cocher **Prix fixe de réception** lorsque vous utilisez un modèle d’évaluation des coûts périodiques tel que FIFO, LIFO ou moyenne pondérée, et que vous exigez qu’un écart de prix d’achat fasse l’objet d’un suivi dans le grand livre si le prix d’une réception diffère du coût de l’article par défaut.

### <a name="moving-average"></a>Moyenne mobile

### <a name="is-moving-average-the-same-as-a-floating-average"></a>La moyenne mobile est-elle la même chose qu’une moyenne flottante ?

Les termes moyenne mobile, moyenne flottante et coût moyen en vigueur sont souvent utilisés comme synonymes. Parmi ces termes, la moyenne mobile est le seul modèle d’établissement des coûts officiel disponible dans Supply Chain Management. Bien que le coût moyen en vigueur ne soit pas un modèle de coût officiel, c’est la technique qui est utilisée lorsque vous utilisez un modèle de coût périodique tel que FIFO, LIFO ou moyenne pondérée. Le terme moyenne flottante n’est pas utilisé dans Supply Chain Management et peut avoir des connotations différentes dans d’autres systèmes.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>Comment puis-je tenir compte de la différence entre le prix de l’accusé de réception de marchandises et le prix facturé lorsque j’utilise la moyenne mobile ?

Lorsque vous utilisez la moyenne mobile, le coût physique (prix de réception) est utilisé pour calculer la moyenne mobile pour toutes les transactions de sortie. S’il existe une différence entre le coût physique (prix de réception) et le coût financier (prix facturé), le système comptabilisera automatiquement la différence sur le compte principal spécifié pour le type de validation **Différence de prix pour la moyenne mobile** sur l’onglet **Stock** de la page **Profil de validation de stock**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Où est la différence de prix pour la moyenne mobile présentée dans le grand livre ?

S’il existe une différence de prix entre la validation d’une mise à jour physique et d’une mise à jour financière pour une réception, la différence est imputée sur le compte principal spécifié pour le type de validation **Différence de prix pour la moyenne mobile** sur l’onglet **Stock** de la page **Profil de validation de stock**. Pour plus d’informations, consultez [Moyenne mobile](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Lorsque j’utilise la moyenne mobile, que se passe-t-il s’il y a une sortie avant la réception ?

Généralement, il peut y avoir une sortie avant la réception, soit parce que vous autorisez un stock physique négatif pour le groupe de modèles d’articles, soit parce que la sortie est antidatée. Pour plus d’informations, voir la section [Stock négatif](#negative-inventory) de cette rubrique.

Si vous antidatez des transactions, nous vous recommandons d’examiner attentivement votre processus d’entreprise et vos opérations pour déterminer s’il existe un moyen d’éviter ce scénario. Si vous antidatez une transaction pour un article qui utilise une moyenne mobile, le système affectera la moyenne mobile actuelle à la transaction. Les sorties ultérieures ne sont pas ajustées. Pour plus d’informations sur la moyenne mobile avec des transactions antidatées, voir [Moyenne mobile](moving-average.md).

### <a name="standard-costing"></a>Évaluation des coûts standard

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Quelle est la différence entre l’évaluation des coûts standard et le prix fixe de réception ?

L’évaluation des coûts standard nécessite de définir un prix d’article et d’activer le coût dans une version d’évaluation des coûts. Ce coût est utilisé pour toutes les réceptions et les sorties. Les écarts entre les réceptions et les stocks sont enregistrés dans le grand livre à l’aide des comptes d’écart de coût standard que vous spécifiez sur l’onglet **Coût standard** de la page **Profil de validation de stock**.

Toutefois, lorsque vous utilisez un prix de réception fixe, seul le coût des réceptions est fixe et le système utilise le coût que vous spécifiez sur le raccourci **Gérer les coûts** de la page **Produit lancé**. Les différences entre le coût par défaut et le prix de la commande d’achat entraîneront la comptabilisation de l’écart sur le prix d’achat dans les comptes de profits et pertes du prix de réception fixe. Les sorties n’utilisent pas de prix de réception fixe. Au lieu de cela, les sorties seront évaluées selon le coût moyen en vigueur au moment de la validation (sauf si vous utilisez le marquage) et elles seront réévaluées selon le modèle heuristique que vous sélectionnez lorsque vous exécutez la clôture de l’inventaire.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Puis-je utiliser des réservations FEFO avec l’évaluation des coûts standard ?

Oui, vous pouvez utiliser des réservations FEFO sur un groupe de modèles d’article lorsque vous sélectionnez l’évaluation des coûts standard. Les réservations FEFO contrôlent la logique de réservation utilisée pour le traitement physique des articles, tandis que l’évaluation des coûts standard contrôle le coût physique et financier d’un article.

### <a name="can-i-upload-pending-prices"></a>Puis-je télécharger des prix en attente ?

Oui, vous pouvez utiliser le complément Excel ou le Data Management Framework pour télécharger un prix en attente. Nous vous recommandons d’utiliser les entités suivantes :

- Prix d’article en attente (V2)
- Coûts unitaires des catégories de coûts de gamme en attente
- Facteurs de calcul des nœuds de feuilles de coûts (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>À quelle fréquence puis-je mettre à jour le coût standard d’un article ?

Il n’y a pas de limite à la fréquence à laquelle vous pouvez activer un nouveau coût standard. Si vous activez un nouveau coût pour un article le jour même où le dernier coût a été activé, le système utilisera le coût activé le plus récent sur les nouvelles transactions ou mises à jour (telles que les mises à jour de transactions existantes).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Puis-je désactiver ou supprimer un coût activé ?

Non, vous ne pouvez pas désactiver ou supprimer un coût activé. Si vous avez mal activé un coût, vous pouvez activer un nouveau coût ayant le bon coût.

### <a name="are-calculation-groups-used-with-standard-costing"></a>Les groupes de calcul sont-ils utilisés avec les coûts standard ?

Les groupes de calcul peuvent être utilisés avec n’importe quel article, quel que soit le groupe de modèles d’article que vous choisissez. Les groupes de calcul sont utilisés lors du repositionnement des coûts ou du processus de calcul des coûts pour déterminer les paramètres à utiliser pour les éléments pour lesquels vous exécutez le calcul. Pour plus d’informations sur les groupes de calcul, voir [Groupes de calculs de nomenclature](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>Quand dois-je utiliser une version d’évaluation des coûts planifiés ?

Les versions d’évaluation des coûts peuvent avoir un type *Coût standard* ou *Coût planifié*. Le type *Coût standard* est utilisé pour les coûts qui sont actifs dans le système et qui seront comptabilisés dans les transactions. Le type *Coût planifié* est utilisé pour exécuter des simulations sur les coûts et n’affecte pas le coût des transactions.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>Le coût total d’une entité peut-il être transféré à une autre entité en tant que frais de vente ?

Il n’existe aucun moyen automatisé de copier les coûts d’une entreprise à une autre. De plus, il n’existe aucun moyen automatisé de copier les coûts d’un prix d’achat vers un prix de vente. Si votre organisation doit effectuer l’une de ces tâches, déterminez si vous pouvez utiliser l’infrastructure de gestion des données pour exporter les données de votre version d’évaluation des coûts et les télécharger dans une autre société, soit en tant que prix de vente dans la version d’évaluation des coûts, soit en tant qu’accord commercial. Une manipulation manuelle des fichiers peut être nécessaire.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>Quelle est la meilleure façon de copier les coûts pré-budgétés dans une version d’évaluation des coûts standard ?

Vous pouvez utiliser le bouton **Copier** de la page **Versions d’évaluation des coûts** pour copier le prix des articles, le prix des catégories de coûts ou les coûts indirects d’une version d’évaluation des coûts à une autre.
