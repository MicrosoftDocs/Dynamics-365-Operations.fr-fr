---
title: Offres groupées dans la prise en compte de revenu
description: Cet article décrit la fonctionnalité d’offre groupée incluse dans la fonction de prise en compte de revenu en Comptabilité client. Une offre groupée comprend un article parent et plusieurs éléments constitutifs.
author: bking
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 9b33906fd1907ce476eec5ba36ab243aa072cf6f
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348295"
---
# <a name="revenue-recognition-bundles"></a>Offres groupées dans la prise en compte de revenu

[!include [banner](../includes/banner.md)]

Cet article décrit la fonctionnalité d’offre groupée incluse dans la fonction de prise en compte de revenu en Comptabilité client. Une offre groupée comprend un article parent et plusieurs éléments constitutifs. L’article parent est saisi sur une commande client, pour que la saisie soit plus efficace. Cependant, il est ensuite éclaté dans les éléments constitutifs. Les documents internes, tels que le bon de livraison, répertorient les éléments constitutifs. Cependant, les documents externes affichent uniquement l’élément parent.

> [!NOTE]
> Les canaux Microsoft Dynamics 365 Commerce, tels que les services en ligne, les points de vente (PDV) et les centres d’appels, ne prennent pas en charge la prise en compte de revenu (y compris la fonctionnalité d’offre groupée). Cela inclut également la solution Prospect en disponibilités pour Dynamics 365 Supply Chain Management et Dynamics 365 Sales. Les articles configurés pour utiliser la prise en compte de revenu ne doivent pas être ajoutés aux commandes ou aux transactions créées dans les canaux Commerce ou dans la solution Prospect en disponibilités.

Pour configurer des offres groupées, vous devez saisir les clés de configuration pour la prise en compte de revenu. Cependant, vous pouvez utiliser des offres groupées même si la prise en compte de revenu n’est pas configurée. De même, vous pouvez utiliser la prise en compte de revenu si les offres groupées ne sont pas configurées. Si la prise en compte de revenu est configurée, les éléments constitutifs déterminent le prix du produit et l’échéancier de produit utilisés pour la comptabilisation ou le report lorsqu’une commande client est facturée.

Le paramétrage d’offres groupées utilise la fonctionnalité de nomenclature. Pour plus d’informations sur la configuration d’un article d’offre groupée, voir [Configuration de la fonctionnalité de prise en compte de revenu](revenue-recognition-setup.md). Si l’article parent est marqué comme une offre groupée, il est traité différemment des autres articles de la nomenclature. Voici une liste des différences :

- Les offres groupées doivent être éclatées lors de la confirmation de la commande client, en sélectionnant **Confirmer les commandes client** sur l’onglet **Vendre** du volet Actions sur la page de commande client. Les articles groupés ne doivent jamais être éclatés en sélectionnant **Ligne de nomenclature** sous **Éclater** sur le menu **Ligne de commande client** sur le raccourci **Lignes de commande client**. Sinon, l’article sera traité comme une nomenclature et non comme une offre groupée.
- Une commande client contenant un article groupé doit être confirmée avant la création du bon de livraison ou de la facture.
- Lorsqu’un lot est éclaté via la confirmation de la commande client, l’article parent est annulé et son prix unitaire et les remises sont attribués aux éléments constitutifs du lot.
- La somme des éléments constitutifs doit toujours être égale au prix de l’élément parent. Par conséquent, il existe des limitations sur les champs qui peuvent être mis à jour ou modifiés pour les éléments constitutifs. Par exemple, le prix unitaire ne peut pas être modifié manuellement. Il ne peut pas non plus être modifié indirectement en faisant entrer en vigueur un nouvel accord sur les prix. Pour éviter un nouvel accord de prix, les dimensions de l’inventaire ne peuvent pas être modifiées sur les éléments constitutifs.
- Lorsqu’un document externe tel que la confirmation de commande client ou la facture est imprimé, l’article parent est imprimé, pas les articles constitutifs.

## <a name="bundles-on-sales-orders"></a>Offres groupées sur les commandes client

La société de démonstration USMF inclut la configuration d’offre groupée suivante. Notez que toutes les configurations pour la prise en compte de revenu, telles que la configuration des calendriers de revenus, ont été supprimées des éléments inclus dans ce scénario.

**Élément parent :** Lot d’ordinateurs portables

- **Élément constitutif :** Quantité de 1 de l’article 1000
- **Élément constitutif :** Quantité de 1 de l’article S0021
- **Élément constitutif :** Quantité de 1 de l’article Support

Le *prix de vente de base* des éléments constitutifs est une partie essentielle de la configuration des composants. Le prix de vente de base est défini sur le raccourci **Vendre** d’un élément. Il est utilisé pour calculer le facteur de répartition lorsque le prix unitaire de l’article parent est alloué aux articles constitutifs. Les prix de vente des accords commerciaux ne sont jamais utilisés à cette fin.

Les prix de vente de base suivants sont définis pour les éléments constitutifs :

- **1000 :** 1 900 $
- **S0021 :** 150 $
- **Support :** 500 $

Une commande client est saisie pour le client US-004, Cave Wholesales. La seule ligne qui est saisie est pour le lot d’ordinateurs portables. Le prix unitaire par défaut de la ligne parente peut provenir de nombreux endroits, tels que l’accord commercial ou le prix de vente de base. Dans cet exemple, un montant de 2 300 $ a été saisi manuellement comme prix unitaire.

