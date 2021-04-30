---
title: Déclaration de retenue à la source pour l’Égypte
description: Cette rubrique explique comment configurer et générer les déclarations de retenue à la source pour l’Égypte.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e0d13a2de9acaa8b1c896e130b4dabb222e45dcb
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881420"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Déclaration de retenue à la source pour l’Égypte (EG-00005)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Vue d’ensemble
Cette rubrique explique comment configurer et générer la déclaration de retenue à la source et les formulaires 41 et 11 de déclaration de retenue à la source pour les entités juridiques en Égypte 

Toutes les entités égyptiennes doivent préparer le formulaire 41 qui récapitule toutes les taxes retenues des fournisseurs et des prestataires de services locaux. En plus du formulaire 41, le formulaire 11 doit être généré pour détailler toutes les retenues des fournisseurs étrangers. 

L’état **Déclaration de retenue à la source** dans Dynamics 365 Finance comprend les états suivants :

- Numéro du formulaire de déclaration 41
- Numéro du formulaire de déclaration 11
    
    
## <a name="prerequisites"></a>Conditions préalables
L’adresse principale de l’entité juridique doit être en Égypte.
Dans l’espace de travail **Gestion des fonctionnalités**, les fonctionnalités suivantes doivent être activées :

   - **Retenue à la source globale**

Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

1. Accédez à **Taxe** > **Paramétrage** > **Paramètres** > **Paramètres de comptabilité**, puis dans l’onglet **Retenue à la source** définissez l’option **Activer la retenue à la source globale** sur **Oui**.
2. Dans l’espace de travail **Gestion des états électroniques**, importez les formats de gestion des états électroniques suivants à partir du référentiel :

    - Déclaration de WHT Excel (EG)

    > [!NOTE]
    > Le format ci-dessus est basé sur le **Modèle de déclaration fiscale** et utilise la **Mise en correspondance des modèles de déclaration fiscale**. Cette configuration supplémentaire est automatiquement importée.

Pour plus d’informations sur la manière d’importer des configurations de gestion des états électroniques, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Télécharger des configurations de gestion des états électroniques

La mise en œuvre des formulaires de déclaration de WHT pour l’Égypte est basée sur des configurations de gestion des états électroniques (ER). Pour plus d’informations sur les fonctionnalités et les concepts de la gestion des états, voir [Gestion des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Pour les environnements de production et de test d’acceptation par l’utilisateur (UAT), suivez les instructions de la rubrique [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Pour générer les déclarations de retenue dans une entité juridique égyptienne, vous devez télécharger les configurations suivantes :

- Déclaration fiscale version model.version.82.xml ou version ultérieure
- Déclaration fiscale version model mapping.version.82.133.xml ou version ultérieure
- Déclaration de WHT Excel (EG).version.82.21 ou version ultérieure

Après avoir terminé le téléchargement des configurations ER à partir de Lifecycle Services (LCS) ou du référentiel global, procédez comme suit.

1. Accédez à l’espace de travail **Génération des états électronique** et sélectionnez la vignette **Configurations des états**.
1. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger > Charger depuis le fichier XML**.
1. Chargez tous les fichiers dans l’ordre dans lequel ils sont répertoriés dans les puces précédentes. Une fois toutes les configurations chargées, l’arborescence de configuration doit être présente dans Finance.

## <a name="set-up-application-specific-parameters"></a>Configurer des paramètres spécifiques à l’application

L’option des paramètres spécifiques à l’application permet aux utilisateurs d’établir les critères de classement et de calcul des transactions de taxe dans chaque ligne d’un rapport généré en fonction de la configuration du **groupe d’articles de retenue à la source** ou d’autres critères établis dans la définition de la recherche.

Le formulaire 41 de déclaration de retenue à la source comprend une colonne spécifique dans laquelle la transaction de retenue à la source doit être classée conformément à la classification des autorités fiscales nommée **Type de code de remise**. Au lieu d’inclure ces nouvelles classifications en tant que nouvelles données d’entrée lorsque les transactions sont validées, les classifications seront déterminées en fonction des différentes recherches introduites dans **Configurations** > **Configurer les paramètres spécifiques à l’application** > **Paramétrage** pour répondre aux exigences des états de retenue pour l’Égypte. 

La configuration suivante permet de classer les transactions dans l’état du formulaire 41 de déclaration de retenue :

- **DiscountTaxTypeLookup** -> Colonne n° 18 

Procédez comme suit pour configurer les différentes recherches utilisées pour générer la déclaration de WHT et les états de registres associés. 

1. Dans l’espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** > **Paramétrage** pour configurer les règles d’identification du classement des transactions dans l’état déclaration de WHT. 
2. Sélectionnez la version actuelle et, sur le raccourci **Recherches**, sélectionnez le nom de la recherche. Par exemple, **DiscountTaxTypeLookup**. Cette recherche identifie la liste des types de remise requis par l’administration fiscale.
3. Sur le raccourci **Conditions**, sélectionnez **Ajouter** et, dans la nouvelle ligne dans la colonne **Résultat de la recherche**, sélectionnez la ligne associée qui représente la classification dans la **Colonne 18**.
4. Dans la colonne **Groupe d’articles de retenue à la source**, sélectionnez le code associé utilisé pour identifier la classification. Par exemple, **Remise autorisée**.  
5. Répétez les étapes 3 et 4 pour toutes les recherches disponibles.
6. Sélectionnez **Ajouter** à nouveau pour inclure la ligne d’enregistrement finale, et dans la colonne **Résultat de la recherche**, sélectionnez **Non applicable**. 
7. Dans les colonnes restantes, sélectionnez **Non vide**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Définir les paramètres de comptabilité

Pour générer les états du formulaire de déclaration de WHT dans Microsoft Excel, définissez un format ER sur la page **Paramètres de Comptabilité**.

1. Accédez à **Taxe** > **Paramétrage** > **Paramètres de comptabilité**.
2. Sur l’onglet **Retenue à la source**, dans le champ **Mise en correspondance des formats de déclaration de WHT**, sélectionnez **Déclaration de WHT Excel (EG)**. Si vous laissez le champ vide, l’état de taxe standard sera généré au format SSRS.


![Formulaire de déclaration](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Générer les formulaires de déclaration de retenue
Le processus de préparation et d’envoi d’un formulaire de déclaration de retenue pour une période spécifique est basé sur les transactions de retenue à la source validées pendant la tâche de règlement et de validation de la taxe. Pour plus d’informations sur la retenue à la source globale, voir [Retenue à la source globale](../general-ledger/global-withholding-tax-overview.md).

Effectuez les étapes de configuration suivantes pour générer l’état de déclaration de taxe.

1. Accédez à **Taxe** > **Déclarations** > **Retenue à la source** > **Paiement de la retenue à la source*.
2. Sélectionnez la période de règlement, puis sélectionnez la date de début de l’état. 
3. Entrez la date de transaction, puis sélectionnez **OK**.
4. Dans la boîte de dialogue qui s’ouvre, sélectionnez un ou plusieurs types de formulaires **Formulaire N° 41**, **Formulaire N° 11** ou **Aucun**. Si vous sélectionnez **Aucun**, l’état standard est généré. 
5. Sélectionnez la langue. Tous les états sont traduits en **en-us** et en **ar-eg**.
6. Entrez la branche et le nom de la banque où le paiement de la taxe sera payé.
7. Sélectionnez le type d’entreprise, puis saisissez les numéros de vérification et de document. 
8. Saisissez le type d’entité. 
9. Saisissez le nom de la personne inscrite afin que le formulaire lui soit attribué et sélectionnez **OK** pour confirmer la génération de l’état. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
