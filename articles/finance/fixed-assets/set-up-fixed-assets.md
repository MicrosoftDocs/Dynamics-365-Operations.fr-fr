---
title: Paramétrage d’immobilisations
description: Cette rubrique fournit une vue d’ensemble du paramétrage du module Immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c42522f69ecf2eb25d8d9384737115826ff4cda
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978509"
---
# <a name="set-up-fixed-assets"></a>Paramétrage d’immobilisations

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble du paramétrage du module **Immobilisations**.

## <a name="overview"></a>Vue d’ensemble

Les paramètres contrôlent le comportement général dans les Immobilisations.

Les groupes d’immobilisations vous permettent de regrouper vos immobilisations et de spécifier des attributs par défaut pour chaque immobilisation attribuée à un groupe. Les registres sont affectés aux groupes d’immobilisations. Les registres effectuent le suivi de la valeur financière d’une immobilisation dans le temps à l’aide de la configuration d’amortissement qui est définie dans le profil d’amortissement.

Les immobilisations sont affectées à un groupe lors de leur création. Par défaut, les registres affectés au groupe d’immobilisations sont ensuite affectés à l’immobilisation. Les registres qui sont configurés pour valider dans la comptabilité sont associés à un profil de validation. Les comptes généraux sont définis pour chaque registre dans le profil de validation et sont utilisés lorsque des transactions d’immobilisation sont validées.

