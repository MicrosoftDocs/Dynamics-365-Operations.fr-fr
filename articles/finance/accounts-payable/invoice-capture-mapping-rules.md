---
title: Règles de mappage de la solution Invoice capture
description: Cet article fournit des informations sur la configuration des règles de mappage dans la solution Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691178"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Règles de mappage de la solution Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les règles de mappage apportent des données de base de Microsoft Dynamics 365 Finance ou le système de planification des ressources d’entreprise (ERP). Une fois les règles de mappage configurées, les informations requises pour créer des factures fournisseur dans Finance sont dérivées. Lorsque des règles de mappage sont utilisées, l’assistant Comptabilité fournisseur vérifie le statut au lieu de remplir manuellement toutes les valeurs de champ manquantes.

Il existe quatre types de règles de mappage :

- Entité juridique
- Compte fournisseur
- Article
- Type de dépense

## <a name="manage-mapping-rules-by-using-the-app"></a>Gérer les règles de mappage à l’aide de l’application

Pour gérer les règles de mappage à l’aide de l’application, sélectionnez **Configuration**. L’onglet **Configuration de la règle de mappage** propose quatre options :

- Entité juridique 
- Compte fournisseur 
- Mise en correspondance d’éléments 
- Type de dépense

Par exemple, vous sélectionnez l’option **Règles d’entités juridiques de mise en correspondance**. Le code d’entité juridique est identifié en utilisant le nom, l’adresse et le numéro d’enregistrement fiscal de la société. Pour une règle nommée **LE-USPM**, si le nom de la société contient le texte « Contoso Robotics USA », le code de l’entité juridique est **USPM**.

La page affiche toutes les règles de mise en correspondance actives. Si vous souhaitez afficher les règles de mappage inactives, sélectionnez **Règles d’entité juridique de mise en correspondance actives**, puis sélectionnez **Règles d’entité juridique de mise en correspondance inactives**.

Les actions suivantes sont disponibles pour les règles de mise en correspondance.

### <a name="create-a-mapping-rule"></a>Création d’une règle de mise en correspondance

Vous pouvez utiliser deux méthodes pour créer une règle de mise en correspondance :

- Sélectionnez **Nouveau** pour créer une règle de mise en correspondance. Entrez ensuite les informations de la règle de mise en correspondance. La valeur **Nom de la règle** doit être unique pour chaque type de règle de mise en correspondance.
- Si vous sélectionnez une règle de mise en correspondance existante, le bouton **Copier** devient disponible. Sélectionnez-le, puis sélectionnez **OK** dans la boîte de dialogue qui s’affiche. Une règle de mise en correspondance est créée en dupliquant la règle sélectionnée.

### <a name="edit-a-mapping-rule"></a>Modifier une règle de mise en correspondance

Pour modifier une règle de mise en correspondance, sélectionnez un champ et modifiez la valeur.

### <a name="activatedeactivate-mapping-rules"></a>Activer/désactiver les règles de mise en correspondance

Pour désactiver une ou plusieurs règles de mise en correspondance, sélectionnez-les sur la page **Règles de mise en correspondance actives**, puis sélectionnez **Désactiver**. Les règles sont déplacées de la page **Règles de mise en correspondance actives** à la page **Règles de mise en correspondance inactives**.

De même, pour activer une ou plusieurs règles de mise en correspondance, sélectionnez-les sur la page **Règles de mise en correspondance inactives**, puis sélectionnez **Activer**.

### <a name="remove-mapping-rules"></a>Supprimer les règles de mise en correspondance

Pour supprimer les règles de mise en correspondance, sélectionnez-les et sélectionnez **Supprimer**.

### <a name="check-for-conflicts"></a>Rechercher des conflits

Si deux règles de mise en correspondance ont les mêmes valeurs **Entité juridique** et **Compte fournisseur**, mais différentes valeurs **Nom de l’article**, un conflit est détecté et la règle de mise en correspondance n’est ni créée ni mise à jour.

## <a name="importexport-mapping-rules-from-excel"></a>Importer/exporter des règles de mise en correspondance depuis Excel

Un complément Excel peut être utilisé pour gérer les règles dans un lot. Les options suivantes sont disponibles :

- Téléchargez un modèle Excel.
- Exportez vers Excel.
- Importez depuis Excel.

### <a name="download-an-excel-template"></a>Télécharger un modèle Excel

Pour télécharger un modèle Excel, sélectionnez **Télécharger le modèle**. Puis sélectionnez les champs à inclure dans le modèle.

### <a name="export-to-excel"></a>Exporter vers Excel

Vous pouvez exporter de deux manières :

- Sélectionnez **Ouvrir dans Excel Online** pour ouvrir le fichier dans Excel. Vous pouvez ensuite modifier le fichier en ligne. Lorsque vous avez terminé, sélectionnez **Enregistrer**. Toutes vos modifications sont enregistrées sur la page **Règle de mise en correspondance**.
- Sélectionnez **Télécharger la feuille de travail** pour télécharger un fichier Excel contenant les règles de mise en correspondance. Vous pouvez ensuite modifier le fichier. Lorsque vous avez terminé, sélectionnez **Importer depuis Excel** pour télécharger la feuille de calcul mise à jour.

### <a name="import-from-excel"></a>Importer depuis Excel

1. Sélectionnez **Importer depuis Excel** pour importer des données à partir d’un fichier XLSX. Vous pouvez également importer des valeurs séparées par des virgules (CSV) ou des fichiers XML. Avant d’importer, vous devez décider si les doublons sont autorisés.
2. Sélectionnez **Réviser la mise en correspondance** pour réviser la mise en correspondance des attributs et déterminer s’il est correct. Vous pouvez modifier la relation de mise en correspondance.
3. Lorsque vous avez terminé, sélectionnez **Finir l’importation** pour lancer l’importation.
4. Vous pouvez sélectionner **Suivre le processus** pour suivre la progression du processus d’importation.

    Le statut d’importation est mis à jour de **Terminer** à **Analyser**, puis à **Transformer**, et enfin à **Terminé**.

Lorsque le processus d’importation est terminé, des statistiques sur les réussites, les échecs partiels, les erreurs et le total traité sont affichées.
