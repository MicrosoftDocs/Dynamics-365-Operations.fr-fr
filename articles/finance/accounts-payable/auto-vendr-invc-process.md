---
title: Vue d’ensemble des processus de facturation automatisés des fournisseurs
description: Cette rubrique décrit la capacité d’automatisation du traitement de vos factures fournisseur et les avantages de l’utilisation d’un processus automatisé.
author: abruer
ms.date: 02/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f21b76bb0d30370e4ea4fdd718999d537e9ce925
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358428"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Vue d’ensemble des processus de facturation automatisés des fournisseurs

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la capacité d’automatisation du traitement de vos factures fournisseur et les avantages de l’utilisation d’un processus automatisé. Cette fonctionnalité comprend les fonctionnalités activées dans la gestion des fonctionnalités. Ces fonctionnalités s’appliquent uniquement aux factures fournisseurs, et non aux factures traitées à l’aide de la page **Journal des factures** ou **Journal du registre des factures**.

Les organisations collaborent souvent avec des fournisseurs pour traiter les factures papier à l’aide de services de reconnaissance optique des caractères (OCR). Le fournisseur de services renvoie des métadonnées de facture lisibles par une machine. Pour faciliter l’automatisation, les fonctionnalités d’automatisation de la comptabilité fournisseur vous permettent de consommer ces artefacts à partir de la comptabilité fournisseurs.

Vous pouvez automatiser certains processus de facturation des fournisseurs de la comptabilité fournisseur. Ces processus incluent l’envoi des factures fournisseur importées au système de workflow et la mise en correspondance des lignes de réception des marchandises avec les lignes de facture fournisseur en attente. Le processus automatisé affiche des informations sur la progression d’une facture fournisseur dans chacun des processus. Cette capacité peut aider les employés et les responsables de la comptabilité fournisseur à traiter plus efficacement les factures des fournisseurs. Elle permet également de réduire les erreurs et les inefficacités qui peuvent survenir lorsque des informations sont saisies et traitées manuellement.

Les processus d’automatisation peuvent être utilisés pour effectuer les tâches suivantes :

- Appliquer automatiquement les acomptes aux factures fournisseur
- Envoyer automatiquement les factures importées au système de workflow.
- Mettre en correspondance les accusés de réception de marchandises et les lignes de facture fournisseur en attente.
- Simuler la validation avant la validation d’une facture fournisseur.
- Visualiser rapidement et efficacement l’historique des automatisations et des workflows.
- Afficher et analyser les résultats de l’automatisation du traitement des factures fournisseurs.
- Reprenez le traitement automatisé de plusieurs factures.

## <a name="submit-imported-vendor-invoices-to-the-workflow-system"></a>Envoyer les factures fournisseur importées dans le système de workflow

Dans le cadre d’un processus de facturation des comptes fournisseurs sans contact, une facture importée peut être automatiquement soumise au système de workflow. Le processus s’exécutera en arrière-plan, à la fréquence que vous spécifiez (toutes les heures ou tous les jours). La capacité d’envoyer automatiquement des factures importées au système de flux de travail nécessite que votre processus commence par une facture importée. Pour garantir que la facture peut être traitée du début à la fin sans intervention manuelle, une tâche de validation automatisée doit être incluse dans la configuration du workflow.


Les factures liées aux bons de commande, et les factures qui contiennent une catégorie d’approvisionnement sans bon de commande et des lignes non stockées peuvent être automatiquement envoyées au système de workflow. Les factures saisies manuellement et les factures créées à l’aide de l’espace de travail **Facturation de collaboration fournisseur** doivent être envoyées manuellement au système de workflow. Le traitement de l’application d’acomptes doit être effectué manuellement pour les factures importées. Vous pouvez appliquer manuellement des acomptes avant ou après la validation de la facture importée. Vous pouvez appliquer manuellement des acomptes à des factures standard non imputées à l’aide de la page **Factures fournisseur**. Après validation, l’acompte réglé pourra être appliqué manuellement à d’autres factures de ce fournisseur sur la page **Fournisseurs** (**Comptabilité fournisseur \> Commun \> Fournisseurs \> Tous les fournisseurs \> Onglet Facture \> Appliquer**).

La fonction d’automatisation fournit un cadre flexible qui vous permet de définir des règles spécifiques à l’entreprise pour l’envoi des factures fournisseur importées au système de workflow et la mise en correspondance des lignes de réception de produit validées avec les lignes de facture fournisseur en attente.

## <a name="match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Faire correspondre les réceptions de marchandises aux lignes de facture qui ont une stratégie de rapprochement à trois facteurs

