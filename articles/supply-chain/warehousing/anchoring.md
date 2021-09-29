---
title: Ancrage
description: Cette rubrique explique comment activer et utiliser l’ancrage.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a17574cccbdf6f26f0453bda67eabaa16d559cd3
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505568"
---
# <a name="anchoring"></a>Ancrage

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des détails sur le processus d’ancrage. Elle décrit la configuration requise et la logique qui est exécutée lorsqu’un magasinier modifie soit l’emplacement intermédiaire, soit l’emplacement de chargement.

La fonction d’ancrage vous permet de remplacer l’emplacement de préparation ou de chargement. Toutes les mises ouvertes sont ensuite dirigées vers le nouvel emplacement intermédiaire ou de chargement que vous spécifiez.

Cette fonctionnalité fait gagner les collaborateurs en efficacité lorsqu’ils expédient des marchandises. Voici quelques exemples :

- Un collaborateur qui doit placer des articles de la commande 1 dans un emplacement intermédiaire dans le Quai 1 ne peut pas finaliser cette opération, car un chargement précédent n’a pas libéré l’emplacement. Au lieu d’attendre que l’emplacement intermédiaire du Quai 1 devienne disponible, le collaborateur décide d’utiliser l’emplacement intermédiaire du Quai 2. Par conséquent, il remplace l’emplacement intermédiaire suggéré. L’emplacement de rangement de tous les articles restants pour l’ordre d’exécution est ensuite mis à jour avec l’emplacement intermédiaire du Quai 2.
- Un collaborateur qui doit effectuer plusieurs prélèvements pour la même livraison peut être sûr que tous les articles mis sont assemblés au même endroit. Par conséquent, moins de temps est nécessaire pour charger les articles dans le camion.

Vous configurez l’ancrage pour les éléments de menu de l’appareil mobile à l’aide de l’option **Ancre**. Si vous définissez cette option sur *Oui*, vous pouvez utiliser le champ **Ancrer par** pour spécifier si vous souhaitez ancrer par expédition ou par chargement. Si vous définissez le champ **Ancrer par** sur *Expédition*, les mises ouvertes suivantes sont modifiées avec le nouvel emplacement pour cette expédition. Si vous le définissez sur *Chargement*, les mises ouvertes suivantes sont modifiées avec le nouvel emplacement pour ce chargement.

> [!IMPORTANT]
> L’emplacement des mises ouvertes suivantes est modifié uniquement sur les lignes de travail générées à partir de la même ligne de modèle de travail. En d’autres termes, le système ancre les lignes de placement qui proviennent de la même ligne de modèle de travail.

Cette rubrique fournit un scénario qui montre comment fonctionne l’ancrage. Au cours du scénario, vous allez créer des ensembles de commandes client et lancer chaque ensemble dans l’entrepôt. Vous remplacerez ensuite l’emplacement intermédiaire suggéré et vérifierez que tout le travail de rangement restant est dirigé vers le nouvel emplacement.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Conditions préalables du scénario : rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur *USMF* avant de commencer.

## <a name="scenario-setup"></a>Configuration d’un scénario

Avant de travailler sur l’exemple de scénario, vous devez activer l’ancrage pour l’élément du menu de l’appareil mobile pertinent.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Paramétrer une option de menu d’appareil mobile pour activer l’ancrage

Procédez comme suit pour activer l’ancrage pour un élément du menu d’un appareil mobile.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’enregistrement nommé *Prélèvement ventes*. Si aucun enregistrement existant ne porte ce nom, créez-le. Confirmez ou définissez les valeurs suivantes pour l’enregistrement :

    - **Nom de l’élément de menu :** *Prélèvement ventes*
    - **Titre :** *Prélèvement des ventes*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Oui*
    - **Dirigé par :** *Utilisateur dirigé*
    - **Ancrage :** *Oui*

        Ce paramètre oblige le système à ancrer plusieurs lignes d’ordre de travail ensemble pendant le prélèvement des ventes.

    - **Ancrer par :** *Chargement*

        Ce paramètre provoque l’ancrage du système par chargement.

    - **Remplacer le contenant cible :** *Oui*
    - **Remplacer le contenant pendant le placement :** *Oui*
    - **Maintenir le travail verrouillé par l’utilisateur :** *Oui*
    - **Autoriser le prélèvement excessif :** *Oui*

### <a name="set-up-a-work-template-to-enable-staging"></a>Configurer un modèle de travail pour activer l’échelonnement

