---
title: "Crédit et recouvrements dans la Comptabilité client"
description: "Les informations de recouvrement de la Comptabilité client sont gérées dans une vue centrale unique qui utilise la page Recouvrements de Microsoft Dynamics 365 for Finance and Operations. Les directeurs des crédits et perceptions peuvent utiliser cette vue centrale pour gérer les recouvrements. Les agents de recouvrement peuvent lancer le processus de recouvrement soit à partir des listes de clients générées à l'aide de critères de recouvrement prédéfinis, soit à partir de la page Clients."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 23fc1a160cf25255a1677ca0e501c374746b6e34
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="credit-and-collections-in-accounts-receivable"></a>Crédit et recouvrements dans le module Ventes

[!include[banner](../includes/banner.md)]


Les informations de recouvrement de la Comptabilité client sont gérées dans une vue centrale unique qui utilise la page Finance and Operations. Les directeurs des crédits et perceptions peuvent utiliser cette vue centrale pour gérer les recouvrements. Les agents de recouvrement peuvent lancer le processus de recouvrement soit à partir des listes de clients générées à l'aide de critères de recouvrement prédéfinis, soit à partir de la page Clients.

Avant de commencer à paramétrer ou utiliser des recouvrements, vous devez comprendre les concepts suivants :
-   Les instantanés de balance âgée des clients contiennent des informations sur les balances âgées à un moment donné
-   Les regroupements de clients de recouvrement vous aident à organiser votre travail.
-   Les agents de recouvrement peuvent avoir leurs propres regroupements de clients
-   Les pages de liste permettent d'organiser les clients, les activités et les demandes de devis de recouvrement.
-   Toutes les informations de recouvrement d'un client sont indiquées sur une seule page qui vous permet d'effectuer diverses opérations.
-   Exonération, rétablissement ou contrepassation des intérêts et des commissions en une seule étape
-   Création de transactions d'annulation en une seule étape
-   Traitement des paiements des impayés en une seule étape

Les sections suivantes décrivent chaque concept.

## <a name="customer-aging-snapshots"></a>Instantanés de balance âgée des clients
Un instantané de balance âgée contient les balances âgées calculées pour un client à un moment donné. Ces informations s'affichent sur la page de liste Soldes chronologiques et sur la page Recouvrements. Vous devez créer un instantané de balance âgée avant de consulter des informations sur les pages de liste Recouvrements. 

Pour chaque client, un instantané de balance âgée contient un en-tête d'instantané de balance âgée et les enregistrements détaillés correspondant à chaque plage âgée dans la définition de plage âgée. 

L'en-tête d'instantané de balance âgée contient le montant total dû, la limite de crédit, le montant du bon de livraison, le nombre de transactions avec litiges de paiement et le montant total de celles-ci pour le compte client. Toutes les transactions pour le client sont incluses dans le calcul de ces montants. Le montant total dû, la limite de crédit, le montant du bon de livraison et le montant de la commande client sont indiqués dans le récapitulatif Informations crédit de la page Recouvrements. 

Pour chaque plage âgée de la définition de plage âgée, un enregistrement détaillé d'instantané de balance âgée est créé. Chaque enregistrement détaillé d'instantané de balance âgée contient l'ID plage âgée et le montant total des transactions avec les dates comprises dans la plage âgée. Les transactions sont affectées à une plage âgée (par exemple, 30 jours de retard). La date est relative à la date Agé tel que spécifiée lors de la création de l'instantané de balance âgée. Ces informations sont indiquées dans la page de liste Soldes chronologiques et dans le récapitulatif Soldes chronologiques de la page Recouvrements.

## <a name="collections-customer-pools"></a>Regroupement de clients pour recouvrement
Les regroupements de clients sont des requêtes qui définissent un groupe d'enregistrements client qui peuvent être affichés et gérés pour les processus liés aux recouvrements ou balances âgées. Les regroupements de clients permettent de filtrer des informations dans les pages de liste Soldes chronologiques, Activités de recouvrement et Dossiers de recouvrement. Vous pouvez également utiliser les regroupements de clients pour filtrer les comptes client inclus lors de la création des instantanés de balance âgée.

## <a name="collections-agents"></a>Agents de recouvrement
Par défaut, les utilisateurs de Microsoft Dynamics 365 for Finance and Operations peuvent afficher toutes les informations client dans les pages de liste de recouvrement. Les enregistrements d'agents de recouvrement permettent de déterminer les regroupements de clients disponibles pour filtrer les informations dans les pages de liste de recouvrement et sur la page Recouvrements. 

Un agent de recouvrement est une personne qui travaille avec les clients pour s'assurer que les paiements sont collectés en temps voulu. Dans Finance and Operations, les agents de recouvrement sont des collaborateurs paramétrés en tant qu'utilisateurs dans la page Paramétrage utilisateur.

## <a name="collections-list-pages"></a>Pages de liste Recouvrements
Les pages de liste suivantes permettent d'organiser les informations de recouvrement.
-   Soldes chronologiques – Les colonnes de la page de liste indiquent les soldes client et les montants âgés par plage âgée. Ces informations sont stockées dans un instantané de balance âgée. Les plages âgées sont déterminées par la définition de plage âgée utilisée. La définition de plage âgée est extraite du regroupement de clients éventuellement spécifié pour la requête de regroupement. Si le regroupement de clients ne dispose pas de définition de plage âgée, la définition de plage âgée par défaut spécifiée sur la page Paramètres de la comptabilité client est utilisée. Si aucune définition de plage âgée par défaut n'est spécifiée, la première définition de plage âgée figurant sur la page Définitions des plages âgées est utilisée.
-   Activités de recouvrement – Les colonnes de la page de liste affichent les activités identifiées en tant qu'activités de recouvrement. Ces activités sont créées à l'aide de la page Recouvrements. Les activités permettent de suivre le travail effectué en relation avec les recouvrements.
-   Dossiers de recouvrement – Les colonnes de la page de liste affichent les informations relatives aux demandes de devis associées à une catégorie de demande de devis et au type de demande de devis Recouvrements.

