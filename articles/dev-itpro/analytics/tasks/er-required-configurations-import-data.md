---
title: ER Créer des configurations pour importer des données d'un fichier externe
description: Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut concevoir des configurations de format pour la génération d'états électroniques (ER) pour importer des données dans une application Dynamics 365 for Finance and Operations, Enterprise Edition à partir d'un fichier externe.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6675f35c9ec163a620e63af32ecdbff02197d3c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551182"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER Créer des configurations pour importer des données d'un fichier externe

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut concevoir des configurations de format pour la génération d'états électroniques (ER) pour importer des données dans une application Dynamics 365 for Finance and Operations, Enterprise Edition à partir d'un fichier externe. Dans cet exemple, vous allez créer les configurations ER requises pour l'exemple de société, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord effectuer les étapes du Guide de tâche, « ER Créer un fournisseur de configuration et le marquer comme actif. » Ces étapes peuvent être effectuées à l'aide de l'ensemble de données USMF. Vous devez également télécharger et enregistrer localement les fichiers suivants à l'aide des liens de la rubrique Vue d'ensemble des états électroniques (https://go.microsoft.com/fwlink/?linkid=852550): 1099model.xml, 1099format.xml, 1099entries.xml, 1099entries.xlsx.

    * La génération d'états électroniques offre aux utilisateurs professionnels la capacité de configurer le processus d'importation des fichiers de données externes vers des tables dans Dynamics 365 for Finance and Operations, Enterprise Edition, au format .XML ou .TXT. Tout d'abord, un modèle de données abstrait et une configuration de modèle de données de génération d'états électroniques doivent être conçus pour représenter les données que vous importez. Ensuite, vous devez définir la structure du fichier que vous importez et la méthode à utiliser pour déplacer les données du fichier vers le modèle de données abstrait. La configuration du format ER qui correspond au modèle de données conçu doit être créée pour le modèle de données abstrait. Enfin, la configuration du modèle de données doit être étendue avec une mise en correspondance décrivant comment les données importées restent des données de modèle de données abstrait, et comment elles sont utilisées pour la mise à jour des tables dans Dynamics 365 for Finance and Operations, Enterprise Edition.  La configuration du modèle de données ER doit être complétée avec une nouvelle mise en correspondance de modèle qui décrit la liaison du modèle de données aux destinations de l'application.  
    * Le scénario suivant montre les fonctionnalités d'importation de données de génération d'états électroniques. Cela inclut les transactions fournisseur suivies en externe, puis importées dans Dynamics 365 for Finance and Operations, Enterprise Edition afin d'être déclarées ultérieurement dans le Règlement fournisseur pour les déclarations d'honoraires.   

## <a name="add-a-new-er-model-configuration"></a>Ajouter une nouvelle configuration du modèle ER
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc. est disponible et marqué comme actif. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».   
2. Cliquez sur Configurations des états.
    * Plutôt que de créer un modèle pour prendre en charge l'importation de données, chargez le fichier, 1099model.xml, que vous avez précédemment téléchargé. Ce fichier contient le modèle personnalisé de données des transactions des fournisseurs. Ce modèle de données est mis en correspondance avec les composants de données de Dynamics 365 for Finance and Operations, Enterprise Edition situés dans l'entité de données AOA.   
3. Cliquez sur Échanger.
4. Cliquez sur Charger depuis le fichier XML.
    * Cliquez sur Parcourir et accédez au fichier 1099model.xml que vous avez précédemment téléchargé.  
5. Cliquez sur OK.
6. Dans l'arborescence, sélectionnez « Modèles de paiements de déclaration des honoraires »

## <a name="review-data-model-settings"></a>Passer en revue les paramètres de modèle de données
1. Cliquez sur Concepteur.
    * Ce modèle est conçu pour représenter les transactions des fournisseurs du point de vue de l'entreprise et est distinct de l'implémentation dans Dynamics 365 for Finance and Operations, Enterprise Edition.   
