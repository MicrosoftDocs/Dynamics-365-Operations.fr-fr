---
title: "Fonctionnalités obsolètes"
description: "Cette rubrique décrit les fonctions qui ont été supprimées, ou qu&quot;il est prévu de supprimer, de Dynamics 365 for Operations. Elle répertorie également les fonctions qui ont été supprimées dans les versions de Dynamics AX 7.0."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: e9ba7239b9ff8b9b97c9dabc06fb2c68760d19d4
ms.lasthandoff: 03/31/2017


---

# <a name="deprecated-features"></a>Fonctionnalités obsolètes

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer, de Dynamics 365 for Operations. Elle répertorie également les fonctions qui ont été supprimées dans les versions de Dynamics AX 7.0.

<a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Fonctionnalités qui sont devenues obsolètes dans Dynamics 365 for Operations 1611 avec la mise à jour de plateforme 3
---------------------------------------------------------------------------------------------

### <a name="aeb-payment-formats-for-spain"></a>Formats de paiement AEB pour l'Espagne

Les formats de paiement Consejo Superior Bancario sont utilisés pour envoyer des fichiers de remise à la banque pour les paiements client et les paiements fournisseur. Le contenu de ces formats est déterminé par Asociación Española de Banca. Cela concerne Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                                  |
| Remplacé par une autre fonctionnalité ? | Oui, les formats de transfert du crédit ISO20022 et de paiement de débit direct pour l'Espagne |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Les transferts de paiements bancaires pour la Lithuanie

Les transferts de paiements bancaires sont générés et imprimés au moyen du format d'exportation de transfert de paiement (LT) pour la Lituanie. Le marché lithuanien a commencé à utiliser le LITAS, le système bancaire électronique unifié, en 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                    |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour la Lituanie |
| Modules concernés             | Module Comptabilité fournisseur                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Les formats de paiement BBS Direkte Remittering pour la Norvège

Les formats de paiement BBS Direkte Remittering incluent l'exportation de collecte des paiements client (débit) et l'importation de message de retour.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                                                                                                                        |
| Remplacé par une autre fonctionnalité ? | Le format de paiement client AvtaleGiro pour la Norvège peut être utilisé pour générer des messages de débit direct. L'importation de message de retour sera implémentée dans les versions futures. |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Outil de plan de comptes pour l'Espagne

Cet outil est utilisé lorsqu'un plan de comptes en Espagne nécessite des modifications importantes. Les utilisateurs peuvent importer un nouveau plan de comptes dans Microsoft Excel ou au format de texte, et peuvent également importer des tableaux d'analyse.

|                              |                |
|------------------------------|----------------|
| Motif de la suppression       | Utilisation limitée  |
| Remplacé par une autre fonctionnalité ? | Non             |
| Modules concernés             | Comptabilité |

### <a name="dom80-payment-format-for-belgium"></a>Format de paiement Dom80 pour la Belgique

Le format de paiement belge hérité pour la collecte de paiement (débit direct).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                  |
| Remplacé par une autre fonctionnalité ? | Oui, le format de paiement de débit direct ISO 20022 pour la Belgique |
| Modules concernés             | Module Comptabilité client                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formats de paiement DTA/EZAG pour la Suisse

Les formats DTA/EZAG sont intégrés dans le système ESR car ils peuvent conserver le numéro de référence. Du fait que les numéros de référence ne sont pas obligatoires, ces formats peuvent être utilisés pour traiter tous les paiements fournisseur. Ces formats sont utilisés par les sociétés qui ont un compte bancaire à un emplacement autre que « Postfinance ».

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                      |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour la Suisse |
| Modules concernés             | Module Comptabilité fournisseur                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Format de paiement EDIFACT-DIRDEB pour l'Autriche

Le format de paiement EDIFACT-DIRDEB pour la collecte de paiement (débit direct).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                  |
| Remplacé par une autre fonctionnalité ? | Oui, le format de paiement de débit direct ISO 20022 pour l'Autriche |
| Modules concernés             | Module Comptabilité client                                    |

### <a name="edivat-for-belgium"></a>EDIVAT pour la Belgique

EDIVAT est une norme belge obsolète pour la déclaration électronique via courrier sécurisé. Microsoft Dynamics AX 2012 conserve la solution en lecture seule pour permettre l'accès aux données historiques.

|                              |                                      |
|------------------------------|--------------------------------------|
| Motif de la suppression       | La fonctionnalité n'est plus utilisée. |
| Remplacé par une autre fonctionnalité ? | Non                                   |
| Modules concernés             | Comptabilité                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Format d'importation de paiements eGiro EDIFACT CREMUL pour la Norvège

eGiro s'appuie sur la norme internationale EDIFACT CREMUL (Avis de crédit multiple) standard, utilisée pour la validation automatique des paiements client. Dans Microsoft Dynamics AX, eGiro est implémenté comme format d'importation de paiements client.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                                                     |
| Remplacé par une autre fonctionnalité ? | Non. Le format sera remplacé par les formats d'importation des relevés ISO 20022 dans les versions futures. |
| Modules concernés             | Module Comptabilité client                                                                       |

### <a name="external-inventory-for-poland"></a>Stock externe pour la Pologne

