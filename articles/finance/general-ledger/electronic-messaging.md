---
title: Messagerie électronique
description: Cette rubrique fournit des informations générales et de configuration pour la messagerie électronique dans Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 08/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 16b0e0fa74109f1c63ed47606bebe2fefc604fc5
ms.sourcegitcommit: efcb853a68a77037cca23582d9f6f96ea573727a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7478722"
---
# <a name="electronic-messaging"></a>Messages électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales et de configuration pour la fonctionnalité **Messages électroniques** (ME).

Récemment, les gouvernements et autorités législatives de différents pays/régions du monde entier ont implémenté l’obligation de génération d’états pour les sociétés qui sont enregistrées dans ces pays ou régions. L’objectif de ces obligations vise à permettre d’obtenir des données de ces sociétés au format électronique, directement depuis les systèmes auxquelles elles ont été comptabilisées, enregistrées, et traitées.

La fonctionnalité ME de Microsoft Dynamics 365 Finance prend en charge différents processus d’interopérabilité électronique entre Finance et les systèmes que les gouvernements et les autorités législatives offrent pour la génération d’états, la soumission et la réception d’informations officielles.

La fonctionnalité ME est intégrée au module **États électroniques** (ER). Vous pouvez paramétrer des formats d’ER pour les messageries électroniques. Pour plus d’informations, voir [États électroniques (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Concepts de base pour la fonctionnalité ME

La fonctionnalité ME est basée sur les entités suivantes :

- **Message électronique** : un état ou une déclaration qui doit être déclarée ou transmise en interne, telle qu'une déclaration envoyée à un bureau des impôts.
- **Éléments de messagerie électronique** : Enregistrements à inclure dans le message qui est déclaré.
- **Traitement de message électronique** : chaîne d’actions qui doivent être effectuées pour collecter les données nécessaires, générer des états, stocker des données dans Azure Storage Blob, transmettre des états en dehors du système, recevoir des réponses extérieures au système et mettre à jour la base de données en fonction des informations reçues. Les actions de la chaîne peuvent être liées ou non.

L'illustration suivante montre le flux des données pour ME.

![Flux de données de la messagerie électronique.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Scénarios pris en charge par la fonctionnalité ME

La fonctionnalité ME prend en charge les scénarios suivants :

- Créez des messages et générez manuellement des états qui sont basés sur des formats d’exportation d’ER de différents types : notamment Microsoft Excel, XML, JSON (JavaScript Object Notation), PDF, Texte et Microsoft Word.
- Créez et traitez automatiquement les messages qui sont basés sur les informations demandées et reçues depuis une autorité à l'aide d'un format d’ER d’importation associé.
- Collectez et traitez les informations d’une source de données comme des éléments du message. La source de données est une table Finance.
- Stockez des informations supplémentaires, et évaluez différentes valeurs en appelant des classes exécutables définies spécifiquement concernant les messages ou les éléments du message.
- Regroupez les informations collectées dans les éléments de message, répartissez les informations par message, et générez des états dans des formats d’ER d’exportation associés.
- Transmettez les états générés à un service web à l’aide des informations de sécurité stockées dans Azure Key Vault.
- Recevez une réponse d’un service Web, interprétez la réponse, et mettez à jour les données dans Finance, au besoin.
- Stockez et vérifiez tous les états générés.
- Stockez et vérifiez toutes les informations de journal associées aux actions exécutées pour un message ou un élément du message.
- Contrôlez le traitement par l’intermédiaire de différents statuts de message et statuts d’élément du message.

## <a name="security-privileges"></a>Privilèges de sécurité

Les privilèges de sécurité suivants sont disponibles pour les messages électroniques.

| Privilège de sécurité           | Niveau d'accès | Association |
|------------------------------|--------------|-------------|
| Mettre à jour les messages électroniques | Ce privilège donne un accès complet à la fonctionnalité ME. Si vous disposez de ce privilège, vous pouvez paramétrer la messagerie électronique et exécuter tous les traitements. | Ce privilège est inclus dans le droit de sécurité **Tenir à jour les transactions de taxe**. Ce droit, à son tour, est inclus dans le rôle de sécurité **Comptable**. |
| Afficher les messages électroniques     | Ce privilège donne un accès en lecture seule à la fonctionnalité ME. Si vous disposez de ce privilège, vous pouvez afficher les paramètres et les messages de la messagerie électronique. Cependant, vous ne pouvez rien configurer ni exécuter. | Ce privilège est inclus dans le droit de sécurité **Interroger le statut des transactions de taxe**. Ce droit, à son tour, est inclus dans les rôles de sécurité suivants :<ul><li>Gestionnaire de recouvrement</li><li>Commis à la comptabilité client</li><li>Responsable Comptabilité client</li><li>Comptable des taxes</li><li>Comptable</li><li>Responsable comptabilité</li><li>Chef comptable</li><li>Responsable des ventes</li><li>Commis à la comptabilité fournisseur</li></ul> |
| Traiter les messages électroniques  | Ce privilège donne accès uniquement aux pages **Messages électroniques** et **Éléments des messages électroniques**. Si vous disposez de ce privilège, vous pouvez exécuter tous les traitements appelés à partir de ces pages. | Ce privilège est inclus dans le droit de sécurité **Utiliser les messages électroniques**. Ce droit, à son tour, est inclus dans le rôle de sécurité **Opérateur des messages électroniques**. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Fonctionnalités réglementaires spécifiques au pays prises en charge par la fonctionnalité ME

Le tableau suivant fournit des informations sur certaines fonctionnalités réglementaires spécifiques au pays qui sont prises en charge par la fonctionnalité ME.

| Pays     | Nom de la fonction | Enregistrement de démonstration de fonctionnalité |
|-------------|--------------|------------------------|
| Espagne       | [Fourniture immédiate d'informations sur la TVA (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Hongrie     | [Système de facturation en ligne](../localizations/emea-hun-online-invoicing.md) | |
| Royaume-Uni | [Rendre la taxe numérique - Envoi de déclarations de TVA](../localizations/emea-gbr-mtd-vat-integration.md) | [Finance and Operations : Taxe numérique britannique - Déclaration de TVA dans Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Lituanie   | [Génération d'états i.SAF](../localizations/emea-ltu-isaf.md) | |
| Pologne      | [Déclaration de TVA avec registres (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance : registres d'audit de TVA SAF/JPK](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Pays-Bas | [Déclaration de TVA pour les Pays-Bas](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| République tchèque | [Déclaration de TVA](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brésil      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Russie      | [Déclaration de TVA](../localizations/rus-vat-declaration.md) | |
| Russie      | [Génération d’états comptables au format électronique](../localizations/rus-accounting-reporting.md) | |
| Russie      | [Déclaration de taxe sur les bénéfices](../localizations/rus-profit-tax-declaration.md) | |
| Russie      | [Déclaration fiscale évaluée](../localizations/rus-assessed-tax-declaration.md) | |
| Russie      | [Déclaration de taxe au transport](../localizations/rus-transport-tax-declaration.md) | |
| Russie      | [Déclaration de l’impôt foncier](../localizations/rus-land-tax-declaration.md) | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

