---
title: Exemples de scénarios d’inventaire tournant
description: Cet article fournit une collection de scénarios qui mettent en avant les fonctionnalités d’inventaire tournant de Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 90a3f132a96081b56ab60f5b0ba5cc328b820879
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899322"
---
# <a name="cycle-counting-example-scenarios"></a>Exemples de scénarios d’inventaire tournant

[!include [banner](../includes/banner.md)]

Cet article fournit une collection de scénarios qui mettent en avant les fonctionnalités d’inventaire tournant de Microsoft Dynamics 365 Supply Chain Management. Elle décrit d’abord les exigences de votre environnement Supply Chain Management existant. Elle explique ensuite comment configurer l’inventaire tournant et décrit tous les stades de celui-ci. Lorsque vous aurez terminé, vous devrez avoir une bonne compréhension de l’inventaire tournant, y compris l’inventaire tournant guidé, l’inventaire tournant à l’aveugle, l’inventaire tournant ponctuel, les seuils d’inventaire tournant et les plans d’inventaire tournant.

## <a name="prerequisites"></a>Conditions préalables

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Chaque scénario de cet article fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Supply Chain Management. Pour utiliser les valeurs fournies ici en étudiant les scénarios, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique (société) sur **USMF** avant de commencer.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Activer la prise en charge de l’application mobile Warehouse Management

