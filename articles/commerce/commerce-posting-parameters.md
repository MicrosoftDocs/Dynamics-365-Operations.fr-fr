---
title: Paramètres de validation de Commerce
description: Cette rubrique décrit les paramètres spécifiques à la comptabilisation des transactions financières et physiques dans Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 1b49c893567d39f05e16cefee47407a424b7e139
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649201"
---
# <a name="commerce-posting-parameters"></a>Paramètres de validation de Commerce

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit les paramètres spécifiques à la comptabilisation des transactions financières et physiques dans Microsoft Dynamics 365 Commerce. Les paramètres de validation de Commerce sont situés dans Commerce headquarters à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Commerce \> Validation**.

## <a name="periodic-discount-parameters"></a>Paramètres de remise périodique

Le tableau suivant présente les paramètres de remise périodiques spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Valider la remise périodique | Cette option contrôle si les offres périodiques sont validées sur les comptes généraux. Les remises exceptionnelles comprennent les remises mix and match, les remises sur quantité et les offres de remise. Quand ce paramètre est activé, des champs supplémentaires peuvent être définis dans la section **Remises périodiques**. |
| Type de compte général | <p>Sélectionnez le type de compte utilisé pour valider les remises exceptionnelles :</p><ul><li>**Standard** – Le système n’utilise pas les champs liés aux remises sur cette page. Au lieu de cela, il utilise les comptes qui sont définis sur la page **Validation** de Commerce headquarters (**Gestion des stocks \> Configuration \> Validation \> Formulaires de Validation**).</li><li>**Périodique** – Le système utilise les comptes de remise Commerce qui sont spécifiés par les champs liés à la remise sur cette page. Si vous sélectionnez cette option, vous devez spécifier le compte général pour chaque type d’offre (remise, remise mix and match, quantité et seuil). Quand vous configurez chaque remise, vous pouvez définir un compte. Quand la fonctionnalité de Validation du compte de remise est utilisée sur la page de configuration des remises, une entrée de débit et une entrée de crédit supplémentaires sont effectuées pour reclasser la comptabilisation de la remise du compte général de remise Commerce vers le compte général de remise. Pour plus d’informations, voir [Remises Retails](retail-discounts-overview.md).</li></ul> |
| Valider le code remise | Cette option n’est plus utilisée dans la solution Commerce standard et sera obsolète. |
| Valider la remise périodique pour les commandes | Cette option contrôle si les remises périodiques de vente au détail sont validées dans la comptabilité pour les commandes client et les commandes du centre d’appels. |

## <a name="inventory-update-parameters"></a>Paramètres de mise à jour du stock

Le tableau suivant présente les paramètres de mise à jour du stock spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Utiliser l’ID de traitement par lots par défaut quand les numéros de traitement par lots sont introuvables | Cette option contrôle si un ID de traitement par lots par défaut est pour les articles de traitement par lots si les numéros de traitement par lots sont introuvables et un stock négatif est autorisé. |
| ID de traitement par lots par défaut | Numéro de traitement par lots à utiliser si les numéros de traitement par lots des articles sont introuvables et que le paramètre **Utiliser l’ID de traitement par lots par défaut quand les numéros de traitement par lots sont introuvables** est activé. |

## <a name="aggregation-parameters"></a>Paramètres d’agrégation

Le tableau suivant présente les paramètres d’agrégation spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Mise en coffre-fort | Activez ce paramètre pour regrouper toutes les transactions au moment de la publication du relevé et créer une seule ligne dans le journal pour la publication au lieu d’une ligne distincte pour chaque dépôt. |
| Remise en banque | Activez ce paramètre pour regrouper toutes les transactions au moment de la publication du relevé et créer une seule ligne dans le journal pour la publication au lieu d’une ligne distincte pour chaque dépôt. |
| Transactions de vente | Activez ce paramètre pour consolider les transactions dans le cadre du processus de validation du relevé de transaction. Nous vous recommandons d’activer ce paramètre. Il s’appelait auparavant **Pièces comptables**. |
| Ne pas regrouper les retours | Si cette option est sélectionnée, chaque transaction de retour sera validée comme une commande client distincte au moment de la validation d’un relevé de vente au détail. |

## <a name="batch-processing-parameters"></a>Paramètres du traitement par lots

