---
title: Bases de répartition
description: Cette rubrique fournit des informations sur les bases de répartition. Les bases de répartition sont des composants clé dans le contrôle de gestion et permettent généralement d'affecter des frais généraux.
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c2cea745ec645b2e9cc6f9d72a0aeae2f7467155
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188002"
---
# <a name="allocation-bases"></a>Bases de répartition 

[!include [banner](../includes/banner.md)]

Une base de répartition est la base sur laquelle le contrôle de gestion affecte les frais généraux. Une base de répartition peut être une quantité, telles que les heures-machine utilisées, les kilowatt-heures (kWh) qui sont consommées, ou la superficie qui est occupée. Les bases de répartition sont la plupart utilisées pour affecter des frais généraux dans le stock qui est produit. Par exemple, un service informatique affecte les dépenses en fonction du nombre d'ordinateurs que chaque département utilise.

Il existe trois types de bases de répartition dans le contrôle de gestion :

- Bases de répartition du membre de la dimension prédéfinies
- Bases de répartition de la hiérarchie
- Bases de répartition de la formule

## <a name="predefined-dimension-member-allocation-bases"></a>Bases de répartition du membre de la dimension prédéfinies

Les bases de répartition des membres de dimension prédéfinies sont créées automatiquement lorsqu'un membre de dimension d'un des types suivants est créé :

- Membres de la dimension statistique
- Membres de la dimension d'élément de coût

> [!NOTE]
> Les bases de répartition des membres de dimension prédéfinies qui reposent sur un membre de dimension d'élément de coût prennent en compte uniquement les valeurs du fournisseur de données source, comme la comptabilité ou le budget.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Exemple 1 : Utilisez un membre de dimension d'élément de coût comme base de répartition
Cet exemple montre comment créer une règle de répartition des coûts pour attribuer l'élément de coût 10002 (Assurance salariale) au solde enregistré sur l'élément de coût 10001 (Salaires). La règle de répartition est définie selon le rapport des salaires de chaque département et du total des salaires. (Révision nécessaire !)

En comptabilité, le plan de comptes est défini comme suit.

| Plan de comptes | Compte principal | Description        | Type de compte principal |
|------------------|--------------|--------------------|-------------------|
| Partagées           | 10001        | Salaires           | Dépense           |
| Partagées           | 10002        | Assurance salariale | Dépense           |

Définissez une dimension d'élément de coût, puis configurez le connecteur de données. Une fois que les données sont importées, les écritures suivantes sont créées dans le contrôle de gestion.

**Membres de la dimension d'élément de coût**

| Nom de la dimension d'élément de coût | Élément de coût |  Description       | Type    |
|-----------------------------|--------------|--------------------|---------|
| Éléments de coût               | 10001        | Salaires           | Principale |
| Éléments de coût               | 10002        | Assurance salariale | Principale |

**Bases de répartition du membre de la dimension prédéfinies** 

| Nom  | Description        | Dimension d'élément de coût |
|-------|--------------------|------------------------|
| 10001 | Salaires           | Éléments de coût          |
| 10002 | Assurance salariale | Éléments de coût          |

En comptabilité, les écritures suivantes ont été validées :

- Les entrées affichant le compte principal des salaires provenant du système de paie et sont validées dans les centres de coût.
- Les dépenses liées à l'assurance salariale sont validées manuellement dans un centre de coût par défaut.

| Date comptable | Centre de coût |  Description        | Compte principal |  Description       | Montant en devise comptable |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | RH                  | 10001        | Salaires           | 2 000,00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | Salaires           | 5 000,00                      |
| 03-01-2017      | CC003       | TS                  | 10001        | Salaires           | 3 000,00                      |
| 03-01-2017      | CC099       | Centre de coût par défaut | 10002        | Assurance salariale | 1 000,00                      |

Une fois que les données source en comptabilité sont traitées, les écritures suivantes sont créées dans le contrôle de gestion.

**Écritures de coût**

| Objet de coût |  Description        | Élément de coût  |  Description       | Comportement de coûts   |Montant|Date comptable|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | RH                  | 10001         | Salaires           | Non classifié    |2 000,00|  03-01-2017    |
| CC002       | FI                  | 10001         | Salaires           | Non classifié    |5 000,00|     03-01-2017         |
| CC003       | TS                  | 10001         | Salaires           | Non classifié    |3 000,00|      03-01-2017        |
| CC099       | Centre de coût par défaut | 10002         | Assurance salariale | Non classifié    |1 000,00|      03-01-2017       |

