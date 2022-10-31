---
title: Documents en attente de comptabilité
description: Cet article décrit comment utiliser la fonctionnalité de la page Documents en attente de comptabilité.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709247"
---
# <a name="documents-pending-accounting"></a>Documents en attente de comptabilité

[!include [banner](../includes/banner.md)]

Cet article décrit comment utiliser la fonctionnalité de la page **Documents en attente de comptabilité**.

Dans Microsoft Dynamics 365 Finance 10.0.30, la fonctionnalité **Performances améliorées de l’infrastructure comptable des documents sources** est disponible. Cette fonctionnalité améliore les processus de validation pour les validations de documents compatibles avec les documents sources, en commençant par le processus de validation des factures financières.

Lorsque cette fonctionnalité est activée, la validation du document de comptabilité auxiliaire est effectuée séparément du processus de génération comptable ou de *journalisation* qui crée les détails comptables complets qui sont transférés vers la comptabilité générale. Par exemple, dans le processus de validation de factures financières, la facture client dans le module **Comptabilité client** est enregistrée avant la génération de la comptabilité complète. Cette fonctionnalité de performances améliorées permet d’enregistrer plus rapidement les factures des clients tout en retardant la génération comptable.

Les boutons suivants sont disponibles sur la page **Documents en attente de comptabilité**.

- **Générer la comptabilité** : envoyez un document actuellement en attente de génération comptable pour la journalisation.
- **Afficher les répartitions** : affichez les répartitions comptables d’un document sélectionné dans la liste.
- **Afficher le journal des erreurs** : affichez les détails du message d’erreur qui existent pour un document dont l’état comptable indique des erreurs. Vous pouvez afficher les mêmes détails du message d’erreur en sélectionnant le lien **Journal des erreurs** sur la ligne du document.

La génération comptable est effectuée par un processus en arrière-plan d’automatisation de processus nommé **Processeur de l’infrastructure comptable**. Pour plus d’informations sur l’installation et la configuration de toutes les automatisations de processus, consultez [Automatisation de processus](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
