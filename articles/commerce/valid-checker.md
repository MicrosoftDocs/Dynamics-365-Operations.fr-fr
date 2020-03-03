---
title: Vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
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
ms.openlocfilehash: 3da8bdf6feb932e074680b6cb80e1b7b71f9a82b
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004249"
---
# <a name="retail-transaction-consistency-checker"></a>Vérificateur de cohérence des transactions de vente au détail


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Cette rubrique décrit la fonctionnalité Vérificateur de cohérence des transactions dans Microsoft Dynamics 365 Commerce. Le vérificateur de cohérence identifie et isole les transactions incohérentes avant leur prélèvement par le processus de validation des relevés.

Lorsqu'un relevé est validé, la validation peut échouer en raison de données incohérentes dans les tables de transactions commerciales. Ce problème de données peut être causé par des problèmes imprévus dans l'application PDV, ou si les transactions ont été mal importées à partir de systèmes PDV tiers. Voici des exemples de cas où ces incohérences peuvent apparaître : 

- Le total des transactions dans la table des en-têtes ne correspond pas au total des transactions sur les lignes.
- Le nombre de lignes dans la table des en-têtes ne correspond pas au nombre de lignes dans la table des transactions.
- Les taxes dans la table des en-têtes ne correspondent pas au montant des taxes sur les lignes. 

Lorsque des transactions incohérentes sont prélevées par le processus de validation des relevés, des factures client et des journaux de paiement incohérents sont créés, et l'ensemble du processus de validation des relevés échoue. La récupération des relevés de cet état implique des correctifs de données complexes sur plusieurs tables de transactions. Le vérificateur de cohérence des transactions empêche ces problèmes.

Le graphique suivant illustre le processus de validation avec le vérificateur de cohérence des transactions.

![Processus de validation des relevés avec le vérificateur de cohérence des transactions](./media/validchecker.png "Processus de validation des relevés avec le vérificateur de cohérence des transactions de vente au détail")

Le processus de traitement par lots **Valider les transactions en magasin** vérifie la cohérence des tables de transactions commerciales pour les scénarios suivants.

- **Compte client** - Valide que le compte client dans les tables de transactions existe dans les données principales client HQ.
- **Nombre de lignes** - Valide que le nombre de lignes capturées dans la table des en-têtes de transaction correspond au nombre de lignes dans les tables de transactions de vente.
- **Prix incluant la taxe** : vérifie que le paramètre **Prix incluant la taxe** est cohérent dans les lignes de transaction.
- **Montant du paiement** : vérifie que les enregistrements de paiement correspondent au montant du paiement dans l'en-tête.
- **Montant brut** : vérifie que le montant brut dans l'en-tête est la somme des montants nets sur les lignes plus le montant de la taxe.
- **Montant net** – Valide que le montant net dans l'en-tête est la somme des montants nets sur les lignes.
- **Moins-perçu/Trop-perçu** – Valide que la différence entre le montant brut dans l'en-tête et le montant du paiement ne dépasse pas la configuration maximale du moins-perçu/trop-perçu.
- **Montant de remise** – Valide que le montant de remise dans les tables de remise et le montant de remise dans les tables de lignes de transaction sont cohérents, et que le montant de remise dans l'en-tête est la somme des montants de remise sur les lignes.
- **Remise ligne** – Valide que la remise ligne sur la ligne de transaction est la somme de toutes les lignes de la table de remise correspondant à la ligne de transaction.
- **Article Carte cadeau** – Commerce ne prend pas en charge le retour des articles Carte cadeau. Toutefois, le solde d'une carte cadeau peut être décaissé. Le processus de validation du relevé échoue pour tout article Carte cadeau qui est traité comme une ligne de retour au lieu d'une ligne de décaissement. Le processus de validation pour les articles Carte cadeau garantit que seules les lignes de retour de carte cadeau dans les tables de transactions sont des lignes de décaissement de carte cadeau.
- **Prix négatif** – Valide qu'il n'existe aucune ligne de transaction avec un prix négatif.
- **Article et variante** : vérifie que les articles et les variantes sur les lignes de transaction existent dans le fichier principal des articles et variantes.
- **Montant de taxe** : valide que les enregistrements de taxe correspondent bien au montant des taxes sur les lignes.
- **Numéro de série** : valide que le numéro de série est présent sur les lignes de transaction pour les articles contrôlés par numéro de série.
- **Signe** : valide que le signe sur la quantité et le montant net est identique sur toutes les lignes de transaction.
- **Date d'activité** : valide que les périodes financières pour toutes les dates d'activité des transactions sont en cours.

## <a name="set-up-the-consistency-checker"></a>Paramétrer le vérificateur de cohérence

Configurez le processus de traitement par lots « Valider les transactions en magasin » sous **Retail et Commerce \> IT vente au détail et commerce \> Validation PDV** pour les exécutions périodiques. Le traitement par lots peut être planifié en fonction de la hiérarchie d'organisation du magasin, qui est similaire au mode de paramétrage des processus « Calculer les relevés en mode de traitement par lots » et « Valider les relevés en mode de traitement par lots ». Il est recommandé de configurer ce processus de traitement par lots pour qu'il s'exécute plusieurs fois par jour et de le planifier pour qu'il s'exécute à la fin de l'exécution de chaque tâche P.

## <a name="results-of-validation-process"></a>Résultats du processus de validation

Les résultats du contrôle de validation par le processus de traitement par lots sont référencés dans la transaction appropriée. Le champ **Statut de validation** dans l'enregistrement de la transaction est défini sur **Réussite** ou **Erreur**, et la date de la dernière exécution de la validation s'affiche dans le champ **Heure de la dernière validation**.

Pour afficher un texte plus descriptif de l'erreur associée à un échec de validation, sélectionnez l'enregistrement de transaction approprié et cliquez sur le bouton **Erreurs de validation**.

Les transactions qui échouent au contrôle de validation et les transactions qui n'ont pas encore été validées ne seront pas extraites dans des relevés. Au cours du processus « Calcul du relevé », les utilisateurs seront informés si des transactions auraient dû être incluses dans le relevé.

Si une erreur de validation est détectée, le seul moyen de corriger l'erreur est de contacter le support technique de Microsoft. Dans une prochaine version, la fonctionnalité sera ajoutée afin que les utilisateurs puissent corriger les enregistrements en échec via l'interface utilisateur. Les fonctionnalités de journalisation et d'audit seront également disponibles pour suivre l'historique des modifications.

> [!NOTE]
> Des règles de validation supplémentaires pour prendre en charge d'autres scénarios seront ajoutées dans une prochaine version.