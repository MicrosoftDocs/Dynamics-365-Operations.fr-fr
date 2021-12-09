---
title: Configurer les champs promus pour les étapes dans l'application mobile Warehouse Management
description: Cette rubrique décrit comment promouvoir et mettre en évidence des informations spécifiques pour toute étape des flux de tâches pour l’application mobile Warehouse Management.
author: MarkusFogelberg
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 392fc4d7e4f423b38e8394fa25d2e42de913bfc6
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860456"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Configurer les champs promus pour les étapes dans l'application mobile Warehouse Management

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until GA with 10.0.23 -->

> [!IMPORTANT]
> Les fonctionnalités décrites dans cette rubrique s'appliquent uniquement à la nouvelle application mobile Warehouse Management. Elles n'affectent pas l'ancienne application d'entrepôt, qui est désormais obsolète.

Cette rubrique décrit comment promouvoir et mettre en évidence des informations spécifiques pour toute étape des flux de tâches pour l’application mobile Warehouse Management. Cette capacité peut aider à concentrer l'attention des collaborateurs sur les domaines les plus importants lorsqu'ils travaillent dans un flux. Pour chaque étape de chaque processus, les administrateurs peuvent sélectionner les champs à promouvoir et les champs à mettre en évidence.

## <a name="enable-promoted-fields-in-your-system"></a>Activer les champs promus dans votre système