Pour utiliser l’application mobile Warehouse Management, la fonctionnalité *Paramètres utilisateur, icônes et titres d’étape pour la nouvelle application d’entrepôt* doit être activée sur votre système. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Confirmer les expéditions sortantes à partir des tâches par lots* dans l’espace de travail [Paramètres utilisateur, icônes et titres des étapes pour la nouvelle application d’entrepôt](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Préparer les données de démonstration pour les scénarios

Suivez ces étapes pour vérifier que toutes les données de démonstration requises pour les scénarios sont disponibles dans la société USMF de votre système. Créez tous les enregistrements ou valeurs manquants.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Dans le volet de liste, sélectionnez **Julia Funderburk**.
1. Dans le raccourci **Utilisateurs**, sélectionnez la ligne qui a les valeurs suivantes. Si aucune ligne existante n’a ces valeurs, créez-la.

    - **ID d’utilisateur :** *61*
    - **Nom d’utilisateur :** *WH61*
    - **Entrepôt par défaut :** *61*
    - **Nom du menu :** *Principal*

1. Dans le raccourci **Travail**, définissez les valeurs suivantes pour l’utilisateur *61* si elles ne sont pas déjà définies :

    - **Superviseur d’inventaire tournant :** *Non*
    - **Limite maximale du pourcentage :** *0*
    - **Limite maximale de la quantité :** *0*
    - **Limite maximale de la valeur :** *0*

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Pools de travail**.
1. Les pools de travail servent à isoler le travail d’entrepôt selon le type de travail (dans ce cas, un travail d’inventaire tournant). Assurez-vous qu’il existe un enregistrement avec les paramètres suivants :

    - **ID du pool de travail :** *CycleCount*
    - **Description :** *Nombre de cycles*

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Nombre de cycles*. Si aucun enregistrement existant ne porte ce nom, créez-le. Confirmez ou définissez les valeurs suivantes pour l’enregistrement :

    - **Nom de l’élément de menu :** *Nombre de cycles*
    - **Titre :** *Nombre de cycles guidé*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*
    - **Dirigé par :** *Dirigé par le système* (Cette valeur indique que Supply Chain Management affectera un ID de travail d’inventaire tournant à l’employé.)
    - **Afficher le statut de stock :** *Oui*

1. Dans le volet Actions, sélectionnez **Inventaire tournant**.
1. Dans la boîte de dialogue **Inventaire tournant des appareils mobiles**, confirmez ou définissez les valeurs suivantes :

    - **Afficher le numéro d’article :** *Oui*
    - **Afficher le contenant :** *Oui*
    - **Nombre de tentatives :** *1*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Nombre de cycles à l’aveugle*. Si aucun enregistrement existant ne porte ce nom, créez-le. Confirmez ou définissez les valeurs suivantes pour l’enregistrement :

    - **Nom de l’élément de menu :** *Nombre de cycles à l’aveugle*
    - **Titre :** *Nombre de cycles à l’aveugle*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*
    - **Dirigé par :** *Regroupement d’inventaires tournants* (Cette valeur indique que le collaborateur peut regrouper plusieurs ID de travail d’inventaire tournant qui sont spécifiques à un emplacement, à une zone ou à un pool de travail.)

1. Dans le volet Actions, sélectionnez **Inventaire tournant**.
1. Dans la boîte de dialogue **Inventaire tournant des appareils mobiles**, confirmez ou définissez les valeurs suivantes :

    - **Afficher le numéro d’article :** *Non*
    - **Afficher le contenant :** *Non*
    - **Nombre de tentatives :** *0*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Inventaire ponctuel*. Si aucun enregistrement existant ne porte ce nom, créez-le. Confirmez ou définissez les valeurs suivantes pour l’enregistrement :

    - **Nom de l’élément de menu :** *Inventaire ponctuel*
    - **Titre :** *Inventaire ponctuel*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Non*
    - **Processus de création de travail :** *Inventaire tournant ponctuel* (Cette valeur indique que le collaborateur peut compter les articles dans un emplacement d’entrepôt à tout moment, sans créer de travail d’inventaire tournant. Pour effectuer l’inventaire tournant ponctuel dans un emplacement, le travailleur entre l’ID de l’emplacement.)

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Stock*. Si aucun enregistrement existant ne porte ce nom, créez-le. Vérifiez que les éléments de menu d’inventaire tournant suivants apparaissent dans la colonne **Structure des menus** :

    - Inventaire tournant
    - Nombre de cycles à l’aveugle
    - Inventaire ponctuel

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôts**.
1. Dans l’onglet **Inventaire tournant**, définissez les valeurs suivantes :

    - **Type d’ajustement d’inventaire tournant par défaut :** *Nombre de cycles* (Ce champ spécifie le type de journal qui est validé lorsque l’inventaire tournant est effectué.)
    - **ID de classe de travail d’inventaire tournant par défaut :** *CCount* (Ce champ spécifie la classe de travail utilisée pour l’inventaire tournant.)
    - **Priorité de travail d’inventaire tournant par défaut :** *50* (Ce champ définit la priorité du travail d’inventaire tournant par rapport aux autres types de travail dans l’entrepôt. Si vous entrez un nombre plus faible que celui saisi pour d’autres types de travail, vous élevez la priorité du travail d’inventaire tournant.)

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Types d’ajustement**.
1. La page **Types d’ajustement** vous permet de créer des codes pour les différents ajustements d’entrée et de sortie qui peuvent survenir. Vérifiez qu’il existe un enregistrement avec les paramètres suivants :

    - **Type d’ajustement d’inventaire :** *Nombre de cycles*
    - **Description :** *Nombre de cycles*
    - **Nom :** *ICnt*

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Définition d’entrepôt \> Entrepôts**.
1. Dans le volet de liste, sélectionnez l’entrepôt *61*. Si aucun enregistrement existant ne porte ce nom, créez-le.
1. Dans le raccourci **Entrepôt**, définissez les valeurs suivantes :

    - **Utiliser le processus de gestion d’entrepôt :** *Oui* (Cette valeur active l’entrepôt pour les processus de gestion d’entrepôt.)
    - **Autoriser les mouvements de contenants pendant l’inventaire tournant :** *Oui* (Cette valeur permet aux collaborateurs de déplacer les contenants au cours d’un inventaire tournant.)

## <a name="scenario-1-guided-cycle-counting"></a>Scénario 1 : Inventaire tournant guidé

Avant que l’inventaire tournant guidé puisse se produire, vous devez créer un travail. Ce travail guidera la personne affectée dans l’entrepôt, d’un emplacement à l’autre, pour réaliser les dénombrements qui sont définis dans le travail.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Créer un travail d’inventaire tournant pour le scénario 1

Suivez ces étapes pour créer un travail d’inventaire tournant pour l’emplacement d’article *01A02R2S2B* (BULK-06) dans l’entrepôt *61*.

1. Accédez à **Gestion de l’entrepôt \> Inventaire tournant \> Travail d’inventaire tournant par emplacement**.
1. Dans la boîte de dialogue **Créer un travail d’inventaire tournant par emplacement**, définissez le champ **ID du pool de travail** sur *CycleCount*.
1. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, sur l’onglet **Plage**, procédez comme suit :

    - Pour la rangée où le champ **Champ** est défini sur *Entrepôt*, définissez le champ **Critères** sur *61*.
    - Pour la rangée où le champ **Champ** est défini sur *Emplacement*, définissez le champ **Critères** sur *01A02R2S2B*.

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Sélectionnez **OK** pour fermer la boîte de dialogue **Créer un travail d’inventaire tournant par emplacement**.

    Lorsque le processus de création du travail est terminé, un message s’affiche dans le Centre d’action.

1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Trouvez le travail nouvellement créé en définissant un filtre sur la colonne **ID de pool de travail** pour rechercher les enregistrements qui ont une valeur de *CycleCount*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Pour effectuer le travail d’inventaire tournant pour le scénario 1

Après avoir créé le travail d’inventaire tournant, vous effectuez le travail d’inventaire tournant en comptant les articles dans un emplacement d’entrepôt, puis en saisissant les résultats dans Supply Chain Management. Procédez comme suit pour effectuer le travail d’inventaire tournant dans l’application mobile Warehouse Management.

1. Connectez-vous à l’application mobile Warehouse Management en tant qu’utilisateur de travail que vous avez configuré dans la section [Préparer les données de démonstration pour les scénarios](#prepare-demo-data) plus haut dans cet article. Pour l’exemple de cet article, l’utilisateur est nommé *Julia Funderburk* et configuré pour l’entrepôt *61*. (Les données de démonstration USMF devraient vous permettre de vous connecter en tant que cet utilisateur de travail en entrant *61* comme identifiant d’utilisateur et *1* comme mot de passe.)
1. Dans le menu principal, sélectionnez **Stock**.
1. Dans le menu **Stock**, sélectionnez **Inventaire tournant guidé**.
1. Sélectionnez le champ **Qté**, entrez *9* à l’aide du pavé numérique, puis sélectionnez **OK** (le bouton de coche).
1. Le système s’attendait à ce que vous saisissiez un nombre de 10 pièces pour cet article, cet emplacement et ce contenant. Par conséquent, vous êtes invité à recompter. Sélectionnez le champ **Qté**, entrez de nouveau *9* à l’aide du pavé numérique, puis sélectionnez **OK** (le bouton de coche). À la deuxième tentative, votre compte sera accepté.

    > [!NOTE]
    > Lorsque le système a détecté une différence entre la quantité en stock attendue et la quantité que vous avez saisie, il vous a demandé de compter une deuxième fois car le champ **Nombre de tentatives** est défini sur *1* pour l’élément de menu **Inventaire tournant guidé** de l’appareil mobile. Vous avez été guidé vers un numéro d’article et un numéro de contenant spécifiques, car les deux options **Afficher le numéro d’article** et **Afficher le contenant** sont définies sur *Oui* pour l’élément de menu de l’appareil mobile.

1. Cliquez sur **OK** (bouton de coche).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Examiner les différences d’inventaire tournant pour le scénario 1

Suivez ces étapes pour examiner les différences d’inventaire tournant.

1. Revenez à Supply Chain Management.
1. Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.
1. Recherchez et sélectionnez le travail d’inventaire tournant que vous avez examiné plus tôt. (Par exemple, définissez un filtre sur la colonne **ID du pool de travail** pour rechercher les enregistrements qui ont une valeur de *CycleCount*.) Notez que le champ **Statut du travail** pour ce travail est maintenant défini sur *Révision en attente*.

    > [!NOTE]
    > Pour le compte d’utilisateur de travail que vous avez utilisé pour effectuer le travail de comptage, l’option **Superviseur d’inventaire tournant** est définie sur *Non*, et les champs **Limite maximale du pourcentage**, **Limite maximale de la quantité** et **Limite maximale de la valeur** sont tous définis sur *0* (zéro). Par conséquent, toutes les différences de comptage signalées par cet utilisateur doivent être approuvées manuellement, et le champ **Statut du travail** pour le travail connexe est défini sur *Révision en attente*. Si la valeur comptée se trouvait dans les limites d’écart (spécifiées par les champs **Limite maximale du pourcentage** ou **Limite maximale de la quantité** de la page **Utilisateurs du travail**), ou si l’option **Superviseur d’inventaire tournant** a été définie sur *Oui* pour l’utilisateur, le travail aurait été automatiquement clôturé.

1. Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Inventaire tournant**.
1. Dans le volet Actions, sélectionnez **Accepter l’inventaire**.

    La différence est validée à l’aide du journal de comptage standard et un nouvel ordre de travail est créé.

1. Sur la page **Transactions d’inventaire tournant**, dans le volet Actions, sélectionnez **Travail dérivé** pour trouver le travail qui a été créé pour la différence approuvée.

## <a name="scenario-2-blind-cycle-counting"></a>Scénario 2 : Inventaire tournant à l’aveugle

Ce scénario nécessite que le scénario 1 soit déjà réalisé dans votre système.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Créer un travail d’inventaire tournant pour le scénario 2

Avant que l’inventaire tournant à l’aveugle puisse se produire, vous devez créer un travail. Suivez ces étapes pour créer un travail d’inventaire tournant pour l’emplacement d’article *01A02R2S2B* (BULK-06) dans l’entrepôt *61*.

1. Accédez à **Gestion de l’entrepôt \> Inventaire tournant \> Travail d’inventaire tournant par article**.
1. Dans la boîte de dialogue **Créer un travail d’inventaire tournant par article**, définissez le champ **ID du pool de travail** sur *CycleCount*.
1. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez trois lignes comportant les paramètres suivants :

    - Ligne 1 :

        - **Table :** *Articles*
        - **Champ :** *Numéro d’article*
        - **Critères :** *L0101*

    - Ligne 2 :

        - **Table :** *Dimensions de stock*
        - **Champ :** *Entrepôt*
        - **Critères :** *61*

    - Ligne 3 :

        - **Table :** *Dimensions de stock*
        - **Champ :** *Emplacement*
        - **Critères :** *01A02R2S2B*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Sélectionnez **OK** pour fermer la boîte de dialogue **Créer un travail d’inventaire tournant par article**.

    Lorsque le processus de création du travail est terminé, vous recevez un message d’information.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Pour effectuer le travail d’inventaire tournant pour le scénario 2

Après avoir créé le travail d’inventaire tournant, procédez comme suit pour effectuer le travail dans l’application mobile Warehouse Management.

1. Connectez-vous à l’application mobile Warehouse Management en tant qu’utilisateur de travail que vous avez configuré dans la section [Préparer les données de démonstration pour les scénarios](#prepare-demo-data) plus haut dans cet article. Pour l’exemple de cet article, l’utilisateur est nommé *Julia Funderburk* et configuré pour l’entrepôt *61*. (Les données de démonstration USMF devraient vous permettre de vous connecter en tant que cet utilisateur de travail en entrant *61* comme identifiant d’utilisateur et *1* comme mot de passe.)
1. Dans le menu principal, sélectionnez **Stock**.
1. Dans le menu **Stock**, sélectionnez **Inventaire tournant à l’aveugle**.
1. Sélectionnez le champ **Identifiant de zone**, entrez *BULK06*, puis sélectionnez **OK** (le bouton de coche).
1. Sélectionnez le champ **Article**, entrez *L0101*, puis sélectionnez **OK** (le bouton de coche).
1. Sélectionnez le champ **Contenant**, entrez *LP\_BULK\_06\_01*, puis sélectionnez **OK** (le bouton de coche).
1. Sélectionnez le champ **Qté**, entrez *10*, puis sélectionnez **OK** (le bouton de coche).

    > [!NOTE]
    > Quand bien même le système a détecté une différence entre la quantité en stock attendue et la quantité que vous avez saisie, il ne vous a pas demandé de compter une deuxième fois car le champ **Nombre de tentatives** est défini sur *0* (zéro) pour l’élément de menu **Inventaire tournant à l’aveugle** de l’appareil mobile. Il vous a été demandé de scanner le numéro d’article et le numéro de contenant parce que les deux options **Afficher le numéro d’article** et **Afficher le contenant** sont définies sur *Non* pour l’élément de menu de l’appareil mobile.

1. Cliquez sur **OK** (bouton de coche).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Examiner les différences d’inventaire tournant pour le scénario 2

Suivez ces étapes pour examiner les différences d’inventaire tournant.

1. Revenez à Supply Chain Management.
1. Accédez à **Gestion des entrepôts \> Commun \> Travail \> Travail d’inventaire tournant en attente de révision**.
1. Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Inventaire tournant**.
1. Dans le volet Actions, sélectionnez **Rejeter le comptage**.

    Parce que la différence de comptage a été rejetée, le travail est fermé.

## <a name="scenario-3-spot-cycle-counting"></a>Scénario 3 : Inventaire tournant ponctuel

Le registre de stock disponible indique qu’il y a une quantité disponible de l’article *L0101* à l’emplacement *01A02R2S2B*. Le magasinier est à l’emplacement *01A02R2S1B*. Bien que cet emplacement doive être vide, il est plein. Par conséquent, le magasinier effectue immédiatement un comptage ponctuel de cet emplacement.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Pour effectuer le travail d’inventaire tournant pour le scénario 3

Procédez comme suit pour effectuer le travail d’inventaire tournant dans l’application mobile Warehouse Management.

1. Connectez-vous à l’application mobile Warehouse Management en tant qu’utilisateur de travail que vous avez configuré dans la section [Préparer les données de démonstration pour les scénarios](#prepare-demo-data) plus haut dans cet article. Pour l’exemple de cet article, l’utilisateur est nommé *Julia Funderburk* et configuré pour l’entrepôt *61*. (Les données de démonstration USMF devraient vous permettre de vous connecter en tant que cet utilisateur de travail en entrant *61* comme identifiant d’utilisateur et *1* comme mot de passe.)
1. Dans le menu principal, sélectionnez **Stock**.
1. Dans le menu **Stock**, sélectionnez **Comptage ponctuel**.
1. Sélectionnez le champ **Emplacement**, entrez *01A02R2S1B*, puis sélectionnez **OK** (le bouton de coche).

    Le système détecte que l’emplacement est vide dans Supply Chain Management.

1. Sélectionnez **Ajouter un contenant ou un article**.
1. Sélectionnez le champ **Article**, entrez *L0101*, puis sélectionnez **OK** (le bouton de coche).
1. Sélectionnez le champ **Contenant**, entrez *LP\_BULK\_06\_01*, puis sélectionnez **OK** (le bouton de coche).
1. Sélectionnez le champ **Qté**, entrez *9*, puis sélectionnez **OK** (le bouton de coche).

    Étant donné que le système détecte que le contenant spécifié est déjà disponible à un autre emplacement dans Supply Chain Management, ce contenant sera déplacé vers l’emplacement actuel. Par conséquent, le système vous demande de confirmer le mouvement.

1. Cliquez sur **OK** (bouton de coche).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Examiner les différences d’inventaire tournant pour le scénario 3

Suivez ces étapes pour examiner les résultats du comptage.

1. Revenez à Supply Chain Management.
1. Accédez à **Gestion des entrepôts \> Commun \> Détails du travail**.
1. Sélectionnez la case à cocher **Afficher fermés** en haut de la grille.
1. Définissez le filtre de la colonne **Type d’ordre de travail** sur *Mouvement de stock*.

    Le système a automatiquement détecté ce comptage comme un mouvement de stock. Ce mouvement est autorisé parce que l’option **Autoriser les mouvements de contenant pendant l’inventaire tournant** est définie sur *Oui* pour l’entrepôt *61* sur la page **Entrepôts**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Scénario 4 : Définir des seuils d’inventaire tournant

Une façon de créer un travail d’inventaire tournant consiste à utiliser des seuils. Un seuil d’inventaire tournant indique la limite de quantité ou de pourcentage des articles en stock. Le travail d’inventaire tournant est automatiquement créé lorsque le seuil est atteint.

Par exemple, supposons que vous ayez 60 articles dans un emplacement dont le seuil d’inventaire tournant est de 40. Lors d’une transaction de commande client, 25 articles sont prélevés de l’emplacement et placés dans un emplacement temporaire. Étant donné que le nombre d’articles restants, 35, est inférieur à la quantité de seuil, un travail d’inventaire tournant est automatiquement créé pour l’emplacement.

Procédez comme suit pour définir des seuils d’inventaire tournant :

1. Accédez à **Gestion de l’entrepôt \> Paramétrage \> Inventaire tournant \> Seuils d’inventaire tournant**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un seuil et définissez-lui les valeurs suivantes :

    - **ID seuil d’inventaire tournant :** *L0101*
    - **Description :** *Seuil L0101*
    - **Quantité de seuil :** *2*
    - **Unité :** *ea*
    - **Seuil de capacité basé sur le pourcentage :** *0,00*
    - **Type de seuil d’inventaire tournant :** *Quantité*
    - **Traiter l’inventaire tournant immédiatement :** *Oui*
    - **Jours entre les inventaires tournants :** *1*
    - **ID du pool de travail :** *CycleCount*

1. Dans le volet Actions, sélectionnez **Sélectionner des articles**.
1. Dans la boîte de dialogue de l’éditeur de requête, dans l’onglet **Plage**, recherchez la ligne où le champ **Champ** est défini sur *Numéro d’article*. Définissez le champ **Critères** de cette ligne sur *L0101*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.

    Vous avez maintenant défini un seuil d’inventaire tournant pour l’article *L0101*.

Un inventaire tournant sera maintenant créé pour l’article *L0101* à n’importe quel emplacement si la quantité en stock est inférieure à 2 et si la date du dernier inventaire tournant pour l’emplacement n’est pas aujourd’hui.

## <a name="scenario-5-define-cycle-count-plans"></a>Scénario 5 : Définir des plans d’inventaire tournant

Les plans d’inventaire tournant vous permettent d’automatiser la création de travaux d’inventaire tournant. Vous pouvez configurer chaque plan d’inventaire tournant avec des requêtes d’articles et d’emplacements spécifiques. Lorsque le traitement par lots s’exécute, il crée un travail d’inventaire tournant pour tous les emplacements qui correspondent aux critères d’article et d’emplacement (jusqu’au nombre maximal d’inventaires spécifié pour le plan). Lorsqu’un travail d’inventaire tournant est créé, la ligne de travail d’inventaire comprend des informations sur l’emplacement à inventorier. Le stock disponible associé à cet emplacement n’est pas bloqué. Par conséquent, il est disponible pour le traitement des réservations et des sorties, même s’il existe un travail de comptage ouvert.

Procédez comme suit pour définir un plan d’inventaire tournant.

1. Accédez à **Gestion de l’entrepôt \> Paramétrage \> Inventaire tournant \> Plans d’inventaire tournant**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille, puis définissez valeurs suivantes pour elle :

    - **ID plan d’inventaire tournant :** *BULK06*
    - **Description :** *Comptage de l’emplacement pour BULK06*
    - **ID du pool de travail :** *CycleCount*
    - **Nombre maximal d’inventaires tournants :** *10*
    - **Jours entre les inventaires tournants :** *10*
    - **Emplacements vides :** *Exclure vides*
    - **Modèle de travail :** Laissez ce champ vide.

1. Dans le volet Actions, sélectionnez **Sélectionner des emplacements**.
1. Une boîte de dialogue d’éditeur de requête standard s’affiche. Dans l’onglet **Plage**, ajoutez une ligne et définissez les valeurs suivantes pour elle :

    - **Table :** *Emplacements*
    - **Champ :** *ID zone*
    - **Critères :** *BULK06*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Dans le volet Actions, sélectionnez **Traiter le plan d’inventaire tournant**.
1. Dans la boîte de dialogue **Plans d’inventaire tournant**, dans le raccourci **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur *Oui*.
1. Sélectionnez **Récurrence**.
1. Dans la boîte de dialogue **Définir la récurrence**, configurez le traitement par lots de sorte qu’il démarre immédiatement et s’exécute une fois par minute, et de sorte qu’il n’y ait pas de date de fin.
1. Sélectionnez **OK** pour fermer la boîte de dialogue **Définir la récurrence**.
1. Cliquez sur **OK** pour fermer la boîte de dialogue **Plans d’inventaire tournant**.

    Un message vous informe que le travail a été ajouté à la file d’attente des traitements par lots.

1. Accédez à **Gestion de l’entrepôt \> Commun \> Programmation de l’inventaire tournant**. Le plan commence immédiatement et crée un travail de comptage. Étant donné que le travail de comptage n’est pas terminé, le champ **Statut** est défini sur *En cours*. Au bout d’une minute, la valeur de la colonne **Total inventaires tournants** passe à *1*.

    > [!NOTE]
    > Le travail d’inventaire tournant ne sera pas créé si le nombre de jours depuis le dernier inventaire tournant est inférieur à la valeur que vous avez définie pour le champ **Jours entre inventaires tournants** pour le plan d’inventaire tournant. Par exemple, si le champ **Jours entre les inventaires tournants** est défini sur *5*, le travail d’inventaire tournant sera créé tous les cinq jours. Toutefois, si le travail d’inventaire tournant est traité le jour 3, le travail d’inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le jour 8.

1. Dans le volet Actions, sélectionnez **Travail** pour afficher le travail de comptage qui a été créé.