Dans cet exemple simplifié, une règle de répartition des coûts est créée pour attribuer l'élément de coût 10002 (Assurance salariale) par rapport au solde enregistré sur l'élément de coût 10001 (Salaires).

**Règle de distribution des coûts**

| Nœud de hiérarchie des dimensions d'objet de coût | Nœud de hiérarchie des dimensions d'élément de coût | Comportement de coûts | Base de répartition |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Non classifié  | 10001           |

**Exécuter le calcul des frais généraux**

Une fois l'élément de coût 10001 (salaires) appliqué comme base de répartition, le résultat du calcul des frais généraux est le suivant.

| Objet de coût | Description | Ampleur |   Facteur de répartition         | Montant |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | RH          | 2 000     | (2 000 ÷ 10 000) × 1 000,00 | 200,00 |
| CC002       | FI          | 5 000     | (5 000 ÷ 10 000) × 1 000,00 | 500,00 |
| CC003       | TS          | 3 000     | (3 000 ÷ 10 000) × 1 000,00 | 300,00 |

**Journal**

| Journal de saisie | Type de journal                          | Période de calendrier fiscal | Année | Période   | Version                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Journal de calcul de la distribution des coûts | Exercice                 | 2017 | Période 1 | Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1 |

**Entrées du journal pour le solde d'objet de coût**

| Date comptable | Objet de coût | Description         | Élément de coût | Description        | Comportement de coûts |  Montant  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | Centre de coût par défaut | 10002        | Assurance salariale | Non classifié  | 1 000,00 |

**Écritures de coût**

| Objet de coût |  Description        | Élément de coût |    Description     | Comportement de coûts | Montant    | Date comptable |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Centre de coût par défaut | 10002        | Assurance salariale | Non classifié  | -1 000,00 | 31-01-2017      |
| CC001       | RH                  | 10002        | Assurance salariale | Non classifié  | 200,00    | 31-01-2017      |
| CC002       | FI                  | 10002        | Assurance salariale | Non classifié  | 500,00    | 31-01-2017      |
| CC099       | TS                  | 10002        | Assurance salariale | Non classifié  | 300,00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Exemple 2 : Utilisez un membre de la dimension statistique comme base de répartition

Les membres de la dimension statistique peuvent être utilisés comme base de répartition pour définir des stratégies ou pour déclarer la consommation non-monétaire par objet de coût. Vous pouvez créer manuellement les membres de la dimension statistique ou les importer à partir d'un fichier à l'aide de l'outil d'importation/d'exportation Gestion des données.

**Membres de la dimension statistique**

| Nom de la dimension statistique | Élément statistique | Description               | Unité |
|----------------------------|---------------------|---------------------------|------|
| Éléments statistiques       | ETP                 | Employés à temps plein       | Ea   |
| Éléments statistiques       | Électricité         | Consommation électrique   | kWh  |

Lorsqu'un membre de la dimension statistique est enregistré, un enregistrement correspondant est créé dans les bases de répartition des membres de la dimension prédéfinies.

**Bases de répartition du membre de la dimension prédéfinies**

| Nom        | Description             | Dimension d'élément statistique |
|-------------|-------------------------|-------------------------------|
| ETP         | Employés à temps plein     | Éléments statistiques          |
| Électricité | Consommation électrique | Éléments statistiques          |

Les mesures statistiques peuvent provenir de différentes sources :

- La consommation d'électricité peut être mesurée en mètres qui sont installés dans différents domaines de la société.
- Les tables contiennent des mesures statistiques. Par exemple, la table des HcmEmployment contient une liste de tous les employés et des centres de coût pour lesquels ils travaillent.

| Nom       | Centre de coût |  Description  | Type de collaborateur |
|------------|-------------|----|-------------|
| Employé A | CC001       | RH | Employé    |
| Employé B | CC002       | FI | Employé    |
| Employé C | CC002       | FI | Employé    |
| Employé D | CC003       | TS | Employé    |
| Employé F | CC003       | TS | Employé    |

> [!NOTE]
> Toutes les tables qui contiennent des dimensions financières peuvent être utilisées comme sources pour les mesures statistiques.

Le contrôle de gestion prend en charge un ensemble de mesures statistiques à l'aide des connexions de données suivantes :

- Outil d'importation/d'exportation de la gestion des données
- Mesures statistiques

