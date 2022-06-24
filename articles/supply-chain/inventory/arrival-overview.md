---
title: Vue d’ensemble des arrivées
description: Cet article fournit des informations sur la fonctionnalité Vue d’ensemble des arrivées. La page Vue d’ensemble des arrivées fait partie de cette fonction et fournit une vue d’ensemble de tous les articles attendus en tant qu’articles entrants.
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 8118db9469c01c43b23c64ee383ac1d383a0ba7a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874070"
---
# <a name="arrival-overview"></a>Vue d’ensemble des arrivées

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la fonctionnalité Vue d’ensemble des arrivées. La page Vue d’ensemble des arrivées fait partie de cette fonction et fournit une vue d’ensemble de tous les articles attendus en tant qu’articles entrants.

La page **Vue d’ensemble des arrivées** fournit une vue d’ensemble de tous les articles entrants prévus. Elle montre également les arrivées qui peuvent être initialisées en fonction de la vue d’ensemble. Cet article aborde plus en détail le processus de réception.

## <a name="business-scenario"></a>Scénario d’entreprise
Considérez le scénario suivant dans les processus entrants.

[![Scénario métier.](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sammy, un employé de la réception, souhaite connaître les arrivées attendues ce jour. Dans la page **Vue d’ensemble des arrivées**, Sammy peut obtenir une vue d’ensemble des tâches actuelles, et une estimation grossière des quantités, volumes, poids, types d’ordre, et ainsi de suite. Ensuite, une livraison arrive à l’un des quais d’embarquement, et Sammy reçoit une liste de livraison. Dans la page **Vue d’ensemble des arrivées**, Sammy peut effectuer les tâches suivantes :

-   Identifier l’odre de réception correspondant, et enregistrer la réception comme **En cours**. Les lignes requises pour un enregistrement sont automatiquement générées, et la réception peut être contrôlée, même si les transactions n’ont pas encore été validées comme **Enregistrées**.
-   Accéder à la référence des journaux des arrivées appropriés (autrement dit, le journal **Arrivée d’articles** ou le journal **Entrée en production** ), et identifier les journaux qui sont prêts pour la mise à jour d’accusé de réception de marchandises.

## <a name="arrival-overview-page"></a>Page Vue d’ensemble des arrivées
Pour ouvrir la page **Vue d’ensemble des arrivées**, cliquez sur **Gestion des stocks** &gt; **Commandes entrantes** &gt; **Vue d’ensemble des arrivées**. Vous pouvez afficher une liste des ordres prévus en réception. La vue d’ensemble comporte un en-tête et des lignes. Les informations d’en-tête sont regroupées par type d’ordre, date de réception prévue, et destination de livraison. Lorsqu’une ligne d’en-tête est sélectionnée pour l’arrivée, toutes les lignes détaillées relatives à la référence de réception sont sélectionnées pour l’arrivée dans la partie de détails de ligne de la page. Lorsque toutes les lignes de journal associées ont été validées, ces informations ne sont plus affichées.

### <a name="arrival-overview-profiles"></a>Profils de vue d’ensemble des arrivées

La page **Vue d’ensemble des arrivées** fournit une vue d’ensemble des articles qui sont chargés à l’arrivée et la date à laquelle il est prévu qu’ils arrivent. Dans le cadre du processus d’arrivée, plusieurs ensembles de paramètres personnels peuvent être utilisés. Les utilisateurs peuvent définir leurs propres paramètres sur la page **Profils de vue d’ensemble des arrivées**.

### <a name="set-up-item-arrival"></a>Paramétrer l’arrivée d’articles

Dans notre exemple, Sammy veut ajouter un nouvel ordinateur à un emplacement qui sera utilisé pour recevoir les produits finis issus de la production du site 1. Dans la page **Profils de vue d’ensemble des arrivées**, Sammy crée un paramétrage **Production du site 1** et spécifie les paramètres suivants.

1.  Dans l’organisateur **Options des arrivées**, dans le groupe de champs **Plage**, entrez l’intervalle en jours et les entrepôts à inclure dans la vue d’ensemble.
2.  Dans l’organisateur **Options des arrivées**, dans le groupe de champs **Journal**, entrez un entrepôt de réception, un emplacement, et un nom de journal (arrivée d’articles/entrée en production).
3.  Dans l’organisateur **Détails des requêtes des arrivées**, dans le groupe de champs **Site**, dans le champ **Limiter au site**, entrez un site pour limiter la vue à la zone de vue d’ensemble.
4.  Dans l’organisateur **Détails des requêtes des arrivées<**, dans le groupe de champs **Types de transactions affichés**, définissez l’option **Ordres de fabrication** sur **Oui**.
5.  Dans l’organisateur **Détails des requêtes des arrivées**, dans le groupe **Divers**, définissez l’option **Mettre à jour au démarrage** sur **Oui** si la vue est mise à jour automatiquement au démarrage. Définissez l’option **Mettre à jour après modification de la plage** sur **Oui** si la vue est automatiquement mise à jour lorsque les valeurs de plage sont modifiées.

Pour cet exemple, le champ **Nom du profil de vue d’ensemble des arrivées** sur l’organisateur **Options des arrivées** de la page **Vue d’ensemble des arrivées** est défini sur **Production du site 1**.

### <a name="prerequisites-for-arrival-journals"></a>Conditions préalables pour les journaux des arrivées

Pour créer automatiquement des journaux des arrivées depuis la page **Vue d’ensemble des arrivées**, vous devez définir les informations appropriées dans le groupe de champs **Journal** sur l’organisateur **Options des arrivées**.

-   Vous devez spécifier un nom de journal pour créer un nouveau journal.

[![Spécification d’un nom de journal.](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Si vous spécifiez des valeurs dans les champs **Entrepôt** et **Emplacement**, ces valeurs sont appliquées aux lignes du journal. Si vous ne spécifiez pas de valeurs, le système utilise les valeurs de la dimension spécifiée dans les mouvements de stock.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Articles reçus d’un seul ordre de réception attendu

Dans l’organisateur **Réceptions**, Sammy sélectionne une ligne, puis clique sur **Commencer une arrivée**. Toutes les lignes associées dans la plage spécifiée et qui ont une quantité à enregistrer sont sélectionnées automatiquement. Un journal des arrivées d’articles est généré et l’ordre de réception prévu et le journal sont mis en correspondance. La quantité est automatiquement initialisée sur toutes les lignes créées.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Articles reçus de plusieurs ordres de réception attendus

Dans l’organisateur **Réceptions**, Sammy sélectionne plusieurs lignes, puis clique sur **Commencer une arrivée**. Un journal des arrivées d’articles est généré et tous les ordres de réception prévus et le journal sont mis en correspondance. Toutes les lignes sont créées dans un seul en-tête de journal des arrivées d’articles, et la quantité est automatiquement initialisée.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Articles reçus d’un ou plusieurs ordres de réception attendus

#### <a name="view-information"></a>Afficher les informations

Pour obtenir une vue d’ensemble des réceptions prévues dans l’intervalle de dates, Sammy entre les informations suivantes dans les champs de l’organisateur **Options des arrivées** sur la page **Vue d’ensemble des arrivées**, puis clique sur **Mettre à jour** pour mettre à jour la vue :

-   Nom du profil de vue d’ensemble des arrivées : **Recherche**
-   Afficher les lignes : **Tout**
-   Jours avant : (Vide)
-   Jours après : **0**
-   Entrepôts : **GW, EP**

Sammy peut afficher les informations suivantes :

-   Tous les ordres de réception associés pour la date système et un nombre infini de jours avant celle-ci (intervalle **InventTrans.StatusDate** ), et les réceptions aux entrepôts GW et MW, quel que soit leur statut.
-   Ligne de détail des informations pour plusieurs ordres. Sammy peut sélectionner plusieurs lignes d’en-tête dans la vue d’ensemble, puis cliquer sur **Afficher tous les éléments sélectionnés** pour afficher toutes les informations correspondantes du détail de ligne pour tous les ordres sélectionnés.
-   Informations sur une commande fournisseur spécifique. Pour afficher des informations concernant uniquement un numéro de référence spécifique dans la vue d’ensemble, Sammy peut entrer un numéro de compte dans le champ **Numéro de compte** et un numéro de commande dans le champ **Numéro de référence**.
-   Vue d’ensemble des tâches d’enregistrement qui sont dues pour toutes les lignes de commande qu’un journal des arrivées d’articles a créées pour n’a pas encore validées. Pour afficher ces informations, Sammy peut sélectionner **En cours** dans le champ **Afficher les lignes**.

### <a name="update-journals"></a>Mise à jour des journaux

Pour enregistrer une ou plusieurs lignes de commande à traiter, Sammy peut sélectionner les lignes dans la vue d’ensemble ou dans la grille, puis cliquer sur **Journaux** &gt; **Afficher les arrivées à partir des réceptions**. Les en-têtes d’arrivée d’articles qui correspondent aux lignes sont affichés. Pour mettre à jour l’accusé de réception de marchandises de la commande fournisseur avec les articles enregistrés, Sammy peut accéder aux en-têtes de journal des arrivées d’articles prêts à être mis à jour. Pour accéder à ces en-têtes de journal des arrivées d’articles, il clique sur **Journaux** &gt; **Journaux prêts pour l’accusé de réception de produits**. Toutes les lignes d’en-tête qui sont prêtes à être mises à jour dans l’accusé de réception de marchandises dans la plage d’entrepôt spécifiée sont affichées. (Les lignes d’en-tête affichées ne sont pas associées à l’intervalle en jours).

### <a name="start-an-arrival-registration"></a>Démarrer un enregistrement de pointage à l’arrivée

En sélectionnant plusieurs lignes sur la page **Vue d’ensemble des arrivées**, Sammy peut lancer une arrivée pour plus d’une référence de réception. Lorsqu’il sélectionne une ligne dans la vue d’ensemble des réceptions, les détails de la ligne correspondants sont sélectionnés. Si une quantité à enregistrer existe, le bouton **Commencer une arrivée** est disponible. Sammy peut utiliser deux méthodes pour démarrer l’enregistrement de pointage à l’arrivée :

-   Pour filtrer la page afin qu’elle affiche uniquement les enregistrements qui répondent aux critères spécifiques, dans le champ **Référence fournisseur**, il suffit de scanner un numéro de référence d’un fournisseur, tel que le code-barres d’une note de livraison.
-   Dans la vue d’ensemble ou les détails de la page **Vue d’ensemble des arrivées**, sélectionnez ou supprimez manuellement la sélection des enregistrements pour l’enregistrement de pointage à l’arrivée. Lorsque Sammy cliquera sur **Commencer une arrivée**, les enregistrements sélectionnés seront automatiquement créés dans un journal des arrivées d’articles. Les enregistrements incluent les informations de ligne, et toutes les informations de champ uniques sont renseignées.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Mettre à jour les informations sur les arrivées et l’accusé de réception de marchandises
Lorsque toutes les marchandises ont été enregistrées, le gestionnaire d’entrepôt ou le gestionnaire des achats peut mettre à jour les articles reçus avec un accusé de réception de marchandises pour ajouter les coûts physiques. Pour mettre à jour les informations relatives aux arrivées et valider un accusé de réception de marchandises, procédez comme suit.

1.  Cliquez sur **Gestion des stocks** &gt; **Commandes entrantes** &gt; **Vue d’ensemble des arrivées**.
2.  Dans la page **Vue d’ensemble des arrivées**, cliquez sur **Journaux** &gt; **Journaux prêts pour l’accusé de réception de produits** pour afficher une liste des journaux qui sont prêts pour la mise à jour de l’accusé de réception de marchandises.
3.  Sélectionnez les journaux qui doivent être mis à jour, puis cliquez sur **Fonctions** &gt; **Accusé de réception de marchandises**.
4.  Dans la page **Validation**, entrez le nombre de l’accusé de réception de marchandises, s’il n’est pas déjà disponible dans le journal, puis cliquez sur **Ajouter** pour traiter l’accusé de réception de marchandises.

## <a name="summary"></a>Synthèse
La page **Vue d’ensemble des arrivées** donne au gestionnaire d’entrepôt et aux collaborateurs d’entrepôt une vue d’ensemble du travail prévu qui doit être effectué dans le cadre du processus entrant. La page peut également être utilisée pour démarrer le processus d’arrivée d’articles, pour garantir que les articles sont suivis à la première entrée dans l’entrepôt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]