Preuve des marchandises prises d'un fournisseur pour les ventes sans achat. Marchandises gérées dans le stock externe, n'affectant pas le stock standard, qui peuvent être vendues puis achetées automatiquement. Ce processus crée de vrais mouvements de stock.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Motif de la suppression       | Remplacé par une autre fonction                     |
| Remplacé par une autre fonctionnalité ? | Oui, la fonctionnalité de consignation entrante de base |
| Modules concernés             | Comptabilité fournisseur, Gestion des stocks          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Générateur d'états financiers pour l'Europe de l'Est

Un outil est utilisé pour paramétrer la collecte des informations pour la comptabilité et les états fiscaux et pour exporter le données vers les modèles d'état XLS et DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Motif de la suppression       | Utilisation limitée                                                                            |
| Remplacé par une autre fonctionnalité ? | Non. L'outil sera remplacé par des configurations de génération d'états électroniques dans les versions futures. |
| Modules concernés             | Comptabilité                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importation des transactions de paiement client pour la Finlande

Vous pouvez sélectionner un format d'importation pour les paiements finlandais pour importer des transactions de paiement client à partir d'un fichier externe fourni par la banque.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                                                     |
| Remplacé par une autre fonctionnalité ? | Non. Le format sera remplacé par les formats d'importation des relevés ISO 20022 dans les versions futures. |
| Modules concernés             | Module Comptabilité client                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importation des transactions de paiement dans un journal de comptabilité pour la Finlande

Un format qui est spécifique à la Finlande est utilisé pour importer les transactions comptables dans la comptabilité.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                                                     |
| Remplacé par une autre fonctionnalité ? | N° Le format sera remplacé par les formats d'importation des relevés ISO 20022 dans les versions futures. |
| Modules concernés             | Module Comptabilité client                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>L'intégration à Isabel synchronized (CIS) pour la Belgique

Isabel est le cadre des opérations bancaires électroniques en Europe et une norme de facto en Belgique.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | L'intégration avec le client Isabel est devenue obsolète.                                                                |
| Remplacé par une autre fonctionnalité ? | Non. Les formats de paiement qui ne sont plus utilisés sont remplacés par le format de paiement de transfert de crédit ISO20022 pour la Belgique. |
| Modules concernés             | Module Comptabilité fournisseur                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modifications dans le plan de comptes et les règles comptables pour l'Espagne

Cette fonctionnalité est utilisée pour les modifications apportées au plan de comptes et aux règles comptables en Espagne. Elle mappe les comptes pour aider à transformer l'ancien plan de comptes en nouveau plan de comptes, et compare l'exercice précédent au nouvel exercice, même s'ils ont été validés à des numéros de compte distincts.

|                              |                |
|------------------------------|----------------|
| Motif de la suppression       | Utilisation limitée  |
| Remplacé par une autre fonctionnalité ? | N°             |
| Modules concernés             | Comptabilité |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Format de paiement fournisseur Pagamento Fornittori

Format de paiement italien hérité pour les transferts de crédit.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motif de la suppression       | Le format de paiement n'est plus utilisé.                  |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour l'Italie |
| Modules concernés             | Module Comptabilité fournisseur                                       |

### <a name="payment-export-formats-for-estonia"></a>Formats d'exportation de paiement pour l'Estonie

Les formats Telehansa et Teleservice sont utilisés pour l'exportation de paiements bancaires.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                  |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour l'Estonie |
| Modules concernés             | Module Comptabilité fournisseur                                         |

### <a name="payment-file-archive-for-norway"></a>Archive de fichier de paiement pour la Norvège

Lorsque des fichiers de paiement sont générés, l'archive du fichier archive automatiquement tous les fichiers créés, même les fichiers enregistrés ou lus précédemment.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Motif de la suppression       | Remplacé par une autre fonction                                        |
| Remplacé par une autre fonctionnalité ? | Oui, les tâches de gestion des états électroniques archivées                            |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client, Administration d'organisation |

### <a name="payment-import-formats-for-estonia"></a>Formats d'importation de paiement pour l'Estonie

Les formats Telehansa et TeleTeenus sont utilisés pour l'importation de paiements bancaires.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                                                    |
| Remplacé par une autre fonctionnalité ? | Non. Les formats seront remplacés par les formats d'importation des relevés ISO 20022 dans les versions futures. |
| Modules concernés             | Module Comptabilité client                                                                        |

### <a name="performance-management-goal-workflow"></a>Workflow de l'objectif de gestion des performances

La gestion des performances inclut la gestion et l'intégration d'objectifs incluant des entretiens d'évaluation des performances.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La gestion des performances a été remodelée, et le nombre de pages d'objectifs a été réduit pour simplifier le processus.                 |
| Remplacé par une autre fonctionnalité ? | Non. Les objectifs sont visibles des responsables via le portail en libre-service pour responsables, qui peuvent être changés et affichés par le responsable. |
| Modules concernés             | Gestion du capital humain                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formats de paiement Postgirot et Postgirot Utland pour la Suède

Formats de paiement Postgirot et Postgirot Utland pour la Suède.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                 |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour la Suède |
| Modules concernés             | Module Comptabilité fournisseur                                        |

### <a name="radio-frequency-identifier"></a>Identification par radiofréquence