[![Lot d’ordinateurs portables sur une commande client.](./media/bundle-01.png)](./media/bundle-01.png)

Étant donné que la commande client contient un lot, elle doit être confirmée. La boîte de dialogue de confirmation affiche les composants de l’offre groupée.

[![Boîte de dialogue Confirmer les commandes client avec les éléments constitutifs.](./media/bundle-02.png)](./media/bundle-02.png)

Cependant, le rapport de confirmation imprimé affichera uniquement l’élément parent du lot, car ce rapport est le document externe présenté au client.

[![Rapport de confirmation avec uniquement l’élément parent.](./media/bundle-03.png)](./media/bundle-03.png)

Une fois la commande client confirmée, l’article parent est toujours affiché sur la commande client, mais son statut est désormais **Annulé**. De plus, le montant net fait l’objet d’un suivi dans le champ **Montant net de l’offre groupée**. Ce montant est nécessaire pour imprimer la facture, car la facture montre l’article parent, pas les articles constitutifs.

La somme des articles constitutifs doit être égale à la valeur du **Montant net de l’offre groupée** de l’article parent, car cette valeur est le montant présenté au client sur la facture imprimée. Pour garantir que la facture correspond aux montants enregistrés en comptabilité, les modifications apportées aux éléments constitutifs sont limitées. Par exemple, le site et l’entrepôt ne peuvent pas être modifiés, car ces modifications peuvent déclencher un changement de prix, basé sur un accord commercial.

Le prix unitaire de la ligne de l’article parent est attribué aux composants de la manière suivante :

**Prix de vente total de base des composants :** 1 900 $ + 500 $ + 150 $ = 2 550 $

- **Composant 1 :** 2 300 $ × (1 900 ÷ 2 550) = 1 713,73 $
- **Composant 2 :** 2 300 $ × (500 ÷ 2 550) = 450,98 $
- **Composant 3 :** 2 300 $ × (150 ÷ 2 550) = 135,29 $

La somme des composants doit être égale à 2 300 $, et c’est le cas (1713,73 $ + 450,98 $ + 135,29 $ = 2 300 $).

Si des modifications sont nécessaires pour tous les éléments constitutifs, l’élément parent peut être supprimé. Dans ce cas, les éléments constitutifs sont également supprimés. L’article parent peut ensuite être ajouté à nouveau et les modifications requises peuvent être effectuées avant la confirmation de la commande client.

[![Article d’offre groupée qui inclut les modifications apportées aux éléments constitutifs.](./media/bundle-04.png)](./media/bundle-04.png)

Lorsque la commande client est emballée et retirée, les documents comprennent uniquement les composants de l’offre groupée. Le bon de livraison et la facture doivent inclure un lot complet. Sinon, ils ne peuvent pas être validés. Par exemple, la boîte de dialogue affiche trois éléments constitutifs. Si vous essayez de supprimer l’un d’entre eux, vous recevez un message d’erreur indiquant que tous les produits du lot doivent être expédiés avant de pouvoir être facturés.

Une offre groupée doit être expédiée et facturée comme un lot complet. Par exemple, si vous remplacez la quantité de l’article 1000 par 4, mais que vous laissez la quantité des autres articles composant à 5, le bon de livraison et la facture ne peuvent pas être validés.

Un montant partiel ne peut être expédié et facturé que si la quantité est réduite pour tous les composants de l’offre groupée. Par exemple, une quantité de 5 de l’article Lot d’ordinateurs portables est saisie sur une commande client. Une fois la commande client confirmée, les trois éléments constitutifs sont indiqués sur la commande client et la quantité de chacun est de 5. Par défaut, lors de l’expédition et de la facturation, la quantité sera fixée à 5 pour chaque élément constitutif. Cependant, vous pouvez ajuster la quantité à 3 pour les trois éléments constitutifs. Dans ce cas, trois lots complets seront expédiés et facturés. Les deux articles groupés restants (une quantité de 2 de chacun des trois articles) peuvent être expédiés et facturés ultérieurement.

L’étape finale consiste à facturer la commande client. Lors de la facturation, la boîte de dialogue de facturation affichera les éléments constitutifs.

[![Boîte de dialogue de facturation avec les éléments constitutifs.](./media/bundle-06.png)](./media/bundle-06.png)

Cependant, la facture imprimée affichera uniquement l’élément parent.
 
[![Facture imprimée avec uniquement l’élément parent.](./media/bundle-07.png)](./media/bundle-07.png)

Le journal des factures qui est créé après la validation n’inclut pas l’article parent du groupe, car le statut de cet article est **Annulé**.

[![Journal des factures sans l’élément parent.](./media/bundle-08.png)](./media/bundle-08.png)

Il est important que le journal des factures n’inclue pas l’article parent du groupe, car tous les processus exécutés après la validation de la facture sont basés sur ce journal des factures. Par exemple, si vous créez une note de crédit à partir de l’onglet **Vendre** du volet Actions, la note de crédit créée inclura les éléments constitutifs mais pas l’élément parent.

[![Note de crédit qui montre les éléments constitutifs mais pas l’élément parent.](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