2. Dans l'arborescence, développer « 1099-MISC ».
3. Dans l'arborescence, sélectionnez « 1099-MISC\Transactions ».
4. Dans l'arborescence, développer « 1099-MISC\Transactions ».
    * L'Élément de transactions de ce modèle représente des transactions individuelles. Les éléments enfant permettent de spécifier les informations requises, tels que le compte fournisseur et la date de transaction, pour chaque transaction.   
5. Fermez la page.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Ajouter une nouvelle configuration du format ER prenant en charge l'importation de données
    * Les étapes de cette sous-tâche montrent comment une configuration de format peut être créée pour gérer l'importation de données à partir de fichiers externes.   
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Dans le champ Nouveau, entrez « Format basé sur le modèle de données modèle de paiements de déclaration des honoraires ».
3. Sélectionnez Oui dans le champ Prend en charge l'importation de données.
4. Appuyez sur la touche Échap pour fermer cette page.
    * Plutôt que de créer un format pour prendre en charge l'importation de données, chargez le fichier 1099format.xml, que vous avez précédemment téléchargé. Ce fichier contient la structure définie du fichier que vous importez et la mise en correspondance de la structure au modèle de données personnalisé des transactions des fournisseurs.   
5. Cliquez sur Échanger.
6. Cliquez sur Charger depuis le fichier XML.
    * Cliquez sur Parcourir et accédez au fichier 1099format.xml que vous avez précédemment téléchargé.  
7. Cliquez sur OK.
8. Dans l'arborescence, développez « Modèle de paiements de déclaration des honoraires ».
9. Dans l'arborescence, sélectionnez « Modèle de paiements de déclaration des honoraires\Formats d'importation des transactions des fournisseurs ».

## <a name="review-format-settings"></a>Passer en revue les paramètres de format
1. Cliquez sur Concepteur.
2. Activez « Afficher les détails ».
3. Cliquez sur Développer/réduire.
4. Cliquez sur Développer/réduire.
    * Le format conçu représente la structure attendue du fichier externe. Ce fichier doit être au format XML et avoir l'élément racine de règlement. La transaction de chaque fournisseur est représentée par l'élément de transaction défini comme ayant une multiplicité de zéro-à-plusieurs Cela signifie que le fichier entrant peut contenir de zéro à de multiple transactions. Les éléments imbriqués de l'élément « Transaction » représentent les attributs d'une seule transaction. Notez que tous les attributs, excepté celui du pays, sont marqués comme obligatoires, ce qui signifie qu'ils doivent figurer dans le fichier d'importation.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Passer en revue les paramètres de la mise en correspondance des formats vers un modèle de données
1. Cliquez sur Mettre en correspondance vers le modèle.
    * La mise en correspondance de « Pour importer les transactions des fournisseurs » contient les règles de transfert de données du fichier XML entrant à partir de la partie sélectionnée du modèle de données personnalisé, qui est défini en sélectionnant la définition de 1099-MISC.  
2. Cliquez sur Concepteur.
3. Activez « Afficher les détails ».
4. Dans l'arborescence, développez « format : Enregistrement ».
5. Dans l'arborescence, sélectionnez « format : Enregistrement ».
    * Notez que le format conçu s'affiche ici comme un composant de source de données.  
6. Dans l'arborescence, développez « format : Enregistrement\*règlement : Élément 1..1 (règlement) : Enregistrement ».
7. Dans l'arborescence, développez « format : Enregistrement\*règlement : Élément XML 1..1 (règlement) : Enregistrement\transaction : Élément XML 0..* (transaction) : Liste d'enregistrements ».
8. Dans l'arborescence, développez « format : Enregistrement\*règlement : Élément XML 1..1 (règlement) : Enregistrement\transaction : Élément XML 0..* (transaction) : Liste d'enregistrements\*fournisseur : Élément XML 1..1 (fournisseur) : Enregistrement ».
9. Dans l'arborescence, développez « format : Enregistrement\*règlement : Élément XML 1..1 (règlement) : Enregistrement\transaction : Élément XML 0..* (transaction) : Liste d'enregistrements\*pays : Élément XML 0..1 (pays) : Enregistrement ».
10. Dans l'arborescence, sélectionnez « format : Enregistrement\*règlement : Élément XML 1..1 (règlement) : Enregistrement\transaction : Élément XML 0..* (transaction) : Liste d'enregistrements\*fournisseur : Élément XML 1..1 (fournisseur) : Enregistrement ».
    * Notez que la présentation des éléments de format obligatoires et facultatifs est différente dans le composant prédéfini de source de données « format ».  