> [!NOTE]
> Vous devez créer un instantané de balance âgée avant d'afficher des informations dans ces pages de liste. Les informations ne sont affichées que pour les clients pour lesquels un instantané de balance âgée a été créé. L'accès aux enregistrements affichés dans la page de liste peut également être filtré de la manière suivante :
<li>Par défaut, un utilisateur de Finance and Operations a accès à tous les clients associés à un instantané de balance âgée.</li>
<li>Si des regroupements de clients existent, un utilisateur doit être paramétré en tant qu'agent de recouvrement pour les utiliser afin de filtrer les informations des pages de liste de recouvrement. Les informations sont limitées aux clients inclus dans le regroupement de clients sélectionné.</li>
<li>Si un utilisateur est paramétré en tant qu'agent de recouvrement, seuls les regroupements sélectionnés pour celui-ci sont disponibles dans la page de liste. Si l'option Autoriser l'agent à voir tous les regroupements de clients est sélectionnée sur la page Agent de recouvrement pour l'agent de recouvrement, tous les regroupements sont disponibles pour celui-ci.</li>


## <a name="collections-page"></a>Page Recouvrements
La page Recouvrements permet d'afficher, de gérer et d'utiliser les informations, les activités et les demandes de devis de recouvrement pour un client spécifique. 

Le volet supérieur affiche les incidents pour le client sélectionné. Le volet du milieu affiche les transactions pour le client. Le volet inférieur affiche les activités pour le client. Vous pouvez créer des demandes de devis de recouvrement pour suivre les informations de recouvrement pour une ou plusieurs transactions et activités. Les informations des volets supérieur et inférieur peuvent êtres filtrées par demande de devis. 

Les récapitulatifs affichent les informations relatives aux balances âgées et à la limite de crédit pour le client sélectionné. Ces informations sont stockées dans l'instantané de balance âgée. Si nécessaire, vous pouvez mettre à jour l'instantané de balance âgée avec les informations actuelles. 

Le volet Actions inclut des boutons qui affichent les informations relatives au client, à la demande de devis, à la transaction ou à l'activité sélectionné. Vous pouvez également exécuter des actions courantes, telles que modifier le statut des recouvrements d'une transaction, envoyer un message électronique via l'intégration avec votre fournisseur de messagerie électronique, rembourser les clients, traiter les impayés et annuler les soldes irrécouvrables.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a>Exonération, rétablissement ou contrepassation d'intérêts et de frais
Vous pouvez exonérer, rétablir ou contrepasser l'intégralité des notes d'intérêt, ou les frais et les intérêts de transaction faisant partie des notes d'intérêt. Pour ce faire, accédez à l'onglet Recouvrement du volet Actions dans la page de liste Tous les clients, puis cliquez sur Note d'intérêt, Intérêt de la transaction ou Frais. 

Ces ajustements affectent uniquement les notes d'intérêt, et les intérêts et les commissions qu'elles incluent. Les procédures décrites dans la section « Création de transactions d'annulation en une seule étape » permettent d'annuler l'ensemble des frais dus par le client.

Pour plus d'informations, voir [Créer un code intérêt avec une plage](tasks/create-interest-code-range.md) et [Traiter les intérêts](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Création de transactions d'annulation
Vous pouvez annuler les créances irrécouvrables en cliquant sur Annuler dans l'écran Recouvrements, et dans les pages de liste Soldes chronologiques, Clients et Factures client en cours. 

Lorsque vous annulez des transactions pour un client, celles-ci sont automatiquement marquées pour règlement. Le montant annulé dépend du montant net des transactions marquées. La transaction d'annulation est créée dans le journal des opérations diverses et peut contenir jusqu'à trois types de lignes de journal.

-   Le premier type de ligne de journal contient l'entrée d'annulation du client. Si les transactions marquées contiennent plusieurs combinaisons code devise/dimension/profil de validation, une ligne de journal distincte est créée pour chaque combinaison.
-   Le deuxième type de ligne de journal contient l'entrée d'annulation de comptabilité. Si les transactions marquées contiennent plusieurs combinaisons code devise/dimension/profil de validation, une ligne de journal distincte est créée pour chaque combinaison.
-   Le troisième type de ligne de journal contient les informations d'annulation de comptabilité pour les taxes. Cette ligne du journal est créée uniquement si l'option Taxe distincte de la page Paramètres de la comptabilité client est activée. Si les transactions marquées contiennent plusieurs combinaisons compte de collecte de taxe/dimension/code taxe, une ligne de journal distincte est créée pour chaque combinaison.

La transaction d'annulation est créée dans la devise de la transaction.

Pour plus d'informations, voir [Créer un journal d'annulation pour un client](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Traitement des paiements des impayés 
--------------------------------------------

Vous pouvez traiter les paiements des impayés en cliquant sur Paiement des impayés sur la page Recouvrements. Lorsque vous cliquez sur ce bouton, le paiement est annulé. Si des frais d'impayés s'appliquent au client, une transaction de frais est créée dans le journal des paiements. Le montant des frais est basé sur les paramètres relatifs aux frais automatiques. Les frais automatiques qui s'appliquent aux paiements des impayés sont spécifiés par le groupe de frais sélectionné sur la page Comptes bancaires pour le compte bancaire concerné.