Pour extraire des mesures statistiques du système, un modèle de fournisseur de mesures statistiques est requis. Pour plus d'informations, voir Modèle de fournisseur de mesures statistiques. (Ajouterai un lien une fois la rubrique écrite.)

**Modèles de fournisseur de mesures statistiques**

| Nom  | Fonction | Table source  | Champ de somme      | Champ de date     |
|-------|----------|---------------|----------------|----------------|
| FTE’s | Nombre    | HcmEmployment | Non applicable | Non applicable |

Une fois que la source de données pour la mesure statistique est traitée, les entrées statistiques suivantes sont créées dans le module Contrôle de gestion.

**Entrées statistiques**

| Objet de coût | Description      | Date comptable | Membre de la dimension statistique | Description         | Ampleur |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH               | 31-01-2017      | ETP                        | Employés à temps plein | 1,00      |
| CC002       | FI               | 31-01-2017      | ETP                        | Employés à temps plein | 2.00      |
| CC003       | TS               | 31-01-2017      | ETP                        | Employés à temps plein | 2.00      |

Voici l'exemple d'une règle de répartition des coûts si la base de répartition des membres de la dimension prédéfinie ETP est affectée comme base de répartition dans celle-ci.

| Objet de coût | Description  | Ampleur | Facteur de répartition |
|-------------|------|-----------|-------------------|
| CC001       | RH   | 1,00      | (1/5) × Montant    |
| CC002       | FI   | 2.00      | (2/5) × Montant    |
| CC003       | TS   | 2.00      | (2/5) × Montant    |

Vous pouvez utiliser l'entité de données Mesures statistiques importées pour importer des mesures statistiques dans le contrôle de gestion. Vous pouvez également utiliser l'outil d'importation/d'exportation Gestion des données. Dans Excel, la consommation d'électricité est enregistrée comme suit.

| Date comptable | Membre de la dimension | Ampleur | Identificateur de la source |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | Électricité       |
| 31-01-2017      | CC002            | 4,100.00  | Électricité       |
| 31-01-2017      | CC003            | 15 000,00 | Électricité       |

Une fois que la source de données pour la mesure statistique est traitée, les entrées statistiques suivantes sont créées dans le module Contrôle de gestion.

**Entrées statistiques**

| Objet de coût |    | Date comptable | Membre de la dimension statistique |    Description          | Ampleur |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RH | 31-01-2017      | Électricité                  | Consommation électrique | 2,450.00  |
| CC002       | FI | 31-01-2017      | Électricité                  | Consommation électrique | 4,100.00  |
| CC003       | TS | 31-01-2017      | Électricité                  | Consommation électrique | 15 000,00 |

Voici l'exemple d'une règle de répartition des coûts si la base de répartition des membres de la dimension prédéfinie Électricité est affectée comme base de répartition dans celle-ci.

| Objet de coût | Description  | Ampleur | Facteur de répartition          |
|-------------|------|-----------|----------------------------|
| CC001       | RH   | 2,450.00  | (2,450 ÷ 21,550) × Montant  |
| CC002       | FI   | 4,100.00  | (4,100 ÷ 21,550) × Montant  |
| CC003       | TS   | 15 000,00 | (15,000 ÷ 21,550) × Montant |

## <a name="hierarchy-allocation-bases"></a>Bases de répartition de la hiérarchie

Les comptables peuvent créer manuellement les bases de répartition de hiérarchie en appliquant un nœud de hiérarchie de dimensions d'objet de coût à une base de répartition existante. De cette manière, vous pouvez limiter la plage de la base de répartition des membres de la dimension prédéfinie initiale. Une base de répartition des membres de la dimension prédéfinie peut être utilisée pour créer plusieurs bases de répartition hiérarchique. Les plages peuvent être gérées dans la hiérarchie de dimensions d'objet de coût associée aux bases de répartition hiérarchique.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Exemple : Bases de répartition hiérarchique reposant sur les employés à temps plein dans l'organisation
Voici l'exemple d'une hiérarchie de dimensions d'objet de coût qui peut être créée pour décrire une organisation simplifiée.

| Nom de la hiérarchie | Niveau de nœud 0 | Niveau de nœud 1 | Niveau de nœud 2 | Membres de la dimension |
|----------------|--------------|--------------|--------------|-------------------|
| Organisation   | PDG          | Directeur financier          | FICO         | CC001             |
| Organisation   | PDG          | Directeur financier          | RH           | CC002             |
| Organisation   | PDG          | Directeur informatique          | TS           | CC003             |

