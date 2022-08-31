---
title: Relevé des avantages
description: Le rapport Relevé des avantages explique les avantages auxquels un employé est actuellement inscrit.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 36e7082a890ebec3031021a0871cddad91597447
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336884"
---
# <a name="benefit-statement"></a>Relevé des avantages

Le rapport **Relevé des avantages** fournit un relevé des avantages auxquels un employé est actuellement inscrit. Le rapport peut être consulté directement par un employé ou par l’administrateur des prestations. Le rapport **Relevé des avantages** fournit une liste des avantages sociaux inscrits de l’employé, des options de couverture, des coûts et des personnes à charge ou bénéficiaires inscrits. Le relevé peut être imprimé pour un seul ou plusieurs travailleurs.

> [!NOTE]
La fonctionnalité **Relevé des avantages** est activée dans l’espace de travail **Gestion des fonctionnalités**. Pour ce faire, la fonctionnalité **Gestion des avantages** doit être activée dans Gestion des fonctionnalités. 


## <a name="importing-the-benefit-statement"></a>Importation du relevé des avantages 

Vous devez importer le **Relevé des avantages** en utilisant la configuration du rapport avant que le **Relevé des avantages** ne soit disponible. Pour ce faire, procédez comme suit :

1.  Accédez à l’espace de travail **Administration système**.

2.  Sélectionnez la mosaïque **Gestion des états électroniques**.

3.  Accédez à **Fournisseurs de configuration** et sélectionnez **Référentiels**.

  ![Sélection des référentiels.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Sélectionnez **Ressources RH** dans la liste, puis sélectionnez **Ouvrir**.

    ![Référentiels de configuration.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Sélectionnez le **Modèle de relevé des avantages** dans le volet de gauche et développez-le pour que le **Format du relevé des avantages** s’affiche.

6.  Sélectionnez le **Format du relevé des avantages** dans le volet de gauche.

7.  Sur le côté droit de l’écran, un raccourci **Versions** s’affiche. Sélectionnez **Importer**.

    ![Raccourci Versions.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Générer le relevé des avantages sous forme de fichier PDF

Par défaut, la **Déclaration des avantages** s’imprimera en tant que document Microsoft Word. Pour imprimer au format PDF, vous devrez configurer l’option PDF dans **Destination de la gestion des états électroniques**. 

1. Pour ce faire, accédez à **Espace de travail d’administration système** > **Gestion des états électroniques** > **Liens connexes** > **Destination de la gestion des états électroniques**.

1.  Sélectionnez **Nouveau**.

2.  Dans le champ **Références**, sélectionnez le format **Format du relevé des avantages**.

3.  Dans le raccourci **Destination du fichier**, sélectionnez **Nouveau**.

4.  Dans le champ **Nom**, entrez **PDF du relevé des avantages**.

5.  Dans le champ **Nom du composant de fichier**, entrez ou sélectionnez **Relevé des avantages**.

6.  Activez la case à cocher **Convertir en PDF**.

7.  Sélectionnez **Paramètres** à partir de l’option de menu. 

    ![Destination du fichier.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Sélectionnez le raccourci **Fichier**, puis sélectionnez **Activé**.

9.  Cliquez sur **OK**.
   
> [!NOTE]
> La fonctionnalité de gestion des avantages est dans un état d’aperçu. Il existe un problème connu lors de l’utilisation du paramètre de destination des e-mails dans le rapport **Destination de la gestion des états électroniques**. Vous pouvez recevoir un message d’erreur et l’e-mail ne sera pas envoyé.

Le **Relevé des avantages** peut être généré à partir des pages suivantes :

-   **Espace de travail de gestion des avantages** > **Liens** > **Rapports** > **Déclaration des avantages**

-   **Employés (formulaire hérité)** > **Onglet Informations personnelles** > **Déclaration des avantages**

-   **Saisie simplifiée des employés** > **Rapports des avantages** > **Déclaration des avantages**

-   **Libre-service pour les employés** > **Avantages** > **Voir le relevé des avantages**

> [!NOTE]
>  Accédez au **Relevé des avantages** dans **Libre-service pour les employés** est contrôlé par le privilège **Voir le relevé des avantages**. C’est sous le devoir **Avantages du libre-service pour les employés**. Ce privilège est accordé par défaut aux employés.

## <a name="report-contents"></a>Contenu du rapport

Le **Relevé des avantages** imprimera les choix de régime confirmés de l’employé, y compris les régimes auxquels il a renoncé. L’image suivant présente un exemple de ce rapport. 

![Rapport concernant les relevés d’avantages.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

Le rapport affichera le **Plan**, l’**Option de couverture**, le **Coût du personnel** et le **Coût employeur**. Le rapport énumérera également toutes les personnes à charge couvertes. Si le plan est associé à des bénéficiaires, les bénéficiaires ainsi que leur priorité de distribution et leur pourcentage s’afficheront.

Le rapport **Relevé des avanatges** peut être imprimé pour plusieurs employés en même temps en utilisant le raccourci **Enregistrements à inclure** sur la page **Relevé des avantages**.