Procédez comme suit pour configurer un modèle de travail afin d’activer l’échelonnement. Cette configuration prend en charge le scénario dans lequel un collaborateur place des articles pour une commande dans un emplacement intermédiaire.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de travail**.
1. Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.
1. Dans la grille, sélectionnez le modèle de travail **Phase CC 61**.
1. Dans la section **Détails du modèle de travail**, veillez à ce que les lignes suivantes existent et soient configurées comme indiqué ici :

    - Ligne 1 :

        - **Type de travail :** *Choisir*
        - **Obligatoire :** Sélectionné (=*Oui*)
        - **ID classe de travail :** *Prélèvement CC*

    - Ligne 2 :

        - **Type de travail :** *Put*
        - **Obligatoire :** Sélectionné (=*Oui*)
        - **Code de la directive :** *Phase*
        - **ID classe de travail :** *Prélèvement CC*

    - Ligne 3 :

        - **Type de travail :** *Choisir*
        - **Obligatoire :** Sélectionné (=*Oui*)
        - **Arrêter le travail :** *Oui*
        - **ID classe de travail :** *Chargement CC*

    - Ligne 4 :

        - **Type de travail :** *Put*
        - **Obligatoire :** Sélectionné (=*Oui*)
        - **Code de la directive :** *Baydoor*
        - **ID classe de travail :** *Chargement CC*

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir l’éditeur de requête.
1. Sous l’onglet **Plage**, veillez à ce que la ligne suivante soit présente :

    - **Table :** *Transactions de travail temporaire*
    - **Table dérivée :** *Transactions de travail temporaire*
    - **Champ :** *Entrepôt*
    - **Critères :** *61*

1. Sous l’onglet **Tri**, veillez à ce que la ligne suivante soit présente :

    - **Table :** *Transactions de travail temporaire*
    - **Table dérivée :** *Transactions de travail temporaire*
    - **Champ :** *ID expédition*
    - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour appliquer vos paramètres et fermer l’éditeur de requêtes. Acceptez les modifications si vous y êtes invité.
1. Dans le volet Actions, sélectionnez **Décompositions de l’en-tête de travail**.
1. Sur la ligne où le champ **Nom de domaine** est défini sur *ID d’expédition*, veillez à ce que la case **Regrouper par ce champ** soit sélectionnée.

### <a name="set-up-license-plates-locations-and-inventory"></a>Configurer les contenants, les emplacements et l’inventaire

Avant de créer des commandes client et des expéditions, vous devez vous assurer que les emplacements, les contenants et l’inventaire requis existent.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Contenants**, et créez deux contenants :

    - MyLP1
    - MyLP2

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**, et créez les emplacements suivants s’ils ne sont pas déjà présents.

    | Entrepôt | Entrepôt   | ID profil d’emplacement | ID zone   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PRÉLEVER-06             | ATELIER     |
    | 61        | 06A01R3S1B | PRÉLEVER-06             | ATELIER     |
    | 61        | STAGE01    | STAGE               | *(Vide)* |
    | 61        | STAGE02    | STAGE               | *(Vide)* |
    | 61        | STAGE03    | STAGE               | *(Vide)* |
    | 61        | STAGE04    | STAGE               | *(Vide)* |

1. Veillez à ce que le stock suivant soit disponible. Si vous devez ajuster le stock, vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou utiliser tout autre flux.

    | Numéro d’article | Quantité | Entrepôt | Entrepôt   | Contenant |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | MyLP1         |
    | A0002       | 100      | 61        | 06A01R3S1B | MyLP2         |

### <a name="create-demand"></a>Créer une demande

Avant de pouvoir essayer la fonctionnalité d’ancrage, vous devez créer une certaine demande. Pour ce scénario, vous allez créer trois commandes client pour le même client.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer la première commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *61*

1. Cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Elle comprend une ligne vide sur le raccourci **Lignes de commande client**. Définissez les valeurs suivantes pour cette ligne :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *1*

1. Sur la barre d’outils, sélectionnez **Ajouter une ligne** au-dessus de la grille pour ajouter une deuxième ligne de commande client et définissez-en les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *1*

1. Procédez comme suit pour chaque ligne de la commande afin de réserver le stock qui y correspond :

    1. Dans le raccourci **Lignes de commande client**, sélectionnez une ligne de commande client.
    1. Dans la barre d’outils, sélectionnez **Inventaire \> Réservation**.
    1. Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.
    1. Dans le volet Actions, sélectionnez **Enregistrer**.

