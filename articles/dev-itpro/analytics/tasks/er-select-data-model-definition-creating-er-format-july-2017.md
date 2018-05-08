--- 
title: "Sélectionner la définition du modèle de données lors de la création du format pour la gestion des états électroniques (ER)"
description: "Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Créer un fournisseur de configuration et le marquer comme actif."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 70d928b0f0807731a5f96ef5497fb6060fbfebf5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="select-data-model-definition-while-creating-format-for-electronic-reporting-er"></a>Sélectionner la définition du modèle de données lors de la création du format pour la gestion des états électroniques (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Créer un fournisseur de configuration et le marquer comme actif. 

Cette procédure indique comment l'élément racine d'un modèle peut être sélectionné comme définition du modèle de données pour insérer une configuration du format ER conçue pour générer des documents électroniques. Dans cette procédure, vous ajouterez une nouvelle configuration du format ER pour la société fictive, Litware, Inc. 

Cette procédure est destinée aux utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Les étapes peuvent être effectuées à l'aide de n'importe quel ensemble de données.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, Créer un fournisseur de configuration et le marquer comme actif.  
2. Cliquez sur Configurations des états.

## <a name="add-a-new-er-data-model-configuration"></a>Ajouter une nouvelle configuration du modèle de données ER
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
    * Nous ajoutons une nouvelle configuration de modèle ER contenant un modèle de données conçu pour être utilisé comme source de données pour la génération d'états ER.  
2. Dans le champ Nom, tapez « Modèle de paiement (fictif) ».
    * Modèle de paiement (fictif)  
3. Cliquez sur Créer une configuration.
4. Cliquez sur Concepteur.
    * Ouvrez le concepteur ER pour spécifier la structure du modèle de données de cette configuration.  
    * Supposons que nous concevions le modèle de données pour le domaine des paiements pour prendre en charge 2 modes de paiement : virement et débit direct.  
5. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
6. Dans le champ Nom, tapez « Paiements – virement ».
    * Paiements – virement  
7. Cliquez sur Ajouter.
8. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
9. Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».
10. Dans le champ Nom, tapez « Paiements – débit direct ».
    * Paiements – débit direct  
11. Cliquez sur Ajouter.
12. Cliquez sur Enregistrer.
13. Fermez la page.
14. Cliquez sur Modifier le statut.
    * Exécutez la version brouillon du modèle pour la rendre disponible dans les nouvelles mises en correspondance et les nouveaux formats de modèle.  
15. Cliquez sur Terminé.
16. Cliquez sur OK.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Commencer à entrer une nouvelle configuration du format ER
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de paiement (fictif) ».
3. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
    * Notez que tous les éléments racine du modèle de données sélectionné peuvent être sélectionnés comme définition du modèle de données. Vous pouvez continuer à créer votre format à l'aide des éléments racine requis du modèle de données. Une mise en correspondance de modèle manquante pour l'élément racine sélectionné ne vous empêche pas de continuer.  
4. Fermez la page.

## <a name="add-a-new-er-model-mapping-configuration"></a>Ajouter une nouvelle configuration de mise en correspondance du modèle de données ER
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Modèle de paiement (fictif) ».
3. Dans le champ Nom, tapez « Mises en correspondance de modèle de paiement (fictives) ».
    * Mises en correspondance de modèle de paiement (fictives)  
4. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
5. Cliquez sur Créer une configuration.

## <a name="design-er-model-mappings"></a>Créer des mises en correspondance de modèle ER
1. Cliquez sur Concepteur.
    * Utilisez le concepteur ER pour spécifier les mises en correspondance de modèle pour les éléments racine requis.  
2. Cliquez sur Concepteur.
    * Simulez le paramétrage de la mise en correspondance de modèle sélectionnée pour l'élément racine du modèle sélectionné.  
3. Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de tables ».
4. Cliquez sur Ajouter racine.
5. Dans le champ Nom, tapez « Comptabilité ».
6. Dans le champ Table, tapez « LedgerJournalTrans ».
    * LedgerJournalTrans  
7. Cliquez sur OK.
8. Cliquez sur Enregistrer.
9. Fermez la page.
10. Fermez la page.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Commencer à entrer une nouvelle autre configuration du format ER
1. Dans l'arborescence, sélectionnez « Modèle de paiement (fictif) ».
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de paiement (fictif) ».
4. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
    * Notez qu'un seul élément racine est désormais disponible pour la mise en correspondance avec les sources de données d'application. Si au moins une mise en correspondance de modèle est introduite, seuls les éléments racine du modèle qui sont mis en correspondance avec les sources de données d'application peuvent être sélectionnés comme définition de modèle lorsque le format ER est ajouté.   
5. Fermez la page.


