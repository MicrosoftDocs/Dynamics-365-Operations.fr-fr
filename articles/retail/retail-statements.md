---
title: "Relevés de la vente au détail"
description: "Cette rubrique décrit la procédure de création et de validation des relevés."
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeb851587cc40828088dfa22fda1d70f49561c3a
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="retail-statements"></a>Relevés de la vente au détail
Dans Microsoft Dynamics 365 for Retail, le processus de validation des relevés est utilisé pour comptabiliser les transactions qui ont lieu dans le point de vente (PDV) du cloud ou le Modern POS (MPOS). Le processus de validation des relevés utilise le programme de distribution pour extraire un ensemble de transactions de PDV au siège du client. Les paramètres définis sur les pages **Paramètres des ventes au détail** et **Magasins** permettent de sélectionner les transactions qui sont extraites dans des relevés individuels.  

L'illustration suivante présente le processus de validation du relevé. Dans ce processus, les transactions enregistrées dans le PDV sont transmises au client à l'aide de Retail Planification. Une fois que le client a reçu les transactions, vous pouvez créer, calculer et valider les relevés de transaction du magasin. 

[![Processus de validation des relevés](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Création et validation des relevés
Vous pouvez créer un relevé manuellement ou à l'aide de processus de traitement par lots que vous définissez afin qu'ils s'exécutent régulièrement tout au long de la journée. Dans les deux cas, les étapes suivantes permettent de créer et de valider des relevés.

###  <a name="create-the-statement"></a>Création du relevé
Cette étape identifie le magasin pour lequel le relevé est créé manuellement. Si vous configurez un processus de traitement par lots, vous pouvez créer automatiquement des relevés pour tous les magasins, en fonction d'un programme que vous définissez. 

### <a name="calculate-the-statement"></a>Calcul du relevé
Dans cette étape, les lignes de transaction sont sélectionnées en fonction des critères définis pour chaque magasin sur les pages **Paramètres des ventes au détail** et **Magasins**. Sur ces pages, vous définissez les critères et indiquez comment les transactions sont calculées. Pour afficher la liste des transactions incluses dans le relevé avant de calculer le relevé, utilisez la page **Transactions**. 

Le calcul du relevé utilise des comptages de caisse des caisses enregistreuses comme montant compté. Vous pouvez également entrer manuellement le montant compté. Le relevé indique la différence entre la valeur de vente des transactions et le montant calculé réel pour tous les modes de paiement. Le relevé est validé uniquement si cette différence est inférieure à la différence de validation maximale définie pour le magasin. 

> [!NOTE]
> Le processus de calcul des relevés utilise la souche de numéros globale.

Lorsque vous calculez un relevé, le calcul inclut les tâches suivantes :

- Pour la plage de dates sélectionnée, marquez les transactions qui n'étaient pas incluses dans un calcul du relevé précédent. 
- Calculez les montants totaux qui ont été proposés dans les transactions sélectionnées. Les résultats sont présentés sur les lignes de relevé, en fonction de la méthode de relevé :

  - Si la méthode de relevé est **Total**, une ligne est créée pour chaque mode de paiement dans les transactions sélectionnées. 
  - Si la méthode de relevé est **Personnel**, une ligne est créée pour chaque mode de paiement dans les transactions réalisées par les membres du personnel sélectionnés. 
  - Si la méthode de relevé est **Terminal de PDV**, une ligne est créée pour chaque mode de paiement dans les transactions effectuées sur la caisse enregistreuse sélectionnée. 
  - Si la méthode de relevé est **Équipe de travail**, une ligne est créée pour chaque mode de paiement dans les transactions effectuées sur la caisse enregistreuse sélectionnée pendant un changement d'équipe.

Si la case à cocher **Fractionné par mode de relevé** est activée sur la page **Magasins**, un relevé distinct est créé selon la valeur sélectionnée dans le champ **Méthode de relevé**.

Si les heures de fonctionnement de votre magasin s'étendent après minuit, vous pouvez configurer la validation du relevé en fonction de la fin du jour ouvrable au lieu de la fin du jour civil. 

Dans la page **Magasins**, dans l'organisateur **Relevé/clôture**, dans le champ **Fin du jour ouvrable**, entrez l'heure à laquelle la dernière transaction doit être enregistrée pour être incluse dans le relevé du jour ouvrable. Activez la case à cocher **Valider comme jour ouvrable** pour valider les transactions le même jour ouvrable. Lorsque le relevé est validé, les transactions qui sont enregistrées au cours du même jour ouvrable peuvent être incluses sur la même commande client, même si certaines transactions ont lieu avant minuit et d'autres, après minuit. 

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Exemple : Validation d'un relevé pour un jour ouvrable qui s'étend sur deux jours civils 

Un magasin est ouvert entre 8 h 00 du matin et 3 h 00 du matin, et la case à cocher **Valider comme jour ouvrable** est activée dans la configuration du magasin. Le 31 mai, le magasin enregistre des transactions entre 8 h 00 du matin et minuit. Le magasin enregistre également des transactions entre 0 h 01 du matin et 3 h 00 du matin le 1er juin. 

Lorsque le magasin valide son relevé à la fermeture du jour ouvrable, la commande client générée inclut toutes les transactions enregistrées entre 8 h 00 et 3 h 00 du matin, même si les transactions se sont produites sur deux jours, le 31 mai et le 1er juin. 

Si la case à cocher **Valider comme jour ouvrable** est désactivée pour le même magasin, des commandes client distinctes sont générées lorsque le magasin valide son relevé à la fin du jour ouvrable. Une commande client inclut les transactions qui ont été enregistrées entre 8 h 00 du matin et minuit le 31 mai, et la deuxième commande client inclut les transactions enregistrées entre les heures ouvrables de 0 h 01 et 3 h 00 du matin le 1er juin.
 
> [!NOTE]
> Avant de créer des relevés, vous devez clôturer les équipes de travail de la période du relevé. 

### <a name="post-the-statement"></a>Validation du relevé
Lorsque vous validez un relevé, les commandes client et les factures sont créées pour les ventes au détail du relevé.

- Les ventes cash and carry sont regroupées sur une commande client et facturées pour le client par défaut affecté au magasin. 
- Les ventes au détail pour lesquelles un client a été ajouté à la transaction dans le PDV de Microsoft Dynamics 365 for Retail génèrent des commandes client et factures distinctes, une pour chaque client unique. 

Les journaux de paiements sont automatiquement créés pour les paiements dans le relevé, et le stock est mis à jour pour le magasin du PDV.

