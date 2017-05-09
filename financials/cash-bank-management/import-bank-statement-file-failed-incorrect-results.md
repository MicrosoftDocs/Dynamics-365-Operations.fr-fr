---
title: "Dépannage d&quot;importation de fichier de relevé bancaire"
description: "Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 for Operations. En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement. Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects. Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire. Cet article décrit comment résoudre ces différences ainsi que les problèmes."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: 9717cf2f36033efe8465906324966242977c6eb2
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-file-import-troubleshooting"></a>Dépannage d'importation de fichier de relevé bancaire

[!include[banner](../includes/banner.md)]


Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 for Operations. En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement. Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects. Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire. Cet article décrit comment résoudre ces différences ainsi que les problèmes.

<a name="what-is-the-error"></a>Quelle est l'erreur ?
------------------

Une fois que vous avez essayé d'importer un fichier de relevé bancaire, allez dans l'historique des tâches de gestion des données et ses détails d'exécution pour trouver l'erreur. L'erreur peut aider en pointant vers le relevé, le solde ou la ligne de relevé. Toutefois, il est peu probable qu'elle fournisse assez d'informations pour vous aider à identifier le champ ou l'élément qui provoque le problème.

## <a name="what-are-the-differences"></a>Quelles sont les différences ?
Comparez la définition bancaire de la mise en page de fichier à la définition d'importation de Microsoft Dynamics 365 for Operations, et notez les différences dans les champs et les éléments. Comparez le fichier de relevé bancaire à l'exemple de fichier Dynamics 365 for Operations associé. Dans les fichiers ISO20022, il est facile d'afficher toutes les différences.

## <a name="transformations"></a>Transformations
Généralement, la modification doit être effectuée dans l'une des trois transformations. Chaque transformation concerne une norme spécifique.

| Nom de la ressource                                         | Nom de fichier                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Transformations de débogage
### <a name="adjust-the-bai2-and-mt940-files"></a>Modifiez les fichiers BAI2 et MT940

Les fichiers BAI2 et MT940 sont basés sur des fichiers texte et exigent un ajustement pour activer le débogage Extensible Stylesheet Language Transformations (XSLT). Le programme effectue cet ajustement lors de l'importation d'un fichier.

1.  Créez un fichier XML, puis copiez le texte suivant dans celui-ci.

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Copiez le contenu du fichier de relevé bancaire, et collez-le dans le fichier XML afin qu'il remplace **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Déboguer un XSLT

Pour plus d'informations, voir <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Démarrez Microsoft Visual Studio.
2.  Créez une application de console.
3.  Ouvrez le XSLT approprié.
4.  Cliquez sur le XLST et sa page de propriétés.
5.  Définissez l'entrée de l'emplacement du fichier de relevé bancaire.
6.  Définissez un emplacement et un nom de fichier pour le résultat.
7.  Définissez les points d'arrêt requis.
8.  Dans le menu, cliquez sur **XML** &gt; **Démarrer le débogage XSLT**.

### <a name="format-the-xslt-output"></a>Mettre en forme le résultat XSLT

Lorsque la transformation est exécutée, elle crée un fichier de sortie visible dans Visual Studio. Faites Ctrl+A, Ctrl+K, et Ctrl+D pour mettre en forme rapidement le fichier de sortie.

### <a name="adjust-the-transformation"></a>Ajuster la transformation

Ajustez la transformation pour obtenir le champ ou l'élément approprié dans le fichier de relevé bancaire. Mappez ensuite ce champ ou cet élément à l'élément Dynamics 365 for Operations approprié.

### <a name="debitcredit-indicator"></a>Indicateur de débit/crédit

Parfois, les débits peuvent être importés en tant que crédits, et des crédits peuvent être importés en tant que débits. Pour résoudre ce problème, vous devez modifier le XSLT approprié. Si des relevés bancaires proviennent de plusieurs banques, assurez-vous qu'elles utilisent toutes la même méthode de débit/crédit, ou créez des transformations distinctes.

-   Modèle BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator
-   Modèle ISO20022XML-to-Reconcilation.xslt GetCreditDebit
-   Modèle MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemples de formats de relevé bancaire et de mises en page techniques
Le tableau suivant répertorie des exemples de définitions de mise en page techniques de fichier d'importation de rapprochement bancaire avancé et trois fichiers d'exemples de relevé bancaire associés : Vous pouvez télécharger les fichiers d'exemple et les dispositions techniques ici : https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Définition de mise en page technique                             | Fichier d'exemple de relevé bancaire          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |






