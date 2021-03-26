---
title: Réaffectation de la prise en compte de revenu - Scénario 4
description: Cette rubrique décrit un scénario de réaffectation dans lequel une ligne est supprimée d’une commande client existante, partiellement facturée. Ce scénario produit le même résultat, que la ligne soit supprimée de la commande client ou définie sur un statut annulé.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 50a2d0d2ca28d9b62713502700f2c4bd2e42751e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238302"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Réaffectation de la prise en compte de revenu - Scénario 4

[!include [banner](../includes/banner.md)]

Cette rubrique décrit un scénario de réaffectation dans lequel une ligne est supprimée d’une commande client existante, partiellement facturée. Ce scénario produit le même résultat, que la ligne soit supprimée de la commande client ou définie sur un statut annulé.

Pour ce scénario, l’option **Valider les corrections des factures dans la Comptabilité client** est définie sur **Non** sur l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de Comptabilité**).

[![Option Valider les corrections des factures dans la Comptabilité client définie sur Non](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Une commande client est créée pour le client US\_SI\_0003. Le client achète un ordinateur portable (numéro d’article S0012), des services d’installation (numéro d’article S0001) et un plan de support (numéro d’article S0008 « Service d’ingénierie continu »). Le produit de l’ordinateur portable et des services d’installation est immédiatement reconnu. Le produit du plan de support est différé et reconnu sur 12 mois, comme défini par la plage de dates dans le contrat.

[![Lignes de commande client pour l’ordinateur portable, les services d’installation et le plan de support](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

La commande client est confirmée. Étant donné que les trois articles sont configurés pour la répartition du prix du produit, celui-ci est calculé lorsque la commande client est confirmée. Vous pouvez afficher les produits qui seront reconnus sur la page **Répartition de prix du produit** (sur la page **Commande client**, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Prise en compte de revenu**, sélectionnez **Répartition de prix du produit**). Le produit de l’ordinateur portable sera imputé au compte Produit pour un montant de 995,84 $. Le produit des services d’installation sera aussi imputé au compte Produit pour un montant de 314,47 $. Le produit du plan de support sera imputé au compte Produit différé pour un montant de 188,69 $. La somme des prix doit être égale à la somme des lignes qui ont été configurées pour capturer la répartition de prix du produit (1 499 $).

[![Page Répartition de prix du produit](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

Le client est facturé pour l’ordinateur portable et le plan de support, mais pas pour les services d’installation. L’illustration suivante montre l’écriture comptable validée pour la facture.

[![Écriture comptable de la commande client facturée](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

L’écriture comptable enregistre 1 276,94 $ dans Comptes clients. Cependant, comme cette facture est une facture partielle, les revenus ou revenus différés plus la taxe ne correspondent pas au montant en Comptabilité client. La différence de -14,47 $ est enregistrée dans un compte de compensation des revenus de facturation partielle.

L’échéancier de prise en compte de revenu est également créé.

[![Page Échéancier de prise en compte de revenu pour la facture partielle](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

Plus tard, le client décide de ne pas acheter de services d’installation. Par conséquent, cette ligne est supprimée de la commande client. Notez que la commande client ne peut pas être confirmée à nouveau, car seules les lignes facturées sont conservées.

[![Commande client après la suppression de la ligne pour les services d’installation](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Même si la commande client ne peut pas être confirmée, elle peut être réaffectée. Dans la commande client, sélectionnez **Redistribuer le prix avec les nouvelles lignes de commande** pour ouvrir la page **Redistribuer le prix avec les nouvelles lignes de commande**. Sélectionnez les deux lignes de commande client restantes, puis sélectionnez **Mettre à jour la réaffectation**. La colonne **Montant réaffecté** affiche le nouveau prix des revenus pour chaque ligne de commande client restante.

[![Nouveaux prix de produit sur la page Redistribuer le prix avec les nouvelles lignes de commande](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Ensuite, sélectionnez **Justificatif attendu** pour afficher les écritures comptables.

[![Écritures comptables sur la page Justificatif attendu](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

Sur la page **Justificatif attendu**, les cinq dernières lignes contrepassent l’écriture comptable d’origine de la facture validée. Les quatre premières lignes sont les nouvelles écritures comptables qui sont validées pour la facture. Il est important de comprendre qu’une nouvelle facture n’est pas présentée au client. Après la réaffectation, le client doit toujours 1 276,94 $, qui est le montant qui doit être imputé aux comptes clients dans la nouvelle écriture comptable. Le total du nouveau produit ou produit différé et de la taxe est égal à 1 276,94 $. Par conséquent, vous n’êtes pas obligé d’imputer le compte Compensation de produit de facture partielle.

Pour terminer la réaffectation, sélectionnez **Processus**. Une date de validation est saisie. Une fois la réaffectation terminée, la page **Répartition de prix du produit** montre la réallocation des prix pour les deux articles restants.

[![Réallocation de prix pour les articles restants sur la page Répartition de prix du produit](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

L’échéancier de prise en compte de revenu a également été mis à jour, en fonction du nouveau prix de réaffectation du produit. À partir de la commande client, ouvrez la page **Échéancier de prise en compte de revenu**. Auparavant, il y avait 13 lignes pour l’article S0008 (un échéancier de 12 mois était attribué à cet article). Il y a maintenant 39 lignes : les 13 échéances d’origine, 13 échéances de contrepassation et 13 lignes basées sur le nouveau prix du produit.

[![Page Échéancier de prise en compte de revenu mis à jour avec 39 lignes pour l’article S0008](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Lorsque vous sélectionnez **Justificatif**, le journal des factures affiche l’écriture comptable d’origine. Pour afficher l’écriture de contrepassation et la nouvelle écriture comptable à partir de la commande client, sélectionnez **Ajustements de produit** dans le volet Actions, puis sélectionnez **Justificatif**.

Ensuite, ouvrez la page **Tous les clients** (**Comptabilité client \> Clients \> Tous les clients**), sélectionnez le client **US\_SI\_0003**, puis sélectionnez **Transactions**. La page **Transactions clients** affiche uniquement la facture d’origine (000008), ainsi que l’écriture comptable d’origine. Comme l’option **Valider les corrections des factures dans la comptabilité client** est définie sur **Non** sur la page **Paramètres de Comptabilité**, seule la Comptabilité est mise à jour. Par conséquent, la contrepassation et la mise à jour des écritures comptables ne sont pas affichées. Notez que les transactions de prise en compte de revenu créées dans le [scénario 3](rev-rec-reallocation-scenario-3.md) sont indiquées.

[![Écriture comptable d’origine sur la page Transactions client](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]