Le tableau suivant présente les paramètres de traitement par lots spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Nombre maximal de relevés en parallèle | Ce champ définit le nombre de tâches de traitement par lots utilisées pour valider plusieurs relevés. |
| Nombre maximal de threads pour le traitement des commandes par relevé | Ce champ représente le nombre maximal de threads utilisés par le traitement par lots de validation de relevé pour créer et facturer les commandes client d’un seul relevé. Le nombre total de threads utilisés par le processus de validation du relevé est calculé en multipliant la valeur de ce paramètre par la valeur du paramètre **Nombre maximal de validation de relevés en parallèle**. Si la valeur de ce paramètre est trop élevée, cela peut avoir un impact négatif sur les performances du processus de validation du relevé. |
| Nombre maximal de lignes de transaction incluses dans l’agrégation | Ce champ définit le nombre de lignes de transaction qui sont incluses dans une seule transaction regroupée avant qu’une transactionsoit créée. Les transactions regroupées sont créées selon différents critères d’agrégation, tels que le client, la date d’activité ou les dimensions financières. Notez que les lignes d’une transaction unique ne seront pas fractionnées entre différentes transactions regroupées. Par conséquent, le nombre de lignes dans une transaction regroupée peut être légèrement supérieur ou inférieur en fonction de facteurs comme le nombre de produits distincts. |
| Nombre maximal de threads pour valider les transactions en magasin | Ce champ définit le nombre maximal de threads utilisés pour valider les transactions. La validation des transactions est une étape obligatoire à effectuer avant que les transactions puissent être extraites dans les relevés. Vous devez également définir un produit de carte cadeau sur le raccourci **Carte cadeau** sous l’onglet **Validation** de la page **Paramètres Commerce**, même si l’organisation n’utilise pas de cartes cadeaux. |

Le tableau suivant répertorie les valeurs recommandées pour les paramètres du tableau précédent. Ces valeurs doivent être testées et adaptées à la configuration de déploiement et à l’infrastructure disponible. Les valeurs supériures aux valeurs recommandées peut affecter négativement d’autres traitements par lots et doit être validée.

| Paramètre | Valeur recommandée | Détails |
|-----------|-------------------|---------|
| Nombre maximal de validation de relevés en parallèle | <p>Définissez ce paramètre sur le nombre de tâches par lots disponibles pour le groupe de lots qui exécute la tâche **Déclaration**.</p><p>**Règle générale :** multipliez le nombre de serveurs virtuels Application Object Server (AOS) par le nombre de tâches par lots disponibles par serveur virtuel AOS.</p> | Ce paramètre n’est pas applicable quand la fonctionnalité **Relevés de vente au détail – Flux continu** est activée. |
| Nombre maximal de threads pour le traitement des commandes par relevé | Commencez à tester les valeurs à **4**. En règle générale, la valeur ne doit pas dépasser **8**. | Ce paramètre définit le nombre de threads utilisés pour créer et publier des commandes client. Il représente le nombre de threads disponibles pour publication par instruction. |
| Nombre maximal de lignes de transaction incluses dans l’agrégation | Commencez à tester les valeurs à **1000**. Selon la configuration de Commerce headquarters, des commandes plus petites peuvent être plus avantageuses pour les performances. | Ce paramètre définit le nombre de lignes incluses dans chaque commande client au moment de la validation du relevé. Une fois ce nombre atteint, les lignes seront divisées en une nouvelle commande. Le nombre de lignes de vente ne sera pas exactement égale au nombre spécifié, étant donné que le fractionnement se produit au niveau de la commande client. Néanmoins, le nombre sera proche du nombre défini. Ce paramètre est utilisé pour générer des bons de commande pour les transactions de vente au détail qui n’ont pas de client nommé. |
| Nombre maximal de threads pour valider les transactions en magasin | Nous vous recommandons de définir ce paramètre sur **4**, et de ne pas l’augmenter sauf si vous atteignez des performances acceptables. Le nombre de threads utilisés par ce processus ne peut pas dépasser le nombre de processeurs disponibles pour le serveur de traitement par lots. Si le nombre de threads est trop élevé, d’autres traitements par lots peuvent être affectés. | Ce paramètre contrôle le nombre de transactions pouvant être validées en même temps pour un magasin donné. |

> [!NOTE]
> Tous les paramètres associés aux validations de relevé et définis dans les magasins et sur la page **Paramètres Commerce** s’appliquent à la fonction améliorée de validation des relevés.