Avant de pouvoir configurer des champs promus, vous devez effectuer la procédure suivante pour activer les fonctionnalités requises et générer les noms de champ requis dans l'application mobile Warehouse Management.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Dans l’[espace de travail **Gestion des fonctionnalités**](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), activez les fonctionnalités qui sont répertoriées comme suit :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *instructions d'étape de l'application d'entrepôt*

    Pour plus d'informations sur la fonctionnalité *Instructions d'étape de l'application d'entrepôt*, voir [Personnaliser les titres et les instructions des étapes pour l'application mobile Warehouse Management](mobile-app-titles-instructions.md). Cette fonctionnalité est une condition préalable à la fonctionnalité *Champs promus par l'application d'entrepôt*.

1. Activez la fonctionnalité qui est répertoriée de la manière suivante :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *Champs promus par l'application d'entrepôt*

    Cette fonctionnalité est la fonctionnalité décrite dans cette rubrique.

1. Mettez à jour les noms de champ dans l'application mobile Warehouse Management en accédant à **Warehouse Management \> Paramétrage \> Périphérique mobile \> Noms des champs d'application d'entrepôt** et en sélectionnant **Créer une configuration par défaut**. Pour plus d’informations, voir [Configurer les champs pour l’application mobile Gestion des entrepôts](configure-app-field-names-priorities-warehouse.md).
1. Répétez l'étape précédente pour chaque entité juridique (société) où vous utilisez l'application mobile Warehouse Management.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Configurer les champs promus à partir d'un remplacement spécifique au menu

La procédure suivante permet de paramétrer les champs promus.

1. Créez une dérogation spécifique au menu pour le menu et l'étape concernés, comme décrit dans [Personnaliser les titres et les instructions d'étape pour l'application mobile Warehouse Management](mobile-app-titles-instructions.md).
1. Trouvez la combinaison de valeurs **ID de l'étape** et **Nom de l'option de menu** que vous souhaitez modifier, puis sélectionnez la valeur dans la colonne **ID de l'étape**.
1. Sur la page qui apparaît, sur le raccourci **Sélectionner les champs promus**, sélectionnez **Sélectionner des champs** sur la barre d'outils.
1. Dans la boîte de dialogue **Champs promus**, sélectionnez les champs que vous souhaitez promouvoir. Vous pouvez également mettre en surbrillance jusqu'à deux des champs sélectionnés. Les champs en surbrillance seront affichés en gras dans l'application mobile Warehouse Management. Lorsque vous sélectionnez des champs, tenez compte du fait que certains écrans peuvent être suffisamment grands pour n'afficher que le ou les deux premiers champs promus. Pour un exemple qui montre comment utiliser ces paramètres, consultez le scénario plus loin dans cette rubrique.

    > [!NOTE]
    > La liste **Champs disponibles** est limitée aux champs qui peuvent apparaître pour l'option de menu. Cependant, d'autres facteurs (tels que la composition de l'article) déterminent si un champ apparaît réellement dans l'application mobile Warehouse Management. Si vous avez configuré des champs promus, seuls les champs sélectionnés apparaîtront sur la page principale de l'application mobile Warehouse Management. Cependant, les collaborateurs peuvent toujours afficher les champs restants en appuyant sur la page de détails.

1. Sélectionner **OK** pour appliquer vos paramètres. Vos champs sélectionnés sont maintenant répertoriés sur le raccourci **Sélectionner les champs promus**.

## <a name="example-scenario"></a>Exemple de scénario

### <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser les exemples d'enregistrements et de valeurs spécifiés dans ce scénario, vous devez utiliser un système sur lequel les données de démonstration standard sont installées. Vous devez également sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Configurer le prélèvement des ventes avec des étapes promues à l'étape du contenant

Dans cette procédure, vous allez configurer les champs promus et mis en surbrillance pour l'option de menu **Prélèvement des ventes** à l'étape du contenant.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.
1. Recherchez l'ID d'étape nommé *LicensePlateId*, et sélectionnez-le.
1. Dans le volet Actions, sélectionnez **Ajouter une configuration d'étape**.
1. Dans la boîte de dialogue déroulante, utilisez le champ **Option de menu** à rechercher et sélectionnez *Prélèvement des ventes*.
1. Cliquez sur **OK**.
1. La page de détails du remplacement que vous venez de créer apparaît. Sur le raccourci **Sélectionner les champs promus**, sélectionnez **Sélectionner des champs** sur la barre d'outils.
1. Dans la boîte de dialogue **Champs promus**, vous pouvez sélectionner les champs à promouvoir et mettre en évidence. Dans la liste **Champs disponibles**, recherchez et sélectionnez les champs suivants, et utilisez les boutons pour les déplacer vers la liste **Champs sélectionnés** :

    - Emplacement
    - Article
    - Nom produit
    - Statut du stock

1. Utilisez les boutons fléchés vers le haut et vers le bas pour personnaliser l'ordre des champs dans la liste **Champs sélectionnés**. Dans l'application mobile Warehouse Management, les champs apparaîtront dans l'ordre que vous avez défini ici.
1. Sélectionnez le champ **Emplacement**, puis sélectionnez **Surligner**.
1. Sélectionnez **OK** pour enregistrer la configuration.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Afficher les champs promus dans l'application mobile Warehouse Management

Dans cette procédure, vous allez ouvrir l'application mobile Warehouse Management et suivre les étapes pour afficher les champs que vous avez promus et mis en évidence dans la procédure précédente.

1. Dans Microsoft Dynamics 365 Supply Chain Management, créez une commande client qui nécessitera une étape de prélèvement à partir d'un emplacement suivi par contenant. Ensuite lancez la commande client dans l’entrepôt. Notez l’ID de travail qui est généré.
1. Ouvrez l’application mobile Warehouse Management et connectez-vous à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant *24* comme ID d’utilisateur et *1* comme mot de passe.)
1. Sélectionnez le menu **Sortant**, puis sélectionnez l'option de menu **Prélèvement des ventes**.
1. Suivez les instructions de saisie de données à l'écran pour saisir l'ID de travail qui a été généré à l'étape 1.
1. À l'étape qui contient le texte **Numériser un contenant**, vous devriez voir les modifications que vous avez apportées sur la page des détails. Les champs apparaissent dans l'ordre que vous avez défini pour les champs promus, et le champ **Emplacement** est indiqué en gras.
