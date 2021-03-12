---
title: Processus de configuration du rapprochement bancaire avancé
description: Le rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 Finance. Cet article décrit l’ensemble des processus de rapprochement.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b3c68c8e985e5ef770421cb5e7120db4d97d1de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976488"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Processus de configuration du rapprochement bancaire avancé

[!include [banner](../includes/banner.md)]

Le rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 Finance. Cet article décrit l’ensemble des processus de rapprochement.  

Un certain nombre d’éléments doit être défini avant d’utiliser la fonctionnalité de rapprochement bancaire avancé. Pour plus d’informations sur la configuration de l’importation de relevé bancaire, consultez [Configurer le processus d’importation de rapprochement bancaire avancé](set-up-advanced-bank-reconciliation-import-process.md).  La configuration requise pour configurer le processus de rapprochement est détaillée ci-dessous.

## <a name="transaction-codes"></a>Codes transaction
Les codes transaction peuvent être utilisés dans le cadre des règles de correspondance de rapprochement bancaire pour faire correspondre les mêmes types de transactions entre Finance et votre relevé bancaire. Afin d’effectuer ce type de correspondance, vous devez d’abord définir les types de transactions utilisés pour les transactions bancaires de Finance, puis mettre en correspondance ces types avec les codes de transaction de relevé utilisés par votre banque. Les types de transactions pour les transactions bancaires sont définis dans la page **Type de transaction bancaire**. C’est également là que vous définissez le compte principal à utiliser pour les validations associées à ce type de transaction. 

Une fois que vos codes de transaction bancaire sont définis, vous les mettez en correspondance avec les codes de transaction utilisés dans vos relevés bancaires électroniques. Ce processus de mise en correspondance est effectué à l’aide de la page **Mappage de code de transaction**. La mise en correspondance des codes transaction est effectuée séparément pour chaque compte bancaire.

## <a name="matching-rules-and-matching-rule-sets"></a>Règles de correspondance et ensembles de règles de correspondance
Les règles de correspondance permettent de définir les critères de rapprochement automatique entre les transactions bancaires Finance et les transactions de relevé bancaire. Le paramétrage des règles de correspondance est effectué sur la page **Règles de correspondance de rapprochement**. Pour plus d’informations, voir [Paramétrage des règles de correspondance du rapprochement bancaire](set-up-bank-reconciliation-matching-rules.md). 

Les ensembles de règles de correspondance sont utilisés pour définir un groupe de règles de correspondance qui sont exécutées dans l’ordre pendant le processus de rapprochement bancaire.  Les ensembles de règles de correspondance sont configurés sur la page **Ensembles de règles de correspondance de rapprochement**.

## <a name="cash-and-bank-management-parameters"></a>Paramètres de gestion de la trésorerie et de la banque
Il existe un certain nombre de paramètres spécifiques au processus de rapprochement bancaire avancé sur la page **Paramètres de gestion de la trésorerie et de la banque**.  L’option **Afficher le montant de la ligne de relevé au débit/crédit** change l’affichage des montants sur la page **Relevé bancaire**. Si cette option est sélectionnée, les montants de transaction de relevé bancaire seront affichés dans des colonnes de crédit et de débit distinctes. Sinon, les montants de transaction de relevé bancaire seront affichés dans une seule colonne de montant avec le symbole approprié. 

Les options de validation définies sur la page des paramètres remplacent les sélections définies dans les règles de correspondance. Par exemple, vous ne pouvez pas rapprocher manuellement ou automatiquement les documents au-delà de la différence de dates définie dans la page des paramètres. De plus, si l’option **Contrôler la mise en correspondance du type de transaction** est sélectionnée, les types de transactions doivent être mis en correspondance entre la transaction bancaire Finance et une transaction de relevé bancaire pour que les transactions soient rapprochées manuellement ou automatiquement. 

Vous devez également configurer les souches de numéros nécessaires sur la page **Paramètres de gestion de la trésorerie et de la banque**.  Sous l’onglet **Souches de numéros**, définissez les codes de souche de numéros pour les références d’**ID téléchargement, d’ID relevé, d’ID rapprochement et de rapprochement bancaire**.

## <a name="bank-account-reconciliation-options"></a>Options de rapprochement de compte bancaire
Vous devez d’abord activer le rapprochement bancaire avancé pour le compte bancaire. Un certain nombre d’options supplémentaires est disponible sur la page **Compte bancaire** une fois que la fonctionnalité de rapprochement bancaire avancé est activée. 

La fonctionnalité **Utiliser les relevés bancaires comme confirmation des paiements électroniques** intègre la fonctionnalité de rapprochement bancaire à des statuts de paiement électronique. Lorsque cette option est activée, un document bancaire est automatiquement créé pour que le statut de paiement électronique soit défini sur **Envoyé**. En outre, le statut d’un paiement électronique sera mis à jour de **Envoyé** à **Reçu** lorsque le paiement est mis en correspondance, rapproché et validé. 

Le champ **Nom de compte bancaire dans les relevés** est le nom utilisé pour le compte bancaire sur vos relevés bancaires électroniques. Ce nom est utilisé pour déterminer les transactions à importer pour un compte bancaire à partir d’un relevé qui peut contenir des informations concernant plusieurs comptes bancaires. 

L’option **Rapprocher après l’importation** validera automatiquement le relevé bancaire, créera un rapprochement bancaire et une feuille de calcul et exécutera l’ensemble de règles de correspondance par défaut. Cette fonctionnalité automatise le processus jusqu’au point où les transactions doivent être manuellement mises en correspondance. Le paramétrage du compte bancaire sera défini par défaut lors de l’importation.



