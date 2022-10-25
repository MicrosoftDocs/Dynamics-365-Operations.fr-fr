---
title: Configurer des détours pour les étapes dans les éléments de menu de l’appareil mobile
description: Cet article explique comment configurer des détours pour les éléments de menu afin que les collaborateurs puissent parquer la tâche en cours, effectuer une autre tâche, puis revenir à la tâche d’origine sans perdre aucune information.
author: Mirzaab
ms.date: 09/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour, WHSMobileAppFlowStepDetourSelectFields, WHSMobileAppFlowStepSelectPromotedFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2e387dd4e6499912f2d53dddc17ccc053f1ca699
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689308"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Configurer des détours pour les étapes dans les éléments de menu de l’appareil mobile

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 10.0.31 GA -->

> [!IMPORTANT]
> Les fonctionnalités décrites dans cet article s’appliquent uniquement à la nouvelle application mobile Warehouse Management. Elles n’affectent pas l’ancienne application d’entrepôt, qui est désormais obsolète.

Cet article explique comment configurer des détours pour les éléments de menu afin que les collaborateurs puissent "parquer" la tâche en cours, effectuer une autre tâche, puis revenir à la tâche d’origine sans perdre aucune information.

Un détour est une option de menu distinct qui peut être ouvert à partir d’une étape d’une tâche principale. A la fin du détour, le collaborateur est ramené à l’endroit où il a quitté la tâche principale. Lors de la configuration, vous spécifiez l’option de menu qui doit servir de détour. Vous sélectionnez également les valeurs de champ de la tâche principale qui doivent être automatiquement transférées (copiés) au détour et saisies là-bas. Par conséquent, vous devez comprendre à quel endroit du flux de tâches vous souhaitez que le détour soit disponible pour les collaborateurs. Vous devez également vous assurer que les informations qui doivent être copiées dans le détour sont disponibles pour cette étape du flux de tâches.

## <a name="enable-detours-in-your-system"></a>Activer les détours dans votre système

Avant de pouvoir configurer des détours pour les étapes dans les options de menu de l’appareil mobile, vous devez effectuer la procédure suivante pour activer les fonctionnalités requises et générer les noms de champ requis dans l’application mobile Warehouse Management.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Assurez-vous que la caractéristique *Instructions d’étape de l’application Warehouse* est activée pour votre système. À compter de la version 10.0.29 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Pour plus d’informations sur la fonctionnalité *Instructions d’étape de l’application d’entrepôt*, voir [Personnaliser les titres et les instructions des étapes pour l’application mobile Warehouse Management](mobile-app-titles-instructions.md). Cette fonctionnalité est une condition préalable à la fonctionnalité *Détours de l’application Warehouse Management*.
1. Activez les fonctionnalités suivantes, qui fournissent les fonctionnalités décrites dans cet article :
    - *Détours de l’application Warehouse Management*<br>(Depuis la version 10.0.29 de Supply Chain Management, cette fonctionnalité est activée par défaut.)
    - *Détours à plusieurs niveaux pour l’application mobile Warehouse Management*
    - *Soumettre automatiquement les étapes de détour pour l’application mobile Warehouse Management*
1. Si les fonctionnalités *Détours de l’application Warehouse Management* et/ou *Détours à plusieurs niveaux pour l’application mobile Warehouse Management* n’étaient pas déjà activées, mettez à jour les noms des champs dans l’application mobile Warehouse Management en accédant à **Warehouse management\> Configuration \> Appareil mobile \> Noms des champs d’application d’entrepôt** et en sélectionnant **Créer une configuration par défaut**. Pour plus d’informations, voir [Configurer les champs pour l’application mobile Gestion des entrepôts](configure-app-field-names-priorities-warehouse.md).
1. Répétez l’étape précédente pour chaque entité juridique (société) où vous utilisez l’application mobile Warehouse Management.

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Configurer un détour à partir d’un remplacement spécifique au menu

Utilisez la procédure suivante pour configurer un détour à partir d’une dérogation spécifique au menu.

