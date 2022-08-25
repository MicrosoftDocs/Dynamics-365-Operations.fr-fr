---
title: Préparer les métadonnées d’application à utiliser dans RCS
description: Cet article décrit comment créer une nouvelle configuration de rapports contenant les métadonnées de l’application.
author: kfend
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: a9ccbb120be43eaf7a8ae8b5bf8eaafb4850b199
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289972"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Préparer les métadonnées d’application à utiliser dans RCS
[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d’états électroniques peut créer une nouvelle configuration de génération d’états électroniques (ER) contenant les métadonnées de l’application pour concevoir les configurations de mise en correspondance de modèle ER dans le service RCS (Regulatory Configuration Service). Cette configuration sera utilisée pour concevoir un exemple de configuration de mise en correspondance de modèle ER pour accéder à des transactions de commerce extérieur. Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cet article [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="prerequisites"></a>Conditions préalables
1.    Accédez à **Administration d’organisation** > **Espaces de travail** > **États électroniques**. 
2.    Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). 
3.    Cliquez sur **Configuration des métadonnées**. 
4.    Supposons que nous utilisons RCS pour créer une solution ER pour une application Finance et Opérations générera des documents électroniques contenant les informations du commerce extérieur. Pour spécifier la mise en correspondance entre le modèle de données ER et les sources de données nécessaires, nous devons avoir accès dans RCS aux métadonnées de l’application Finance et Opérations. Par conséquent, dans le cadre de la conception de la solution ER, nous devons paramétrer une nouvelle configuration de métadonnées ER contenant toutes les métadonnées actuellement requises pour générer des les états électroniques pour le domaine d’activité sélectionné. 

## <a name="add-metadata-configuration"></a>Ajouter une configuration des métadonnées 
1.    Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue. 
2.    Dans le champ **Nom**, tapez « Métadonnées du commerce extérieur ». 
3.    Cliquez sur **Créer une configuration**. 
4.    Cliquez sur **Concepteur**. 
5.    Cliquez sur **Ajouter**. 
  
> [!NOTE]
> Vous pouvez sélectionner toutes les métadonnées pour l’application entière, ou pour des modèles ou des modules sélectionnés. Notez que dans ce cas les métadonnées suivantes sont automatiquement ajoutées : tables des enregistrements, énumérations, et types de données étendus (EDT, Extended Data Types). Lorsque d’autres types de métadonnées sont requis, ils doivent être ajoutés manuellement. 
 
Nous avons des métadonnées relatives aux transactions de commerce extérieur en sélectionnant manuellement les éléments de métadonnées. 
  
6.    Cliquez sur **Ajouter une source de données**. 
7.    Cliquez sur **Enregistrements de la table**. 
8.    Utilisez le filtre rapide pour filtrer sur le champ **Nom** avec une valeur « déclaration d’échanges de biens ». 
9.    Sélectionnez l’enregistrement de table **Déclaration d’échanges de biens**. 
10.    Cliquez sur **OK**.
  
Nous avons ajouté des informations de métadonnées sur la table d’enregistrements de la déclaration d’échanges de biens. 
  
11.    Dans l’arborescence, développez **Enregistrements de table Déclaration d’échanges de biens**\>**Relations**. 
12.    Dans l’arborescence, sélectionnez **Enregistrements de table Déclaration d’échanges de biens**\>**Relations\IntrastatCommodity (Enregistrements de table EcoResCategory)**.     
13.    Cliquez sur **Ajouter des métadonnées**. 
  
> [!NOTE]
> Les métadonnées sur les relations requises pour la table d’enregistrements sélectionnée doivent être ajoutées manuellement. 
  
16.    Cliquez sur **Ajouter une source de données**. 
17.    Cliquez sur **Énumération**. 
18.    Utilisez le filtre rapide pour filtrer sur le champ **Nom** avec une valeur « IntrastatDirection ». 
19.    Sélectionnez l’enregistrement d’énumération **IntrastatDirection**. 
20.    Cliquez sur **OK**. 
21.    Cliquez sur **Enregistrer**.  
22.    Fermez la page. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Compléter la version temporaire de la configuration de métadonnées
1.    Cliquez sur **Modifier le statut**. 
2.    Cliquez sur **Terminé.** 
3.    Cliquez sur **OK**. 
4.    Sélectionnez la version **1** terminée. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Exporter la version achevée de la configuration des métadonnées à partir de l’application dans un fichier XML
1.    Cliquez sur **Exchange**. 
2.    Cliquez sur **Exporter en tant que fichier XML**. 
3.    Cliquez sur **OK**. 
    
La configuration de métadonnées ER créée a été enregistrée comme fichier XML qui peut être importé dans RCS et utilisé comme source d’informations sur les métadonnées du domaine du commerce extérieur. Sur la base de ces informations, nous pouvons spécifier le mappage entre les métadonnées d’application et le modèle de données ER.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