1. Répétez les étapes 2 à 6 pour créer une deuxième commande client. Définissez les valeurs suivantes pour cette ligne :

    - Dans la boîte de dialogue **Créer une commande client** :

        - **Compte client :** *US-001*
        - **Entrepôt :** *61*

    - Sur la ligne de commande client 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *2*

    - Sur la ligne de commande client 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *2*

1. Répétez l’étape 7 pour réserver chaque ligne de la commande client 2.
1. Répétez les étapes 2 à 6 pour créer une troisième commande client. Définissez les valeurs suivantes pour cette ligne :

    - Dans la boîte de dialogue **Créer une commande client** :

        - **Compte client :** *US-001*
        - **Entrepôt :** *61*

    - Sur la ligne de commande client 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *3*

    - Sur la ligne de commande client 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *3*

1. Répétez l’étape 7 pour réserver chaque ligne de la commande client 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Utiliser l’atelier Planification des chargements pour créer un chargement et le lancer dans l’entrepôt

Procédez comme suit pour créer un chargement pour les commandes que vous avez créées pour ce scénario, puis le lancer dans l’entrepôt.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Sur l’onglet **Lignes de vente**, recherchez et sélectionnez toutes les lignes de commande client pour la commande client 1 et la commande client 2.
1. Dans le volet Actions, sous l’onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**.
1. Dans la boîte de dialogue **Affectation des modèles de chargement**, dans le champ **ID du modèle de chargement**, sélectionnez un modèle de chargement, tel que *Modèle de chargement standard*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans la section **Chargements**, recherchez et sélectionnez le chargement que vous avez créé.
1. Sur la barre d’outils, sélectionnez **Lancer \> Lancement dans l’entrepôt**.
1. Dans la boîte de dialogue **Lancer le chargement dans l’entrepôt**, sélectionnez **OK** pour lancer le chargement sélectionné dans l’entrepôt.
1. Accédez à **Gestion des entrepôts \> Travail \> Tout le travail** pour afficher le travail créé. Vous devriez trouver deux nouveaux identifiants de travail, un pour chaque expédition. Chaque ID de travail dispose de lignes de prélèvement et de placement qui placent l’inventaire des emplacements de prélèvement vers l’emplacement intermédiaire et de l’emplacement intermédiaire vers l’emplacement de type Baydoor. Prenez note de la valeur **ID de travail** pour la première expédition, car vous en aurez besoin dans la procédure suivante.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Prélèvement des commandes clients jusqu’à l’emplacement intermédiaire pour la première expédition

1. Connectez-vous à l’application mobile Warehouse Management en tant que collaborateur de l’entrepôt *61*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant _61_ comme ID d’utilisateur et _1_ comme mot de passe.)
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.
1. Sélectionnez le champ **ID**, puis entrez l’ID de travail pour la première expédition.
1. Confirmez votre entrée.
1. Dans le champ **LP**, entrez un numéro de contenant pour le premier élément (*MyLP1*).
1. Confirmez votre entrée.
1. Dans le champ **LP cible**, entrez n’importe quel numéro (le contenant cible n’a pas déjà besoin d’exister).

    Vous prélèverez toutes les lignes créées à partir de la vague traitée dans le même contenant cible.

1. Confirmez votre entrée.
1. Dans le champ **LP**, entrez un numéro de contenant pour le second élément (*MyLP2*).
1. Confirmez votre entrée.

    Imaginez que le collaborateur a maintenant récupéré la commande, mais lorsqu’il arrive à l’emplacement intermédiaire spécifié dans le travail, il constate que l’espace est déjà occupé. Cependant, le collaborateur peut voir qu’un autre emplacement à proximité (*STAGE03*) est disponible. Par conséquent, il demande à modifier l’emplacement intermédiaire. Puisque la fonctionnalité d’ancrage et activée, le système met ensuite automatiquement à jour l’emplacement intermédiaire pour ce travail et tous les travaux associés.