La base de répartition des membres de la dimension prédéfinie ETP qui a été créée dans la section précédente contient les écritures suivantes.

**Entrées statistiques**

| Objet de coût | Description  | Date comptable | Membre de la dimension statistique | Description | Ampleur |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH   | 31-01-2017      | ETP                        | Employés à temps plein | 1,00      |
| CC002       | FI   | 31-01-2017      | ETP                        | Employés à temps plein | 2.00      |
| CC003       | TS   | 31-01-2017      | ETP                        | Employés à temps plein | 2.00      |

Un coût doit être réparti entre les centres de coût rattachés au directeur financier de l'organisation. Il est reconnu que le taux de répartition correct correspond au nombre d'employés à temps plein par centre de coût.

**Bases de répartition de la hiérarchie**

| Nom                  | Base de répartition | Hiérarchie des dimensions d'objet de coût | Nœud de hiérarchie des dimensions d'objet de coût |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Nombre d'ETP professionnelles d'un processus CFO | ETP           | Organisation                    | Directeur financier                                  |

Une fonctionnalité d'aperçu vous permet de valider la base de répartition hiérarchique créée, reposant sur les entrées statistiques dans le système.

**Détails de la base de répartition**

| Objet de coût | Description  |  Ampleur |
|-------------|------|------------|
| CC001       | RH   | 1,00       |
| CC002       | FI   | 2.00       |

Voici l'exemple d'une règle de répartition des coûts si la base de répartition Nombre d'ETP dans la hiérarchie CFO est affectée comme base de répartition dans celle-ci.

| Objet de coût | Description  | Ampleur | Facteur de répartition |
|-------------|------|-----------|-------------------|
| CC001       | RH   | 1,00      | (1/3) × Montant    |
| CC002       | FI   | 2.00      | (2/3) × Montant    |

## <a name="formula-allocation-bases"></a>Bases de répartition de la formule

Les bases de répartition des formules vous permettent de définir des formules avancées pour accomplir la base de répartition correcte. Vous pouvez créer des bases de répartition de formule manuellement.

Lorsque vous créez une base de répartition de formule, vous sélectionnez la dimension statistique et la dimension d'élément de coût devant servir de base à la formule. Toutes les bases de répartition qui proviennent des dimensions précédemment sélectionnées peuvent être utilisées dans une base de répartition de formule.

> [!NOTE]
> Les bases de répartition de formule définies précédemment permettent de définir une nouvelle base de répartition de formule.

Dans les facteurs de base de répartition de formule, vous créez un alias et l'associez à une base ou une constante de répartition. Les alias sont ensuite utilisés pour définir la formule.

Vous pouvez utiliser les opérateurs disponibles pour définir votre formule.

| Symboles | Détails           |
|---------|----------------|
| ( )     | Parenthèses    |
| \<      | Inférieur à   |
| \>      | Supérieur à    |
| +       | Addition       |
| –       | Soustraction    |
| \*      | Multiplication |

Les instructions **IF** traditionnelles ne sont pas prises en charge. Toutefois, vous pouvez créer des instructions et les valider si elles sont vraies.

| Relevé | Contrôle | Résultat |
|-----------|------------|--------|
| a \> b    | Vrai       | 1      |
| a \> b    | Faux      | 0      |

### <a name="example-1-a-simple-formula"></a>Exemple 1 : Une formule unique

Les factures d'électricité se composent généralement de deux parties :

- Les frais fixes pour une connexion à la grille
- Un coût associé à la consommation par kWh

La base de répartition des membres de la dimension prédéfinie Électricité a déjà été définie et gère ces valeurs.

**Entrées statistiques**

| Objet de coût | Nom | Date comptable | Membre de la dimension statistique | Description             | Ampleur |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RH   | 31-01-2017      | Électricité                  | Consommation électrique | 2,450.00  |
| CC002       | FI   | 31-01-2017      | Électricité                  | Consommation électrique | 4,100.00  |
| CC003       | TS   | 31-01-2017      | Électricité                  | Consommation électrique | 15 000,00 |

Si les frais fixes doivent maintenant être des objets de coût répartis équitablement qui consomment de l'électricité, vous avez deux options pour répartir les coûts :

- Créez une nouvelle base de répartition prédéfinie, l'électricité fixe, puis appliquez une mesure statistique de 1,00 pour chaque objet de coût qui a consommé l'électricité.
- Créez une base de répartition de formule, l'électricité fixe, qui valorise la base de répartition prédéfinie Électricité déjà définie dans le système. L'avantage de cette option est que les données doivent être chargées dans le contrôle de gestion pour un seul membre statistique de la dimension Électricité.

