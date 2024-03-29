---
title: Prise en compte de revenu dans les commandes client
description: Cet article décrit les fonctionnalités de base pour constater le produit dans les commandes client et les factures. La prise en compte de revenu est disponible sur les commandes client et sur les factures correspondantes créées à partir des commandes client.
author: bking
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: bb031b41c07aaff06b41830fb0c322503e9f27ec
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348236"
---
# <a name="revenue-recognition-on-sales-orders"></a>prise en compte de revenu dans les commandes client

[!include [banner](../includes/banner.md)]

> [!NOTE]
> La fonctionnalité de prise en compte de revenu ne peut pas être activée via la gestion des fonctionnalités. Vous devez pour l’instant utiliser les clés de configuration pour l’activer.

Cet article décrit les fonctionnalités de base pour constater le produit dans les commandes client et les factures. La prise en compte de revenu est disponible sur une commande client et sur la facture correspondante créée à partir de la commande client. La commande client peut également être créée via un projet Régie.

> [!NOTE]
> Dans les illustrations de cet article, des colonnes ont été masquées ou ajoutées aux grilles afin de mieux expliquer les concepts. Par conséquent, les pages et les données des illustrations peuvent être différentes de ce que vous voyez dans le produit.

## <a name="enter-a-sales-order"></a>Entrer une commande client

La commande client suivante est entrée ; elle comprend trois articles paramétrés pour la prise en compte de revenu.