1. Créez une dérogation spécifique au menu pour le menu et l’étape concernés, comme décrit dans [Personnaliser les titres et les instructions d’étape pour l’application mobile Warehouse Management](mobile-app-titles-instructions.md).
1. Trouvez la combinaison de valeurs **ID de l’étape** et **Nom de l’option de menu** que vous souhaitez modifier, puis sélectionnez la valeur dans la colonne **ID de l’étape**.
1. Sur la page qui apparaît, sur le raccourci **Détours disponibles (options de menu)**, vous pouvez spécifier l’option de menu qui doit servir de détour. Vous pouvez également sélectionner les valeurs de champ de la tâche principale qui doivent être automatiquement copiées vers et depuis le détour. Pour des exemples qui montrent comment utiliser ces paramètres, consultez les scénarios plus loin dans cet article.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a><a name="scenario-1"></a>Exemple de scénario 1 : Préparation des ventes où une recherche d’emplacement agit comme un détour

Ce scénario montre comment configurer une demande d’emplacement en tant que détour dans un flux de tâches de prélèvement des ventes dirigé par le collaborateur. Ce détour permettra aux collaborateurs de rechercher toutes les contenants à l’emplacement dans lequel ils choisissent et de choisir le contenant qu’ils souhaitent utiliser pour terminer la sélection. Ce type de détour peut être utile si le code-barres est endommagé et donc illisible par le scanner. Alternativement, il peut être utile qu’un collaborateur apprenne ce qui est réellement disponible dans le système. Notez que ce scénario ne fonctionne que si vous choisissez des emplacements contrôlés par les contenants.

### <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser les enregistrements et les valeurs de l'échantillon spécifiés pour travailler sur ce scénario, vous devez utiliser un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. Vous devez également sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Créer une dérogation spécifique au menu et configurer le détour pour le scénario 1

Dans cette procédure, vous allez configurer un détour pour l’option de menu **Prélèvement des ventes** à l’étape du contenant.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.
1. Recherchez l’ID d’étape nommé *LicensePlateId*, et sélectionnez-le.
1. Dans le volet Actions, sélectionnez **Ajouter une configuration d’étape**.
1. Dans la boîte de dialogue déroulante, utilisez le champ **Option de menu** à rechercher et sélectionnez *Prélèvement des ventes*.
1. Cliquez sur **OK**.
1. La page de détails du remplacement que vous venez de créer apparaît. Dans le raccourci **Détours disponibles (options de menu)**, sélectionnez **Ajouter** sur la barre d’outils.
1. Dans la boîte de dialogue **Ajouter un détour**, sélectionnez **Recherche d’emplacement** comme le détour qui sera mis à disposition dans l’application mobile Warehouse Management.
1. Cliquez sur **OK**.
1. Sur le raccourci **Détours disponibles (éléments de menu)**, sélectionnez le détour que vous venez d’ajouter, puis sélectionnez **Sélectionner les champs à envoyer** sur la barre d’outils.
1. Dans la boîte de dialogue **Sélectionner les champs à envoyer**, spécifiez les informations qui doivent être envoyées vers et depuis le détour. Dans ce scénario, vous autorisez les collaborateurs à utiliser l’emplacement qu’ils doivent choisir comme entrée pour le détour de recherche d’emplacement. Par conséquent, dans la section **Envoyer à partir du prélèvement des ventes**, sélectionnez **Ajouter** dans la barre d’outils pour ajouter une ligne à la grille. Définissez ensuite les valeurs suivantes pour la nouvelle ligne :

    - **Copie de la sélection des ventes :** *Emplacement*
    - **Coller dans la recherche de localisation :** *Emplacement*
    - **Soumission automatique :** *Sélectionné* (la page est actualisée avec la valeur *Emplacement*)

1. Étant donné que le détour dans ce scénario est configuré à l’étape du contenant, il sera utile que les collaborateurs puissent ramener le contenant de la recherche au flux principal. Par conséquent, dans la section **Renvoyer à la recherche d’emplacement**, sélectionnez **Ajouter** dans la barre d’outils pour ajouter une ligne à la grille. Définissez ensuite les valeurs suivantes pour la nouvelle ligne :

    - **Copie à partir de la recherche d’emplacement :** *Contenant*
    - **Coller dans la sélection des ventes :** *Contenant*
    - **Soumission automatique :** *Effacé* (aucune mise à jour automatique ne se produit lors du retour du détour avec une valeur *Contenant*)

