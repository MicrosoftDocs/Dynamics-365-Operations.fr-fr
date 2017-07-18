---
title: "Membres de la dimension statistique et modèles de fournisseur de mesures statistiques"
description: "Cette rubrique fournit des informations sur les membres de la dimension statistique et les modèles de fournisseur de modèles statistiques. Les membres de la dimension statistique peuvent être utilisés comme base de répartition dans les stratégies telles que la distribution et la répartition des coûts. Ils peuvent également être utilisés pour déclarer la consommation des coûts non monétaires."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 180863b5c3b8fe7870ab58f3849e52583f5880c1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Membres de la dimension statistique et modèles de fournisseur de mesures statistiques

[!include[banner](../includes/banner.md)]

Une dimension statistique et ses membres permettent d'enregistrer et de contrôler les entrées non monétaires dans le module Contrôle de gestion. Les membres de la dimension statistique peuvent être utilisés à deux fins :

- Comme base de répartition dans les stratégies telles que la distribution ou la répartition des coûts
- Pour la déclaration de la consommation non monétaire

## <a name="statistical-dimension"></a>Dimension statistique

Une dimension statistique a un nom unique et un ensemble unique de membres de dimension. La dimension statistique est affectée à un ID de comptabilité de contrôle de gestion. Cette relation lie tous les membres correspondants de la dimension statistique à la comptabilité de contrôle de gestion. Par conséquent, toutes les entrées statistiques seront créées dans le contexte de la comptabilité de contrôle de gestion.

> [!NOTE]
> Une dimension statistique peut être affectée à plusieurs comptabilités de contrôle de gestion.

Voici un exemple de dimension statistique.

| Nom                        | Connecteur de données pour les membres de la dimension |
|-----------------------------|--------------------------------------|
| Éléments statistiques partagés | Membres de la dimension importés           |

Voici un exemple de dimension statistique affectée à une comptabilité de contrôle de gestion.

| Nom                  | Devise comptable | Type de taux de change | Calendrier fiscal | Dimension d'élément de coût | Dimension statistique       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Comptabilité de gestion | USD                 | Devise constante  | Période fiscale   | Éléments de coût partagés   | Éléments statistiques partagés |

## <a name="statistical-dimension-members"></a>Membres de la dimension statistique

Un membre de la dimension statistique représente une entité pour laquelle vous souhaitez enregistrer des mesures non monétaires. Ces mesures peuvent être utilisées comme base de répartition ou simplement pour déclarer des valeurs non monétaires.

Les membres de la dimension statistique peuvent être créés manuellement. Ils peuvent également être importés à partir d'un fichier à l'aide de l'outil d'importation/exportation Gestion des données.

Un membre de la dimension statistique devient automatiquement une base de répartition prédéfinie. Il peut être utilisé comme base de répartition dans les stratégies ou comme entrée dans d'autres types de bases de répartition.

Voici quelques exemples de membres classiques de la dimension statistique.

| Nom de la dimension statistique  | Éléments statistiques | Description             | Unité |
|-----------------------------|----------------------|-------------------------|------|
| Éléments statistiques partagés | ETP                  | Employés à temps plein     | Ea.  |
| Éléments statistiques partagés | Électricité          | Consommation électrique | kWh  |
| Éléments statistiques partagés | CC emballage              | Centre de coût d'emballage   | Hrs. |

## <a name="statistical-measure-provider-template"></a>Modèle de fournisseur de mesures statistiques

Les mesures statistiques peuvent provenir de plusieurs types de sources. Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, est une importante source d'extraction de mesures statistiques. Vous pouvez utiliser un modèle de fournisseur de mesures statistiques pour configurer facilement les mesures statistiques que vous souhaitez extraire.

La définition d'un modèle de fournisseur de mesures statistiques est générique et peut être réutilisée dans plusieurs membres de la dimension statistique.

> [!NOTE]
> Toutes les tables qui contiennent des dimensions financières peuvent être utilisées comme sources pour les mesures statistiques.

**Exemple : nombre d'employés par centre de coût**

Le nombre d'employés par centre de coût est une mesure statistique qui peut être utilisée à différentes fins pour fournir des données de gestion :

