---
title: Concepts clés de la gestion des recouvrements
description: Les rubriques définissent les concepts clés de la gestion des recouvrements.
author: JodiChristiansen
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 508723752ec7ae5f48e52c728b6ef526ec49e4e2
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723021"
---
# <a name="collections-management-key-concepts"></a>Concepts clés de la gestion des recouvrements

[!include [banner](../includes/banner.md)]

Avant de commencer à paramétrer ou utiliser des recouvrements, vous devez comprendre les concepts suivants :

- Les instantanés de balance âgée des clients contiennent des informations sur les balances âgées à un moment donné.
- Les regroupements de clients de recouvrement vous aident à organiser votre travail.
- Les agents de recouvrement peuvent avoir leurs propres regroupements de clients.
- Les pages de liste permettent d’organiser les clients, les activités et les demandes de devis de recouvrement.
- Toutes les informations de recouvrement d’un client sont indiquées sur une seule page qui vous permet d’effectuer diverses opérations.
- Les intérêts et commissions peuvent être exonérés, rétablis ou contrepassés en une seule étape.
- Des transactions d’annulation peuvent être créées en une seule étape.
- Les paiements de fonds insuffisants peuvent être traités en une seule étape.

Cette rubrique décrit chaque concept.

## <a name="customer-aging-snapshots"></a>Instantanés de balance âgée des clients

Un instantané de balance âgée contient les balances âgées calculées pour un client à un moment donné. Ces informations s’affichent sur la page de liste **Soldes échus** et sur la page **Recouvrements**. Un instantané vieillissant doit être créé avant de pouvoir afficher des informations sur les pages de la liste des collections (**Soldes échus**, **Activités de recouvrements**, et **Dossiers de recouvrements**).

Pour chaque client, un instantané de balance âgée contient un en-tête d’instantané de balance âgée et les enregistrements détaillés correspondant à chaque plage âgée dans la définition de plage âgée.

L’en-tête d’instantané de balance âgée contient le montant total dû, la limite de crédit, le montant du bon de livraison, le nombre de transactions avec litiges de paiement et le montant total de celles-ci pour le compte client. Toutes les transactions pour le client sont incluses dans le calcul de ces montants. Le montant total dû, la limite de crédit, le montant du bon de livraison et le montant de la commande client sont indiqués dans le récapitulatif **Informations crédit** de la page **Recouvrements**.

Pour chaque plage âgée de la définition de plage âgée, un enregistrement détaillé d’instantané de balance âgée est créé. Chaque enregistrement détaillé contient l’ID de la plage âgée et le montant total des transactions avec des dates comprises dans la plage âgée. Les transactions sont affectées à une plage âgée (par exemple, 30 jours de retard). La date est relative à la valeur de date **Agé tel que** que vous spécifiez lors de la création de l’instantané de balance âgée. Ces informations sont indiquées dans la page de liste **Soldes échus** et dans le récapitulatif **Soldes échus** de la page **Recouvrements**.

## <a name="collections-customer-pools"></a>Regroupement de clients pour recouvrement

Les regroupements de clients sont des requêtes qui définissent un groupe d’enregistrements client. Vous pouvez utiliser ces enregistrements groupés pour afficher des informations sur les comptes clients qui sont inclus et pour gérer les recouvrements ou les processus de vieillissement pour eux. Vous pouvez utiliser les regroupements de clients pour filtrer des informations dans les pages de liste de recouvrements. Ils vous permettent également de filtrer les comptes client inclus lors de la création des instantanés de balance âgée.

## <a name="collections-agents"></a>Agents de recouvrement

Par défaut, les utilisateurs peuvent afficher toutes les informations client dans les pages de liste de recouvrement. Les enregistrements d’agents de recouvrement permettent de déterminer les regroupements de clients disponibles pour filtrer les informations dans les pages de liste de recouvrement et sur la page **Recouvrements**.

Les agents de recouvrement collaborent avec les clients pour s’assurer que les paiements sont collectés en temps voulu. Ils sont des collaborateurs paramétrés en tant qu’utilisateurs dans la page **Paramétrage utilisateur**.

## <a name="collections-list-pages"></a>Pages de liste Recouvrements

Les pages de liste suivantes permettent d’organiser les informations de recouvrement :

- **Soldes échus** – Les colonnes de cette page de liste affichent les soldes client et les montants âgés par plage âgée. Ces informations sont stockées dans un instantané de balance âgée. Les plages âgées sont déterminées par la définition de plage âgée utilisée. La définition de plage âgée est extraite du regroupement de clients éventuellement spécifié pour la requête de regroupement. Si le regroupement de clients ne dispose pas de définition de plage âgée, la définition de plage âgée par défaut spécifiée sur la page **Paramètres de la comptabilité client** est utilisée. Si aucune définition de plage âgée par défaut n’est spécifiée, la première définition de plage âgée figurant sur la page **Définitions des plages âgées** est utilisée.
- **Activités de recouvrement** – Les colonnes de cette page de liste affichent les activités identifiées en tant qu’activités de recouvrement. Ces activités sont créées à l’aide de la page **Recouvrements**. Vous utilisez des activités pour suivre le travail effectué en relation avec les recouvrements.
- **Dossiers de recouvrement** – Les colonnes de cette page de liste affichent les informations relatives aux demandes de devis associées à une catégorie de demande de devis et au type de demande de devis **Recouvrements**.

### <a name="aging-snapshots"></a>Instantanés de balance âgée

Vous devez créer un instantané de balance âgée avant d’afficher des informations dans les pages de liste de recouvrement. Les informations ne sont affichées que pour les clients pour lesquels un instantané de balance âgée a été créé. L’accès aux enregistrements affichés dans la page de liste peut également être filtré de la manière décrite ici :

