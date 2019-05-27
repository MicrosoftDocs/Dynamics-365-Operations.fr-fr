---
title: Créer des configurations d'états électroniques pour importer des données à partir de fichiers CSV externes
description: Cette procédure permet de créer des configurations d'états électroniques pour importer des données dans l'application Dynamics 365 for Finance and Operations, à partir d'un fichier externe au format CSV.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d3ea3d797de154979eae112658cf05d1914feeb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544930"
---
# <a name="design-er-configurations-to-import-data-from-external-csv-files"></a>Créer des configurations d'états électroniques pour importer des données à partir de fichiers CSV externes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet de créer des configurations d'états électroniques pour importer des données dans l'application Dynamics 365 for Finance and Operations, à partir d'un fichier externe au format CSV. Dans cette procédure, vous allez créer les configurations ER requises pour l'exemple de société, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Créer un fournisseur de configuration et le marquer comme actif. » 

Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Ces étapes peuvent être effectuées à l'aide de l'ensemble de données USMF. 

Vous devez également télécharger et enregistrer localement les fichiers suivants : (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vous pouvez configurer un processus pour importer des fichiers externes au format XML, TXT ou CSV dans des tables de l'application Dynamics 365 for Finance and Operations. Tout d'abord, vous devez créer un modèle de données abstrait pour représenter les données importées, d'un point de vue commercial - une configuration de modèle de données ER est créée pour cela. Ensuite, définissez une structure du fichier importé qui correspond au modèle de données conçu comme moyen de transférer les données du fichier vers le modèle de données abstrait - une configuration de format ER est créée pour cela. Enfin, la configuration du modèle de données ER doit être étendue avec une nouvelle mise en correspondance de modèle décrivant comment les données du fichier importé restent des données de modèle de données abstrait, et comment elles sont utilisées pour la mise à jour des tables d'application ou des entités de données.  
    * Les étapes suivantes décrivent comment les transactions fournisseur suivies en externe sont importées depuis le fichier CSV externe pour une utilisation ultérieure dans le règlement fournisseur pour les déclarations d'honoraires.   
    * Vérifiez que le fournisseur de la configuration pour la société fictive Litware, Inc. est disponible et marqué comme actif. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».  
2. Cliquez sur Configurations des états.
3. Appliquez le filtre « Modèle de paiements 1099 ». Appliquez le filtre « Modèle de paiements de déclaration des honoraires ». Si vous avez déjà effectué la procédure « ER Créer des configurations requises pour importer des données à partir d'un fichier externe pour la gestion des états électroniques » et si la configuration « Modèle de paiements de déclaration des honoraires » est disponible dans l'arborescence de configuration, ignorez toutes les étapes de la sous-tâche suivante.   

## <a name="add-a-new-er-model-configuration"></a>Ajouter une nouvelle configuration du modèle ER
1. Plutôt que de créer un modèle pour prendre en charge l'importation de données, chargez le fichier 1099model.xml que vous avez précédemment téléchargé. Ce fichier contient le modèle personnalisé de données des transactions des fournisseurs. Ce modèle de données est déjà mis en correspondance avec les composants de données nécessaires.  
2. Cliquez sur Échanger.
3. Cliquez sur Charger depuis le fichier XML.
4. Cliquez sur Parcourir et accédez au fichier 1099model.xml que vous avez précédemment téléchargé.  
5. Cliquez sur OK.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Ajouter une nouvelle configuration du format ER prenant en charge l'importation de données
1. Dans l'arborescence, sélectionnez « Modèles de paiements de déclaration des honoraires »
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nouveau, entrez « Format basé sur le modèle de données modèle de paiements de déclaration des honoraires ».
4. Sélectionnez Oui dans le champ Prend en charge l'importation de données.
5. Appuyez sur la touche Échap pour fermer cette page.
    * Plutôt que de créer un format ER pour prendre en charge l'importation de données, chargez le fichier 1099formatcsv.xml que vous avez précédemment téléchargé. Ce fichier contient le format ER requis qui définit la structure du fichier CSV entrant et la mise en correspondance de cette structure avec le modèle de données des transactions des fournisseurs.   
6. Cliquez sur Échanger.
7. Cliquez sur Charger depuis le fichier XML.
    * Cliquez sur Parcourir et accédez au fichier 1099formatcsv.xml que vous avez précédemment téléchargé.  
8. Cliquez sur OK.
9. Dans l'arborescence, développez « Modèle de paiements de déclaration des honoraires ».
10. Dans l'arborescence, sélectionnez « Modèle de paiements de déclaration des honoraires\Pour importer les transactions des fournisseurs (CSV) ».

## <a name="review-format-settings"></a>Passer en revue les paramètres de format
1. Cliquez sur Concepteur.
2. Cliquez sur Développer/réduire.
3. Activez « Afficher les détails ».
    * Le format conçu représente la structure attendue du fichier externe au format CSV.  
4. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence ».
    * Pour l'élément Racine de type SEQUENCE, l'option « Nouvelle ligne - Windows (CR LF) » a été sélectionnée dans le champ « Caractères spéciaux ». Selon ce paramètre, chaque ligne du fichier d'analyse doit être considérée comme un enregistrement distinct.   
5. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* ».
    * Pour l'élément Racine\Ligne de type SEQUENCE, l'option « Un plusieurs » a été sélectionnée dans le champ « Multiplicité ». En fonction de ce paramètre, au moins une ligne sera présentée dans le fichier d'analyse.   
6. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident ».
    * Notez que l'élément Root\Line\Types de type CASE a été ajouté comme élément imbriqué de la séquence Root\Line. Comme cet élément CASE contient 3 éléments de séquence imbriqués, ce paramètre suppose que le fichier d'analyse doit contenir 3 types de ligne différents.   
7. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\En-tête : Séquence 1..1 ».
    * L'élément Root\Line\Types\Header de type SEQUENCE contient l'élément STRING imbriqué dont la valeur a été définie comme valeur de chaîne fixe. Cette séquence analyse la ligne d'en-tête du fichier d'analyse.   
8. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\Enregistrement: Séquence 1..1 (,) ».
    * L'élément Root\Line\Types\Record de type SEQUENCE a été configuré pour analyser les lignes de transaction. Notez que l'option de caractère « Séparateur personnalisé » a été configurée comme virgule. Cela signifie que la virgule est utilisée comme séparateur de champs pour ce type de ligne dans le fichier d'analyse.   
    * Notez que plusieurs éléments imbriqués de différents types de données ont été ajoutés pour l'élément Root\Line\Types\Record afin d'analyser les lignes de la transaction en tant que champs séparés. Notez que l'option « Application de devis » a été configurée avec « Aucun ». Cela signifie que dans le fichier d'analyse, tous les champs de ce type seront considérés comme n'ayant pas de caractères inclus.   
9. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\Enregistrement : Séquence 1..1 (,)TransactionDate : DateTime ».
    * Par exemple, l'élément Root\Line\Types\Record\TransactionDate de type DATETIME a été configuré pour extraire la valeur de date et d'heure de la transaction du fichier d'analyse au format « J/m/aaaa ».   
10. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\Enregistrement : Séquence 1..1 (,)\CountryCode : Chaîne 0..1 ».
    * Notez que l'élément Root\Line\Types\Record\CountryCode du type STRING a été configuré avec l'option « Zéro un » dans le champ « Multiplicité ». Ce paramètre prend en compte la valeur du champ CountryCode dans la ligne d'analyse comme facultative.   
11. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\Enregistrement : Séquence 1..1 (,)\Remarque : Séquence 1..1 (,) ».
    * Notez que l'élément Root\Line\Types\Record\Remark du type SEQUENCE a été configuré avec l'option « Tous » dans le champ « Application de devis » et le caractère double entre guillemets dans le champ « Guillemets ». Cela signifie que tous les champs de ce type de ligne dans le fichier d'analyse (décrits par les éléments imbriqués: Texte du type STRING) seront considérés comme encadrés par des guillemets.  
12. Dans l'arborescence, sélectionnez « Entrant : Fichier\Racine : Séquence\Ligne : Séquence 1..* \Types : Incident\Non analysé : Séquence 1..1 ».
    * L'élément Root\Line\Types\Unparsed du type SEQUENCE a été configuré pour analyser les lignes de transaction de la structure qui ne correspond pas à celle décrite ci-dessus dans l'élément CASE parent.   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Passer en revue les paramètres de la mise en correspondance des formats vers un modèle de données
1. Cliquez sur Mettre en correspondance vers le modèle.
    * La mise en correspondance de modèle « Mise en correspondance avec le modèle à partir du format CSV » décrit le flux de données du transfert de données depuis le fichier CSV entrant vers le modèle de données.   
2. Cliquez sur Concepteur.
3. Dans l'arborescence, développez « format ».
    * Notez que le format conçu s'affiche ici comme un composant de source de données.  
4. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant) ».
5. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine) ».
6. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence(Racine)\Ligne : Séquence 1..*(Ligne) ».
7. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine)\Ligne : Séquence 1..*(Ligne)\Types : Incident (Types) ».
8. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine)\Ligne : Séquence 1..*(Ligne)\Types : Incident (Types)\Enregistrement : Séquence 1..1 (,)(Enregistrement) ».
9. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine)\Ligne : Séquence 1..*(Ligne)\Types : Incident (Types)\Enregistrement : Séquence 1..1 (,)\(Enregistrement)Données ».
10. Dans l'arborescence, développez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine)\Ligne : Séquence 1..*(Ligne)\Types : Incident (Types)\Enregistrement : Séquence 1..1 (,)(Enregistrement\)Données\CountryCode : Chaîne 0..1 (CountryCode) ».
11. Dans l'arborescence, sélectionnez « format\Entrant : Fichier (Entrant)\Racine : Séquence (Racine)\Ligne : Séquence 1..*(Ligne)\Types : Incident (Types)\Enregistrement : Séquence 1..1 (,)(Enregistrement)\Données\TransactionDate : DateTime(TransactionDate) ».
    * Notez que les éléments de format obligatoires et facultatifs, tels que TransactionDate et CountryCode, sont différents dans le composant de source de données « format » prédéfini.   