- Mesure de déclarations statistiques par centre de coût
- Base de répartition pour différents types de dépenses
- Taux des coûts internes par centre de coût :

    - Coût par employé
    - Produit par employé

La table HcmEmployment contient la liste de tous les employés dans l'instance. Cette table est une table globale. Par conséquent, les enregistrements ne sont pas liés à un ID de zone de données spécifique.

Voici un exemple d'employés dans la table HcmEmployment.

| Nom       | Centre de coût | Description   | Type de collaborateur |
|------------|-------------|----|-------------|
| Employé 1 | CC001       | RH | Employé    |
| Employé 2 | CC002       | FI | Employé    |
| Employé 3 | CC002       | FI | Employé    |
| Employé 4 | CC003       | TS | Employé    |
| Employé 5 | CC003       | TS | Employé    |
| Employé 6 | CC002       | FI | Fournisseur  |

Lorsque vous créez un enregistrement **Modèle de fournisseur de mesures statistiques**, vous devez choisir quelle fonction utiliser :

- **Nombre** – Un nombre d'enregistrements par objet de coût est transféré.
- **Somme** – Une somme d'enregistrements par objet de coût est transférée. (Le champ **Somme** et le champ **Date** sont obligatoires.)

## <a name="using-the-count-function"></a>Utilisation de la fonction Nombre

Par exemple, un modèle de fournisseur de mesures statistiques peut être paramétré comme suit :

| Nom  | Fonction | Table source  | Champ de somme      | Champ de date     |
|-------|----------|---------------|----------------|----------------|
| ETP  | Nombre    | HcmEmployment | Non applicable | Non applicable |

Vous pouvez également ajouter une ou plusieurs plages pour limiter les mesures de la table source.

Dans cet exemple, si vous souhaitez uniquement comptabiliser tous les employés à temps plein, vous pouvez ajouter une plage dans le champ **Type de collaborateur**. Dans le champ **Critères**, sélectionnez **Employé** pour limiter la plage de sortie comme suit :

**Plages**

| Table source  | Champ       | Critères |
|---------------|-------------|----------|
| HcmEmployment | Type de collaborateur | Employé |

Avant de pouvoir entrer des mesures statistiques dans le module Contrôle de gestion, vous devez établir la relation entre le modèle de fournisseur de mesures statistiques et le membre de la dimension statistique. Cette relation est créée par comptabilité de contrôle de gestion et par version. La relation se compose d'un connecteur de données et d'un fournisseur de données. Vous pouvez avoir plusieurs connecteurs de données et fournisseurs de données par membre de dimension statistique.

> [!NOTE]
> Dans cet exemple, nous allons créer une relation uniquement pour la **Version réelle**.

Accédez à **Comptabilité de contrôle de gestion** \> **Version réelle** \> **Gérer** \> **Mesures statistiques** pour établir la relation. Pour ce scénario, sélectionnez le connecteur de données **Dynamics 365 for Finance and Operations, Enterprise Edition – Mesures statistiques**, car nous souhaitons extraire des données de Finance and Operations.

**Source de données**

| Nom        | Connecteur de données                                                                     | Membre de la dimension statistique |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| ETP D365FO | Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition – Mesures statistiques | ETP                         |

**Configuration du fournisseur de données**

| Nom du modèle statistique |
|---------------------------|
| ETP                      |

Une fois que la source de données pour la mesure statistique est traitée, les entrées statistiques suivantes sont créées dans le module Contrôle de gestion.

**Journal**

| Journal de saisie | Type de journal                       | Période de calendrier fiscal | Année   |  Période  |  Version | Entrées source du connecteur de données|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Journal de transfert d'entrées statistiques | Exercice                 | 2017   | Période 1 | USMF de la comptabilité de contrôle de gestion | ETP                   |

**Écritures du journal de transfert d'entrées statistiques**

| Date comptable | Ampleur | Élément statistique |   Description       | Centre de coût |
|-----------------|-----------|---------------------|---------------------|-------------|
| 31-01-2017      | 1,00      | ETP                | Employés à temps plein | CC001       |
| 31-01-2017      | 2.00      | ETP                | Employés à temps plein | CC002       |
| 31-01-2017      | 2.00      | ETP                | Employés à temps plein | CC003       |