- Par défaut, les utilisateurs ont accès à tous les clients associés à un instantané de balance âgée.
- Si des regroupements de clients existent, un utilisateur doit être paramétré en tant qu’agent de recouvrement pour les utiliser afin de filtrer les informations des pages de liste de recouvrement. Les informations sont limitées aux clients inclus dans le regroupement de clients sélectionné.
- Si un utilisateur est paramétré en tant qu’agent de recouvrement, seuls les regroupements sélectionnés pour celui-ci sont disponibles dans les page de liste de recouvrements. Si l’option **Autoriser l’agent à voir tous les regroupements de clients** est sélectionnée sur la page **Agent de recouvrement** pour l’agent de recouvrement, tous les regroupements sont disponibles pour celui-ci.

## <a name="collections-page"></a>Page Recouvrements

La page **Recouvrements** permet d’afficher, de gérer et d’utiliser les informations, les activités et les demandes de devis de recouvrement pour un client spécifique.

La section supérieure de la page affiche les dossiers pour le client sélectionné, la section centrale affiche les transactions pour le client et la section inférieure affiche les activités pour le client. Vous pouvez créer des demandes de devis de recouvrement pour suivre les informations de recouvrement pour une ou plusieurs transactions et activités. Les informations des sections supérieure et inférieure peuvent êtres filtrées par demande de devis.

Les récapitulatifs affichent les informations relatives aux balances âgées et à la limite de crédit pour le client sélectionné. Ces informations sont stockées dans l’instantané de balance âgée. Si nécessaire, vous pouvez mettre à jour l’instantané de balance âgée avec les informations actuelles.

Le volet Actions inclut des boutons qui affichent les informations relatives au client, à la demande de devis, à la transaction ou à l’activité sélectionné. Vous pouvez également exécuter des actions courantes, telles que modifier le statut des recouvrements d’une transaction, envoyer un message électronique via l’intégration avec votre fournisseur de messagerie électronique, rembourser les clients, traiter les impayés et annuler les soldes irrécouvrables.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Exonération, rétablissement ou contrepassation d’intérêts et de frais

Vous pouvez exonérer, rétablir ou contrepasser l’intégralité des notes d’intérêt, ou les frais et les intérêts de transaction faisant partie des notes d’intérêt. Pour ce faire, accédez à l’onglet **Recouvrement** du volet Actions dans la page de liste **Tous les clients**, sélectionnez **Note d’intérêt**, **Intérêt de la transaction** ou **Frais**.

Ces ajustements affectent uniquement les notes d’intérêt, et les intérêts et les commissions qu’elles incluent. Pour savoir comment annuler tous les frais qu’un client doit, consultez la section [Création de transactions d’annulation](#creating-write-off-transactions) de cette rubrique.

Pour plus d’informations, voir Créer un code intérêt avec une plage et Traiter les intérêts.

## <a name="creating-write-off-transactions"></a>Création de transactions d’annulation

Vous pouvez annuler les créances irrécouvrables en sélectionnant **Annuler** dans la page **Recouvrements** et les pages de liste des recouvrements.

Lorsque vous annulez des transactions pour un client, celles-ci sont automatiquement marquées pour règlement. Le montant annulé dépend du montant net des transactions marquées. La transaction d’annulation est créée dans le journal des opérations diverses et peut contenir jusqu’à trois types de lignes de journal :

- Le premier type de ligne de journal contient l’entrée d’annulation du client. Si les transactions marquées contiennent plusieurs combinaisons codes devise, dimensions et profils de validation, une ligne de journal distincte est créée pour chaque combinaison.
- Le deuxième type de ligne de journal contient l’entrée d’annulation de comptabilité. Si les transactions marquées contiennent plusieurs combinaisons codes devise, dimensions et profils de validation, une ligne de journal distincte est créée pour chaque combinaison.
- Le troisième type de ligne de journal contient les informations d’annulation de comptabilité pour les taxes. Cette ligne du journal est créée uniquement si l’option **Taxe distincte** de la page **Paramètres de la comptabilité client** est activée. Si les transactions marquées contiennent plusieurs combinaisons comptes de collecte de taxe, dimensions, codes taxe, une ligne de journal distincte est créée pour chaque combinaison. La transaction d’annulation est créée dans la devise de la transaction. Pour plus d’informations, voir Créer un journal d’annulation pour un client.

## <a name="process-nsf-payments"></a>Traiter les paiements des impayés

Vous pouvez traiter les paiements des impayés en sélectionnant **Paiement des impayés** dans la page **Recouvrements**. Lorsque vous sélectionnez ce bouton, le paiement est annulé. Si des frais d’impayés s’appliquent au client, une transaction de frais est créée dans le journal des paiements. Le montant des frais est basé sur les paramètres relatifs aux frais automatiques. Les frais automatiques qui s’appliquent aux paiements des impayés sont spécifiés par le groupe de frais sélectionné sur la page **Comptes bancaires** pour le compte bancaire concerné.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrage de la gestion du crédit client](./cm-credit-mgmt-setup.md)

[Informations sur le paramétrage de la gestion du crédit client](./cm-setup-information.md)

[Ajout d’informations sur la gestion du crédit pour un client](./cm-add-credit-mgmt-information-customer.md)

[Groupes de créditer du client](./cm-customer-credit-groups.md)

[Ajustements de limite de crédit client](./cm-credit-limit-adjustments.md)

[Blocages pour les commandes client](./cm-sales-order-credit-holds.md)

[Tâches périodiques de gestion des crédits client](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