11. Dans l'arborescence, développez « Transactions : Liste des enregistrements= format.settlement. '$enumerated ».
    * Notez que les éléments du format qui définit la structure du fichier importé sont associés aux éléments du modèle de données personnalisé. Selon ces liens, le contenu du fichier XML importé sera enregistré au moment de l'exécution dans le modèle de données existant. Soyez attentif à la liaison de l'élément de pays. Pour tout élément de transaction dans le fichier entrant ne comportant pas un tel élément, le code pays par défaut « États-Unis » sera renseigné dans le modèle de données.  
12. Cliquez sur l'onglet Validations.
    * Cette mise en correspondance de format peut contenir la logique définie par l'utilisateur pour valider la précision des données importées d'un point de vue de l'entreprise. Par exemple, en fonction du paramètre, pour toute transaction dans le fichier d'importation n'ayant pas de code pays défini, un message d'avertissement sera généré dans la fenêtre Informations informant l'utilisateur sur l'incident et indiquant le numéro de souche de la transaction.  
13. Fermez la page.

## <a name="run-the-format-mapping-to-the-data-model"></a>Exécuter la mise en correspondance des formats vers un modèle de données
    * Exécutez cette mise en correspondance de formats à des fins de test. Utilisez le fichier 1099entries.xml que vous avez précédemment téléchargé. Vous pouvez exporter ce fichier du classeur 1099entries.xlsx utilisé pour la gestion des transactions fournisseur. La sortie générée sera importée à partir fichier XML sélectionné et renseignera le modèle de données personnalisé au moment de l'importation réelle.  
1. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et accédez au fichier 1099entries.xml que vous avez précédemment téléchargé.  
2. Cliquez sur OK.
    * Vous remarquerez le message d'avertissement concernant le code pays manquant pour une transaction dans le fichier importé.  
    * Examinez la sortie au format XML, qui représente les données importées depuis le fichier sélectionné et déplacées vers le modèle de données.   
3. Fermez la page.
4. Fermez la page.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Passer en revue les paramètres de la mise en correspondance des modèles vers les destinations
1. Dans l'arborescence, sélectionnez « Modèles de paiements de déclaration des honoraires »
2. Cliquez sur Concepteur.
3. Cliquez sur Mettre en correspondance le modèle à la source de données.
    * La mise en correspondance « Pour l'importation des transactions manuelles de déclaration d'honoraires » a été définie avec le type Vers la direction de destination. Cela signifie qu'elle a été entrée pour prendre en charge l'importation de données et qu'elle contient le paramétrage des règles définissant la manière dont le fichier externe importé et persistant comme des données de modèle de données abstrait est utilisé pour la mise à jour des tables dans l'application Dynamics 365 for Finance and Operations, Enterprise Edition.  
4. Cliquez sur Concepteur.
5. Dans l'arborescence, développez « Modèle de données modèle de paiements de déclaration des honoraires ».
6. Dans l'arborescence, développez « modèle : Modèle de données modèle de paiements de déclaration des honoraires\Transactions : Liste d'enregistrements ».
    * Notez que le modèle conçu s'affiche ici comme un élément de source de données. Au moment de l'exécution, il contiendra les données importées depuis le fichier externe. Plusieurs tables ont été ajoutés comme éléments de source de données pour garantir que les données importées sont conformes aux données de la canditature actuelle, notamment si le compte fournisseur de transaction d'importation est disponible dans le système, si la combinaison de codes d'importation des pays et des états existe, etc.  
