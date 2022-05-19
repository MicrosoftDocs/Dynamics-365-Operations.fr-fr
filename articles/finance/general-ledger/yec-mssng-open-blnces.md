---
title: Soldes d’ouverture manquants à la clôture de fin d’exercice
description: Cette rubrique explique pourquoi les soldes d’ouverture peuvent être manquants lorsque vous clôturez un exercice et comment les reconstituer, le cas échéant.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 582363ba6c5f6e63e695d41e73ee2f0b382cf26e
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727170"
---
# <a name="year-end-close-missing-opening-balances"></a>Soldes d’ouverture manquants à la clôture de fin d’exercice

[!include [banner](../includes/banner.md)]

Cette rubrique explique pourquoi les soldes d’ouverture peuvent être manquants lorsque vous clôturez un exercice et comment les reconstituer, le cas échéant.

### <a name="symptom"></a>Problème

Pourquoi n’y a-t-il pas de solde d’ouverture après l’exécution de la clôture de fin d’exercice de comptabilité ? 

### <a name="resolution"></a>Résolution

Voici des éléments à vérifier si vous avez clôturé un exercice en comptabilité, puis généré une balance comptable qui n’affiche pas les soldes d’ouverture pour l’exercice suivant.

Si le champ **Annuler la clôture précédente** est défini sur **Oui**, la clôture de fin d’exercice pour le même exercice est annulée. Lors de la contrepassation de la clôture de fin d’exercice, toutes les écritures de solde de clôture et de solde d’ouverture sont supprimées, comme si l’exercice n’avait jamais été clôturé. Les justificatifs sont également supprimés. Le processus de clôture de fin d’exercice ne s’exécutera pas à nouveau automatiquement. Vous devez recommencer le processus, cette fois en définissant l’option **Annuler la clôture précédente** sur **Non**.

Ce scénario est traité dans la rubrique FAQ sur la clôture de fin d’exercice. Pour plus d’informations, voir [FAQ sur les activités de fin d’exercice](faq-year-end-activities.md).

### <a name="symptom"></a>Problème

J’ai exécuté la clôture de fin d’exercice avec l’option **Annuler la clôture précédente** définie sur **Non**, et je n’ai toujours pas de soldes d’ouverture pour mon exercice.

### <a name="resolution"></a>Résolution

Commencez par vérifier le statut du traitement par lots. La clôture d’un exercice comprend un certain nombre de tâches distinctes, mais l’étape la plus critique est la tâche de traitement par lots avec la description de la tâche **Étape 5.0.0**. L’enregistrement des transactions d’ouverture, et éventuellement des transactions de clôture en Comptabilité a lieu au cours de cette étape. 

[![Liste de l’historique des lots.](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Si cette étape s’est terminée avec succès, mais que vous ne voyez pas les soldes d’ouverture sur la page **Demande de balance comptable** (**Comptabilité > Recherches et rapports > Balance comptable**), examinez les résultats du traitement par lots de la clôture de fin d’exercice pour voir si l’étape Reconstruire les soldes s’est terminée avec succès.

[![Résultats du traitement par lots de la clôture de fin d’exercice.](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Si cette étape a échoué pour une raison quelconque, les transactions d’ouverture (et éventuellement de clôture) ont probablement été validées avec succès. Vous pouvez vérifier que les transactions comptables ont été validées avec succès à l’aide de la page **Demande de justificatif de transaction** en spécifiant le numéro et la date du justificatif figurant dans la boîte de dialogue de clôture de fin d’exercice pour l’exercice que vous clôturez, (**Comptabilité > Recherches et états > Justificatif de transaction**).

[![Demande de justificatif de transaction.](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Si les justificatifs d’ouverture (et éventuellement de clôture) sont présents, vous n’avez pas besoin d’exécuter à nouveau la clôture de fin d’exercice. Reportez-vous plutôt à la section suivante pour savoir comment poursuivre.

### <a name="symptom"></a>Problème

L’étape « Reconstruire les soldes » de la clôture de fin d’exercice a échoué. Dois-je relancer tout le processus de clôture de fin d’exercice ?

### <a name="resolution"></a>Résolution

L’étape Reconstruire les soldes met à jour les soldes de la comptabilité qui sont utilisés lors de la génération de la demande de balance comptable.  Il s’agit de la dernière étape du processus de clôture de fin d’exercice.  Si cette étape est la seule qui a échoué, les transactions comptables ont été validées avec succès.  Vous n’avez pas à exécuter à nouveau la clôture de fin d’exercice. Vous pouvez exécuter le processus pour reconstruire les soldes manuellement à l’aide de la page **Ensembles de dimensions financières** (**Comptabilité> Plan comptable > Dimensions > Ensembles de dimensions financières**).

[![Bouton Reconstruire les soldes sur la page Ensembles de dimensions financières.](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Si le traitement de cette étape prend du temps, nous vous recommandons de passer en revue les meilleures pratiques pour les ensembles de dimensions financières, comme décrit dans [Bonnes pratiques pour la mise à jour des ensembles de dimensions financières](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 

