---
title: "Vue d&quot;ensemble du rapprochement bancaire avancé"
description: "Le rapprochement bancaire avancé permet d&quot;importer des relevés bancaires électroniques et pour les rapprocher automatiquement des transactions bancaires dans Microsoft Dynamics 365 pour les opérations.  Cet article décrit l’ensemble des processus de rapprochement."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Vue d'ensemble du rapprochement bancaire avancé

Le rapprochement bancaire avancé permet d'importer des relevés bancaires électroniques et pour les rapprocher automatiquement des transactions bancaires dans Microsoft Dynamics 365 pour les opérations.  Cet article décrit l’ensemble des processus de rapprochement.  

Il existe un certain nombre de pièces qui doivent être configurées avant d'utiliser la fonction avancée de rapprochement bancaire. Pour plus d'informations sur le paramétrage de l'importation des relevés bancaires, voir [paramétrer le processus d'importation des relevés bancaires] (setup-advanced-bank-reconciliation-import-process.md).  Les exigences pour le paramétrage du processus de rapprochement sont détaillés ci-dessous.

## <a name="transaction-codes"></a>Codes transaction
Codes transaction peuvent être utilisés dans le cadre de le rapprochement bancaire correspondant des règles.  Codes transaction aideront à correspondre uniquement les mêmes types de transactions entre Dynamics 365 pour les opérations et vos relevés bancaires.  Afin d'effectuer ce type de rapprochement, vous devez définir des types de transactions utilisés pour les transactions bancaires de Dynamics 365 pour les opérations, puis mettez en correspondance ces types aux codes transaction du relevé utilisés par votre banque.  Les types de transaction pour Dynamics 365 pour les transactions bancaires d'opérations sont définis sous ** type de transaction bancaire ** la page.  Elle permet également de définir le compte principal à utiliser pour les validations associées à ce type de transaction. 

Une fois votre Dynamics 365 pour les codes de transaction bancaire d'opérations sont définis, vous mettez en correspondance ensuite celles aux codes transaction utilisés dans vos relevés bancaires électroniques.  Ce processus de mise en correspondance est exécuté au ** mise en correspondance du code transaction ** la page.  La mise en correspondance de code transaction terminée séparément pour chaque compte bancaire.

## <a name="matching-rules-and-matching-rule-sets"></a>Règles de correspondance et ensembles de règles de correspondance
Correspond les règles permettent de définir des critères pour le rapprochement entre automatique Dynamics 365 pour les transactions bancaires d'opérations et des transactions de relevé bancaire.  Le paramétrage de rapprochement des règles est effectuée en fonction ** rapprochement rapprochant les règles ** page.  Pour plus d'informations, voir [paramétrer le rapprochement bancaire correspondant règles] (setup-bank-reconciliation-matching-rules.md). 

Correspond des ensembles de règles permettent de définir un groupe pour faire correspondre les règles qui sont exécutées dans l'ordre lors de le processus de rapprochement bancaire.  Correspond des ensembles de règles sont configurés sur ** rapprochement correspondant des ensembles de règles ** la page.

## <a name="cash-and-bank-management-parameters"></a>Paramètres de gestion de la trésorerie et de la banque
Prenez connaissance des paramètres spécifiques au processus de rapprochement bancaire avancé sous ** les paramètres de gestion des fonds et des banques ** la page.  ** Montant de la ligne de relevé d'afficher dans le débit/crédit ** les modifications la vue des montants sur ** relevé bancaire ** la page.  Si cette option est sélectionnée, les montants de la transaction du relevé bancaire sont affichés dans les colonnes distinctes de débit et de crédit.  En l'absence de sélection, les montants de la transaction du relevé bancaire sont affichés dans une seule colonne de montant avec le signe approprié. 

Les options de contrôle définies dans la page de paramètres remplacent les sélections définies sur correspondre les règles.  Par exemple, vous ne pouvez pas entrer manuellement ou automatiquement correspondre les documents au delà de la différence de date définie dans la page Paramètres.  De plus, si l'option ** validez la mise en correspondance de type de transaction ** est activée, les types de transactions doivent être mis en correspondance entre Dynamics 365 pour les opérations transaction bancaire et la transaction de relevé bancaire pour que des transactions correspondent manuellement ou automatiquement. 

Vous devez également configurer les souches de numéros nécessaires dans ** les paramètres de gestion des fonds et des banques ** la page.  Sous ** des souches de numéros ** l'onglet, définissez les codes souche de numéros pour le téléchargement ** ID, l'ID instruction, rapprochez l'ID, et le rapprochement bancaire ** des références.

## <a name="bank-account-reconciliation-options"></a>Options de rapprochement de compte bancaire
Vous devez activer le rapprochement bancaire avancé pour le compte bancaire.  Plusieurs options supplémentaires sont disponibles sous ** compte bancaire ** la page une fois que la fonction avancée de rapprochement bancaire est activée. 

** Utilisez les relevés bancaires comme confirmation de paiement électronique ** la fonctionnalité intègre une fonctionnalité de rapprochement bancaire avec un statut de paiement électronique.  Si cette option est activée, un document bancaire est créé automatiquement pour le statut de paiement électronique est défini sur ** envoyé **.  En outre, le statut d'un paiement électronique est mis à jour à partir de ** envoyé ** à ** reçu ** lorsque le paiement est mis en correspondance, rapproché, et validé. 

** Nom du compte bancaire dans les relevés ** le champ correspond au nom utilisé pour le compte bancaire sur vos relevés bancaires électroniques.  Ce nom est utilisé la détermination des transactions à importer pour un compte bancaire d'un relevé qui peut contenir des informations sur les comptes bancaires multiples. 

L'option ** rapprochez après l'importation ** valide automatiquement le relevé bancaire, crée un nouveau rapprochement bancaire et feuille de calcul, et réexécute l'ensemble de règles correspondant par défaut.  Cette fonctionnalité automatise le processus coûtant jusqu'des transactions qui doivent être mises en correspondance manuellement.  Le paramétrage sur le compte bancaire est par défaut celle lorsque important.