## <a name="invoice-parameters"></a>Paramètres de facture

Le tableau suivant présente les paramètres de facture spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Nom de journal | Nom du journal des paiements utilisé à la création des journaux des paiements client pour les paiements des commandes client. Ce paramètre s’applique à tous les paiements de commande publiés pour les commandes de point de vente (PDV), de centre d’appels et de canaux d’e-commerce. |
| Intitulé du compte | Nom du compte de paiement. |
| Hiérarchiser les dimensions à partir du mode de paiement | Quand cet indicateur est activé, les dimensions des journaux hiérarchisent les paiements à partir du mode de paiement au lieu des dimensions du magasin. |
| Comportement de calcul de la taxe | Ce paramètre spécifie le comportement quand les commandes client créées à la validation du relevé sont facturées :<ul><li>**Recalculer** – Calculez à nouveau les taxes.</li><li> **Ne pas recalculer** – Utilisez les montants de taxes calculés dans le PDV.</li></ul> |
| Nom de journal | Nom du journal utilisé à la création d’un journal des paiements client pour les remboursements. Ce paramètre s’applique à tous les paiements de commande publiés pour les commandes du PDV, de centre d’appels et de canaux d’e-commerce. |

## <a name="statement-parameters"></a>Paramètres du relevé

Le tableau suivant présente les paramètres de relevé spécifiques à la comptabilisation des transactions financières et physiques.

| Paramètre | Description |
|-----------|-------------|
| Réserver le stock au moment du calcul | Quand ce paramètre est activé, le calcul du relevé réserve temporairement le stock jusqu’à ce que le relevé soit validé. Ce paramètre est désactivé par défaut pour aider à améliorer les performances du calcul du relevé+. Les informations de stock mises à jour peuvent être calculées à l’aide de la tâche de traitement par lots **Valider le stock**. Notez que la tâche de traiement par lots de stock **Valider** n’est plus utilisée quand la création de commande basée sur [un flux en continu](trickle-feed.md) pour les transactions de magasin de détail est activée. |
| Désactivation du comptage obligatoire | Cet indicateur désactive le comptage au moment de la validation dans Commerce headquarters. |
| Recalculer les dimensions financières en cas d’erreur | Quand ce paramètre est activé, les dimensions financières peuvent être réévaluées à la validation du relevé suivant, en cas d’échec de la validation du relevé. |
| Utiliser les dimensions financières du magasin de retour | Quand ce paramètre est activé, il est possible de créer des commande clients de retour liés qui utilisent les dimensions financières du magasin au lieu des dimensions financières de la transaction d’origine. |
| Supprimer les retours | Quand ce paramètre est activé, le relevé peut créer des retours de ventes non comptabilisées en tant que retours en aveugle. Ce paramètre est désactivé par défaut et nous vous recommandons de le garder désactivé. |
| Désactivez la validation de la différence d’arrondi | Ce paramètre désactive la validation de la différence d’arrondi entre un paiement de transaction et le montant brut au moment du traitement des paiements. |
| Régler automatiquement les dépôts client | Quand ce paramètre est activé, les dépôts client validés au moment du traitement des relevés de vente au détail doivent être réglés pour les transactions client en cours. |
| Activez et utilisez le rapprochement de gestion de la trésorerie à partir des PDV | Quand ce paramètre est activé, le rapprochement de la gestion de la trésorerie est effectué dans le PDV et les valeurs sont transmises à la validation des tableaux d’analyse de vente au détail pour créer des lignes de relevé. |
| Niveau de détail du N° document comptable | Ce paramètre définit le niveau de détail inclus dans le N° document comptable pour les transactions sélectionnées provenant du PDV. Les types de transactions incluent les revenus, les dépenses et les remises. Pour les remises, ce paramètre est pris en compte uniquement quand le numéro de compte pour une remise périodique et le numéro de compte pour une remise régulière ne sont pas identiques. Sauf si des détails sont nécessaires, **Résumé** est la valeur recommandée pour ces publications. Quand la publication au niveau récapitulatif est définie, **TransactionDiscountTrans.RecID** ne sera pas rempli. Dans la version Commerce 10.0.27, cet indicateur a été renommé et déplacé. Il s’appelait auparavant **Niveau de détail** et était dans la section **Mise à jour du stock**. |
