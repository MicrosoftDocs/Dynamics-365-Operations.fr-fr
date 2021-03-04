---
title: Options de configuration pour l’automatisation des factures fournisseur (Version préliminaire)
description: Cette rubrique décrit les options disponibles pour le péramétrage et la configuration de l’automatisation des factures fournisseur.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ebab41d8b7697f20095d6d4654718b88c8b08a82
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665196"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Options de configuration pour l’automatisation des factures fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les options disponibles pour le péramétrage et la configuration de l’automatisation des factures fournisseur. Les fonctionnalités d’automatisation des factures utilisent les types de paramètres de configuration suivants :

- Paramètres de soumission des factures fournisseur importées au système de workflow et de mise en correspondance des lignes de réception des marchandises avec les lignes de facture fournisseur en attente.
- Paramètres des tâches d’automatisation du traitement en arrière-plan. L’infrastructure d’automatisation des processus est utilisée pour soumettre les factures fournisseurs importées au système de workflow. Il est également utilisé pour faire correspondre automatiquement les lignes de réception de produit validées aux lignes de facture fournisseur en attente et pour effectuer la validation de rapprochement des factures pour les factures manuelles qui étaient automatiquement rapprochées des lignes de réception de produit. Différents processus métier utilisent cette infrastructure pour définir la fréquence d’exécution du processus sélectionné. Les fréquences disponibles pour les processus en arrière-plan **Faire correspondre la réception des marchandises avec les lignes de facture** et **Soumettre les factures fournisseurs au workflow** sont notamment **Chaque heure** et **Chaque jour**.

Pour configurer ou afficher des informations sur une tâche en arrière-plan, accédez à **Administration système \> Configuration \> Automatisations de processus**, et sélectionnez l’onglet **Tâche en arrière-plan**.

Pour obtenir une automatisation sans contact du processus d’importation à la validation de la facture fournisseur, vous devez configurer un flux de travail de facture fournisseur. Pour configurer un workflow, accédez à **Comptabilité fournisseur > Configuration > Workflows de la comptabilité fournisseur**. Pour vous assurer que la facture peut être traitée du début à la fin sans intervention manuelle, vous devez inclure une tâche de validation automatisée dans votre configuration de workflow.

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Paramètres de soumission des factures fournisseurs importées au système de workflow

La soumission des factures fournisseurs importées au système de workflow utilise des paramètres spécifiques. En outre, d’autres paramètres sont utilisés pour faire correspondre automatiquement les lignes de réception des marchandises avec les lignes de facture fournisseur en attente. Dans l’onglet **Automatisation des factures fournisseurs** de la page **Paramètres de la comptabilité fournisseur**, les paramètres que vous devez définir sont répartis entre les sections suivantes :

- Flux de travail des factures fournisseur
- Rapprocher automatiquement des accusés de réception de marchandises

Les paramètres disponibles sont les suivants :

- **Soumettre automatiquement les factures importées au workflow** - Si vous définissez cette option sur **Oui**, les factures importées sont automatiquement soumises au système de workflow. Si cette option est définie sur **Non**, les factures doivent être soumises manuellement. En définissant cette option sur **Oui**, vous activez un processus sans contact depuis les résultats de l’importation jusqu’à la validation.

    Vous ne pouvez définir cette option sur **Oui** que si un workflow de facturation fournisseur actif est configuré pour votre entité juridique. Pour configurer un workflow, accédez à **Comptabilité fournisseur \> Configuration \> Workflow de la comptabilité fournisseur**.

- **Faire correspondre les réceptions de marchandises avec les lignes de facture avant de les soumettre automatiquement** - Si vous définissez cette option sur **Oui**, la facture importée ne peut pas être soumise automatiquement au système de workflow tant que la quantité des marchandises reçues n’est pas égale à la quantité de la facture. En définissant cette option sur **Oui**, vous activez le rapprochement automatique des réceptions de marchandises validées avec les lignes de facture pour lesquelles une stratégie de rapprochement à trois facteurs est définie. Ce processus s’exécutera jusqu’à ce que la quantité des marchandises reçues soit égale à la quantité de la facture. À ce stade, la facture sera automatiquement soumise au système de workflow.

    L’option « Faire correspondre les réceptions de marchandises avec les lignes de facture avant de les soumettre automatiquement » n’est disponible que si l’option **Activer le contrôle de rapprochement de factures** est sélectionnée. Lorsque cette option est sélectionnée, l’option **Faire correspondre automatiquement les réceptions de marchandises avec les lignes de facture** est automatiquement sélectionnée.

- **Exiger que les totaux calculés soient égaux aux totaux importés pour la soumission automatique au workflow** - Si vous définissez cette option sur **Oui**, la facture ne peut pas être automatiquement soumise au système de workflow tant que les totaux calculés pour la facture ne sont pas égaux aux totaux importés. Si cette option est définie sur **Non**, la facture peut être automatiquement soumise au système de workflow, mais elle ne peut pas être validée tant que les totaux calculés ne sont pas corrigés afin de correspondre aux totaux importés. Si vous n’importez pas le montant de la facture ou le montant des taxes, cette option doit être définie sur **Non**.
- **Faire correspondre automatiquement les réceptions de marchandises avec les lignes de facture** - Si vous définissez cette option sur **Oui**, le traitement en arrière-plan peut être utilisé pour effectuer un rapprochement automatique des réceptions de marchandises validées avec les lignes de facture pour lesquelles une stratégie de rapprochement à trois facteurs est définie. Ce processus s’exécutera jusqu’à ce que la quantité des marchandises reçues soit égale à la quantité de la facture, ou jusqu’à ce que la valeur du champ **Nombre de tentatives de correspondance automatique** soit atteinte. Le processus peut être exécuté jusqu’à ce que la facture ait été soumise au système de workflow.

    Cette option n’est disponible que si l’option **Activer le contrôle de rapprochement de factures** est également sélectionnée.

    Si vous définissez l’option **Faire correspondre les réceptions de marchandises avec les lignes de facture avant de les soumettre automatiquement** sur **Oui**, cette option ne peut pas être définie sur **Non**. Pour définir cette option sur **Non**, vous devez d’abord définir l’option **Faire correspondre les réceptions de marchandises avec les lignes de facture avant de les soumettre automatiquement** sur **Non**.

- **Nombre de tentatives de correspondance automatique** - Sélectionnez le nombre de fois que le système doit essayer de faire correspondre les réceptions de marchandises à une ligne de facture avant de conclure que le processus a échoué. Lorsque le nombre de tentatives spécifié est atteint, la facture est supprimée du traitement automatisé.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]