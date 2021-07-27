---
title: Gérer plusieurs mises en correspondance dérivées pour une seule racine de modèle
description: Cette rubrique explique comment gérer plusieurs mises en correspondance dérivées configurées pour une seule racine de modèle.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595de6292b81ca78bf08a66f61850c3b5a537396
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354389"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Gérer plusieurs mises en correspondance dérivées pour une seule racine de modèle

[!include [banner](../includes/banner.md)]

Un composant [modèle](general-electronic-reporting.md#data-model-and-model-mapping-components) de données de [gestion des états électroniques](general-electronic-reporting.md) est utilisé dans chaque composant au [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques en tant que source de données pour générer les documents sortants. Pour décrire un domaine métier unique, configurez un composant de modèle de données qui a de nombreuses définitions de racine. 

Chaque définition de racine vous permet de représenter les données de ce domaine de la manière la mieux adaptée à des objectifs de gestion des états spécifiques. Pour chaque définition racine, vous pouvez configurer un composant [de mise en correspondance de modèle](general-electronic-reporting.md#data-model-and-model-mapping-components) de gestion des états électroniques comme la mise en œuvre spécifique à Microsoft Dynamics 365 Finance de votre modèle de données. De cette manière, vous décrivez comment votre modèle de données est rempli lors de l’exécution.

Les composants de mise en correspondance de modèle de gestion des états électroniques peuvent résider dans les [configurations](general-electronic-reporting.md#Configuration) de modèle de données de gestion des états électroniques et configurations de mise en correspondance du modèle de gestion des états électroniques. Une seule configuration de gestion des états électroniques peut contenir de nombreux composants de mise en correspondance, chacun d’eux étant configuré pour une seule définition racine. Sinon, une seule configuration de gestion des états électroniques peut contenir un seul composant de mise en correspondance, chacun d’eux étant configuré pour une seule définition racine.

De nombreux fournisseurs de configuration peuvent proposer des configurations de mappage de modèle de gestion des états électroniques pour le même modèle de données de gestion des états électroniques. Ces configurations de mise en correspondance de modèle peuvent contenir des composants de mise en correspondance pour différentes définitions de racine. Vous pouvez utiliser un mappage de modèle pour une définition racine offerte par un [fournisseur](general-electronic-reporting.md#Provider) et utiliser un mappage de modèle pour une autre définition de racine proposée par un autre fournisseur.

Les procédures de cette rubrique expliquent comment gérer plusieurs configurations de mise en correspondance de modèle de gestion des états électroniques d’un modèle de données de gestion des états électroniques lorsqu’elles contiennent différents composants de mise en correspondance de modèle configurés pour la même définition de racine. 

Pour exécuter les procédures dans cette rubrique, vous devez être affecté au rôle Administrateur système ou Développeur d’états électroniques.

Toutes les procédures suivantes peuvent être effectuées dans la société USMF. Aucun codage n’est requis.

## <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

En tant qu’utilisateur doté du rôle de développeur d’états électroniques, vous devez [configurer l’ensemble minimal](er-quick-start2-customize-report.md#ConfigureFramework) de paramètres ER requis pour commencer à utiliser la structure ER pour générer des documents commerciaux.

## <a name="import-the-standard-er-format-configurations"></a>Importer les configurations du format de gestion des états électroniques standard

Pour ajouter les configurations ER standard à votre instance actuelle de Finance, vous devez les importer depuis le référentiel ER qui a été configuré pour cette instance. Suivez les étapes de [Télécharger les configurations ER depuis le référentiel global du service de configuration](er-download-configurations-global-repo.md) pour importer les configurations de format de gestion des états électroniques suivantes :

- **Facture financière (Excel)**, version 220.106
- **Facture de projet (Excel)**, version 226.27

## <a name="review-the-imported-er-configurations"></a>Passer en revue les configurations de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**.

    ![Passer en revue les configurations importées sur la page Configurations.](./media/er-multiple-model-mappings-image1.png)

4. Passez en revue le format **Facture financière (Excel)**  :

    1. Dans l’arborescence de configuration du volet gauche, sélectionnez **Facture financière (Excel)**.
    2. Dans le volet Actions, sélectionnez **Concepteur**.
    3. Sur la page **Concepteur de format**, sous l’onglet **Mise en correspondance**, dans la liste des sources de données, sélectionnez **Modèle**.
    4. Sélectionnez **Afficher**.
    
       Le format de gestion des états électroniques actuel est configuré pour utiliser la définition racine **InvoiceCustomer** de **Modèle de facture**. Lorsque ce format est exécuté et que la source de données **Modèle** est appelée, le mappage de modèle configuré pour la définition racine **InvoiceCustomer** est utilisée pour accéder aux données d’application et remplir le modèle de données.

        ![Passer en revue la source de données de modèle sur la page Concepteur de format.](./media/er-multiple-model-mappings-image2.png)

    6. Fermez la page **Concepteur de format**.

5. Passer en revue le contenu de la configuration **Mappage de modèle de facture** :

    1. Dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture**.
    2. Dans le volet Actions, sélectionnez **Concepteur**.
    3. Sur la page **Mise en correspondance de modèle avec une source de données**, notez que la configuration de mappage de modèle de gestion des états électroniques actuelle contient plusieurs composants de mappage de modèle :

        + La mise en correspondance de modèle **Facture client** est configurée pour la définition racine **InvoiceCustomer** de **Modèle de facture**. Par conséquent, lorsque le format de gestion des états électroniques **Facture financière (Excel)** est exécuté, le mappage de modèle **Facture client** de cette configuration ER peut être choisi pour accéder aux données d’application et remplir le modèle de données.
        + Le mappage de modèle **Facture projet** est configuré pour la définition racine **InvoiceProject** de **Modèle de facture**. Par conséquent, lorsque le format de gestion des états électroniques de **Facture financière (Excel)** est exécuté, la mise en correspondance du modèle **Facture projet** de cette configuration de gestion des états électroniques peut être choisie pour accéder aux données d’application et remplir le modèle de données.

        ![Mappage de modèle de facture sur la page Mappage de modèle à la source de données.](./media/er-multiple-model-mappings-image3.png)

    4. Fermez la page **Mise en correspondance de modèle avec une source de données**.
    5. Sur l’organisateur **Versions**, sélectionnez **Supprimer** pour supprimer toutes les versions de cette configuration de gestion des états électroniques postérieures à la version 240.175.

6. Passer en revue le contenu de la configuration **Mappage de modèle de facture projet (RDP)**  :

    1. Dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture projet (RDP)**.
    2. Dans le volet Actions, sélectionnez **Concepteur**.
    3. Sur la page **Mise en correspondance de modèle avec une source de données**, observez que la configuration de mappage de modèle de gestion des états électroniques actuelle contient le mappage de modèle **InvoiceProject** et que ce mappage de modèle est configuré pour la définition de racine **InvoiceProject** de **Modèle de facture**. Lorsque le format de gestion des états électroniques de **Facture projet (Excel)** est exécuté, sélectionnez le mappage de modèle **InvoiceProject** de cette configuration de gestion des états électroniques pour accéder aux données d’application et remplir le modèle de données.

        ![Mappage de modèle de facture de projet sur la page Mappage de modèle à la source de données.](./media/er-multiple-model-mappings-image4.png)

    4. Fermez la page **Mise en correspondance de modèle avec une source de données**.
    5. Sur l’organisateur **Versions**, sélectionnez **Supprimer** pour supprimer toutes les versions de cette configuration de gestion des états électroniques postérieures à la version 226.35.

## <a name="customize-the-imported-er-configurations"></a>Personnaliser les configurations de gestion des états électroniques importées

Cette section explique comment [Personnaliser](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) les mappages de modèles fournis par Microsoft. Par exemple, une personnalisation peut être nécessaire pour implémenter votre logique personnalisée ou ajouter des liaisons manquantes.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Personnaliser la configuration de mappage de modèle de facture

1. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture**.
2. Dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue **Créer la configuration**, dans le champ **Nouveau**, sélectionnez **Provenant du nom : Mappage de modèle de facture, Microsoft**.
4. Dans le champ **Nom**, saisissez **Mappage de modèle de facture Litware**.
5. Sélectionnez **Créer une configuration**.
6. [Marquez](er-quick-start2-customize-report.md#MarkFormatRunnable) la version [brouillon](general-electronic-reporting.md#component-versioning) du mappage dérivé disponible pour une utilisation au moment de l’exécution :

    1. Dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Utiliser les paramètres**.
    2. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.
    3. Sélectionnez **Modifier** pour rendre la page modifiable, selon les besoins.
    4. Pour la configuration **Mappage de modèle de facture Litware** actuellement sélectionnée dans l’arborescence de configuration, définissez l’option **Exécuter le brouillon** sur **Oui**.

7. Dans le volet Actions, sélectionnez **Concepteur** pour examiner les mappages de modèles de cette configuration.

    ![Passer en revue les mappages de modèle de facture sur la page Mappage de modèle à la source de données.](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > Vous pouvez maintenant ouvrir l’un des composants de mappage de modèle pour la gestion des états électroniques de cette configuration de gestion des états électroniques dans le concepteur pour configurer votre logique personnalisée. Pour plus d’informations, consultez [Personnaliser la configuration du mappage de modèle](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Fermez la page **Mise en correspondance de modèle avec une source de données**.

Vous avez maintenant les configurations **Mappage de modèle de facture** et **Mappage de modèle de facture Litware**, chacune ayant un mappage de modèle configuré pour la définition racine **InvoiceCustomer**. Attribuez explicitement l’un des mappages de modèle en tant que mappage de modèle par défaut utilisé par l’un des formats de gestion des états électroniques, tels que le format **Facture financière (Excel)** qui contient une source de données de modèle avec la définition racine **InvoiceCustomer**. Sinon, lorsque vous exécutez, modifiez ou validez l’un des formats de gestion des états électroniques, l’exception suivante est levée pour vous informer qu’aucun mappage de modèle par défaut n’a été explicitement attribué :
 
> Il existe plus d’un mappage de modèle pour le modèle de données ’\<model name\> (\<root descriptor\>) ’ dans les configurations \<configuration names separated by commas\>. Définissez l’une des configurations par défaut.

![Ouvrir le format pour modification sur la page Configurations.](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Personnaliser la configuration de mappage de modèle de facture projet (RDP)

1. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture projet (RDP)**.
2. Dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue **Créer la configuration**, dans le champ **Nouveau**, sélectionnez **Provenant du nom : Mappage de modèle de facture projet (RDP), Microsoft**.
4. Dans le champ **Nom**, saisissez **Mappage de modèle de facture projet Litware**.
5. Sélectionnez **Créer une configuration**.
6. Pour la configuration **Mappage de modèle de facture projet Litware** actuellement sélectionnée dans l’arborescence de configuration, définissez l’option **Exécuter le brouillon** sur **Oui**.
7. Dans le volet Actions, sélectionnez **Concepteur** pour examiner les mappages de modèles de cette configuration.

    ![Passer en revue les mappages de modèle de facture de projet personnalisés sur la page Mappage de modèle à la source de données.](./media/er-multiple-model-mappings-image7.png)

8. Fermez la page **Mise en correspondance de modèle avec une source de données**.

Vous avez maintenant les configurations **Mappage de modèle de facture**, **Mappage de modèle de facture projet (RDP)**, et **Mappage de modèle de facture projet Litware**. Chacune de ces configurations a un mappage de modèles configuré pour la définition racine **InvoiceProject**. Affectez explicitement l’un des mappages de modèles comme mappage de modèles par défaut utilisé par l’un des formats de gestion des états électroniques. Par exemple, utilisez le format **Facture projet (Excel)** qui contient une source de données de modèle avec la définition racine **InvoiceProject**. Sinon, lorsque vous exécutez ou modifiez l’un des formats de gestion des états électroniques, une exception est levée pour vous informer qu’aucun mappage de modèle par défaut n’a été explicitement attribué.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Sélectionner la configuration Litware de mappage de modèle de facture dérivée comme configuration contenant les mappages de modèle par défaut

1. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture Litware**.
2. Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

    ![Définition de la mise en correspondance des modèles comme mise en correspondance des modèles par défaut sur la page Configurations.](./media/er-multiple-model-mappings-image8.png)

    En raison de ce paramètre, la mise en correspondance des modèles **Copie facture client** est utilisée lorsque vous exécutez la **Facture financière (Excel)**, ou lorsque vous la modifiez ou la validez. La mise en correspondance des modèles **Facture client** de la configuration **Mappage de modèle de facture** est ignorée.

    Vous pouvez maintenant ouvrir le format **Facture financière (Excel)** pour révision dans le concepteur de format.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Sélectionner la configuration Litware de mappage de modèle de facture projet dérivée comme configuration contenant les mappages de modèle par défaut

1. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture projet Litware**.
2. Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

    Dans ce cas, contrairement au cas décrit pour la configuration **Mappage de modèle de facture Litware** dans la précédente section, vous ne pouvez pas commencer à utiliser la mise en correspondance des modèles **Copie InvoiceProject** depuis la configuration **Mappage de modèle de facture projet Litware**. Deux configurations qui contiennent un mappage de modèle pour la définition racine **InvoiceProject** sont actuellement marquées comme configuration par défaut. Par conséquent, ils ont la même priorité d’utilisation. Pour résoudre ce problème, suivez les étapes restantes de cette procédure.

3. Dans l’arborescence de configuration du volet gauche, sélectionnez **Mappage de modèle de facture Litware**.
4. Dans le volet Actions, sélectionnez **Concepteur**.
5. Sur la page **Mise en correspondance de modèle avec une source de données**, sélectionnez **Modifier** pour rendre la page modifiable, si nécessaire.
6. Sélectionnez la mise en correspondance des modèles **Copie facture projet**, puis cochez la case **Est supprimé** correspondante.

    ![Définir la mise en correspondance des modèles comme virtuellement supprimée sur la page Mise en correspondance de modèle avec une source de données.](./media/er-multiple-model-mappings-image9.png)

    En raison de ce paramètre, la configuration **Mappage de modèle de facture Litware** est traitée comme si elle n’a pas de mappage de modèles pour la définition racine **InvoiceProject**. La mise en correspondance des modèles **Copie InvoiceProject** émise par défaut. La configuration, **Mappage de modèle de facture projet Litware**, qui contient ce mappage de modèle, est marquée comme configuration par défaut. Puisqu’elle est marquée par défaut, elle a une priorité supérieure au mappage de modèle **InvoiceProject** depuis la configuration **Mappage de modèle de facture projet (RDP)**.

## <a name="other-considerations"></a>Autres considérations

Le mappage de modèle **Copie InvoiceProject** de la configuration **Mappage de modèle de facture projet Litware** est conçu pour utiliser la source de données **ReportDataProvider**. La source de données fait partie du type *Objet* qui fait référence à la classe d’application **PsaProjInvoiceDP**. Cette classe est implémentée en tant que fournisseur de données pour le rapport SQL Server Reporting Services (SSRS) de facture projet de l’infrastructure de gestion de l’impression. Sélectionnez cette source de données comme le [point d’intégration](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents) de la gestion des états électroniques. L’implémentation actuelle de la gestion des états électroniques pour les rapports de gestion d’impression prend en compte ce paramètre. Pour plus de détails, consultez le code source de la classe d’application **ERPrintMgmtDataProviderReport**. Au moment de l’exécution, l’affectation de la source de données **ReportDataProvider** en tant que point d’intégration du mappage de modèle oblige Finance à traiter ce composant de mappage avec une priorité supérieure au composant de mappage **InvoiceProject** depuis la configuration **Mappage de modèle de facture projet (RDP)**.

## <a name="see-also"></a>Voir également :

- [Gérer la mise en correspondance de modèle de gestion des états électroniques dans des configurations ER distinctes](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Configurer les mises en correspondance de modèle de gestion des états électroniques en fonction du contexte de pays](er-country-dependent-model-mapping.md)
- [Modifications de l’API du cadre des états électroniques](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]