**Entrées statistiques**

| Objet de coût |    | Date comptable | Membre de la dimension statistique |  Description        | Ampleur |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH | 31-01-2017      | ETP                         | Employés à temps plein | 1,00      |
| CC002       | FI | 31-01-2017      | ETP                         | Employés à temps plein | 2.00      |
| CC003       | TS | 31-01-2017      | ETP                         | Employés à temps plein | 2.00      |

Si la base de répartition des membres de la dimension prédéfinie ETP est affectée comme base de répartition dans une règle de distribution des coûts, le coût est distribué à l'aide du facteur de répartition suivant.

| Objet de coût | Description    | Ampleur | Facteur de répartition |
|-------------|----|-----------|-------------------|
| CC001       | RH | 1,00      | (1/5) × Montant    |
| CC002       | FI | 2.00      | (2/5) × Montant    |
| CC003       | TS | 2.00      | (2/5) × Montant    |

## <a name="using-the-sum-function"></a>Utilisation de la fonction Somme

Un centre de coût de production, CC010 (Emballage), est chargé d'emballer les produits avant qu'ils soient expédiés aux clients. Le coût de main-d'œuvre direct est ajouté aux produits via la nomenclature et la gamme. Le coût indirect de fonctionnement du centre de coût doit également être réparti sur les produits fabriqués. Souvent, la meilleure mesure statistique pour une telle répartition est le nombre d'heures de production enregistrées par produit dans la période donnée.

La table ProdRouteTrans contient toutes les transactions de la main-d'œuvre de production par entité juridique DataAreadID.

Voici un exemple de la table ProdRouteTrans.

| Référence        | Numéro | Opération | Type | Heure  | Date physique | Groupe de produits (dimension financière) | Entité juridique |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Ordre de fabrication | P0001  | Emballage | Heure | 8,00  | 01-01-2017    | Jus d'orange B2B                    | USMF         |
| Ordre de fabrication | P0001  | Emballage | Heure | 8,00  | 02-01-2017    | Jus d'orange B2B                    | USMF         |
| Ordre de fabrication | P0002  | Emballage | Heure | 4,00  | 03-01-2017    | Consommateur de jus d'orange               | USMF         |
| Ordre de fabrication | P0003  | Emballage | Heure | 4,00  | 03-01-2017    | Consommateur de jus d'orange               | USMF         |
| Ordre de fabrication | P0004  | Reconst.  | Heure | 10,00 | 03-01-2017    | Consommateur de jus d'orange               | USMF         |

Lorsque vous créez un enregistrement **Modèle de fournisseur de mesures statistiques**, vous devez choisir quelle fonction utiliser :

- **Nombre** – Un nombre d'enregistrements par objet de coût est transféré.
- **Somme** – Une somme d'enregistrements par objet de coût est transférée. (Le champ **Somme** et le champ **Date** sont obligatoires.)

Le modèle de fournisseur de mesures statistiques peut être paramétré comme suit :

| Nom    | Fonction | Table source   | Champ de somme | Champ de date    |
|---------|----------|----------------|-----------|---------------|
| CC emballage | Somme      | ProdRouteTrans | Heures     | Date physique |

Vous pouvez également ajouter des plages pour limiter les mesures de la table source.

Dans cet exemple, si vous souhaitez uniquement la somme des heures associées au centre de coût CC010 Emballage, vous pouvez ajouter une plage dans le champ **Opération**. Dans le champ **Critères**, sélectionnez **Emballage** pour limiter la plage de sortie.

**Plages**

| Table source   | Champ     | Critères  |
|----------------|-----------|-----------|
| ProdRouteTrans | Opération | Emballage |

Avant de pouvoir entrer des mesures statistiques dans le module Contrôle de gestion, vous devez établir la relation entre le modèle de fournisseur de mesures statistiques et le membre de la dimension statistique. Cette relation est créée par comptabilité de contrôle de gestion et par version. La relation se compose d'un connecteur de données et d'un fournisseur de données. Vous pouvez avoir plusieurs connecteurs de données et fournisseurs de données par membre de dimension statistique.