L'identification par radio-fréquence (RFID) est une technologie de collecte de données utilisant des balises électroniques pour stocker des données d'identification et un lecteur sans exigence de visibilité directe pour les capturer.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Motif de la suppression       | Faible utilisation de la part des clients et ensemble de fonctionnalités limité. |
| Remplacé par une autre fonctionnalité ? | Non                                            |
| Modules concernés             | Gestion des stocks                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>État sur la numérotation des factures d'état pour la Lettonie

La législation lettone impose des règles spécifiques sur la numérotation des factures. La fonctionnalité permet d'affecter des numéros spécifiques aux factures client, selon l'utilisateur ou le groupe d'utilisateurs. Vous pouvez ensuite générer un état ou un fichier XML. Vous pouvez également imprimer un état sur les numéros de facture qui sont utilisés.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La numérotation de facture d'état ne doit plus être mise à jour. L'état sur les numéros de facture utilisés n'est plus nécessaire. |
| Remplacé par une autre fonctionnalité ? | N°                                                                                                                       |
| Modules concernés             | Module Comptabilité client                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Paramétrez le nom du responsable et du comptable général d'une société pour la Lithuanie

Les noms du responsable et du comptable général d'une société peuvent être spécifiés dans les informations sur la société et utilisés dans différentes impressions locales d'état.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Motif de la suppression       | Remplacé par une autre fonction                                     |
| Remplacé par une autre fonctionnalité ? | Oui, le paramétrage des officiels peut être utilisé pour le même objectif.   |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client, Gestion de la trésorerie et de la banque |

### <a name="telepay-payment-formats-for-norway"></a>Formats de paiement Telepay pour la Norvège

Les formats de paiement Telepay incluent l'exportation de paiement fournisseur (transfert de crédit) et la collecte de paiement client (débit direct).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                                                        |
| Remplacé par une autre fonctionnalité ? | Oui, le format de paiement de transfert de crédit ISO20022 et le format de paiement client AvtaleGiro pour la Norvège |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Formats d'exportation de paiement fournisseur pour la Finlande

Deux formats pour exporter les paiements sont disponibles pour la Finlande. LM02 (FI) est utilisé pour les paiements locaux, et LUM2 (FI) est utilisé pour les paiements étrangers.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motif de la suppression       | Les formats de paiement ne sont plus utilisés.                  |
| Remplacé par une autre fonctionnalité ? | Oui, le format de virement bancaire ISO20022 pour la Finlande |
| Modules concernés             | Module Comptabilité fournisseur                                         |

### <a name="workflow-for-creating-goals"></a>Workflow pour créer des objectifs

Un workflow pour la gestion de la création des objectifs de l'employé est l'un des workflows disponibles pour faciliter la coordination du processus de gestion des performances.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La gestion des performances a été complètement remodelée dans Microsoft Dynamics 365 for Operations.                                                                                                                                                                                                                                        |
| Remplacé par une autre fonctionnalité ? | La fonction de gestion des performances remodelée donne plus de contrôle sur le contenu des objectifs, les mesures utilisées pour suivre la progression, et l'association des documents associés. Les objectifs peuvent être stockés comme des modèles pour être réutilisés. Cette fonction peut vous aider à paramétrer des objectifs supplémentaires pour vos employés plus rapidement. |
| Modules concernés             | Gestion du capital humain                                                                                                                                                                                                                                                                                                               |

## <a name="features-deprecated-in-dynamics-ax-70-releases"></a>Fonctions obsolètes dans les versions de Dynamics AX 7.0
### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Possibilité d'annuler les modifications apportées à une facture fournisseur

|                              |                         |
|------------------------------|-------------------------|
| Motif de la suppression       | Améliorations des performances |
| Remplacé par une autre fonctionnalité ? | Non                      |
| Modules concernés             | Module Comptabilité fournisseur        |

### <a name="aif-axd-and-axbc-integrations"></a>Intégration d'AIF, AxD et AxBC

Dans l'environnement d'intégration applicative (AIF), les données peuvent être échangées avec les systèmes externes via une logique métier exposée en tant que service. Dynamics AX inclut des services basés sur des documents et sur .NET Business Connector (AxBC). Un document est créé à l'aide de XML. XML inclut des informations d'en-tête qui sont ajoutées pour créer un *message* qui peut être transféré ou extrait de Dynamics AX. Parmi les exemples de documents on trouve les commandes client et les commandes fournisseur. Toutefois, pratiquement n'importe quelle entité (un client par exemple), peut être représentée par un document. Les services basés sur des documents utilisent les classes **Axd&lt;*Document*&gt;** .

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | L'architecture d'AIF et d'AxDs ne pouvait pas être mise à l'échelle vers un service cloud. Il y avait des problèmes de performances avec l'importation en bloc.                                                                               |
| Remplacé par une autre fonctionnalité ? | Dans la version actuelle de Dynamics AX, cette fonctionnalité est remplacée par l'environnement d'importation/exportation des données, qui prend en charge l'importation/exportation en bloc récurrente. Pour AxBC, il est recommandé d'utiliser les tables réelles. |
| Modules concernés             | AxDs, AxBCs et AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>Nomenclatures sans versions de nomenclature

