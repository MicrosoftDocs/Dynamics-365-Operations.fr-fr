--- 
title: "Modifier un format de gestion d'états électroniques en réappliquant un modèle Microsoft Excel (ER)"
description: "Pour réaliser les étapes de cette procédure, vous devez d'abord effectuer la procédure, ER - Concevoir une configuration pour générer des états au format OPENXML »."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: 2f35727376812b0de428ce929ebe0d33bc497984
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="modify-a-format-by-reapplying-a-microsoft-excel-template-for-electronic-reporting-er"></a>Modifier un format de gestion d'états électroniques en réappliquant un modèle Microsoft Excel (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser les étapes de cette procédure, vous devez d'abord effectuer la procédure, ER - Concevoir une configuration pour générer des états au format OPENXML ».

Cette procédure explique comment modifier une configuration du format ER en réappliquant un modèle Microsoft Excel modifié. Dans cette procédure, vous importerez un modèle Excel modifié dans les configurations du format ER qui ont été créées pour la société fictive, Litware, Inc., puis générerez des documents électroniques. Cette procédure est destinée aux utilisateurs disposant du rôle Administrateur système ou Développeur d'états électroniques. Ces étapes peuvent être effectuées à l'aide de l'ensemble de données GBSI. Avant de commencer, téléchargez et enregistrez le fichier, SampleVendPaymWsReport2.xlsx, répertorié dans la rubrique d'aide, Modifier un format de gestion d'états électroniques en réappliquant un modèle Excel (modify-electronic-reporting-format-reapply-excel-template/).

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, Créer un fournisseur de configuration et le marquer comme actif.  

## <a name="select-the-er-format"></a>Sélectionner le format ER
1. Cliquez sur Configurations des états.
2. Dans l'arborescence, développez « Payment model ».
3. Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.
4. Cliquez sur Documents joints.
    * Notez que le fichier Excel SampleVendPaymWsReport.xlsx est actuellement utilisé comme modèle pour le traitement du journal des paiements.   
5. Cliquez sur Ouvrir.
    * Cliquez sur Ouvrir pour examiner la mise en page du modèle Excel.  
    * Examinez le modèle. Notez qu'il contient actuellement les détails suivants pour chaque ligne de paiement : le numéro de compte du fournisseur, le nom du fournisseur, la banque, le numéro d'acheminement, le numéro de compte, le débit, le crédit et la devise. Pour cet exemple, nous souhaitons étendre cette liste en ajoutant des détails sur la date de paiement.   
6. Fermez la page.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Réappliquer un nouveau modèle Excel au format ER
1. Cliquez sur Concepteur.
    * Ouvrez la version brouillon du format ER sélectionné pour modification.  
2. Cliquez sur Importer dans le volet Actions.
3. Cliquez sur Mettre à jour à partir d'Excel.
    * Cliquez sur « Mettre à jour le modèle », puis sélectionnez le fichier, SampleVendPaymWsReport2.xlsx.  
    * Cliquez sur Mettre à jour le modèle et naviguez pour accéder au fichier SampleVendPaymWsReport2.xlsx précédemment téléchargé.  
4. Cliquez sur OK.
    * Le modèle SampleVendPaymWsReport2.xlsx est appliqué. La structure du format ER est synchronisée avec le contenu du modèle, dont les éléments sont ajoutés au format ER. Tous les éléments existants dans le format ER qui ne sont pas inclus dans le modèle sont supprimés de la définition du format.  
5. Dans l'arborescence, sélectionnez « Excel ».
    * Notez que le champ Modèle contient désormais une référence au nouveau modèle.   
6. Cliquez sur Documents joints.
7. Cliquez sur Ouvrir.
    * Cliquez sur Ouvrir pour examiner la mise en page du modèle Excel modifié.  
    * Examinez le modèle. Notez qu'il contient maintenant une ligne pour la date de paiement.   
8. Fermez la page.
9. Dans l'arborescence, développez « Excel ».
10. Dans l'arborescence, développez « Excel\PaymLines ».
11. Dans l'arborescence, sélectionnez « Excel\PaymLines\PaymDate ».
    * Notez que le format ER contient maintenant un élément de plus. Une cellule, PaymDate, a été ajoutée au modèle Excel.  
12. Cliquez sur l'onglet Mise en relation.
13. Dans l'arborescence , développez « model ».
14. Dans l'arborescence, développez model\Payments.
15. Dans l'arborescence, sélectionnez « modèle\Paiments\Date de transaction(TransactionDate) ».
16. Cliquez sur Lier.
    * Spécifiez les données ajoutées à la nouvelle cellule au moment de l'exécution.  
17. Cliquez sur Enregistrer.
18. Fermez la page.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Activer la version brouillon modifiée du format ER à utiliser dans le traitement du journal des paiements
1. Dans le volet Actions, cliquez sur Configurations.
2. Cliquez sur Paramètres utilisateur.
3. Sélectionnez Oui dans le champ Paramètres d'exécution.
4. Cliquez sur OK.
5. Cliquez sur Modifier.
6. Sélectionnez Oui dans le champ Exécuter le brouillon.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Utiliser la version brouillon modifiée du format ER pour le traitement du journal des paiements
    * Examinez la feuille de calcul créée, notamment les nouveaux détails des lignes de paiement – date de paiement.  