12. Dans l'arborescence , développez « Transactions = $both ».
    * Notez que les éléments du format qui définit la structure du fichier importé sont associés aux éléments du modèle de données. Selon ces liens, le contenu du fichier CSV importé sera enregistré au moment de l'exécution dans le modèle de données existant. Soyez attentif à la liaison de l'élément CountryRegion. Pour tout élément de transaction dans le fichier entrant dont la valeur de code pays n'est pas spécifiée, le code pays par défaut « États-Unis » est renseigné dans le modèle de données.   
13. Activez « Afficher les détails ».
14. Cliquez sur l'onglet Validations.
15. Cliquez sur Recherche.
16. Dans le champ Rechercher, tapez « fournisseur ».
17. Cliquez sur Suivant
    * Cette mise en correspondance de format peut contenir la logique définie par l'utilisateur pour valider la précision des données importées d'un point de vue de l'entreprise. Par exemple, en fonction du paramètre, pour toute ligne du fichier d'importation dont la structure ne correspond pas à celle de la ligne d'en-tête ou de la ligne de transaction, un message d'avertissement sera généré dans la fenêtre Informations informant l'utilisateur sur l'incident et indiquant le numéro de séquence de la transaction dans le fichier.   
18. Fermez la page.

## <a name="run-the-format-mapping"></a>Exécuter la mise en correspondance des formats
À des fins de test, exécutez la mise en correspondance des formats à l'aide du fichier 1099entriescsv.csv que vous avez précédemment téléchargé. La sortie générée contient les données importées depuis le fichier CSV sélectionné et transférées vers le modèle de données personnalisé au moment de l'importation réelle.   
1. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et accédez au fichier 1099entriescsv.csv que vous avez précédemment téléchargé.  
2. Cliquez sur OK.
    * Notez les messages d'avertissement sur les lignes qui ne sont pas acceptées. La ligne 4 contient la valeur de revenus qui s'affiche dans un format non acceptable tandis que la ligne 7 ne contient pas le texte des remarques sur la transaction entre guillemets.   
    * Examinez la sortie au format XML, qui représente les données importées depuis le fichier sélectionné et transférées vers le modèle de données. Notez que toutes les 7 lignes du fichier CSV importé ont été traitées. Les titres des champs sur la ligne 1 ont été ignorés, 4 transactions ont été correctement analysées et 2 transactions ont été reconnues comme non valides.   
3. Fermez la page.
4. Fermez la page.