Si la clé de configuration des **versions de nomenclature** a été désactivée, les versions de nomenclature (BOM) ont été masquées dans tous les écrans, et le système a forcé une relation 1 à 1 entre les produits et les nomenclatures. Dans la version actuelle de Dynamics AX, la clé de configuration des **versions de nomenclature** ne peut pas être désactivée.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Motif de la suppression       | L'utilisation d'une clé de configuration pour contrôler les versions de nomenclature n'effectue pas de mise à l'échelle dans un environnement cloud. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                      |
| Modules concernés             | Gestion des informations sur les produits, Gestion des stocks                                    |

### <a name="brazilian-bordero"></a>Bordero brésilien

Mode de paiement spécifique aux sociétés brésiliennes

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La prise en charge du mode de paiement du Bordero brésilien est devenue obsolète dans la localisation brésilienne |
| Remplacé par une autre fonctionnalité ? | N°                                                                                                    |
| Modules concernés             | Module Comptabilité fournisseur                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Relevé Sintegra brésilien

Déclaration de taxe fédérale pour la taxe ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Ce relevé ne s'applique plus dans certains états brésiliens.                                                     |
| Remplacé par une autre fonctionnalité ? | Non. Les utilisateurs peuvent utiliser l'outil de génération d'états électroniques génériques pour configurer le relevé si nécessaire dans des situations spécifiques. |
| Modules concernés             | Registres fiscaux                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Mode de secours NF-e SCAN brésilien

L'environnement de secours (SCAN) permet de générer, d'exporter, et d'importer le statut d'un Nota Fiscal eletrônica (NF-e) lorsque l'environnement du Secretaria da Fazenda (SEFAZ) n'est pas disponible.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Motif de la suppression       | Cette méthode de secours ne s'applique plus dans tous les états brésiliens |
| Remplacé par une autre fonctionnalité ? | N°                                                                          |
| Modules concernés             | Module Comptabilité client                                                         |

### <a name="business-analyzer"></a>Business Analyzer

Cette application mobile permet aux utilisateurs d'examiner les indicateurs clés de l'entreprise.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Cette fonctionnalité a été remplacée par une autre.                                                                                                      |
| Remplacé par une autre fonctionnalité ? | Le pack de contenu Surveiller les performances financières pour Microsoft Power BI va inclure des mesures financières clés qui étaient précédemment disponibles dans le Business Analyzer. |
| Modules concernés             | Comptabilité                                                                                                                                                |

### <a name="business-statistics"></a>Statistiques commerciales

Paramétrage des requêtes de statistiques commerciales qui peut aider à analyser les performances de l'organisation

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Motif de la suppression       | Approche héritée de la BI (Business Intelligence), faible utilisation de la part des clients et ensemble de fonctionnalités limité |
| Remplacé par une autre fonctionnalité ? | Nouvelles solutions de BI pour la version actuelle de Dynamics AX                                      |
| Modules concernés             | Approvisionnements, Comptabilité fournisseur, Ventes et marketing, Comptabilité client         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Modifier la fonction de date de document de modification dans le journal des approbations de facture

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Motif de la suppression       | Faible utilisation                                                               |
| Remplacé par une autre fonctionnalité ? | Oui. La date de document de la transaction fournisseur validée peut être modifiée. |
| Modules concernés             | Module Comptabilité fournisseur                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Format de paiement ClieOp03 pour les Pays-Bas

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format ne s'applique plus aux Pays-Bas, car il a été remplacé par la fonctionnalité SEPA. |
| Remplacé par une autre fonctionnalité ? | Exportation des paiements SEPA                                                                                       |
| Modules concernés             | Tout                                                                                                        |

### <a name="compliance-center"></a>Centre de conformité

Le Centre de conformité est un site Enterprise Portal pour gérer les besoins en matière de documentation pour des initiatives de conformité liées à la législation de Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Peu utilisé par les clients. Microsoft SharePoint inclut la même capacité que celle qui était disponible dans le Centre de conformité. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                     |
| Modules concernés             | Conformité et contrôles internes                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connecteur pour Microsoft Dynamics

Cet outil était utilisé pour faire passer des données clés de Microsoft Dynamics CRM vers les candidatures Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motif de la suppression       | Cette fonctionnalité a été remplacée par une autre. |
| Remplacé par une autre fonctionnalité ? | Dynamics Integrator                                      |
| Modules concernés             | Connecteur pour Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unité de conteneur et stock disponible multidimensions

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Fonctionnalité en double                                                                                                                                         |
| Remplacé par une autre fonctionnalité ? | Oui. Depuis AX 2012, cette fonctionnalité a été remplacée par les fonctionnalités des lots de production consolidés. Ces fonctionnalités incluent l'affichage disponible consolidé. |
| Modules concernés             | Gestion des informations sur les produits, Contrôle de la production, Gestion des stocks, Ventes et marketing                                                                   |