> [!NOTE]
> Dans cet exemple, nous allons créer une relation uniquement pour la **Version réelle**.

Accédez à **Comptabilité de contrôle de gestion** \> **Version réelle** \> **Gérer** \> **Mesures statistiques** pour établir la relation. Pour ce scénario, sélectionnez le connecteur de données **Dynamics 365 for Finance and Operations, Enterprise Edition – Mesures statistiques**, car nous souhaitons extraire des données de Finance and Operations.

**Source de données**

| Nom           | Connecteur de données                                                                     | Membre de la dimension statistique |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| CC emballage D365FO | Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition – Mesures statistiques | CC emballage                      |

Le système identifie que ProdRouteTrans est une table où chaque enregistrement appartient à une entité juridique distincte. Par conséquent, vous devez sélectionner l'entité juridique à partir de laquelle les transactions doivent être importées.

**Configuration du fournisseur de données**

| Nom du modèle statistique | Entité juridique |
|---------------------------|--------------|
| CC emballage                   | USMF         |

Une fois que la source de données pour la mesure statistique est traitée, les entrées statistiques suivantes sont créées dans le module Contrôle de gestion.

**Journal**

| Journal de saisie | Type de journal                     | Période de calendrier fiscal | Année   | Période | Version   |   Entrées source du connecteur de données  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Journal de transfert d'entrées statistiques | Exercice               | 2017    | Période 1  | USMF de la comptabilité de contrôle de gestion | CC emballage |

**Écritures du journal de transfert d'entrées statistiques**

| Date comptable | Ampleur | Élément statistique |  Description          | Groupe de produits         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 31-01-2017      | 16,00     | CC emballage             | Centre de coût d'emballage | Jus d'orange B2B      |
| 31-01-2017      | 8,00      | CC emballage             | Centre de coûts d'emballage | Consommateur de jus d'orange |

**Entrées statistiques**

| Objet de coût           | Date comptable | Membre de la dimension statistique |    Description        | Ampleur |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Jus d'orange B2B      | 31-01-2017      | CC emballage                      | Centre de coût d'emballage | 16,00     |
| Consommateur de jus d'orange | 31-01-2017      | CC emballage                      | Centre de coût d'emballage | 8,00      |

Si la base de répartition des membres de la dimension prédéfinie CC emballage est affectée comme base de répartition dans une règle de distribution des coûts, le coût est distribué à l'aide du facteur de répartition suivant.

| Objet de coût           | Ampleur | Facteur de répartition  |
|-----------------------|-----------|--------------------|
| Jus d'orange B2B      | 16,00     | (16 ÷ 24) × Montant |
| Consommateur de jus d'orange | 8,00      | (8 ÷ 24) × Montant  |

## <a name="imported-statistical-measures"></a>Mesures statistiques importées

Vous pouvez importer des mesures statistiques dans le module Contrôle de gestion à l'aide de l'outil d'importation/exportation Gestion des données.

L'entité de données utilisée pour l'importation est nommée Mesures statistiques importées.

> [!NOTE]
> Cette entité de données est conçue pour autoriser cinq valeurs de dimension uniques par entrée au maximum.

La consommation électrique est enregistrée dans Microsoft Excel à l'aide du format prédéfini de l'entité de données. Voici un exemple :

| Date comptable | Nom du membre 1 de la dimension | Nom du membre 2 de la dimension | Nom du membre 5 de la dimension | Ampleur  | Identificateur de la source |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 31-01-2017      | CC001                  |                        |                        | 2,450.00   | Électricité       |
| 31-01-2017      | CC002                  |                        |                        | 4,100.00   | Électricité       |
| 31-01-2017      | CC003                  |                        |                        | 15 000,00  | Électricité       |

Après avoir importé vos données via l'outil de gestion des données, les données sont stockées dans une table intermédiaire du module Contrôle de gestion. Par conséquent, les données importées peuvent être utilisées dans plusieurs comptabilités de contrôle de gestion. Un rechargement des données n'est pas nécessaire.