![Composants d’immobilisation](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Profils d’amortissement

Vous devez d’abord paramétrer les profils d’amortissement. Dans le profil d’amortissement, vous configurez la manière dont la valeur d’une immobilisation est amortie dans le temps. Vous devez définir la méthode d’amortissement, l’année d’amortissement (année civile ou exercice), et la fréquence d’amortissement. Pour plus d’informations, voir [Paramétrer et créer des profils d’amortissement](tasks/set-up-depreciation-profiles.md).

## <a name="books"></a>Registres

Après avoir paramétré les profils d’amortissement, vous devez créer les registres requis pour vos immobilisations. Chaque registre effecte le suivi d’un cycle de vie financier indépendant d’une immobilisation. Les registres peuvent être configurés pour valider les transactions associées dans la comptabilité. Cette configuration est le paramètre par défaut, car elle est généralement utilisée pour générer les états financiers d’entreprise. Les registres qui ne sont pas validés dans la comptabilité se valident uniquement dans la comptabilité auxiliaire d’immobilisation et sont généralement utilisés à des fins de déclaration de taxe.

Un profil d’amortissement principal est affecté à chaque registre. Les registres ont également un profil d’amortissement alternatif ou de basculement, si ce type de profil s’applique. Pour inclure automatiquement le registre d’immobilisations dans des exécutions d’amortissement, vous devez activer l’option **Calculer l’amortissement**. Si cette option n’est pas activée pour une immobilisation, la proposition d’amortissement ignore l’immobilisation.

Vous pouvez également paramétrer des registres dérivés. Les transactions dérivées spécifiées sont validées par rapport aux registres dérivés comme copie exacte de la transaction principale. Par conséquent, les transactions dérivées sont généralement définies pour les acquisitions et les cessions, pas pour les transactions d’amortissement. Pour plus d’informations sur les modèles de valeur, voir [Configurer des modèles de valeur](tasks/set-up-value-models.md).

## <a name="fixed-asset-posting-profiles"></a>Profils de validation d’immobilisation

Une fois les registres paramétrés, vous pouvez créer le profil de validation. Le profil de validation doit être défini par registre, mais il peut également être défini avec plus de précision. Par exemple, vous pouvez définir le profil de validation de la combinaison d’un registre et d’un groupe d’immobilisations, voire d’un registre d’immobilisation individuel. Par défaut, les comptes généraux définis sont utilisés pour vos transactions d’immobilisation.

Vous devez définir les comptes généraux utilisés lors des processus de cession, les ventes de cession et les mises au rebut de cession. Lors de la cession, les transactions d’immobilisation préalablement validées sont contrepassées des comptes d’origine. Les montants nets sont ensuite déplacés vers le compte approprié pour les profits et pertes de la cession de l’immobilisation. Pour s’assurer que les transactions sont correctement contrepassées, vous devez paramétrer les comptes de chaque type de transaction que vous utilisez dans votre entreprise. Le compte principal doit être le compte principal d’origine que vous définissez dans le profil de validation pour le type de transaction, et le compte de contrepartie doit être le compte de résultat pour les cessions. La valeur comptable nette est une exception. Dans ce cas, le compte principal et le compte de contrepartie doivent être définis sur le compte de résultat pour les cessions. Pour plus d’informations, voir [Paramétrer des profils de validation d’immobilisation](tasks/set-up-fixed-asset-posting-profiles.md).

## <a name="fixed-asset-groups"></a>Groupes d’immobilisations

Le champ **Groupe d’immobilisations** est le seul champ obligatoire lorsque vous créez une immobilisation. La valeur de ce champ détermine la valeur par défaut de plusieurs champs d’informations de l’immobilisation. Les registres sont paramétrés afin qu’un registre par défaut soit affecté à chaque immobilisation dans un groupe. Ainsi, les attributs que vous définissez pour les registres peuvent être spécifiques à un groupe d’immobilisations. Ces attributs incluent la durée de vie et la convention d’amortissement.

Vous pouvez également définir des provisions spéciales pour amortissement, ou l’amortissement de la prime, pour une combinaison spécifique d’un groupe d’immobilisations et d’un registre. Vous devez affecter une priorité à la provision spéciale pour amortissement pour spécifier l’ordre dans lequel les provisions sont calculées lorsque plusieurs provisions sont affectées à un registre. Pour plus d’informations, voir [Paramétrer les groupes d’immobilisation](tasks/set-up-fixed-asset-groups.md).

## <a name="journal-names"></a>Noms de journal

Dans la page **Noms de journal**, vous devez créer les noms de journal à utiliser avec le journal des immobilisations. Vous devez définir le champ **Type de journal** sur **Valider les immobilisations**. Définissez le champ **Souche de N° documents** de manière à ce que les noms de journal soient utilisés pour le journal des immobilisations. Les journaux des immobilisations ne doivent pas utiliser le paramètre **Un seul N° document**, car un seul numéro de document est requis pour plusieurs processus automatisés, tels que les transferts et les fractionnements.

## <a name="fixed-asset-parameters"></a>Paramètres d’immobilisation

La dernière étape consiste à mettre à jour les paramètres des immobilisations.

Le champ **Seuil de capitalisation** détermine les immobilisations qui sont amorties. Si une ligne d’achat est sélectionnée comme immobilisation, mais qu’elle ne correspond pas au seuil de capitalisation, une immobilisation est quand même créée ou mise à jour, mais l’option **Calculer l’amortissement** est définie sur **Non**. Par conséquent, l’immobilisation ne sera pas automatiquement amortie dans le cadre des propositions d’amortissement.

L’option **Créer automatiquement des montants d’ajustement d’amortissement avec cession** est une option importante. Lorsque vous définissez cette option sur **Oui**, l’amortissement des immobilisations est ajusté automatiquement, selon les paramètres d’amortissement au moment de la cession d’immobilisations. Une autre option vous permet de déduire des escomptes de règlement du montant d’acquisition lorsque vous acquérez des immobilisations à l’aide d’une facture fournisseur.

Sur l’organisateur **Commandes fournisseur**, vous pouvez configurer la manière les actifs sont créés dans le cadre du processus d’achat. La première option est nommée **Autoriser l’acquisition d’actifs à partir d’Achats**. Si vous définissez cette option sur **Oui**, l’acquisition d’immobilisation se produit lorsque la facture est validée. Si vous définissez cette option sur **Non**, vous pouvez toujours placer une immobilisation sur une commande fournisseur (CF) et la facture, mais l’acquisition ne sera pas validée. La validation doit être effectuée comme étape distincte, à partir du journal des immobilisations. L’option **Créer un actif lors de la validation de l’accusé de réception des marchandises ou de la facture** vous permet de créer un nouvel actif « à la volée » lors de la validation. Ainsi, il n’est pas nécessaire de paramétrer l’actif en tant qu’immobilisation avant la transaction. La dernière option, **Vérifier la création des immobilisations au cours de la saisie des lignes** ne s’applique qu’aux demandes d’achat.

Vous pouvez configurer les codes de motif afin qu’ils soient obligatoires pour modifier une immobilisation ou pour les transactions d’immobilisations spécifiques.

Enfin, sous l’onglet **Souches de numéros**, vous définissez des souches de numéros pour les immobilisations. La souche de numéros **Immobilisation** peut être remplacée par la souche de numéros **Groupe d’immobilisations** si elle a été spécifiée.

Pour plus d’informations, voir [Créer une immobilisation](tasks/create-fixed-asset.md).