### <a name="cue-group-metadata"></a>Métadonnées de groupe de files d'attente

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les groupes de files d'attente étaient utilisés pour afficher une ou plusieurs files d'attente dans la zone de récapitulatif. L'utilisation était limitée et il y avait également des soucis de performances, car une modification d'enregistrement dans un écran parent entrainait une requête par file d'attente dans le groupe des files d'attente. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                                                                                                                            |
| Modules concernés             | Tout                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Métadonnées de files d'attente

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les métadonnées de files d'attente étaient limitées aux informations de comptage ou de somme.                                                                                                                                                                                   |
| Remplacé par une autre fonctionnalité ? | Les métadonnées de mosaïque ont été introduites pour fournir plus de flexibilité pour la modélisation. Par exemple, vous pouvez modéliser les comptes actuels, la navigation, et les indicateurs de performance clés (KPI). Les métadonnées de mosaïque de compte remplacent directement les métadonnées de files d'attente. |
| Modules concernés             | Tout                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Format de chèque danois

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La prise en charge du format de chèque danois a été abandonnée, et l'état a été supprimé de la localisation DK. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                      |
| Modules concernés             | Tout                                                                                                                     |

### <a name="data-partitions"></a>Partitions de données

Les partitions de données fournissent une séparation logique des données dans la base de données Microsoft Dynamics AX.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les partitions de données ont été introduites dans Microsoft Dynamics AX 2012 R2 pour permettre l'isolement des données. Dans un scénario courant, une société possède des filiales, et les données d’une filiale ne doivent pas être visibles d'une autre filiale, même si les deux filiales sont gérés par le même service informatique. Toutefois, des scripts supplémentaires et du temps système de gestion tout au long du programme ont été requis afin de créer des partitions et de les remplir avec des données et pour sauvegarder les données de la partition. Dans le cloud, sur lequel nous avons accès aux services de base de données PaaS (Platform as a Service) (base de données Microsoft Azure SQL), il est beaucoup plus efficace d’utiliser une base de données en tant que conteneur d’isolation que de faire de l’isolation dans le programme. Même si le partitionnement des données est requis pour les filiales, pour plusieurs locataires ou juste pour une mise à l'échelle, nous pensons que les scénarios peuvent être mieux gérés par l’intermédiaire de plusieurs bases de données ou de plusieurs instances de Dynamics AX. |
| Remplacé par une autre fonctionnalité ? | Les partitions de données seront remplacées par l’intermédiaire de la prise en charge de plusieurs bases de données ou instances de Dynamics AX dans une version ultérieure.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Modules concernés             | Tout                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### <a name="delimitation"></a>Délimitation

|                              |                                        |
|------------------------------|----------------------------------------|
| Motif de la suppression       | Aucune utilisation de la fonctionnalité n'a été trouvée. |
| Remplacé par une autre fonctionnalité ? | Non                                     |
| Modules concernés             | Pointage                    |

### <a name="desktop-client"></a>Client du Bureau

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | L'expérience du client Dynamics AX a été remodelée pour améliorer la facilité d'utilisation sur plusieurs plateformes et périphériques.                      |
| Remplacé par une autre fonctionnalité ? | Le nouveau client Web est basé sur les métadonnées de l'écran du bureau et le modèle de programmation qui a été modifié pour fournir une plateforme Web riche. |
| Modules concernés             | Tout                                                                                                                                    |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 néerlandais

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La fonctionnalité générique est désormais utilisée à la place de la fonctionnalité localisée.                                                                                                                                                                 |
| Remplacé par une autre fonctionnalité ? | Oui, cette fonctionnalité a été remplacée par la fonctionnalité Rapprochement bancaire avancé. En outre, l'implémentation de l'importation du relevé de compte camt.053 ISO20022 est prévue pour le journal des opérations diverses dans la prochaine mise à jour de Dynamics AX. |
| Modules concernés             | Tout                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL pour l'Allemagne)

Cette fonctionnalité fournit la sortie XBLR (eXtensible Business Reporting Language) prévue spécifiquement pour la taxonomie eBilanz allemande.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Peu utilisé par les clients                                                                                                                                                 |
| Remplacé par une autre fonctionnalité ? | Cette fonctionnalité n'a pas été remplacée par une autre fonctionnalité, mais plusieurs packages XBRL spécialisés qui fournissent la fonctionnalité XBRL étendue sont disponibles pour le marché allemand. |
| Modules concernés             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Client Enterprise Portal

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Une plateforme cliente unique a été fournie.                                                                                            |
| Remplacé par une autre fonctionnalité ? | Le nouveau client Web est basé sur les métadonnées de l'écran du bureau et le modèle de programmation qui a été modifié pour fournir une plateforme Web riche. |
| Modules concernés             | Tout                                                                                                                                    |

### <a name="environmental-sustainability"></a>Durabilité environnementale

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Motif de la suppression       | Faible utilisation de la part des clients et ensemble de fonctionnalités limité       |
| Remplacé par une autre fonctionnalité ? | Non                                                 |
| Modules concernés             | Module Conformité et contrôles internes, Comptabilité fournisseur |

### <a name="form-activex-and-managed-host-controls"></a>Écran Contrôles hôtes gérés et ActiveX

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les contrôles hôtes gérés et ActiveX sont basés sur le client de bureau obsolète.                                                                                                             |
| Remplacé par une autre fonctionnalité ? | L'infrastructure de contrôle extensible prend en charge les nouveaux contrôles basés sur HTML, CSS, et JavaScript, il s'agit d'un contrôle de première classe dans l'environnement Microsoft Visual Studio Tooling. |
| Modules concernés             | Tout                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Génération de notes préliminaires à l'aide d'un traitement par lots

