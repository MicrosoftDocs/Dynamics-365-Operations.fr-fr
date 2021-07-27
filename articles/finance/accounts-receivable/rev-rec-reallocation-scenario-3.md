---
title: Réaffectation de la prise en compte de revenu - Scénario 3
description: Cette rubrique décrit un scénario de réaffectation dans lequel une nouvelle ligne est ajoutée à une commande client existante, facturée. Lorsqu’un nouvel article est ajouté à un contrat, il peut être ajouté soit à une nouvelle commande client, soit à la commande client existante.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4242be761ed170155b70211d99eb5018fb254071
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356171"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Réaffectation de la prise en compte de revenu - Scénario 3

[!include [banner](../includes/banner.md)]

Cette rubrique décrit un scénario de réaffectation dans lequel une nouvelle ligne est ajoutée à une commande client existante, facturée. Lorsqu’un nouvel article est ajouté à un contrat, il peut être ajouté soit à une nouvelle commande client, soit à la commande client existante. Ce scénario montre également ce qui se produit lors d’une mise à jour en Comptabilité client suite à une réaffectation.

Pour ce scénario, l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Oui** sur l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de Comptabilité**).

[![Option Valider les corrections des factures dans la Comptabilité client définie sur Oui.](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Une commande client est créée pour le client US\_SI\_0003. Le client achète un ordinateur portable (numéro d’article S0012) et un plan de support (numéro d’article S0008, « Service d’ingénierie continu »). Le produit de l’ordinateur portable est immédiatement reconnu. Le produit du plan de support est différé et reconnu sur 12 mois, comme défini par la plage de dates dans le contrat.

[![Lignes de commande client pour l’ordinateur portable et plan de support.](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

La commande client est confirmée. Étant donné que les deux articles sont configurés pour la répartition du prix du produit, celui-ci est calculé lorsque la commande client est confirmée. Vous pouvez afficher les produits qui seront reconnus sur la page **Répartition de prix du produit** (sur la page **Commande client**, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Prise en compte de revenu**, sélectionnez **Répartition de prix du produit**). Le produit de l’ordinateur portable sera imputé au compte Produit pour un montant de 1 008,01 $. Le produit du plan de support sera imputé au compte Produit différé pour un montant de 190,99 $. La somme des prix doit être égale à la somme des lignes qui ont été configurées pour capturer la répartition de prix du produit (1 199,00 $).

[![Page Répartition de prix du produit.](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

La commande client est entièrement facturée. L’illustration suivante montre l’écriture comptable validée pour la facture.

[![Écriture comptable de la commande client entièrement facturée.](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

L’échéancier de prise en compte de revenu est également créé. Au bout d’un certain temps, deux mois ont un produit identifié pour le plan de support.

[![Page Échéancier de prise en compte de revenu après deux mois.](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

À ce stade, le client décide d’ajouter des services d’installation (numéro d’article S0001). Cet article est ajouté à la commande client existante. Le client est invité à confirmer qu’il souhaite modifier la commande client entièrement facturée et il sélectionne **Oui**.

[![Commande client après l’ajout de la ligne pour les services d’installation.](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Si ce nouvel article est la seule modification apportée au contrat du client, le processus de réaffectation peut maintenant être exécuté. Dans la commande client, sélectionnez **Redistribuer le prix avec les nouvelles lignes de commande** pour ouvrir la page **Redistribuer le prix avec les nouvelles lignes de commande**. Sélectionnez toutes les lignes de la commande client pour cette commande client, puis sélectionnez **Mettre à jour la réaffectation**. La colonne **Montant réaffecté** affiche le nouveau prix des revenus pour chaque ligne de commande client.

[![Nouveaux prix de produit sur la page Redistribuer le prix avec les nouvelles lignes de commande.](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Ensuite, sélectionnez **Justificatif attendu** pour afficher les écritures comptables. Comme l’option **Valider les corrections des factures dans la comptabilité client lors de la réaffectation** est définie sur **Oui** sur la page **Paramètres de Comptabilité**, ces écritures comptables seront enregistrées en Comptabilité via le document de crédit et une nouvelle facture sera créée dans Comptabilité client.

[![Écritures comptables sur la page Justificatif attendu.](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

Sur la page **Justificatif attendu**, les quatre dernières lignes contrepassent l’écriture comptable d’origine de la facture validée. Les cinq premières lignes constituent les nouvelles écritures comptables qui sont imputées pour la facture. Il est important de comprendre qu’une nouvelle facture n’est pas présentée au client. Après la réaffectation, le client doit toujours 1 276,94 $, qui est le montant qui doit être imputé aux comptes clients dans la nouvelle écriture comptable. Le total de la taxe compensatoire et du produit ou produit différé est égal à 995,83 $ + 188,69 $ + 77,94 $ = 1 262,46 $. Le montant du produit ou du produit différé a changé en raison de la réaffectation. La différence de -14,48 $ est imputée dans un compte de compensation des revenus de facturation partielle. Ce solde sera supprimé une fois la facture imputée pour le nouvel article qui a été ajouté à la commande client.

Pour terminer la réaffectation, sélectionnez **Processus**. Une date de validation est saisie. Une fois la réaffectation terminée, la page **Répartition de prix du produit** montre la réallocation des prix pour les trois articles.

[![Réallocation de prix pour les trois articles sur la page Répartition de prix du produit.](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

L’échéancier de prise en compte de revenu a également été mis à jour, en fonction du nouveau prix de réaffectation du produit. À partir de la commande client, ouvrez la page **Échéancier de prise en compte de revenu**. Auparavant, il y avait 13 lignes pour l’article S0008 (un échéancier de 12 mois était attribué à cet article). Il y a maintenant 39 lignes : les 13 échéances d’origine, 13 échéances de contrepassation et 13 lignes basées sur le nouveau prix du produit.

[![Page Échéancier de prise en compte de revenu mis à jour avec 39 lignes pour l’article S0008.](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Lorsque vous sélectionnez **Justificatif**, le journal des factures affiche l’écriture comptable d’origine. Pour afficher l’écriture de contrepassation et la nouvelle écriture comptable à partir de la commande client, sélectionnez **Ajustements de produit** dans le volet Actions, puis sélectionnez **Justificatif**.

Ensuite, ouvrez la page **Tous les clients** (**Comptabilité client \> Clients \> Tous les clients**), sélectionnez le client **US\_SI\_0003**, puis sélectionnez **Transactions**. La page **Transactions client** affiche la facture d’origine (000006), le document de contrepassation (000006-1) et la nouvelle facture (000006-2). La facture originale et le document de contrepassation sont imputés l’un à l’autre et ont un solde de 0 (zéro). Affichez le justificatif pour chaque document pour voir l’impact en Comptabilité.

[![Facture d’origine, document de contrepassation et nouvelle facture sur la page des transactions client.](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

La commande client est à nouveau facturée pour l’article qui a été ajouté. La facture totale présentée au client est de 300 $ + 19;50 $ de taxe = 319,50 $. L’illustration suivante montre l’écriture comptable validée.

[![Page Justificatif de transaction avec l’écriture comptable validée.](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Étant donné que la somme du produit et des ventes est supérieure à 319,50 $, une différence de 14,48 $ est imputée. Ce montant efface le solde du compte de compensation des revenus de la facture partielle. Ce solde a été mis à jour dans la nouvelle écriture comptable qui a été comptabilisée après la réaffectation.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]