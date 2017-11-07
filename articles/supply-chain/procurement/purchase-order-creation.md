---
title: "Création de commandes fournisseur"
description: "Cet article décrit les processus et les options lorsque vous créez manuellement une commande fournisseur."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 1cf09af8de2a312ce17cd88ccc4d8c5c2c051927
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="create-purchase-orders"></a>Création de commandes fournisseur

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Cet article décrit les processus et les options lorsque vous créez manuellement une commande fournisseur.

Lorsque vous créez une commande fournisseur (CF), des informations générales sur l’ensemble de la commande sont spécifiées dans l’en-tête de la CF, et vous ajoutez ensuite une ou plusieurs lignes de CF. Cet article décrit certaines des options les plus fréquemment utilisées qui sont disponibles.  

Vous pouvez également créer des CF en copiant des lignes à partir d’un autre document de CF ou d'une commande client. Dans ce cas, vous pouvez inverser le signe sur le stock, comme vous inverseriez le signe d’une facture pour indiquer le crédit.  

Bien que vous puissiez créer manuellement les CF, elles sont plus généralement générées par d’autres processus. Les commandes peuvent être créés automatiquement en fonction d'autres documents, tels que des demandes. Sinon, elles peuvent être créées dans le cadre du processus de planification principale par le biais de CF planifiées. Si vous utilisez des contrats d'achat, les CF peuvent être créées par l'action **Lancer la commande**. Il existe également des méthodes plus avancées pour créer automatiquement une CF. Par exemple, les commandes peuvent être créées lorsque vous utilisez une livraison directe ou des chaînes de commandes intersociétés.

## <a name="creating-a-purchase-order-header"></a>Création de l'en-tête de commande fournisseur
Lorsque vous créez une nouvelle CF, une boîte de dialogue apparaît, où vous pouvez entrer les informations les plus courantes pour l’en-tête de la CF. Lorsque vous cliquez sur **OK** pour fermer la boîte de dialogue, la commande est créée et vous pouvez ensuite spécifier des informations supplémentaires dans l’en-tête.  

La première chose à prendre en compte lorsque vous créez une CF, est le type de la commande. Le type **Commande fournisseur** est le plus souvent utilisé. Toutefois, si une facture de crédit est requise, vous pouvez utiliser le type **Commande retournée**.  

Vous devez spécifier le fournisseur dans le champ **Compte fournisseur**. Dans ce champ, vous pouvez rechercher le compte ou le nom du fournisseur. Si un fournisseur livre à partir de plusieurs emplacements, mais utilise un compte de facturation unique, vous pouvez sélectionner ce compte de facturation dans le champ **Compte de facturation** et ensuite l’utiliser avec des comptes de fournisseurs différents. Si vous devez créer une CF pour les produits qui ne sont pas commandés à plusieurs reprises, vous pouvez utiliser l'option **Fournisseur occasionnel**. Cette option crée automatiquement un compte fournisseur qui est marqué comme étant un compte unique, pour prendre en charge un processus de nettoyage ultérieur des comptes uniques dans le module **Comptabilité fournisseur**. Lorsque vous sélectionnez un compte fournisseur, de nombreux champs de l’en-tête de la CF héritent des valeurs par défaut des informations qui sont associées au compte fournisseur. Par exemple, le site de remise et l’entrepôt par défaut sont copiés à partir des informations sur le fournisseur. Toutefois, vous pouvez remplacer ces valeurs par défaut si l’achat est destiné à un autre emplacement.  

Si le fournisseur a fourni un numéro de référence pour la commande, vous pouvez enregistrer ces informations dans le champ **Référence fournisseur**. Pour les commandes retournées, vous devez spécifier une valeur dans le champ **Retour marchandises** pour référencer l’autorisation du fournisseur pour le traitement du retour.  

Si un contrat d’achat est associé à la commande, vous devez spécifier ces informations dans le champ **Contrat d’achat**.  

L’en-tête de la CF contient également des informations sur les frais qui s’appliquent à l’ensemble de la commande au lieu de lignes individuelles. Les frais peuvent être ajoutés automatiquement à la commande si les frais automatiques ont été définis pour le fournisseur ou le groupe de frais du fournisseur. Vous pouvez également ajouter manuellement des frais à l’en-tête de commande en cliquant sur **Tenir les frais à jour** dans le volet Actions.