[![Entrer une commande client.](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Il existe deux concepts pour la prise en compte de revenu :

- **Déterminer le prix du produit** Le prix du produit est calculé en fonction du paramétrage des produits lancés. Le prix du produit n’est jamais présenté au client ; il ne sert qu’aux fins de la comptabilité de la facture client. Les lignes de commande client et les documents imprimés dans le cadre de la vente affichent toujours les prix unitaires ou de liste.
- **Déterminer le moment de la prise en compte de revenu.** L’échéancier de produit sert à déterminer le moment où le produit doit être constaté.

    Dans cet exemple, le premier article, S0001, est affecté à un échéancier de produit **1O** (une occurrence). Cette ligne représente un scénario de type jalons, dans lequel le produit est constaté après que l’installation a été effectuée. Par conséquent, le produit sera différé jusqu’à ce que l’installation soit terminée.

    Le second article, S0008, est un article de service qui est paramétré comme article de support post-contrat (PCS). Des services d’ingénierie continus sont assurés au client pendant une période de 12 mois. Par conséquent, un échéancier de produit **12M** est affecté au produit par défaut. Comme cet article est un article PCS, les dates de début et de fin de contrat doivent être définies. Par défaut, les dates de début et de fin du contrat figurent dans les détails de l’article (onglet Paramétrage). Dans l’échéancier de produit, le paramétrage **12M** est défini de sorte que les termes du contrat sont automatiquement renseignés, comme le montre l’illustration suivante.

    [![Echéanciers de produit.](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    Le troisième article, S0012, est matériel. Aucun échéancier de produit ne lui est affecté par défaut. Le produit des matériels est constaté dès la facturation de l’article.

## <a name="confirm-the-sales-order"></a>Confirmer la commande client

Pour afficher des informations supplémentaires sur le prix du produit et l’échéancier de produit, utilisez les boutons du groupe **prise en compte de revenu** sous l’onglet **Gérer** du volet Actions de la commande client. Étant donné que la commande client n’est pas confirmée à ce stade, les boutons qui sont utilisés pour la prise en compte de revenu ne sont pas disponibles. Ces boutons deviennent disponibles (ou non) à mesure que la commande client progresse dans les étapes de son exécution.

[![En-tête de commande client.](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

Les trois premiers boutons fournissent des détails sur le prix du produit des articles de la commande client paramétrée pour la prise en compte de revenu.

- **Répartition de prix du produit** : ce bouton devient disponible lorsque la commande client est confirmée ou que la facture est validée. La confirmation de la commande client et la validation de la facture calculent toutes les deux le produit à constater et le prix qui sera constaté ou reporté dans l’écriture comptable. Selon le paramétrage, le prix du produit calculé peut différer du prix unitaire affiché au client.
- **Redistribuer le prix avec les nouvelles lignes de commande** : ce bouton devient disponible lorsque la commande client est confirmée ou que la facture est validée. Le processus de redistribution permet de recalculer le produit qui doit être constaté après qu’une nouvelle ligne a été ajoutée à la commande client actuelle après qu’elle a été facturée, ou à une nouvelle commande client. Dans les deux cas, l’ajout d’un nouvel article entraîne la modification du contrat. Par conséquent, le prix de produit doit être redistribué.
- **Mettre à jour la répartition du prix du produit** : ce bouton devient disponible une fois que la commande client est confirmée, mais il devient indisponible lorsque la commande client est facturée. La mise à jour sert à réexécuter la répartition de prix du produit sans avoir à confirmer la commande client. Une fois la commande client facturée, il est impossible de recalculer le prix du produit.

Les deux derniers boutons fournissent des détails sur l’échéancier de produit pour les articles de la commande client comportant un échéancier de produit.

- **Échéancier de prise en compte de revenu prévu** : ce bouton devient disponible une fois que la commande client est confirmée, mais il devient indisponible lorsque la commande client est facturée. Il ouvre une page présentant l’échéancier de produit prévu. L’échéancier final peut changer, parce que l’échéancier prévu utilise la date d’expédition demandée, tandis que l’échéancier final utilise la date d’expédition réelle.
- **Échéancier de prise en compte de revenu** : ce bouton devient disponible une fois que la commande client est facturée. L’échéancier de prise en compte de revenu final n’est pas créé au moment de la confirmation ou de la création d’un bon de livraison. Il n’est créé que lorsque la commande client est facturée.

Dans l’exemple suivant, la répartition de prix du produit s’est produite lorsque la commande client a été confirmée. Notez que, même si les prix de produit sont répartis différemment, le montant total dans le champ **Produit à constater** doit toujours être égal à la somme des lignes de commande client facturées au client. Par exemple, la somme des lignes de la commande client, hors taxe, est 1 499 USD. Par conséquent, la somme des valeurs **Produit à constater** doit également être 1 499 USD.

[![Répartition de prix du produit.](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

L’échéancier de prise en compte de revenu prévu est également créé. L’échéancier de produit utilise la valeur **Produit à constater** comme montant à reporter. L’article S0001 reporte 321,21 USD au lieu de 300 USD, et l’article S0008 reporte 160,61 USD au lieu de 100 USD. L’article S0012 ne s’affiche pas dans l’échéancier prévu car le produit n’est pas différé. Lorsque la validation a lieu, l’article S0012 valide 1 017,18 USD directement dans le compte général de produit.

[![Echéancier de prise en compte de revenu prévu.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Créer le bon de livraison

Ensuite, le bon de livraison peut être créé pour la commande client. Aucun produit n’est constaté lors de la validation du bon de livraison. Si la commande client n’a pas été confirmée, la validation du bon de livraison ne déclenche pas le calcul du prix de produit. Elle ne déclenche pas non plus la création de l’échéancier de prise en compte de revenu prévu ou final. Si le groupe de modèles d’article est paramétré pour différer le produit sur le bon de livraison, il poursuivra la validation en utilisant les comptes généraux actuels du profil de validation, pas les nouveaux comptes de produit différé utilisés pour la validation de la facture.

## <a name="create-the-invoice"></a>Créer la facture

L’étape finale consiste à facturer la commande client. Si vous consultez le justificatif de la facture, vous remarquerez que le produit des articles S0001 et S0008 a été différé (321,21 USD + 160,61 USD = 481,82 USD), et le montant restant pour l’article S0012 a été validé au produit (1 017,18 USD). Ces valeurs atteignent le montant de 1 499 USD, ce qui correspond à la somme des lignes de la commande client.

[![Pièces comptables.](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

Une fois la facture créée, les boutons **Répartition de prix du produit**, **Redistribuer le prix avec les nouvelles lignes de commande** et **Echéancier de prise en compte de revenu** pour la prise en compte de revenu deviennent disponibles, mais les boutons **Mettre à jour la répartition du prix du produit** et **Echéancier de prise en compte de revenu prévu** ne sont pas disponibles.

[![Disponibilité du bouton de prise en compte de revenu.](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

Le bouton **Répartition de prix du produit** est toujours disponible pour que vous puissiez afficher le calcul du prix du produit. Si rien n’a été modifié sur la commande client après qu’elle a été confirmée, la validation de la facture ne change pas le montant calculé dans le champ **Produit à constater**.

L’échéancier de prise en compte de revenu prévu est supprimé et remplacé par l’échéancier de prise en compte de revenu final. Les détails de l’échéancier de produit sont conservés pour chaque ligne de commande client et sont utilisés pour débloquer le produit différé vers le produit réel quand les obligations contractuelles sont satisfaites.

[![Echéancier de prise en compte de revenu final.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
