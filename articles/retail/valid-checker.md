---
title: Vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions de vente au détail dans Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2019
ms.locfileid: "379991"
---
# <a name="retail-transaction-consistency-checker"></a>Vérificateur de cohérence des transactions de vente au détail


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions de vente au détail introduite dans Microsoft Dynamics 365 for Finance and Operations version 8.1.3. Le vérificateur de cohérence identifie et isole les transactions incohérentes avant leur prélèvement par le processus de validation des relevés.

Lorsqu'un relevé est validé dans Retail, la validation peut échouer en raison de données incohérentes dans les tables de transactions de vente au détail. Ce problème de données peut être causé par des problèmes imprévus dans l'application POS, ou si les transactions ont été mal importées à partir de systèmes POS tiers. Voici des exemples de cas où ces incohérences peuvent apparaître : 

  - Le total des transactions dans la table des en-têtes ne correspond pas au total des transactions sur les lignes.
  - Le nombre de lignes dans la table des en-têtes ne correspond pas au nombre de lignes dans la table des transactions.
  - Les taxes dans la table des en-têtes ne correspondent pas au montant des taxes sur les lignes. 
  
Lorsque des transactions incohérentes sont prélevées par le processus de validation des relevés, des factures client et des journaux de paiement incohérents sont créés, et l'ensemble du processus de validation des relevés échoue. La récupération des relevés de cet état implique des correctifs de données complexes sur plusieurs tables de transactions. Le vérificateur de cohérence des transactions de vente au détail empêche ces problèmes.

Le graphique suivant illustre le processus de validation avec le vérificateur de cohérence des transactions.

![Processus de validation des relevés avec le vérificateur de cohérence des transactions](./media/validchecker.png "Processus de validation des relevés avec le vérificateur de cohérence des transactions")

Le processus de traitement par lots **Valider les transactions en magasin** vérifie la cohérence des tables de transactions de vente au détail pour les scénarios suivants.

- Compte client - Valide que le compte client dans les tables de transactions de vente au détail existe dans les données principales client HQ.
- Nombre de lignes - Valide que le nombre de lignes capturées dans la table des en-têtes de transaction correspond au nombre de lignes dans les tables de transactions de vente.

## <a name="set-up-the-consistency-checker"></a>Paramétrer le vérificateur de cohérence
Configurez le processus de traitement par lots « Valider les transactions en magasin » sous **Vente au détail \> Informatique au détail \> Validation POS** pour les exécutions périodiques. Le traitement par lots peut être planifié en fonction de la hiérarchie d'organisation du magasin, qui est similaire au mode de paramétrage des processus « Calculer les relevés en mode de traitement par lots » et « Valider les relevés en mode de traitement par lots ». Il est recommandé de configurer ce processus de traitement par lots pour qu'il s'exécute plusieurs fois par jour et de le planifier pour qu'il s'exécute à la fin de l'exécution de chaque tâche P.

## <a name="results-of-validation-process"></a>Résultats du processus de validation
Les résultats du contrôle de validation par le processus de traitement par lots sont référencés dans la transaction de vente au détail appropriée. Le champ **Statut de validation** dans l'enregistrement de la transaction de vente au détail est défini sur **Réussite** ou **Erreur**, et la date de la dernière exécution de la validation s'affiche dans le champ **Heure de la dernière validation**.

Pour afficher un texte plus descriptif de l'erreur associée à un échec de validation, sélectionnez l'enregistrement de transaction de vente au détail approprié et cliquez sur le bouton **Erreurs de validation**.

Les transactions qui échouent au contrôle de validation et les transactions qui n'ont pas encore été validées ne seront pas extraites dans des relevés. Au cours du processus « Calcul du relevé », les utilisateurs seront informés si des transactions auraient dû être incluses dans le relevé.

Si une erreur de validation est détectée, le seul moyen de corriger l'erreur est de contacter le support technique de Microsoft. Dans une prochaine version, la fonctionnalité sera ajoutée afin que les utilisateurs puissent corriger les enregistrements en échec via l'interface utilisateur. Les fonctionnalités de journalisation et d'audit seront également disponibles pour suivre l'historique des modifications.

> [!NOTE]
> Des règles de validation supplémentaires pour prendre en charge d'autres scénarios seront ajoutées dans une prochaine version.