## <a name="adding-purchase-order-lines"></a>Ajout de lignes de commandes fournisseur
Les CF peuvent être pour des produits physiques ou des services. Un paramètre du groupe de modèles de stock détermine si un numéro d’article spécifique s’applique à un produit ou un service. En règle générale, l’article acheté est spécifié par un numéro d’article. Toutefois, si la commande est pour des produits ou des services qui sont consommés directement, vous pouvez également spécifier l’article à l’aide d’une catégorie d’approvisionnement.  

Les lignes de la CF contiennent de nombreux champs, mais la plupart de ces champs ont une valeur par défaut ou une valeur qui provient de l’en-tête de commande. Des champs supplémentaires sont définis lorsque vous sélectionnez un produit ou un service. Les champs qui sont souvent configurés manuellement incluent les champs pour le numéro d’article, la quantité et la date de livraison demandée. Les informations sur les prix et les remises sont également très importantes, mais les valeurs de ces champs sont souvent déterminées par les accords commerciaux ou les contrats d’achat.  

Lorsque vous sélectionnez un produit, vous pouvez rechercher tout ou partie du nom du produit, au lieu d’utiliser le numéro d’article. Si le produit a plusieurs variantes, par exemple différentes tailles, vous pouvez voir une vue d’ensemble des variantes disponibles à l’aide de la fonction **Ajouter des lignes** ou à l’aide de la recherche qui est disponible dans le champ **Numéro de variante**.  

Souvent, vous devrez spécifier plusieurs dimensions pour l’article sélectionné sur chaque ligne de CF. Les dimensions qui doivent être spécifiées dépendent des groupes de dimensions qui ont été affectés à la définition du produit générique. Par exemple, vous devrez souvent spécifier un site et l’entrepôt pour indiquer l’emplacement auquel le produit doit être livré. Vous identifiez les variantes de produit en spécifiant un numéro de variante, ou en entrant des valeurs pour une ou plusieurs dimensions de produit, comme la couleur, la taille, la configuration ou le style. Le suivi des dimensions, tel que le numéro de série et de lot, vous permet d’identifier de manière unique chaque lot de stock. Une fois que vous avez créé une commande, vous pouvez capturer des valeurs de dimension sur la commande à l’aide de l'action **Enregistrement**. Par exemple, vous avez commandé une quantité de 5 pièces d’un article. Par la suite, vous inscrivez que trois de ces pièces seront noires, et que deux d'entre elles seront bleues. Cette approche constitue une alternative à la capture des informations sur les dimensions lors de l’enregistrement des arrivées.  

Vous pouvez vérifier les détails de l’état de transaction de stock des produits stockés. Par exemple, vous pouvez souhaiter vérifier le stock disponible pour vous aider à décider de la quantité à commander. Vous pouvez également consulter l'état du stock d’une quantité commandée pour voir si l’enregistrement des arrivées entrantes a eu lieu.  

Une ligne de CF est utilisée pour retourner un produit au fournisseur aura une quantité négative. Vous pouvez sélectionner un lot spécifique à retourner à l’aide de l'action **Réservation**.  

Parfois, vous pouvez diviser la quantité que vous avez commandée, afin que les différentes parties de celle-ci soient remises à des dates différentes. Vous pouvez configurer ces livraisons à l’aide de l'action **Calendrier de livraison**, qui est disponible sur le menu **Ligne de commande fournisseur** dans la vue **Lignes**.  

Les frais peuvent être ajoutés automatiquement aux lignes de CF si les frais automatiques ont été définis pour le fournisseur ou le groupe de frais du fournisseur et pour l'article ou le groupe de frais de l'article. Toutefois, en règle générale, les frais sont ajoutés manuellement au niveau de la ligne de commande. Pour ajouter des frais, ouvrez la page **Tenir les frais à jour** à l’aide de l'action **Tenir les frais à jour** sur le menu **Finances** de la vue **Lignes**. L’avantage de l’ajout de frais directement au niveau de la ligne de commande est que les frais peuvent être affectés comme un coût de stock. Pour définir des codes de frais sur un coût du produit de compte, utilisez l'option de débit **Article**. Ces types de frais doivent être alloués à partir de l’en-tête de CF pour les lignes avant la confirmation de la commande. Par exemple, vous pouvez souhaiter allouer des frais en fonction de la quantité de chaque ligne. La catégorie de frais affecte également la façon dont les charges sont comptabilisées. Par exemple, les frais fixes spécifient un montant fixe et les frais en pourcentage sont calculés sous la forme d’un pourcentage du montant HT de la ligne de commande. Les CF peuvent être affectées à un chargement, qui peut inclure une estimation de la dépense prévue pour le coût de transport. Vous pouvez réaffecter cette dépense du chargement aux lignes de CF.

