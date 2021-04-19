---
title: EUR-00002 Générer un fichier de déclaration d’échanges de biens de l’UE
description: Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d’échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel.
author: Anasyash
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24caceffd8c0bf29a3f9cc45b7bd1977e119359d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822603"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a>EUR-00002 Générer un fichier de déclaration d’échanges de biens de l’UE

[!include [banner](../../includes/banner.md)]

Cette procédure vous fait parcourir les étapes requises pour exporter la déclaration d’échanges de biens dans le format de fichier électronique et pour prévisualiser les données de déclaration dans un format Excel. 

Avant d’exécuter cette procédure, vous devez transférer des transactions dans la déclaration d’échanges de biens. 

Cette procédure a été créée à l’aide des données fictives de la société DEMF.


## <a name="import-configurations-with-settings"></a>Importer des configurations avec des paramètres
1. Accédez à Espaces de travail > États électroniques.
2. Cliquez sur Activer.
3. Cliquez sur Référentiels.
4. Cliquez sur Ouvrir.
5. Ouvrez le filtre de la colonne Nom de la configuration.
6. Appliquez un filtre sur le champ Nom de la configuration, avec la valeur Déclaration d’échanges de biens (DE), à l’aide de l’opérateur de filtre « commence par ».
    * Vous devez sélectionner le nom de configuration applicable pour le pays de votre entité juridique. Cette procédure utilise l’entité juridique allemande (DEMF) comme exemple, donc « Déclaration d’échanges de biens (DE) » doit être sélectionné.  
    * Cliquez sur Importation, puis sur Oui.  
7. Ouvrez le filtre de la colonne Nom de la configuration.
8. Appliquez un filtre sur le champ Nom de la configuration, avec la valeur État de déclaration d’échanges de biens, à l’aide de l’opérateur de filtre « commence par ».
    * Cliquez sur Importation, puis sur Oui.  

## <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.
2. Développez la section Génération d’états électroniques.
3. Saisissez ou sélectionnez une valeur Déclaration d’échanges de biens (DE) dans le champ Mise en correspondance des formats de fichier.
4. Saisissez ou sélectionnez une valeur État de déclaration d’échanges de biens dans le champ Mise en correspondance des formats d’état.
5. Développez la section Règles d’arrondi.
    * Vous devez paramétrer des règles d’arrondi applicables dans votre pays/région pour la génération d’états de déclaration d’échanges de biens.  
6. Entrez un nombre dans le champ Règle d’arrondi.
    * Entrez la précision de l’arrondi, par exemple, entrez 0,01.  
7. Entrez un nombre dans le champ Nombre de décimales pour le montant.
    * Entrez 2, par exemple.  
8. Sélectionnez une option dans le champ Arrondi en dessous d’un (1) kg.
    * Sélectionnez Arrondi à 1 kg, par exemple.  
9. Entrez un nombre dans le champ Règle d’arrondi.
    * Entrez 1, par exemple pour arrondir le poids à l’entier.  
10. Développez la section Limite inférieure.
11. Dans le champ Poids, saisissez un nombre.
    * Entrez 10, par exemple comme poids minimal.  
12. Dans le champ Montant, entrez un nombre.
    * Entrez 200, par exemple comme montant minimal.  
13. Saisissez ou sélectionnez une valeur dans le champ Marchandise.

## <a name="set-up-compression-of-intrastat"></a>Paramétrer la compression de la déclaration d’échanges de biens
1. Accédez à Taxes > Paramétrage > Commerce extérieur > Compression de la déclaration d’échanges de biens.
2. Cliquez sur Supprimer.
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez Marchandise dans la section Disponible.  
4. Cliquez sur Ajouter.

## <a name="generate-intrastat-declaration"></a>Générer la déclaration d’échanges de biens
1. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.
2. Cliquez sur Valider.
    * La validation est effectuée en fonction du champ Vérifier le paramétrage de la page Paramètres de commerce extérieur.  
3. Cliquez sur OK.
4. Cliquez sur Mise à jour.
5. Cliquez sur Limite inférieure.
6. Entrez une date dans le champ Date de début.
    * Entrez 1er janvier 2015, par exemple.  
7. Sélectionnez Oui dans le champ Compresser.
8. Entrez une date dans le champ Date de fin.
    * Entrez 31 janvier 2015, par exemple.  
9. Cliquez sur OK.
10. Cliquez sur Mise à jour.
11. Cliquez sur Compresser.
    * Cette compression se produit en fonction de la manière dont vous définissez la compression des paramètres de déclaration d’échanges de biens.  
12. Entrez une date dans le champ Date de début.
    * Entrez 1er janvier 2015, par exemple.  
13. Entrez une date dans le champ Date de fin.
    * Entrez le 31 janvier 2015, par exemple.  
14. Cliquez sur OK.
15. Cliquez sur Mise à jour.
16. Cliquez sur Régénérer les numéros de souche.
17. Cliquez sur OK.
18. Cliquez sur Résultat.
19. Cliquez sur État.
20. Entrez le premier jour de la période de déclaration dans le champ Date de début.
    * Définissez la date sur le 1er janvier 2015, par exemple.  
21. Entrez une date dans le champ Date de fin.
    * Entrez 31 janvier 2015, par exemple.  
22. Sélectionnez Oui dans le champ Générer un fichier.
23. Tapez une valeur dans le champ Nom du fichier.
24. Sélectionnez Oui dans le champ Générer un état.
25. Tapez une valeur dans le champ Nom du fichier d’état.
26. Sélectionnez une option dans le champ Direction.
    * Sélectionnez Répartitions, par exemple.  
27. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]