7. Dans l'arborescence, sélectionnez « modèle : Modèle de données modèle de paiements de déclaration des honoraires\Transactions : Liste d'enregistrements\$failed : Champ calculé = IF(OR (ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean ».
8. Cliquez sur Modifier.
9. Cliquez sur Modifier la formule.
    * Lorsque un contrôle au moins échoue pour une seule transaction importée, cette transaction sera marquée comme ayant échoué avec l'attribut de données source « $failed ».  
10. Fermez la page.
11. Cliquez sur Annuler.
12. Dans l'arborescence, sélectionnez « tax1099trans : Table "VendSettlementTax1099" enregistrements= model.Validated ».
13. Cliquez sur Modifier la destination.
    * Cette disposition de génération d'états électroniques a été ajoutée pour indiquer comment les données importées mettront à jour les tables d'application. Dans cet exemple, la table de données VendSettlementTax1099 a été sélectionnée. Comme l'action d'enregistrement Insérer a été sélectionnée, les transactions importées seront insérées dans la table VendSettlementTax1099. Notez qu'une seule mise en correspondance de modèle peut contenir plusieurs destinations. Cela signifie que les données importées peuvent être utilisées pour mettre à jour plusieurs tables de l'application à la fois. Les tables, les vues, et les entités de données peuvent être utilisées comme destination de génération d'états électroniques.   
    * Si la mise en correspondance est appelée à partir d'un point de l'application Dynamics 365 for Finance and Operations, Enterprise Edition (comme un bouton ou une option de menu) qui a été spécialement conçu pour cette action, la destination de génération d'états électroniques doit être marquée comme point d'intégration. Dans cet exemple, il s'agit du point ERTableDestination#VendSettlementTax1099.  
14. Cliquez sur Annuler.
15. Cliquer sur Afficher tout.
16. Cliquez sur Afficher les éléments mappés uniquement.
17. Dans l'arborescence, développez « tax1099trans : Table "VendSettlementTax1099" enregistrements= model.Validated ».
    * Notez que l'élément de source de données qui contient les seules transactions validées est lié à la destination créée. Vous pouvez filtrer les transactions importées pour ignorer celles qui sont incompatibles avec les données des applications.  
18. Dans l'arborescence, sélectionnez « échec : Table "VendSettlementTax1099Entity" enregistrements= model.Failed ».
19. Cliquez sur l'onglet Validations.
    * Cette mise en correspondance de modèle peut contenir la logique définie par l'utilisateur pour valider l'exactitude des données importées à partir des données de l'application existante. Par exemple, en fonction du paramètre présent, pour toute transaction dans le fichier importé ayant un compte fournisseur ne figurant pas dans le système, un message d'avertissement sera généré afin d'informer l'utilisateur et lui indiquer le code de compte fournisseur non valide.  
    * Notez que l'option Action de post-validation peut être utilisée pour chaque contrôle, pour indiquer si le processus d'importation doit être poursuivi ou arrêté, ainsi que si les insertions/mises à jour déjà effectuées peuvent être conservées ou annulées.  
20. Cliquez sur Afficher les éléments mappés uniquement.
21. Cliquer sur Afficher tout.
22. Fermez la page.
    * Exécutez cette mise en correspondance de modèle pour tester le format conçu et les mises en correspondance de modèle. Utilisez le fichier 1099entries.xml. Les données du fichier sélectionné seront importées dans le système.  
23. Cliquez sur Exécuter.
    * Notez que la boîte de dialogue ne contient aucune question supplémentaire sur la mise en correspondance des formats qui doit être utilisée pour analyser le fichier importé, puis pour déplacer les données vers le modèle de données. Cela est dû au fait qu'il n'existe actuellement qu'un format qui utilise ce modèle, qui est marqué comme conçu pour prendre en charge l'importation de données.  
    * Définissez l'ID N° document pour différencier les transactions importées des autres transactions qui peuvent avoir déjà été entrées manuellement ou importées.  
24. Dans le champ Entrez le N° document, tapez « IMPORT-001 ».
    * Naviguez pour accéder au fichier « 1099entries.xml ».  
25. Cliquez sur OK.
    * La liste des avertissements générés fournit des informations sur les comptes fournisseur non valides, un code zone de déclaration des honoraires incorrect, les codes pays manquants, et ainsi de suite. Comparez cette liste des avertissements au contenu inclus dans le fichier XML d'exécution.  
26. Fermez la page.
27. Fermez la page.
28. Fermez la page.
29. Fermez la page.
30. Accédez à Comptabilité fournisseur > Tâches périodiques > Taxe sur les honoraires > Règlement fournisseur pour les déclarations d'honoraires.
    * Cet écran affiche les transactions cumulatives dans la table Tax1099Summary créées selon les transactions importées.  
31. Dans le champ Date de début, définissez la date sur « 01-01-2000 ».
32. Cliquez sur Transactions manuelles de déclaration d'honoraires.
    * Cet écran contient la liste des transactions ajoutées manuellement et celles venant d'être importées.  
33. Ouvrez le filtre de colonne N° document.
34. Entrez la valeur de filtre « IMPORT-001 » dans le champ « N° document » à l'aide de l'opérateur de filtre « commence par ».

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Passer en revue la relation entre les mises en correspondance des modèles et des formats
1. Fermez la page.
2. Fermez la page.
3. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
4. Cliquez sur Configurations des états.
5. Dans l'arborescence, sélectionnez « Modèles de paiements de déclaration des honoraires »
    * Supposons que vous souhaitez prendre en charge l'importation des mêmes données, mais à partir d'un format de fichier .TXT.   
6. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue. 
7. Dans le champ Nouveau, entrez « Format basé sur le modèle de données modèle de paiements de déclaration des honoraires ».
8. Dans le champ Nom, tapez « Importer des données du fichier TXT ».
9. Sélectionnez Oui dans le champ Prend en charge l'importation de données.
10. Cliquez sur Créer une configuration.
11. Cliquez sur Concepteur.
12. Cliquez sur Mettre en correspondance vers le modèle.
13. Cliquez sur Nouveau.
14. Saisissez ou sélectionnez une valeur dans le champ Définition.
    * Sélectionnez l'option « 1099-MISC ».  
15. Dans le champ Nom, tapez « Importer des données du fichier TXT ».
16. Dans le champ Description, tapez « Importer des données du fichier TXT ».
17. Cliquez sur Enregistrer.
18. Fermez la page.
19. Fermez la page.
20. Cliquez sur Modifier.
    * Si vous avez installé le correctif « Support 4012871 de mises en correspondance des modèles GER dans des configurations séparées avec la possibilité de spécifier différents types de conditions préalables afin de les déployer dans différentes versions de Dynamics 365 for Finance and Operations, Enterprise Edition » (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871), exécutez l'étape suivante « Activer l'indicateur "Valeur par défaut de la mise en correspondance des modèles" pour la configuration de format entrée ». Sinon, passez à l'étape suivante.  
21. Sélectionnez Oui dans le champ Valeur par défaut de la mise en correspondance des modèles.
22. Dans l'arborescence, sélectionnez « Modèles de paiements de déclaration des honoraires »
23. Cliquez sur Concepteur.
24. Cliquez sur Mettre en correspondance le modèle à la source de données.
25. Cliquez sur Exécuter.
    * Si vous avez installé le correctif, 4012871 Prise en charge des mises en correspondance des modèles GER dans des configurations séparées avec la possibilité de spécifier différents types de conditions préalables afin de les déployer dans différentes versions de Dynamics 365 for Finance and Operations, Enterprise Edition (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871), sélectionnez la mise en correspondance des modèles préférée dans le champ de recherche. Si vous n'avez pas encore installé le correctif, passez à l'étape suivante, la mise en correspondance ayant déjà été sélectionnée par la définition de la configuration de format par défaut.  
    * Si vous n'avez pas installé le correctif, KB 4012871, notez que la boîte de dialogue contient une question de mise en correspondance de modèles supplémentaire utilisée pour analyser le fichier importé. Les données sont alors déplacées de la boîte de dialogue vers le modèle de données. Actuellement, vous pouvez choisir la mise en correspondance de format à utiliser en fonction du type de fichier que vous envisagez d'importer.  
    * Si vous envisagez d'appeler cette mise en correspondance de modèles à partir d'un point de Dynamics 365 for Finance and Operations, Enterprise Edition qui est spécialement conçu pour l'action, la destination ER et la mise en correspondance des formats doivent être marquées comme faisant partie de l'intégration.  
26. Cliquez sur Annuler.
27. Fermez la page.
28. Fermez la page.