La génération de notes préliminaires ne peut pas être effectuée à l'aide d'un traitement par lots mais peut toujours être effectuée par un utilisateur.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Il n'existe aucun écran pour maintenir et afficher le fichier de notes préliminaires lorsqu'il est généré à l'aide d'un traitement par lots. |
| Remplacé par une autre fonctionnalité ? | Les notes préliminaires peuvent toujours être générées, et l'utilisateur peut contrôler où le fichier est stocké.   |
| Modules concernés             | Comptabilité fournisseur, Comptabilité client, Gestion de la trésorerie et de la banque                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportation de paiement DTAUS et importation de relevé de compte allemands (totaux et transactions)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format ne s'applique plus en Allemagne, car il a été remplacé par la fonctionnalité Espace unique de paiement en euros (SEPA).                                                                                                                                                                 |
| Remplacé par une autre fonctionnalité ? | Oui, cette fonctionnalité a été remplacée par la fonctionnalité de rapprochement bancaire avancée et d'exportation de paiement SEPA pour importer les relevés de compte. En outre, l'implémentation de l'importation du relevé de compte camt.053 ISO20022 est prévue pour le journal des opérations diverses dans la prochaine mise à jour de Dynamics AX. |
| Modules concernés             | Tout                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Format de paiement DTAZV allemand

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format ne s'applique plus en Allemagne, car il a été remplacé par la fonctionnalité SEPA. |
| Remplacé par une autre fonctionnalité ? | Exportation des paiements SEPA                                                                               |
| Modules concernés             | Tout                                                                                                |

### <a name="german-mt940-import"></a>Importation du MT940 allemand

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La fonctionnalité générique est désormais utilisée à la place de la fonctionnalité localisée.                                                                                                                                                                 |
| Remplacé par une autre fonctionnalité ? | Oui, cette fonctionnalité a été remplacée par la fonctionnalité Rapprochement bancaire avancé. En outre, l'implémentation de l'importation du relevé de compte camt.053 ISO20022 est prévue pour le journal des opérations diverses dans la prochaine mise à jour de Dynamics AX. |
| Modules concernés             | Tout                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Liste des ventes intracommunautaires pour l'Allemagne (format XML)

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le format XML pour la génération d'états pour la Liste des ventes intracommunautaires pour l'Allemagne n'est plus pris en charge. Seul le format de fichier texte ELMA5 peut être utilisé pour envoyer la liste des ventes intracommunautaires à l'administration fiscale allemande. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                                                                                 |
| Modules concernés             | Taxes                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>États GL SSRS