1. Cliquez sur **OK**.

Le détour est maintenant entièrement configuré. Un bouton pour démarrer le détour **Recherche d’emplacement** apparaîtra désormais sur l’étape du contenant pour l’option de menu **Prélèvement des ventes**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Complétez un choix de vente sur un appareil mobile et utilisez le détour

Dans cette procédure, vous effectuerez un choix de vente à l’aide de l’application mobile Warehouse Management. Vous utiliserez le détour que vous venez de configurer pour trouver le contenant que vous utiliserez pour terminer l’étape de sélection.

1. Dans Microsoft Dynamics 365 Supply Chain Management, créez une commande client qui nécessitera une étape de prélèvement à partir d’un emplacement suivi par contenant. Ensuite lancez la commande client dans l’entrepôt. Notez l’ID de travail qui est généré.
1. Ouvrez l’application mobile Warehouse Management et connectez-vous à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant *24* comme ID d’utilisateur et *1* comme mot de passe.)
1. Sélectionnez le menu **Sortant**, puis sélectionnez l’option de menu **Prélèvement des ventes**.
1. Suivez les instructions de saisie de données à l’écran pour saisir l’ID de travail qui a été généré à l’étape 1.
1. À l’étape qui contient le texte **Scanner un contenant**, ouvrez le menu des actions. Vous devriez voir un nouveau bouton intitulé **Recherche d’emplacement**. Une flèche dans le coin supérieur gauche indique que le bouton commencera un détour. Sélectionnez **Recherche d’emplacement**.
1. Le détour est commencé. Sur la page suivante, confirmez l’emplacement qui a été copié à partir du flux principal.
1. Dans la liste des plaques d’immatriculation disponibles dans l’emplacement, appuyez sur le contenant que vous souhaitez recopier dans le flux principal. Sélectionnez ensuite le bouton **Précédent**.
1. Vous revenez au flux principal de prélèvement des ventes et le contenant y a été copié à partir du détour. Confirmez la valeur pour passer à l’étape suivante.
1. Vous pouvez maintenant terminer le reste du flux standard en entrant les instructions de saisie de données demandées.

Les travaux de l’entrepôt sont maintenant terminés. Le collaborateur a réussi à ouvrir un détour pour effectuer une tâche secondaire (recherche d’emplacement) sans perdre sa place dans la tâche principale, et a rapporté les informations nécessaires à la réalisation de la tâche principale.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Exemple de scénario 2 : Consultation d’article avec détours de mouvement et d’ajustement

Ce scénario montre comment configurer le mouvement et les ajustements en tant que détours multiples dans le flux de tâches de demande d’emplacement. Cette capacité peut être utile dans les situations où un collaborateur arrive à un emplacement, constate que le stock dans l’emplacement diffère de ce qui est enregistré dans le système et doit donc ajuster ou déplacer des marchandises.

Vous pouvez remplacer la recherche d’emplacement par une demande de contenant ou une demande d’article selon vos besoins.

### <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser les enregistrements et les valeurs de l'échantillon spécifiés pour travailler sur ce scénario, vous devez utiliser un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. Vous devez également sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Créer une dérogation spécifique au menu et configurer le détour pour le scénario 2

Dans cette procédure, vous allez configurer un détour pour l’option de menu **Prélèvement des ventes** à l’étape du contenant.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.
1. Recherchez et sélectionnez l’ID d’étape nommé *LocationInquiryList*.

    > [!NOTE]
    > Pour utiliser une demande d’article au lieu d’une demande d’emplacement, sélectionnez une ligne où l’ID d’étape est nommé *ItemInquiryList*. Pour utiliser une demande de contenant, sélectionnez une ligne où l’ID d’étape est nommé *LPInquiryList*.