Pour importer les données, accédez à **Données importées** \> **Entité de données** \> **Mesures statistiques importées**.

| Identificateur de la source | Date comptable | Ampleur  | Nom du membre 1 de la dimension | Nom du membre 2 de la dimension | Nom du membre 5 de la dimension |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Électricité       | 31-01-2017      | 2,450.00   | CC001                  |                        |                        |
| Électricité       | 31-01-2017      | 4,100.00   | CC002                  |                        |                        |
| Électricité       | 31-01-2017      | 15 000,00  | CC003                  |                        |                        |

Avant de pouvoir entrer des mesures statistiques dans le module Contrôle de gestion, vous devez établir la relation entre l'identificateur de la source et le membre de la dimension statistique. Cette relation est créée par comptabilité de contrôle de gestion et par version. La relation se compose d'un connecteur de données et d'un fournisseur de données. Vous pouvez avoir plusieurs connecteurs de données et fournisseurs de données par membre de dimension statistique.

> [!NOTE]
> Dans cet exemple, nous allons créer une relation uniquement pour la **Version réelle**.

Accédez à **Comptabilité de contrôle de gestion** \> **Version réelle** \> **Gérer** \> **Mesures statistiques** pour établir la relation. Pour ce scénario, sélectionnez le connecteur de données **Mesures statistiques importées**, car les données ont été importées à partir d'un système tiers dans le module Contrôle de gestion via Excel.

**Source de données**

| Nom        | Connecteur de données                | Membre de la dimension statistique |
|-------------|-------------------------------|------------------------------|
| Électricité | Mesures statistiques importées | Électricité                  |

**Configuration du fournisseur de données**

| Importer identificateur de la source | Fonction | Dimension1   | Dimension2 | Dimension5 |
|--------------------------|----------|--------------|------------|------------|
| Électricité              | Somme      | Centres de coût |            |            |

> [!NOTE]
> Lorsque vous définissez la configuration du fournisseur de données, vous devez spécifier les dimensions d'objet de coût à mettre en correspondance avec les transactions importées. Une fois que la source de données pour la mesure statistique est traitée, les entrées statistiques suivantes sont créées dans le module Contrôle de gestion.

**Journal**

| Journal de saisie | Type de journal                       | Période de calendrier fiscal | Année  | Période  |Version      |Entrées source du connecteur de données |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Journal de transfert d'entrées statistiques | Exercice                 | 2017  | Période 1 | USMF de la comptabilité de contrôle de gestion | Électricité |

**Écritures du journal de transfert d'entrées statistiques**

| Date comptable | Ampleur  | Élément de coût |   Description           | Centre de coût |
|-----------------|------------|--------------|-------------------------|-------------|
| 31-01-2017      | 2,450.00   | Électricité  | Consommation électrique | CC001       |
| 31-01-2017      | 4,100.00   | Électricité  | Consommation électrique | CC002       |
| 31-01-2017      | 15 000,00  | Électricité  | Consommation électrique | CC003       |

**Entrées statistiques**

| Objet de coût |    | Date comptable | Membre de la dimension statistique |      Description                   | Ampleur  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | RH | 31-01-2017      | Électricité                  | Consommation électrique | 2,450.00   |
| CC002       | FI | 31-01-2017      | Électricité                  | Consommation électrique | 4,100.00   |
| CC003       | TS | 31-01-2017      | Électricité                  | Consommation électrique | 15 000,00  |

Si la base de répartition des membres de la dimension prédéfinie Électricité est affectée comme base de répartition dans une règle de distribution des coûts, le coût est distribué à l'aide du facteur de répartition suivant.

| Objet de coût |    | Ampleur | Facteur de répartition          |
|-------------|----|-----------|----------------------------|
| CC001       | RH | 2,450.00  | (2,450 ÷ 21,550) × Montant  |
| CC002       | FI | 4,100.00  | (4,100 ÷ 21,550) × Montant  |
| CC003       | TS | 15 000,00 | (15,000 ÷ 21,550) × Montant |

## <a name="see-also"></a>Voir également :

[Bases de répartition](allocation-bases.md)