Les états qui comprennent les options de menu suivantes ont été supprimés : **Synthèse de balance comptable****Balance comptable détaillée****Plan de comptes****Piste d'audit****Soldes** et **Liste des soldes**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les états financiers de Microsoft SQL Server Reporting Services (SSRS) ont été remplacés par des capacités et des états par défaut Management Reporter. |
| Remplacé par une autre fonctionnalité ? | Management Reporter (appelé **États financiers** dans la version actuelle de Dynamics AX)                                                  |
| Modules concernés             | Comptabilité                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>Métadonnées InfoPart et FormPart

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les métadonnées InfoPart et FormPart ont permis la création de récapitulatifs pour deux clients différents.                                                                                                                                    |
| Remplacé par une autre fonctionnalité ? | Les métadonnées InfoPart (une définition d'écran simplifiée) sont converties en écran par l'outillage de mise à niveau. Les métadonnées FormPart, qui référençaient un écran, sont remplacées par une référence plus directe créée par l'outillage de mise à niveau. |
| Modules concernés             | Tout                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Page de liste Compte principal

Liste des comptes pour l'entité juridique et les informations sur le solde associées

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les informations sur le solde sont disponibles dans la page **Balance comptable** par compte et dimension.                                                                                      |
| Remplacé par une autre fonctionnalité ? | La page **Comptes principaux** contient la même liste de comptes que la page de liste **Compte principal**. La vue grille dans **Comptes principaux** affiche également une vue plus petite, semblable à une grille. |
| Modules concernés             | Comptabilité                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>État sur les flux de trésorerie des banques de Malaisie et de Singapour

Cette fonctionnalité permet à un utilisateur d'imprimer un état sur les flux de trésorerie qui indique les transactions et les détails des encaissements et décaissements pour un intervalle de dates spécifique pour des comptes bancaires sélectionnés.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Motif de la suppression       | Les mêmes informations peuvent être obtenues à partir de la transaction bancaire Recherche. |
| Remplacé par une autre fonctionnalité ? | La transaction bancaire Recherche.                                            |
| Modules concernés             | Gestion de la trésorerie et de la banque                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Facture électronique CFD mexicaine

Cette fonctionnalité a permis la génération de factures électroniques mexicaines à l'aide de la méthode Comprobante Fiscal Digital (CFD), dans laquelle la société signe la facture en demandant l'autorisation associée d'une administration. Cette fonctionnalité fournit également un état mensuel qui inclut toutes les factures électroniques qui ont été émises dans la période.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La méthode ne s'applique plus. La génération de factures électroniques à l'aide de la méthode CFD a été abandonnée par les administrations fiscales et remplacée par la méthode Comprobante Fiscal Digital a través de Internet (CFDI), dans laquelle la signature est déléguée au fournisseur tiers (PAC). L'état mensuel a été supprimé, et une option de recherche permet aux utilisateurs d'en savoir plus sur les transactions historiques. |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                                                                                                                                                                                                                                                                                                        |
| Modules concernés             | Comptabilité client, Projet                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>TVA réalisées et non réalisées au Mexique

Microsoft Dynamics AX 2012 gérait la taxe sur la valeur ajoutée non réalisée (VAT) à l'aide de la fonctionnalité spécifique au Mexique pour « la taxe non réalisée ».

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Fonctionnalité en double                                                                                             |
| Remplacé par une autre fonctionnalité ? | Oui, cette fonctionnalité a été remplacée par la fonctionnalité de taxe sur les encaissements standard fournie par Core. |
| Modules concernés             | Taxes                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Intégration à Microsoft Outlook

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Motif de la suppression       | Cette fonctionnalité a été remplacée par l'intégration à Microsoft Exchange Server. |
| Remplacé par une autre fonctionnalité ? | Oui                                                                            |
| Modules concernés             | Ventes et marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Informations sur les salaires dans le module Ressources humaines

Informations sur les salaires dans Ressources humaines

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Cette fonctionnalité a été remplacée par les pages Paie et Ressources humaines principales.                                                                                                                                                                                                                                              |
| Remplacé par une autre fonctionnalité ? | Les pages **Avantages**, **Rémunérations**, et les autres pages associées qui étaient précédemment dans Paie États-Unis ont été reconfigurées et font désormais partie de la configuration du module Ressources humaines principal pour aider à prendre en charge le traitement externe de la paie. Cette fonctionnalité est accessible à l'aide de la clé de configuration **Ressources humaines 1** &gt; **Paie**. |
| Modules concernés             | Ressources humaines, Paie                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Blocage privé des journaux de gestion de stock et d'entrepôt.

Les journaux de gestion de stock et d'entrepôt ne prennent plus en charge la possibilité de marquer un journal comme privé pour un utilisateur sélectionné. Seul les processus de blocage des journaux comme privé pour des groupes d'utilisateurs et de blocage lors de la modification sont pris en charge.

|                              |                                        |
|------------------------------|----------------------------------------|
| Motif de la suppression       | Aucune utilisation de la fonctionnalité n'a été trouvée. |
| Remplacé par une autre fonctionnalité ? | Non                                     |
| Modules concernés             | Gestion des stocks                   |

### <a name="product-builder"></a>Configurateur

Le configurateur était utilisé pour la configuration dynamique d'articles à partir d'une commande client, d'une commande fournisseur, d'un ordre de fabrication, d'un devis de vente, d'un devis de projet ou d'une demande d'articles. En fonction d'un modèle de produit ayant des variables de modélisation, l'utilisateur pouvait sélectionner des valeurs pour répondre aux exigences des clients et pour obtenir une unique variante de produit qui avait une nomenclature et une gamme.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Le configurateur exposait du code X++ aux utilisateurs finaux et il n'est pas pris en charge dans la version actuelle de Dynamics AX. Il a été supprimé pour éviter les efforts de maintenance en double en matière de chevauchement et de codebases importants. |
| Remplacé par une autre fonctionnalité ? | Configuration de produit                                                                                                                                                                                   |
| Modules concernés             | Gestion d'informations sur les produits, Ventes et marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Renommer la dimension de produit

Cette fonctionnalité permet de remplacer le nom de l'une des trois dimensions de produit standard (taille, couleur ou style) par un nom convenant mieux aux exigences métier. Le fonctionnalité de changement de nom comprenait tous les libellés où le nom de la dimension de produit était utilisé.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Motif de la suppression       | La version actuelle de Dynamics AX ne prend pas en charge le changement de nom au moment de l'exécution. |
| Remplacé par une autre fonctionnalité ? | Non                                                                            |
| Modules concernés             | Gestion des informations sur les produits                                                |

### <a name="role-center-pages"></a>Pages d'Aperçu interactif

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Les pages d'aperçu interactif ont été établies sur la plateforme Enterprise Portal obsolète, qui a été remplacée par la nouvelle plateforme client Web dans la version actuelle de Dynamics AX. |
| Remplacé par une autre fonctionnalité ? | Le nouveau modèle d'écran de l'espace de travail offre aux utilisateurs un design orienté processus qui fournit un accès simple aux tâches utilisées couramment dans ce processus.                       |
| Modules concernés             | Tout                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Juridictions fiscales

|                              |                                              |
|------------------------------|----------------------------------------------|
| Motif de la suppression       | Faible utilisation de la part des clients et ensemble de fonctionnalités limité |
| Remplacé par une autre fonctionnalité ? | Non                                           |
| Modules concernés             | taxe U.S.                                 |

### <a name="shipping-carrier-interface"></a>Interface du transporteur

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Fonctionnalité en double                                                                                                                         |
| Remplacé par une autre fonctionnalité ? | Oui, cette fonctionnalité a été partiellement remplacée par la fonctionnalité Gestion de transport, mais n'a pas encore été remplacée par la fonctionnalité Gestion des entrepôts de base (WMS I). |
| Modules concernés             | Gestion des stocks, Ventes et marketing                                                                                                       |

### <a name="sites-services"></a>Services Sites

Sites Services vous permet de créer des sites Web qui étendent vos processus d'entreprise à Internet sans support informatique.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | L'infrastructure Microsoft Azure utilisée par Dynamics AX dispose des nouvelles capacités qui peuvent être utilisées à la place (par exemple, les sites Azure). |
| Remplacé par une autre fonctionnalité ? | Non                                                                                                                                       |
| Modules concernés             | Le recrutement RH, la gestion des incidents, les demandes de devis, enregistrement de fournisseur                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>Stratégie de prévision de la demande SSAS

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Motif de la suppression       | La conception de la fonctionnalité ne peut pas être prise en charge dans la nouvelle architecture de cloud. |
| Remplacé par une autre fonctionnalité ? | Stratégie de prévision de la demande Azure Machine Learning                           |
| Modules concernés             | Planification                                                                     |

### <a name="travel-requisitions"></a>Demandes de voyage

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Motif de la suppression       | Faible utilisation et la plupart des fonctionnalités existaient dans Enterprise Portal. |
| Remplacé par une autre fonctionnalité ? | Non                                                              |
| Modules concernés             | Gestion des dépenses                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Registre de factures fournisseur excluant les détails de validation

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Faible utilisation. Cette fonctionnalité a été remplacée par le journal des factures avec une fonctionnalité de workflow. |
| Remplacé par une autre fonctionnalité ? | Fonctionnalités de workflow du journal des factures.                                                           |
| Modules concernés             | Module Comptabilité fournisseur                                                                                        |

### <a name="virtual-company-accounts"></a>Comptes société virtuels

La fonctionnalité des sociétés virtuelles n'est plus prise en charge dans Dynamics AX. La fonctionnalité des sociétés virtuelles permet aux utilisateurs de paramétrer des tables à partager entre un ensemble de sociétés. Pour obtenir une description de la fonctionnalité, consultez [Comptes société et comptes société virtuels](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). La fonctionnalité fonctionne en regroupant les tables en recouvrements affectés aux sociétés virtuelles, qui sont des groupes de « véritables » sociétés existantes. Les requêtes sont créées afin que toutes les sociétés de la société virtuelle puissent accéder aux données des tables des recouvrements de table associés.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Motif de la suppression</td>
<td><ul>
<li>Les sociétés virtuelles doivent être définies avant que les données soient enregistrées dans les tables. Il est très difficile d'adapter des sociétés virtuelles dans une implémentation existante.</li>
<li>Comme il y a eu tellement de standardisation de données dans la version actuelle de Dynamics AX, il est devenu très difficile de savoir quoi ajouter aux ensembles de tables. Par exemple, il est difficile de savoir quelle table partager. Toutes les tables référencées à partir des tables qui sont dans une société virtuelle doivent également être ajoutées. Du fait de la standardisation des tables, même une diffusion de données principales entre une multitude de tables doit faire partie de la société virtuelle. Toute erreur faite ici provoquera des problèmes fonctionnels.</li>
<li>Lorsqu'une table fait partie d'une société virtuelle, elle perd les informations sur l'origine des données, et seule la société virtuelle est enregistrée.</li>
</ul></td>
</tr>
<tr class="even">
<td>Remplacé par une autre fonctionnalité ?</td>
<td>Les tables générales peuvent être utilisées pour rendre des tables accessibles à partir de toutes les sociétés. Actuellement, il n'existe aucune fonction de remplacement.</td>
</tr>
<tr class="odd">
<td>Modules concernés</td>
<td>Non applicable</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Gestion des entrepôts II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | La solution Gestion des entrepôts II (WMS II) qui était disponible dans le module **Gestion des stocks** duplique la fonctionnalité située dans le module **Gestion des entrepôts** qui a été lancée dans Microsoft Dynamics AX 2012 R3.                                                                         |
| Remplacé par une autre fonctionnalité ? | Le module **Gestion des entrepôts** qui a été lancé dans AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 et Dynamics AX 2012 R3 CU9 remplace les fonctionnalités de Gestion des entrepôts II. Le nouveau module a des fonctionnalités plus avancées et des processus de gestion des entrepôts plus flexibles que dans le module Gestion des entrepôts II. |
| Modules concernés             | Gestion des stocks, Ventes et marketing, Approvisionnements                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Rappels pour les travailleurs dans le module Ressources humaines

Informations sur les salaires dans Ressources humaines

|                              |                 |
|------------------------------|-----------------|
| Motif de la suppression       | Faible utilisation       |
| Remplacé par une autre fonctionnalité ? | Non              |
| Modules concernés             | Ressources humaines |

### <a name="workplanner"></a>Planificateur de travail

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motif de la suppression       | Faible utilisation                                                                                                                                                            |
| Remplacé par une autre fonctionnalité ? | Non, mais la page **Relation de profil**, qui est ouverte sur la page **Groupes de profils**, prend en charge le même scénario que la page **Workplanner** abandonnée. |
| Modules concernés             | Pointage                                                                                                                                                  |

### <a name="x-financial-statements"></a>Tableaux d'analyse X++

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Motif de la suppression       | Cette fonctionnalité a été remplacée par une autre.                                    |
| Remplacé par une autre fonctionnalité ? | Management Reporter (appelé **États financiers** dans la version actuelle de Dynamics AX) |
| Modules concernés             | Comptabilité                                                                              |




