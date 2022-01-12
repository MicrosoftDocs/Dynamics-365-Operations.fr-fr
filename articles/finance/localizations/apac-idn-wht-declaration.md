---
title: Déclaration de retenue à la source pour l’Indonésie
description: Cette rubrique explique comment configurer et générer les déclarations de retenue à la source pour l’Indonésie.
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6cf2f9240ea747054578c52343af34b15c250f38
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7943658"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Déclaration de retenue à la source pour l’Indonésie (ID-00005)

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer et générer le fichier de retenue à la source PPH que les entités juridiques indonésiennes utilisent pour déclarer les transactions de retenue à la source dans l’application e-Bupot.

L’administration fiscale indonésienne (DGT) détermine que les entrepreneurs imposables (PKP) qui sont enregistrés à KPP Pratama en tant que redevables/collecteurs de l’impôt sur le revenu (PPh) Article 23 et/ou Article 26 doivent déclarer électroniquement leur déclaration de revenus aux articles 23 et 26 en utilisant l’application e-Bupot. 

- **Article 23** – La déclaration inclut toutes les transactions de retenue des fournisseurs où le code de pays/région de l’adresse principale est le code pour l’Indonésie.
- **Article 26** – La déclaration inclut toutes les transactions de retenue des fournisseurs où le code de pays/région de l’adresse principale n’est pas le code pour l’Indonésie.

## <a name="prerequisites"></a>Conditions préalables

- L’adresse principale de l’entité juridique doit être en Indonésie.
- Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité **Retenue à la source globale** est activée. Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="download-electronic-reporting-configurations"></a>Télécharger des configurations de gestion des états électroniques

La génération d’un fichier d’import est basée sur des configurations de reporting électronique (ER). Pour plus d’informations sur les fonctionnalités et les concepts de la gestion des états, voir [Gestion des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Pour les environnements de production et de test d’acceptation par l’utilisateur (UAT), suivez les instructions dans [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Pour générer le fichier d’importation, téléchargez les configurations suivantes depuis le référentiel :

- **Déclaration fiscale version model.version.93.xml** ou version ultérieure
- **Déclaration fiscale version model mapping.version.93.153.xml** ou version ultérieure
- **Importation de schéma WHT PPh (ID).version.93.14** ou une version ultérieure

## <a name="set-up-general-ledger-parameters"></a>Définir les paramètres de comptabilité

1. Accédez à **Taxe** \> **Paramétrage** \> **Paramètres de comptabilité**.
2. Sur l’onglet **Retenue à la source**, dans le champ **Mise en correspondance des formats de déclaration de WHT**, sélectionnez **Importation du schéma de WHT PPh (ID)**. 
3. Aller à **Taxe** \> **Paramétrer** \> **Rà la source** \> **Types de revenus de retenue à la source** pour mettre en place le type de revenus de retenue à la source **Kode Bukti Potong**, puis affectez les codes aux groupes de retenue à la source d’article correspondants. Les codes sont nécessaires pour générer le fichier d’intégration en utilisant l’application e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Générer le fichier d’importation de retenue

Le processus de préparation et de génération d’un fichier e-Bupot pour une période spécifique est basé sur les transactions de retenue à la source validées pendant la tâche de règlement ou de validation de la taxe.

Pour générer des paiements, procédez comme suit.

1. Aller à **Taxe** \> **Déclarations** \> **Retenue à la source** \> **Fichier d’importation PPH e-bupot 23 et 26**.
2. Sélectionnez la "date de début" et la "date de fin" de la déclaration, puis sélectionnez la période de règlement.
3. Entrez la date de transaction, puis cliquez sur **OK**.
4. Sélectionnez la langue. Toutes les déclarations sont traduites en anglais américain (**en-us**) et en indonésien (**id**).
5. Sélectionnez le type d’entreprise, puis saisissez les numéros de vérification et de document. 
6. Vérifiez si la déclaration a été signée par le responsable. Ces informations sont déclarées dans le fichier. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
