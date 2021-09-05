---
title: Déclaration de TVA pour l’Égypte
description: Cette rubrique explique comment configurer et générer le formulaire de déclaration de TVA pour l’Égypte.
author: sndray
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a67c6e00b94d49b3eb279416407f603923e53b2e
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2021
ms.locfileid: "7403946"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Déclaration de TVA pour l’Égypte (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

Cette rubrique explique comment configurer et générer le formulaire de déclaration de TVA et les registres de ventes et d’achat pour les entités juridiques en Égypte.

Le formulaire de déclaration de TVA pour l’Égypte est le document officiel qui résume le montant total de la TVA d’aval dû, le montant total de la TVA d’amont récupérable et le montant du passif de la TVA associé. Le formulaire est utilisé pour tous les types de contribuables et doit être rempli manuellement via le portail de l’administration fiscale. Le formulaire de déclaration de TVA est communément appelé transmission de déclaration de TVA.

Le formulaire de déclaration de TVA dans Dynamics 365 Finance comprend les rapports suivants :

- Le formulaire de déclaration de TVA numéro 10, qui fournit une ventilation des montants, des ajustements et du montant de la TVA par poste dans le formulaire de déclaration de TVA, comme décrit dans la législation.
- Le registre des transactions de vente
- Le registre des transactions d’achat

## <a name="prerequisites"></a>Conditions préalables
L’adresse principale de l’entité juridique doit être en Égypte.
Dans l’espace de travail **Gestion des fonctionnalités**, activez les fonctionnalités suivantes :

   - (Égypte) Hiérarchie de catégories pour la déclaration de taxe sur les ventes et les achats.

Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Dans l’espace de travail **Gestion des états électroniques**, importez le format de gestion des états électroniques suivant à partir du référentiel :

- Déclaration de TVA Excel (EG)

> [!NOTE]
> Le format ci-dessus est basé sur le **Modèle de déclaration fiscale** et utilise la **Mise en correspondance des modèles de déclaration fiscale**. Des configurations supplémentaires seront automatiquement importées.

Pour plus d’informations sur la manière d’importer des configurations de gestion des états électroniques, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Télécharger des configurations de gestion des états électroniques

La mise en œuvre du formulaire de déclaration de TVA pour l’Égypte est basée sur des configurations de gestion des états électroniques (ER). Pour plus d’informations sur les fonctionnalités et les concepts de la gestion des états, voir [Gestion des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Pour les environnements de production et de test d’acceptation par l’utilisateur (UAT), voir [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Pour générer le formulaire de déclaration de TVA et les rapports associés dans une entité juridique égyptienne, téléchargez les configurations suivantes :

- Déclaration fiscale version model.version.70.xml ou version ultérieure
- Déclaration fiscale version model mapping.version.70.120.xml ou version ultérieure
- Déclaration de TVA Excel (EG).version.70.32 ou version ultérieure

Après avoir téléchargé les configurations ER à partir de Lifecycle Services (LCS) ou du référentiel global, procédez comme suit.

1. Accédez à l’espace de travail **Génération des états électronique** et sélectionnez la vignette **Configurations des états**.
1. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** > **Charger depuis le fichier XML**.
1. Chargez les fichiers dans l’ordre indiqué ci-dessus. Une fois toutes les configurations chargées, l’arborescence de configuration doit être présente dans Finance.

## <a name="set-up-application-specific-parameters"></a>Configurer des paramètres spécifiques à l’application

Les paramètres spécifiques à l’application vous permettent d’établir les critères de classement et de calcul des transactions fiscales dans chaque ligne lors de la génération du rapport. La détermination est basée sur la configuration du groupe de taxe d’article, du groupe de taxe, du code de taxe et d’autres critères établis dans la définition de recherche.

Les états de registre de vente et d’achat pour l’Égypte comprennent un ensemble de colonnes qui correspondent à des classifications de transactions spécifiques comme des types d’opérations, de produits et de documents spécifiques à l’Égypte. Au lieu d’inclure ces nouvelles classifications en tant que nouvelles données d’entrée lorsque les transactions sont validées, les classifications seront déterminées en fonction des différentes recherches introduites dans **Configurations** > **Configurer les paramètres spécifiques à l’application** > **Paramétrage** pour répondre aux exigences des états TVA pour l’Égypte. 

![Page Paramètres spécifiques à l’application.](media/egypt-vat-declaration-setup1.png)

Les configurations de recherche suivantes sont utilisées pour classer les transactions dans les états des registres de TVA d’achat et de vente :

- **PurchaseItemTypeLookup** > Colonne O : Type d’élément
- **VATRateTypeLookup** > Colonne B : Type de taxe
- **VATRateTypeLookup** > Colonne C : Type d’élément de table
- **PurchaseOperationTypeLookup** > Colonne A : Type de document
- **CustomerTypeLookup** > Colonne A : Type de document
- **SalesOperationTypeLookup** > Colonne N : Type d’opération
- **SalesItemTypeLookup** > Colonne O : Type d’élément

Procédez comme suit pour configurer les différentes recherches utilisées pour générer la déclaration de TVA et les états de registres associés. 

1. Dans l’espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** > **Paramétrage** pour configurer les règles d’identification de la transaction fiscale dans la case correspondante du formulaire de déclaration de TVA.
2. Sélectionnez la version actuelle et, sur le raccourci **Recherches**, sélectionnez le nom de la recherche. Par exemple, **SalesItemTypeLookup**. Cette recherche identifie la liste des classifications dans le registre de TVA de vente qui sont requises par l’administration fiscale.
3. Sur le raccourci **Conditions**, sélectionnez **Ajouter** et, dans la nouvelle ligne dans la colonne **Résultat de la recherche**, sélectionnez la ligne associée qui représente la classification dans **Colonne O**.
4. Dans la colonne **Groupe de taxe**, sélectionnez le groupe de taxe utilisé pour identifier la classification. Par exemple, **Facture de vente locale**. Vous pouvez également utiliser le groupe de taxe d’article, le code TVA ou la combinaison d’attributs d’arborescence si la configuration est définie d’une autre manière. 
5. Dans la colonne **Nom**, sélectionnez la classification de transaction de taxe.
6. Répétez les étapes 3 à 5 pour toutes les recherches disponibles.
7. Sélectionnez **Ajouter** pour inclure la ligne d’enregistrement finale, et dans la colonne **Résultat de la recherche**, sélectionnez **Non applicable**. 
8. Dans les colonnes restantes, sélectionnez **Non vide**. 
9. Dans le champ **État**, sélectionnez **Terminé**.
10. Sélectionnez **Enregistrer**, puis fermez la page **Paramètres spécifiques à l’application**.

> [!NOTE]
> Lorsque vous ajoutez le dernier enregistrement, **Non applicable**, vous définissez la règle suivante : lorsque le groupe de taxe, le groupe de taxe d’article, le code de taxe et le nom transmis en tant qu’argument ne satisfont à aucune des règles précédentes, les transactions ne sont pas incluses dans le registre de TVA. Bien que cette règle ne soit pas utilisée lors de la génération du rapport, la règle permet d’éviter les erreurs de génération de rapport en cas de configuration de règle manquante.

Les tableaux suivants représentent un exemple de configuration suggérée pour les configurations de recherche décrites. 

**SalesItemTypeLookup**

| Résultat de la recherche         | Ligne | Groupe de taxe de vente    | Groupe de taxe d’article    | Code taxe (Code) | Nom                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Local              | 1    | VAT_LOCAL          | *Non vide*             | *Non vide*     | Vente                 |
| Local              | 2    | VAT_LOCAL          | *Non vide*             | *Non vide*     | SalesCreditNote       |
| Local              | 3    | VAT_FINALC         | *Non vide*             | *Non vide*     | Vente                 |
| Local              | 4    | VAT_FINALC         | *Non vide*             | *Non vide*     | SalesCreditNote       |
| Local              | 5    | VAT_PUBLIO         | *Non vide*             | *Non vide*     | Vente                 |
| Local              | 6    | VAT_PUBLIO         | *Non vide*             | *Non vide*     | SalesCreditNote       |
| Exportation                | 7    | VAT_EXPORT         | *Non vide*             | *Non vide*     | Vente                 |
| Exportation                | 8    | VAT_EXPORT         | *Non vide*             | *Non vide*     | SalesCreditNote       |
| Machine et équipement | 9    | *Non vide*        | VAT_M&E                 | *Non vide*     | Vente                 |
| Machine et équipement | 10   | *Non vide*        | VAT_M&E                 | *Non vide*     | SalesCreditNote       |
| Machines avec pièces        | 11   | *Non vide*        | VAT_PARTS               | *Non vide*     | Vente                 |
| Machines avec pièces        | 12   | *Non vide*        | VAT_PARTS               | *Non vide*     | SalesCreditNote       |
| Exonérations            | 13   | VAT_EXE            | *Non vide*           | *Non vide*     | SaleExempt            |
| Exonérations            | 14   | VAT_EXE            | *Non vide*           | *Non vide*     | SalesExemptCreditNote |
| Non applicable        | 15   | *Blanc*            | *Blanc*                 | VAT_ADJ         | *Non vide*           |
| Non applicable        | 16   | *Non vide*        | *Non vide*             | *Non vide*     | *Non vide*           |

 **SalesOperationTypeLookup**

| Résultat de la recherche  | Ligne | Groupe de taxe d’article    | Code taxe    | Nom                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Marchandises          | 1    | VAT_GOODS               | *Non vide* | Vente                 |
| Marchandises          | 2    | VAT_GOODS               | *Non vide* | SalesCreditNote       |
| Marchandises          | 3    | VAT_GOODS               | *Non vide* | SaleExempt            |
| Marchandises          | 4    | VAT_GOODS               | *Non vide* | SalesExemptCreditNote |
| Services       | 5    | VAT_SERV                | *Non vide* | Vente                 |
| Services       | 6    | VAT_SERV                | *Non vide* | SalesCreditNote       |
| Services       | 7    | VAT_SERV                | *Non vide* | SaleExempt            |
| Services       | 8    | VAT_SERV                | *Non vide* | SalesExemptCreditNote |
| Ajustements    | 9    | *Blanc*                 | VAT_ADJ     | Vente                 |
| Ajustements    | 10   | *Blanc*                 | VAT_ADJ     | SalesCreditNote       |
| Non applicable | 11   | *Non vide*             | *Non vide* | *Non vide*           |

**PurchaseItemTypeLookup**

| Résultat de la recherche          | Ligne | Groupe de taxe d’article    | Code taxe    | Nom                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Marchandises                  | 1    | VAT_GOODS               | *Non vide* | Achats                 |
| Marchandises                  | 2    | VAT_GOODS               | *Non vide* | PurchaseCreditNote       |
| Services               | 3    | VAT_SERV                | *Non vide* | Achats                 |
| Services               | 4    | VAT_SERV                | *Non vide* | PurchaseCreditNote       |
| Machine et équipement  | 5    | VAT_M&E                 | *Non vide* | Achats                 |
| Machine et équipement  | 6    | VAT_M&E                 | *Non vide* | PurchaseCreditNote       |
| Machines avec pièces         | 7    | VAT_PARTS               | *Non vide* | Achats                 |
| Machines avec pièces         | 8    | VAT_PARTS               | *Non vide* | PurchaseCreditNote       |
| Exonérations             | 9    | VAT_EXE                 | *Non vide*  | PurchaseExempt           |
| Exonérations             | 10   | VAT_EXE                 | *Non vide* | PurchaseExemptCreditNote |
| Non applicable         | 11   | *Non vide*             | *Non vide* | *Non vide*              |

**PurchaseOperationTypeLookup**

| Résultat de la recherche  | Ligne | Groupe de taxe de vente  | Code taxe    | Nom                     |
|----------------|------|------------------|-------------|--------------------------|
| Local       | 1    | VAT_LOCAL        | *Non vide* | Achats                 |
| Local       | 2    | VAT_LOCAL        | *Non vide* | PurchaseCreditNote       |
| Local       | 3    | VAT_LOCAL        | *Non vide* | PurchaseExempt           |
| Local       | 4    | VAT_LOCAL        | *Non vide* | PurchaseExemptCreditNote |
| Importé       | 5    | VAT_IMPORT       | *Non vide* | Achats                 |
| Importé       | 6    | VAT_IMPORT       | *Non vide* | PurchaseCreditNote       |
| Importé       | 7    | VAT_IMPORT       | *Non vide* | PurchaseExempt           |
| Importé       | 8    | VAT_IMPORT       | *Non vide* | PurchaseExemptCreditNote |
| Ajustements    | 9    | *Blanc*          | VAT_ADJ     | PurchaseCreditNote       |
| Ajustements    | 10   | *Blanc*          | VAT_ADJ     | Achats                 |
| Non applicable | 11   | *Non vide*      | *Non vide* | *Non vide*              |

**CustomerTypeLookup**

|    Résultat de la recherche    | Ligne | Groupe de taxe de vente |
|---------------------|------|-----------------|
| Organisation        |  1   | VAT_LOCAL       |
| Organisation        |  2   | VAT_EXPORT      |
| Organisation        |  3   | VAT_EXE         |
| Consommateur final      |  4   | VAT_FINALC      |
| Organisation publique |  5   | VAT_PUBLIO      |
| Non applicable      |  6   | *Non vide*     |

**VATRateTypeLookup**

| Résultat de la recherche  | Ligne | Code taxe (Code) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Non vide*     |
| SecondTable    | 4    | *Non vide*     |
| Non applicable | 5    | *Non vide*     |


## <a name="set-up-general-ledger-parameters"></a>Définir les paramètres de comptabilité

Pour générer l’état du formulaire de déclaration de TVA au format Microsoft Excel, définissez un format ER sur la page **Paramètres de Comptabilité**.

1. Accédez à **Taxe** > **Paramétrage** > **Paramètres de comptabilité**.
2. Sur l’onglet **Taxe de vente**, dans la section **Options de taxe**, dans le champ **Mise en correspondance des formats de déclaration de TVA**, sélectionnez **Déclaration de TVA Excel (EG)**. Si vous laissez le champ vide, l’état de taxe standard sera généré au format SSRS.
3. Sélectionnez **Hiérarchie de catégories**. Cette catégorie active le code marchandise dans les transactions de l’onglet Commerce extérieur pour permettre aux utilisateurs de sélectionner et de classer les biens et services. La description de cette classification est détaillée dans les états de transaction de vente et d’achat. Cette configuration est facultative.

![Formulaire de déclaration.](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Générer un état de déclaration de TVA
Le processus de préparation et d’envoi d’un état de déclaration de TVA pour une période est basé sur les transactions de paiement de taxe qui ont été validées au cours de la tâche Régler et valider la taxe. Pour plus d’informations sur le règlement et la déclaration de la taxe, voir [Vue d’ensemble des taxes](../general-ledger/indirect-taxes-overview.md).

Effectuez les étapes de configuration suivantes pour générer l’état de déclaration de taxe.

1. Accédez à **Taxe** > **Déclarations** > **Taxe** > **État de la taxe pour la période de règlement** ou **Régler et valider la taxe**.
2. Sélectionnez la **période de règlement**.
3. Sélectionnez la date de début, puis sélectionnez la version de paiement de la taxe.
5. Cliquez sur **OK**. 
6. Entrez le montant du crédit de la période précédente, le cas échéant, ou laissez le montant à zéro.
7. Dans le champ **Détails du rapport**, sélectionnez l’une des options disponibles suivantes. 
   - **Registre de TVA d’amont** : Générez l’état des détails des transactions de taxe d’achat.
   - **Registre de TVA d’aval** : Générez l’état des détails des transactions de taxe de vente.
   - **Déclaration de TVA** : Générez uniquement le formulaire de déclaration de TVA.
8. Entrez le nom de la personne inscrite pour attribuer le formulaire.
9. Sélectionnez la langue. Tous les états sont traduits en **en-us** et en **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