1. Dans le volet Actions, sélectionnez **Ajouter une configuration d’étape**.
1. Dans la boîte de dialogue déroulante, utilisez le champ **Option de menu** à rechercher et sélectionnez *Recherche d’emplacement*.
1. Cliquez sur **OK**.
1. La page de détails du remplacement que vous venez de créer apparaît. Dans le raccourci **Détours disponibles (options de menu)**, sélectionnez **Ajouter** sur la barre d’outils.
1. Dans la boîte de dialogue **Ajouter un détour**, sélectionnez **Mouvement** comme le détour qui sera mis à disposition dans l’application mobile Warehouse Management.
1. Cliquez sur **OK**.
1. Sur le raccourci **Détours disponibles (éléments de menu)**, sélectionnez le détour que vous venez d’ajouter, puis sélectionnez **Sélectionner les champs à envoyer** sur la barre d’outils.
1. Dans la boîte de dialogue **Sélectionner les champs à envoyer**, spécifiez les informations qui doivent être envoyées vers et depuis le détour. Dans ce scénario, vous vous attendez à ce que les collaborateurs recherchent des emplacements contrôlés par les contenants. Par conséquent, il sera utile de copier le contenant de la recherche dans le détour **Mouvement**. Dans la section **Envoyer à partir du prélèvement des ventes**, sélectionnez **Ajouter** dans la barre d’outils pour ajouter une ligne à la grille. Définissez ensuite les valeurs suivantes pour la nouvelle ligne :

    - **Copier à partir de la recherche d’emplacement :** *Emplacement*
    - **Coller en mouvement :** *Loc / LP*
    - **Soumission automatique :** *Effacé* (aucune mise à jour automatique ne se produit)

    Dans ce détour, vous ne vous attendez pas à ce qu’aucune information ne soit copiée, car le flux principal était une recherche pour laquelle aucune étape supplémentaire n’est requise.

1. Cliquez sur **OK**.

Le détour est maintenant entièrement configuré. Un bouton pour démarrer le détour **Mouvement** apparaîtra désormais sur l’étape du contenant pour l’option de menu **Recherche d’emplacement**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Faites une recherche d’emplacement sur un appareil mobile et utilisez le détour

Dans cette procédure, vous effectuerez une recherche d’emplacement à l’aide de l’application mobile Warehouse Management. Vous utiliserez ensuite le détour pour effectuer un mouvement de marchandises.

1. Ouvrez l’application mobile Warehouse Management et connectez-vous à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant *24* comme ID d’utilisateur et *1* comme mot de passe.)
1. Sélectionnez le menu **Stock**, puis sélectionnez l’option de menu **Recherche d’emplacement**.
1. Saisissez un lieu sur lequel vous souhaitez vous renseigner, par exemple *FL-001*.
1. Lorsque la liste apparaît, appuyez longuement sur l’une des cartes qu’elle contient pour afficher les détours disponibles.
1. Sélectionnez **Mouvement**.
1. Notez que le contenant a été copié à partir de la carte que vous avez sélectionnée. Confirmez la valeur.
1. Vous pouvez maintenant suivre le flux de tâches standard pour terminer le mouvement. Une fois le travail terminé, ouvrez le menu des actions et sélectionnez **Annuler**.
1. Vous êtes renvoyé à la page **Recherche d’emplacement**. Notez que les valeurs ne sont pas automatiquement mises à jour. Par conséquent, vous devez actualiser manuellement la page pour voir les modifications du détour de mouvement.

> [!NOTE]
> La fonctionnalité *Détours à plusieurs niveaux pour l’application mobile Warehouse Management* vous permet de définir des détours à plusieurs niveaux (détours dans les détours), ce qui permettra aux utilisateurs de sauter d’un détour existant deux par un, puis de revenir en arrière. La fonctionnalité prend en charge deux niveaux de détours prêts à l’emploi et, si nécessaire, vous pouvez personnaliser votre système pour prendre en charge trois niveaux de détours ou plus en créant des extensions de code sur la table `WHSWorkUserSessionState`.
>
> La fonctionnalité *Soumettre automatiquement les étapes de détour pour l’application mobile Warehouse Management* peut permettre aux collaborateurs d’effectuer plus rapidement et plus facilement les flux de détour dans l’application mobile Warehouse Management. Elle permet d’ignorer certaines étapes de flux en laissant l’application renseigner les données de détour sur le back-end, puis de passer automatiquement à l’étape suivante en soumettant automatiquement la page, comme indiqué dans [*Exemple de scénario 1 : Préparation des ventes où une demande d’emplacement agit comme un détour*](#scenario-1).
