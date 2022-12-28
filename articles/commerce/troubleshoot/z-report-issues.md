---
title: Problèmes relatif au rapprochement des données d’un Z de caisse
description: Cet article décrit les problèmes que les utilisateurs peuvent rencontrer avec le rapprochement des données d’un rapport Z à Commerce headquarters. Il décrit également les causes profondes possibles et les solutions qui peuvent aider à prévenir de futures occurrences.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832140"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problèmes relatif au rapprochement des données d’un Z de caisse

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent vous aider si vous rencontrez des problèmes avec le rapprochement des données d’un rapport Z à Microsoft Dynamics 365 Commerce headquarters. Il décrit les problèmes que les utilisateurs peuvent rencontrer avec la réconciliation des données, les causes profondes possibles et les solutions qui peuvent aider à prévenir de futures occurrences.

## <a name="description"></a>Description

- Il y a un décalage entre les montants indiqués sur le rapport Z et les totaux indiqués sur le relevé calculé.
- La transaction dans headquarters a un nombre incorrect d’éléments de ligne, ou il y a une incohérence entre le total de la ligne et le total de la transaction.
- Le nombre de transactions affichées dans un quart de travail au siège social est inférieur au nombre de transactions sur le rapport Z.
- La publication du relevé a échoué pour l’une des raisons précédentes.

### <a name="root-cause"></a>Cause première

La cause principale la plus courante des symptômes décrits précédemment est la génération d’ID de transaction en double dans la base de données du canal. Des ID de transactions en double peuvent être générés pour les raisons suivantes :

- Le stockage de la base de données locale de Modern POS est corrompu.
- MPOS a certaines transactions en mode hors connexion, et il est réactivé en utilisant un compte qui n’a pas accès à la base de données hors connexion.
- Il existe un problème de personnalisation lié à la génération d’ID de transaction.

## <a name="resolution"></a>Résolution

Habituellement, Commerce s’appuie sur une séquence de numéros pour générer des ID de transaction séquentiels. Si le système ne peut pas déterminer qu’une souche de numéros a été utilisée pour une raison quelconque, un ID de transaction en double est généré. 

Pour résoudre le problème d’ID de transaction en double, créez un ticket de support pour vérifier si les données de transaction peuvent être corrigées. Dans certains cas, par exemple lorsqu’il n’y a pas de perte de données dans headquarters, aucune correction de données n’est possible ou requise.

Pour aider à prévenir ce problème à l’avenir, vous devez activer la fonctionnalité **Activer le nouvel identifiant de transaction pour éviter les identifiants de transaction en double** dans headquarters. Cette fonctionnalité a été présentée dans la version 10.0.19 de Commerce. Il aide à empêcher la création d’ID de transaction séquentiels en garantissant qu’un ID de transaction unique est créé pour chaque transaction. Pour plus d’informations sur cette fonctionnalité, voir [Empêcher les ID de transactions en double](../channel-setup-retail.md#ensure-unique-transaction-ids).