1. Sélectionnez **Emplacement de remplacement** pour remplacer l’emplacement intermédiaire suggéré.
1. Dans le champ **Exceptions de travail**, précisez *La voie intermédiaire a changé*.
1. Dans le champ **Emplacement**, entrez un nouvel emplacement intermédiaire (*STAGE03*).
1. Confirmez votre entrée. Vous recevez un message « Travail terminé ».
1. Accédez à **Gestion des entrepôts \> Travail\> Tout le travail**.
1. Ouvrez l’ID de travail pour la première expédition. Vérifiez que l’emplacement intermédiaire a été mis à jour vers le nouvel emplacement (*STAGE03*) qui a été défini à l’aide de l’appareil mobile.
1. Ouvrez l’ID de travail pour la deuxième expédition. Vérifiez que l’emplacement intermédiaire a été mis à jour vers un nouvel emplacement intermédiaire (*STAGE03*) en raison de la configuration d’ancrage.

> [!NOTE]
> L’emplacement de toutes les lignes de travail ouvertes restantes qui ont le même emplacement intermédiaire et qui ont été générées à partir de la même ligne de modèle de travail sera mis à jour vers le nouvel emplacement.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Utiliser l’atelier Planification des chargements pour ajouter la nouvelle commande client au chargement existant

Procédez comme suit pour ajouter une commande au chargement, puis remettez-la à l’entrepôt.

1. Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.
1. Sur l’onglet **Lignes de vente**, recherchez et sélectionnez toutes les lignes de commande client pour la commande client 3.
1. Sur le volet Actions, sur l’onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez  **Vers le chargement existant** pour ajouter les lignes de commande sélectionnées à un chargement existant.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Dans la section **Chargements**, recherchez et sélectionnez le chargement à partir des étapes précédentes.
1. Sélectionnez **Lancer \> Lancement dans l’entrepôt**.
1. Dans la boîte de dialogue **Lancer le chargement dans l’entrepôt**, sélectionnez **OK** pour lancer le chargement sélectionné dans l’entrepôt.
1. Accédez à **Gestion des entrepôts \> Travail \> Tout le travail** pour afficher le travail créé. Prenez note de la valeur **ID de travail**, car vous en aurez besoin dans la procédure suivante.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Prélèvement des commandes clients jusqu’à l’emplacement intermédiaire pour la troisième expédition

1. Connectez-vous à l’application mobile en tant qu’employé de l’entrepôt *61*.
1. Dans le menu principal, sélectionnez **Sortant**.
1. Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.
1. Sélectionnez le champ **ID**, puis entrez l’ID de travail pour la troisième expédition.
1. Confirmez votre entrée.
1. Dans le champ **LP**, entrez un numéro de contenant pour le premier élément (*MyLP1*).
1. Confirmez votre entrée.
1. Dans le champ **LP cible**, entrez n’importe quel numéro (le contenant cible n’a pas déjà besoin d’exister).
1. Confirmez votre entrée.
1. Dans le champ **LP**, entrez un numéro de contenant pour le second élément (*MyLP2*).
1. Confirmez votre entrée.

    En ce qui concerne le premier chargement, imaginez que le collaborateur constate que l’emplacement intermédiaire spécifié n’est pas disponible. Par conséquent, il souhaite utiliser un autre emplacement intermédiaire (*STAGE04*).

1. Sélectionnez **Emplacement de remplacement** pour remplacer l’emplacement intermédiaire suggéré.
1. Dans le champ **Exceptions de travail**, précisez *La voie intermédiaire a changé*.
1. Dans le champ **Emplacement**, entrez un nouvel emplacement intermédiaire (*STAGE04*).
1. Confirmez votre entrée. Vous recevez un message « Travail terminé ».
1. Accédez à **Gestion des entrepôts \> Travail\> Tout le travail**.
1. Ouvrez l’ID de travail pour la première expédition. Vérifiez que l’emplacement intermédiaire n’a pas été mis à jour vers le nouvel emplacement intermédiaire (*STAGE04*), car la ligne de placement ouverte restante ne correspond pas à la ligne de modèle de travail de la ligne de placement terminée.
1. Ouvrez l’ID de travail pour la deuxième expédition. Vérifiez que l’emplacement intermédiaire n’a pas été mis à jour vers le nouvel emplacement intermédiaire (*STAGE04*), car l’emplacement intermédiaire ne correspond pas à l’emplacement intermédiaire de la ligne de placement terminée. En d’autres termes, la ligne de travail de placement terminée et la ligne de travail ouverte restante ont des emplacements intermédiaires différents et, dans ce cas, seules les lignes qui ont les mêmes emplacements intermédiaires sont mises à jour.
1. Ouvrez l’ID de travail pour la troisième expédition. Vérifiez que l’emplacement intermédiaire a été mis à jour vers un nouvel emplacement intermédiaire (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