Les reçus de produits validés peuvent être automatiquement mis en correspondance avec les lignes de facture pour lesquelles une stratégie de rapprochement à trois facteurs est définie. Le processus s’exécutera jusqu’à ce que la quantité des marchandises reçues soit égale à la quantité de la facture. Dans le cadre de ce processus, vous pouvez spécifier le nombre maximal de fois que le système doit essayer de faire correspondre les réceptions de marchandises avec une ligne de facture avant de conclure que le processus a échoué. Le processus s’exécutera en arrière-plan, toutes les heures ou tous les jours. Vous pouvez exécuter le processus de mise en correspondance automatique dans le cadre du processus d’envoi des factures au système de workflow. Vous pouvez également l’exécuter en tant que processus autonome.

## <a name="pre-validate-vendor-invoice-posting"></a>Pré-valider la validation des factures fournisseur

La simulation de comptabilisation termine les étapes de validation qui sont effectuées pendant le processus de validation des factures fournisseur, mais aucun compte n’est mis à jour. Pour exécuter le processus, vous pouvez sélectionner une seule facture ou plusieurs factures sur la page **Factures fournisseur en attente**.

## <a name="enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>Expérience améliorée pour afficher les informations historiques des workflows et de l’automatisation pour les factures fournisseur

Une vue facile à lire de l’historique du workflow des factures fournisseur est fournie. L’historique du workflow des factures fournisseur est accessible directement à partir de la facture fournisseur. Par conséquent, moins de clics sont nécessaires pour trouver ces informations. Si votre organisation a activé la possibilité de soumettre automatiquement les factures fournisseur importées au workflow, l’historique des automatisations est fourni pour les factures importées. L’historique des automatisations vous aide à identifier l’étape actuelle du processus, ainsi que les étapes qui ont déjà été effectuées. Lorsqu’une étape échoue, des informations détaillées seront fournies pour vous aider à comprendre la raison de l’échec.

## <a name="analytics-and-metrics"></a>Analyses et indicateurs de performance

L’espace de travail **Saisie de facture fournisseur** vous permet de vous concentrer sur les factures fournisseur qui n’ont pas réussi le processus automatisé. Les vignettes de l’espace de travail répertorient les informations sur les factures fournisseur qui n’ont pas été envoyées correctement au système de workflow, importées ou mises en correspondance avec les reçus de produits. Les indicateurs de performance Microsoft Power BI sont également fournis pour donner aux gestionnaires de la comptabilité fournisseur un aperçu de l’efficacité de l’automatisation des factures fournisseur.


## <a name="resume-automation-processing-for-multiple-invoices"></a>Reprendre l’automatisation de plusieurs factures

Lorsqu’une facture importée n’est pas soumise avec succès au workflow à l’aide du processus automatisé, le système la supprimera du traitement automatisé ultérieur. Un commis au paiement de la comptabilité fournisseur peut passer en revue et modifier la facture avant que le processus automatisé ne la soumette à nouveau au workflow. Lorsqu’un motif d’échec peut être résolu par le même correctif pour plusieurs factures, vous pouvez redémarrer le processus automatisé sur la page **Reprendre le traitement automatisé des factures**. 

## <a name="tracking-the-invoice-received-date-value"></a>Suivi de la valeur de la date de réception de la facture

La valeur **Date de réception de la facture** indique la date à laquelle l’entreprise a reçu la facture du fournisseur. Elle fournit un point de départ pour suivre la progression de la facture tout au long des processus d’automatisation. Cette valeur peut être incluse dans les données importées pour une facture fournisseur. Pour les factures créées manuellement, vous pouvez spécifier la date. Si aucune valeur n’est saisie, la date du jour est utilisée par défaut.


## <a name="tracking-the-imported-invoice-amount-and-imported-sales-tax-amount-values"></a>Suivi du montant de la facture importée et des valeurs du montant de la taxe de vente importée

Les valeurs **Montant de la facture importée** et **Montant de la taxe de vente importée** des factures fournisseur peuvent être fournies dans le fichier d’importation des factures fournisseur. En règle générale, ces valeurs proviennent d’une facture qui a été scannée par un fournisseur externe et incluse dans le fichier d’importation. Lorsque la facture est traitée dans la comptabilité fournisseurs, les valeurs seront calculées en fonction des données de la facture. La facture ne peut être validée que si les valeurs importées correspondent aux valeurs calculées. Les valeurs correspondantes garantissent que la facture reflète fidèlement le montant dû au fournisseur. Si votre organisation autorise l’envoi automatique de factures importées au système de workflow, vous pouvez éventuellement exiger que les totaux importés correspondent aux totaux calculés avant que la facture puisse être soumise au système de workflow.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Automatisation des factures fournisseur : reprendre le traitement de l’automatisation pour plusieurs factures
Lorsqu’une facture importée n’est pas soumise avec succès au workflow via le processus automatisé, le système la supprimera du traitement automatisé ultérieur. Un commis au paiement de la comptabilité fournisseur peut passer en revue et modifier la facture avant que le processus automatisé ne la soumette à nouveau au workflow. Lorsqu’un motif d’échec peut être résolu par le même correctif pour plusieurs factures, vous pouvez redémarrer le processus automatisé sur la page **Reprendre le traitement automatisé des factures**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
