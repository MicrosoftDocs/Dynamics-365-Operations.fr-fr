---
title: "Intégration fiscale pour le canal de vente au détail"
description: "Cette rubrique fournit une vue d'ensemble de l'intégration fiscale pour Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: fr-fr
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Intégration fiscale pour le canal de vente au détail

[!include [banner](../includes/banner.md)]

Cette rubrique est une vue d'ensemble de la fonctionnalité d'intégration fiscale disponible dans Microsoft Dynamics 365 for Retail. La fonctionnalité d'intégration fiscale est une infrastructure conçue pour prendre en charge les lois fiscales locales destinées à empêcher la fraude dans le secteur du commerce de détail. Les scénarios habituels pouvant être couverts à l'aide de l'intégration fiscale comprennent :

- Imprimer un reçu fiscal et le remettre au client.
- Sécuriser l'envoi des informations relatives aux ventes et aux retours effectués sur POS à un service externe fourni l'administration.
- Utiliser la protection de données avec une signature numérique autorisée par l'administration.

Cette rubrique fournit des instructions pour configurer l'intégration fiscale afin que les utilisateurs puissent effectuer les tâches suivantes. 

- Configurer des connecteurs fiscaux, qui sont des périphériques ou services fiscaux utilisés à des fins d'enregistrement fiscal, tels que l'enregistrement, les signatures numériques, et l'envoi sécurisé des données fiscales.
- Configurer le fournisseur de document, qui définit une méthode de sortie et un algorithme de génération de document fiscal.
- Configurer le processus d'enregistrement fiscal, qui définit une succession d'étapes et un groupe de connecteurs utilisés à chaque étape.
- Affecter les processus d'enregistrement fiscaux dans les profils de fonctionnalité de POS.
- Affecter des profils techniques de connecteur aux profils matériels (pour les connecteurs fiscaux locaux) ou aux profils de fonctionnalité de POS (pour d'autres types de connecteurs fiscaux).

## <a name="fiscal-integration-execution-flow"></a>Flux d'exécution d'intégration fiscale
Le scénario suivant décrit le flux d'exécution d'intégration fiscale courant.

1. Initialisation du processus d'enregistrement fiscal.
  
   Après avoir exécuté certaines actions au cours desquelles l'enregistrement fiscal est nécessaire, par exemple après avoir conclu une transaction de ventre au détail, le processus d'enregistrement fiscal est associé au profil de fonctionnalité de POS actuel.

1. Recherche d'un connecteur fiscal.
   
   Pour chaque étape d'enregistrement fiscal incluse dans le processus d'enregistrement fiscal, le système met en correspondance la liste des connecteurs fiscaux. Ces connecteurs ont un profil fonctionnel inclus dans le groupe de connecteurs spécifié, avec une liste des connecteurs ayant un profil technique associé au profil matériel actuel (pour un type de connecteur égal à **Local** uniquement) ou au profil de fonctionnalité de POS actuel (pour d'autres types de connecteurs).
   
1. Exécution de l'intégration fiscale.

   Le système effectue toutes les actions nécessaires définies par un assembly lié au connecteur trouvé. Cette opération est effectuée conformément aux paramètres du profil fonctionnel et au profil technique trouvés à l'étape précédente pour ce connecteur.

## <a name="setup-needed-before-using-fiscal-integration"></a>Paramétrage requis avant d'utiliser l'intégration fiscale
Avant d'utiliser la fonctionnalité d'intégration fiscale, vous devez définir les paramètres suivants :

- Définissez la souche de numéros sur la page **Paramètres de vente au détail** pour le numéro de profil fonctionnel fiscal.
  
- Définissez les souches de numéros sur la page **Paramètres partagés de vente au détail** pour les références suivantes :
  
  - Numéro du profil technique fiscal
  - Numéro du groupe de connecteurs fiscaux
  - Numéro du processus d'enregistrement

- Créez un **Connecteur fiscal** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Connecteurs fiscaux** pour chaque périphérique ou service à utiliser à des fins d'intégration fiscale.

-  Créez un **Fournisseur de document fiscal** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Fournisseurs de documents fiscaux** pour tous les connecteurs fiscaux. Le mappage de données est considéré comme faisant partie du fournisseur de document fiscal. Pour paramétrer différents mappages de données pour le même connecteur (comme les réglementations spécifiques à chaque états), vous devez créer différents fournisseurs de documents fiscaux.

- Créez un **Profil fonctionnel de connecteur** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Profils fonctionnels de connecteurs** pour chaque fournisseur de document fiscal.
  - Sélectionnez un nom de connecteur.
  - Sélectionnez un fournisseur de document.
  - Spécifiez des paramètres de taux de TVA sous l'onglet **Paramètres services**.
  - Spécifiez la mise en correspondance des codes de TVA et la mise en correspondance des types de mode de paiement sous l'onglet **Mappage des données**.

  #### <a name="examples"></a>Exemples 

  |  | Format | Exemple | 
  |--------|--------|--------|
  | Paramètres de taux de TVA | valeur : VATrate | 1 : 2 000, 2 : 1 800 |
  | Mise en correspondance des codes de TVA | VATcode : valeur | vat20 : 1, vat18 : 2 |
  | Mise en correspondance des types de modes de paiement | TenderTyp : valeur | Disponibilités : 1, Carte : 2 |

- Créez **Groupes de connecteurs fiscaux** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Groupe de connecteurs fiscaux**. Un groupe de connecteurs est un sous-ensemble de profils fonctionnels liés à des connecteurs fiscaux qui effectuent des fonctions identiques et sont utilisés au même stade au sein d'un processus d'enregistrement fiscal.

   - Ajoutez des profils fonctionnels dans le groupe de connecteurs. Cliquez sur **Ajouter** sur la page **Profils fonctionnels** puis sélectionnez un numéro de profil.
   - Pour interrompre l'utilisation du profil fonctionnel, définissez **Désactiver** sur **Oui**. 
   
     Cette modification affecte le groupe de connecteurs actuel uniquement. Vous pouvez continuer à utiliser le même profil fonctionnel dans d'autres groupes de connecteurs.

     >[!NOTE]
     > Au sein d'un groupe de connecteurs, chaque connecteur fiscal ne peut avoir qu'un profil fonctionnel.

- Créez un **Profil technique de connecteur** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Profils techniques de connecteurs** pour chaque connecteur fiscal.
  - Sélectionnez un nom de connecteur.
  - Sélectionnez un type de connecteur : 
      - **Local** - Définissez ce type pour les périphériques ou les applications physiques installés sur un ordinateur local.
      - **Interne** - Définissez ce type pour les périphériques et services fiscaux connectés au serveur Retail.
      - **Externe** - Pour les services fiscaux externes comme un portail web fournis par une administration fiscale.
    
  - Spécifiez les paramètres sous l'onglet **Connexion**.

      
 >[!NOTE]
 > Une version mise à jour d'une configuration chargée précédemment sera chargée pour les profils fonctionnels et techniques. Si un connecteur ou fournisseur de document approprié est déjà en cours d'utilisation, vous serez notifié. Par défaut, toutes les modifications apportées manuellement dans des profils fonctionnels et techniques sont enregistrées. Pour remplacer ces profils par l'ensemble des paramètres par défaut d'une configuration, cliquez sur **Mettre à jour** sur la page **Profils fonctionnels de connecteur** et la page **Profils techniques de connecteur**.
 
- Créez un **Processus d'enregistrement fiscal** dans **Vente au détail > Paramétrage du canal > Intégration fiscale > Processus d'enregistrements fiscaux** pour chaque processus unique de l'intégration fiscale. Un processus d'enregistrement est défini par la séquence des étapes d'enregistrement et du groupe de connecteurs utilisé dans chaque étape. 
  
  - Ajoutez les étapes d'enregistrement au processus :
      - Cliquez sur **Ajouter**.
      - Sélectionnez un type de connecteur.
      
      >[!NOTE]
      > Ce champ définit l'emplacement où le système recherche le connecteur dans un profil technique, soit dans les profils matériels pour le type de connecteur **Local**, soit dans les profils de fonctionnalité de POS pour les autres types de connecteurs fiscaux.
      
   - Sélectionnez un groupe de connecteurs.
   
     >[!NOTE]
     > Cliquez sur **Valider** pour vérifier l'intégrité de la structure du processus d'enregistrement. Il est recommandé que des validations soient effectués dans les cas suivants :
       >- Pour un nouveau processus d'enregistrement après les paramètres soient complets, notamment la liaison aux profils de fonctionnalité POS et aux profils matériels.
       >- Après avoir mis à jour un processus d'enregistrement existant.

-  Liez les processus d'enregistrements fiscaux aux profils de fonctionnalité de POS dans **Vente au détail > Paramétrage du canal > Paramétrage POS > Profils POS > Profils de fonctionnalité**.
   - Cliquez sur **Modifier** et sélectionnez **Numéro du processus** sous l'onglet **Processus d'enregistrement fiscal**.
- Liez les profils techniques de connecteur aux profils matériels dans **Vente au détail > Paramétrage du canal > Paramétrage POS > Profils POS > Profils matériels**.
   - Cliquez sur **Modifier**, puis cliquez sur **Nouveau** sous l'onglet **Profil technique fiscal**.
   - Sélectionnez un profil technique de connecteur dans le champ **Numéro de profil**.
   
     >[!NOTE]
     > Vous pouvez ajouter plusieurs profils techniques à un profil matériel. Toutefois, ce n'est pas pris en charge si un profil matériel a plus d'une intersection avec un groupe de connecteurs. Pour éviter les paramètres non valides, il est recommandé de valider le processus d'enregistrement après avoir mis à jour tous les profils matériels.