## <a name="purchase-order-actions"></a>Actions liées aux commandes fournisseur
Après avoir ajouté l’en-tête et les lignes à la CF, vous devez souvent effectuer des étapes supplémentaires avant que la commande soit prête à être confirmée. Étant donné que plusieurs options sont disponibles, il peut s’avérer utile d’utiliser [Recherche d'actions](../../fin-and-ops/get-started/action-search.md) pour trouver l’article de menu approprié.  

Vous pouvez configurer des produits de la commande afin qu’ils aient des articles supplémentaires. Les articles supplémentaires sont des produits qui doivent ou peuvent être achetés avec d’autres produits. Les produits supplémentaires peuvent être ajoutés comme produits d’accompagnement gratuitement, ou vous pouvez décider de les ajouter à la commande ou non. Vous pouvez vérifier les articles supplémentaires après l'ajout de chaque ligne de commande. Toutefois, il sera sans doute plus judicieux de passer en revue et d'ajouter des articles supplémentaires pertinents pour toutes les lignes de commande à l’aide de la page **Articles supplémentaires**, que vous pouvez ouvrir à partir du volet Action.  

Les remises sont généralement ajoutées aux lignes lors de leur création. Toutefois, quelques remises s’appliquent à l’ensemble de la commande :

-   L'action **Remise totale** calcule un pourcentage de remise total qui est appliqué à la commande complète. Ne confondez pas cette remise avec le pourcentage d'escompte de règlement. Les escomptes de règlement sont appliqués lorsque la facture est payée, et ils dépendent du règlement du paiement à une date spécifique.
-   Si une remise multiligne s’applique, vous devez utiliser l'action **multiligne** pour la calculer et l'affecter à la commande. Les remises multilignes sont des remises peuvent être proposées si une gamme de produits de la commande dépasse un seuil mixte. Quelques sociétés seulement utilisent ce type de remise.

Les frais qui ont un code de frais qui utilise le type de débit **Article** doivent être affectés au niveau de la ligne avant la confirmation de la commande. Vous trouverez peut-être facile d'affecter ces frais au niveau de l’en-tête de commande, afin que vous puissiez spécifier le montant total des frais. Toutefois, dans ce cas, les frais doivent alors être alloués à chaque ligne avant la confirmation de la commande. Vous pouvez utiliser l'action **Répartir les frais** pour répartir les montants des frais associés au niveau de l’en-tête vers les lignes de commande. Les frais peuvent être répartis en fonction du montant net de chaque ligne, en fonction de la quantité qui a été commandée ou uniformément entre les lignes de commande. Une fois que vous avez affecté des frais sur les lignes, les frais sont supprimés de l’en-tête de commande.  

Les CF peuvent être configurées pour exiger que les fonds budgétaires soient alloués à la commande avant qu'elle puisse être traitée. Dans ce cas, vous pouvez utiliser l'action **Vérification budgétaire** pour allouer le budget.  

Il se peut que vous deviez retarder l’achèvement d’une CF. Par exemple, vous pouvez avoir besoin de plus d’informations sur les produits ou services, ou vous devrez peut-être obtenir une autorisation pour la dépense. Il existe plusieurs façons de suspendre une commande. Par exemple, vous pouvez attendre pour confirmer la commande. Sinon, si un workflow de gestion de modification est utilisé, vous ne soumettez pas la commande à l'approbation. Si vous devez bloquer toutes les commandes pour un fournisseur particulier, vous pouvez également le marquer en tant que **En attente** pour le traitement des données principales sur le fournisseur. Il existe également des circonstances qui pourraient empêcher le traitement de la commande. Par exemple, le traitement peut être empêché si les limites de crédit ont été dépassées, ou si les fonds budgétaires ne sont pas disponibles.

<a name="see-also"></a>Voir également :
--------

[Présentation des commandes fournisseur](purchase-order-overview.md)

[Approbation et confirmation de la commande fournisseur](purchase-order-approval-confirmation.md)

[Accusé de réception de marchandises et commandes fournisseur](product-receipt-against-purchase-orders.md)

[Vue d'ensemble des factures fournisseur](../../financials/accounts-payable/vendor-invoices-overview.md)




