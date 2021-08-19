---
title: Paramètres de gestion des remises
description: Cette rubrique décrit la page des paramètres de gestion des remises. Cette page contient des paramètres qui affectent la validation, les mises à jour de statut, les souches de numéros et d’autres comportements.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 9afff67d043d00ade83a522cf801f2b0af7929f512c83040a37f3de0cf0e2579
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780002"
---
# <a name="rebate-management-parameters"></a>Paramètres de gestion des remises

[!include [banner](../includes/banner.md)]

La page **Paramètres de gestion des remises** est utilisée pour définir les paramètres qui s’appliquent au module **Gestion des remises**. Ces paramètres affectent la validation, les mises à jour de statut, les souches de numéros et d’autres comportements. La configuration de cette page est partagée entre les entités juridiques et peut être modifiée par les utilisateurs disposant des autorisations de sécurité appropriées.

Pour ouvrir la page **Paramètres de gestion des remises**, accédez à **Gestion des remises \> Paramétrage \> Paramètres de gestion des remises**. Ensuite, définissez les champs comme décrit dans les sous-sections suivantes.

## <a name="rebate-management-tab"></a>Onglet Gestion des remises

Le tableau suivant décrit les champs disponibles sur l’onglet **Gestion des remises** de la page **Paramètres de gestion des remises**.

| Champ | Description |
|---|---|
| Statut par défaut | Sélectionnez le statut par défaut de tous les nouveaux accords. Pour définir l’ensemble des valeurs de statut disponibles pour la sélection, utilisez la page [**Statuts de remise**](rebate-statuses.md). |
| Traitement par dimension | Indiquez si les transactions de provision, de remise et d’annulation doivent être traitées par dimension financière. Lorsque cette option est activée, le système utilise les dimensions financières provenant des transactions source dans les transactions cibles. |
| Vérification de validation antérieure | <p>Sélectionnez le comportement du système si des transactions de remise non validées sont traitées plusieurs fois pendant la même période :</p><ul><li>**Avertissement** : le système permet aux utilisateurs de remplacer les lignes de transaction d’origine, mais un avertissement s’affiche.</li><li>**Erreur** : le système empêche les utilisateurs de remplacer les lignes de transaction d’origine et un message d’erreur s’affiche. |
| Valider automatiquement les journaux | Sélectionnez si le système doit valider automatiquement les journaux proposés. Ces journaux comprennent les journaux quotidiens qui sont utilisés pour les provisions et les déductions client, ainsi que les journaux des factures fiscales des fournisseurs. |
| Validation automatique des factures financières | Sélectionnez si le système doit valider automatiquement les factures financières. Cette option s’applique uniquement aux factures financières pour lesquelles le type de paiement est défini sur *Déductions client sur facture fiscale*. |
| Référence de commande d’article de remise | Sélectionnez la référence de remise à utiliser sur les commandes client et fournisseur générées à partir du processus de remise (*Aucun*, *Accord de gestion des remises*, *Numéro de gestion des remises*, *Numéro de transaction de remise*, ou *Notes de document*). |
| Utilisation du processus de revendication | <p>Définissez cette option sur *Oui* pour utiliser le processus de revendication. De cette manière, vous pouvez marquer les transactions créées par la gestion des remises comme revendiquées ou non, puis valider uniquement les transactions revendiquées.</p><p>Par exemple, vous calculez les remises pour un mois de transactions, mais le client a laissé deux jours non revendiqués. Dans ce cas, les transactions non réclamées seront recréées la prochaine fois que vous exécuterez la fonction *Traiter* pour la période suivante.</p><p>Si vous définissez cette option sur *Non*, toutes les transactions de revendication sont validées.</p> |
| Inclure le journal de type de commande | Pour les accords ou les lignes d’accord où le type de transaction est défini sur *Commande*, cette option contrôle si une commande client du type *Journal* doit être incluse. Cela offre une certaine flexibilité si ces types de commande sont utilisés dans des scénarios où une remise ne devrait pas encore s’appliquer. |

## <a name="number-sequences-tab"></a>Onglet Souches de numéros

Utilisez l’onglet **Souche de numéros** sur la page **Paramètres de gestion des remises** pour attribuer des codes de souche de numéros aux différentes souches de numéros utilisées par la gestion des remises. Le tableau suivant décrit le but de chacune de ces souches de numéros. Pour plus d’informations sur les souches de numéros, voir [Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) et ses sujets connexes.

| Référence | Description |
|---|---|
| Accord de gestion des remises | La souche de numéros attribue une valeur de clé unique à chaque accord de remise. Cette clé est utilisée lors de la création des accords. |
| Numéro de gestion des remises | La souche de numéros attribue une valeur de clé unique à chaque remise. Cette clé est utilisée pour identifier les relations de remise. |
| Numéro de transaction de remise | La souche de numéros attribue une valeur de clé unique à chaque transaction de remise. Cette clé est utilisée pour identifier les transactions de remise. |
| Facture fiscale | La souche de numéros attribue une valeur de clé unique à chaque facture de remise. Cette clé est utilisée lorsque les journaux de remise sont automatiquement validés. |

## <a name="feature-visibility-tab"></a>Onglet Visibilité des fonctionnalités

La gestion des remises ajoute des fonctionnalités (champs et fonctions) à plusieurs pages fréquemment utilisées dans Microsoft Dynamics 365 Supply Chain Management. Ces pages incluent des pages liées aux commandes client et aux offres commerciales. Si vous utilisez la gestion des remises, vous devez rendre ces fonctionnalités visibles partout avant de pouvoir en bénéficier. Si vous n’utilisez pas la gestion des remises, vous pouvez masquer les fonctionnalités pour les garder à l’écart.

Sur l’onglet **Visibilité des fonctionnalités** de la page **Paramètres de gestion des remises**, définissez l’option **Activer** sur *Oui* pour rendre visibles les fonctionnalités de gestion des remises partout où elles sont disponibles. Réglez-la sur *Non* pour masquer les fonctionnalités sur les pages communes en dehors du module **Gestion des remises**. Cependant, même lorsque l’option est définie sur *Non*, le module lui-même, y compris la page **Paramètres de gestion des remises**, restera disponible pour les utilisateurs disposant des autorisations appropriées pour y accéder.