**Base de répartition de la formule** 

| Nom              | Dimension d'élément de coût | Dimension statistique | Formule |
|-------------------|------------------------|-----------------------|---------|
| Électricité fixe |                        | Éléments statistiques  |         |

Avant que le champ **Formule** puisse être rempli, vous devez spécifier l'alias qui doit être utilisé dans la formule.

**Facteurs de base de répartition de formule**

| Alias | Constante | Base de répartition |
|-------|----------|-----------------|
| a     |          | Électricité     |
| b     | 0,01     |                 |

Notez que 0 (zéro) n'est pas accepté en tant que constante.

**Base de répartition de la formule**

| Nom              | Dimension d'élément de coût | Dimension statistique | Formule |
|-------------------|------------------------|-----------------------|---------|
| Électricité fixe |                        | Éléments statistiques  | a \> b  |

Une fonctionnalité d'aperçu vous permet de valider la base de répartition de la formule créée, reposant sur les entrées statistiques dans le système.

**Détails de la base de répartition**

| Objet de coût | Description  | Formule           | Ampleur |
|-------------|------|-------------------|-----------|
| CC001       | RH   | 2.450,00 \> 0,01  | 1,00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1,00      |
| CC003       | TS   | 15.000,00 \> 0,01 | 1,00      |

Voici l'exemple d'une règle de répartition des coûts si la base de répartition de la formule prédéfinie Électricité est affectée comme base de répartition dans celle-ci.

**Facteur de répartition de l'ampleur de l'objet de coût**

| Objet de coût | Nom | Ampleur |  Facteur de répartition |
|-------------|------|-----------|--------------------|
| CC001       | RH   | 1,00      | (1/3) × Montant     |
| CC002       | FI   | 1,00      | (1/3) × Montant     |
| CC003       | TS   | 1,00      | (1/3) × Montant     |

### <a name="example-2-an-advanced-formula"></a>Exemple 2 : Une formule avancée
Pour cet exemple, le coût de l'électricité ne doit pas uniquement suivre l'électricité réelle qui est consommée en kWh. La direction veut inciter à réduire la consommation d'électricité. 

| Règle              | Taux | 
|-------------------|------|
| a <= 10000,00 kWh | 0.75 |
| a > 10000,00 kWh  | 1.15 |

Une nouvelle base de répartition de formule, Utilisation de l'électricité, est créée.

**Base de répartition de la formule**

| Nom              | Dimension d'élément de coût | Dimension statistique | Formule |
|-------------------|------------------------|-----------------------|---------|
| Utilisation de l'électricité |                        | Éléments statistiques  |         |

Avant que le champ **Formule** puisse être rempli, vous devez spécifier l'alias qui doit être utilisé dans la formule.

**Facteurs de base de répartition de formule**

| Alias | Constante  | Base de répartition |
|-------|-----------|-----------------|
| a     |           | Électricité     |
| b     | 10 000,00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Base de répartition de la formule**

| Nom              | Dimension d'élément de coût | Dimension statistique | Formule                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Électricité fixe |                        | Éléments statistiques  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

Une fonctionnalité d'aperçu vous permet de valider la base de répartition de la formule créée, reposant sur les entrées statistiques dans le système.

**Détails de la base de répartition**

| Objet de coût |    | Formule                                                                                                                             | Ampleur |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | RH | ((2 450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75)     | 1,837.50  |
| CC002       | FI | ((2 450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75)     | 3,075.00  |
| CC003       | TS | ((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) | 1,3250.00 |

Voici un aperçu de la formule pour CC003 (IT) :

((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) = 13 250,00

(1 × (7 500,00 + 5 000,00 × 1,15)) + (0 × 15 000,00 × 0,75)            

1 × 7 500,00 + 5 750,00 + 0 

Voici l'exemple d'une règle de répartition des coûts si la base de répartition de la formule prédéfinie Électricité fixe est affectée comme base de répartition dans celle-ci.


| Objet de coût | Description | Ampleur |        Facteur de répartition         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     RH      | 1,837.50  | (1,837.50 ÷ 18,162.50) × Montant  |
|    CC002    |     FI      | 3,075.00  | (3,075.00 ÷ 18,162.50) × Montant  |
|    CC003    |     TS      | 13,250.00 | (13,250.00 ÷ 18,162.50) × Montant |

