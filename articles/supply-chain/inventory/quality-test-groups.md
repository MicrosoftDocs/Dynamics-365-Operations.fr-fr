---
title: Groupes de tests de gestion de la qualité
description: Cette rubrique décrit comment créer des groupes de tests, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 230e402c322509f3ea89d4f1dccb5555828377ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578390"
---
# <a name="quality-management-test-groups"></a>Groupes de tests de gestion de la qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des groupes de tests, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.

La page **Groupes de tests** permet de paramétrer, modifier et afficher des groupes de tests et des tests individuels affectés. La partie supérieure de la page affiche les groupes de tests et la partie inférieure affiche les tests affectés à un groupe de tests sélectionné.

Vous pouvez affecter plusieurs stratégies à un groupe de tests, notamment un programme d'échantillonnage, un niveau de qualité acceptable et la demande de tests destructifs. Ensuite, lorsque vous affectez un test individuel à un groupe de test, vous définissez des informations supplémentaires, telles que l’ordre, les documents et les dates de validité Pour un test quantitatif; les informations que vous définissez incluent également les valeurs de mesures acceptables. Pour un test qualitatif, ces informations incluent la variable de test et le résultat par défaut.

Le groupe de test affecté à un ordre de qualité définit l’ensemble des tests par défaut devant être exécutés sur l’article spécifié. Toutefois, vous pouvez ajouter, supprimer ou modifier les tests pour un ordre de qualité. Les résultats de test sont reportés pour chaque test sur un ordre de qualité.

Lorsque vous définissez un groupe de tests, vous pouvez éventuellement spécifier un échantillonnage d'articles. Les échantillonnages d'articles sont utilisés pour définir la quantité de produit à tester. Pour plus d'informations, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md). Vous pouvez également indiquer si les tests d'un groupe de tests sont destructifs. Lors d'un test destructif, l'échantillonnage de l'article est détruit et la quantité est retirée du stock disponible.

## <a name="example-of-a-test-group"></a>Exemple de groupe de tests

Une société de fabrication définit un groupe de tests pour chaque variation de ses directives qualité. Les groupes de test reflètent les différences entre les programmes d’échantillonnage, les ensembles de tests devant être exécutés simultanément, le niveau de qualité acceptable, ainsi que d’autres facteurs. Pour les tests quantitatifs, il existe également des différences entre les valeurs de mesures acceptables. Pour faire appliquer ses directives de qualité, l'entreprise attribue un groupe de tests à chaque règle utilisée pour générer automatiquement des ordres de qualité sur la page **Associations de qualité**. Elle affecte également un groupe de tests aux ordres de qualité créés manuellement.

## <a name="create-a-test-group"></a>Création d’un groupe de test

Pour créer un groupe de tests, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de tests**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille dans la partie supérieure de la page. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Groupe de tests** - Saisissez un identifiant ou un nom unique pour le groupe de tests.
    - **Description** - Entrez une description détaillée du groupe de tests.
    - **Niveau de qualité acceptable** - Entrez le pourcentage total de résultats de test qui doivent réussir pour que le groupe de tests soit considéré comme réussi.
    - **Échantillonnage d'articles** - Sélectionnez un échantillonnage d'article. Pour plus d'informations, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md).
    - **Destructeur** - Cochez cette case pour indiquer que le groupe de tests détruira les éléments testés.

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez l'onglet **Général** dans la partie supérieure de la page. Certains des paramètres du groupe de tests sélectionné sur l'onglet **Vue d’ensemble** sont répétés ici. De plus, vous pouvez définir les champs suivants pour le groupe :

    - **Mettre à jour l'attribut du lot de stock** - Lorsque vous définissez cette option sur *Oui* ici, elle sera automatiquement définie sur *Oui* pour chaque nouveau test ajouté au groupe de tests dans la partie inférieure de la page.
    - **Mettre à jour la disposition de lot** - Lorsque vous définissez cette option sur *Oui*, si l'article en cours de test est contrôlé par lots, la disposition des lots sera automatiquement mise à jour avec la valeur sélectionnée dans le champ **Échec de la disposition de lot des ordres de qualité** ou **Succès de la disposition de lot des ordres de qualité**.
    - **Échec de la disposition de lot des ordres de qualité** - Sélectionnez le code de disposition de traitement par lots à attribuer lorsqu'un ordre de qualité qui inclut ce groupe de test échoue car il ne respecte pas le niveau de qualité acceptable.
    - **Succès de la disposition de lot des ordres de qualité** - Sélectionnez le code de disposition de traitement par lots à attribuer lorsqu'un ordre de qualité qui inclut ce groupe de test réussit car il respecte le niveau de qualité acceptable.
    - **Mettre à jour le statut du stock** - Lorsque vous définissez cette option sur *Oui*, si **Statut du stock** est activé sur le groupe de dimensions de stockage de l'article en cours de test, le statut sera automatiquement mis à jour avec le statut sélectionné dans le champ **Échec du statut de l'ordre de qualité** ou alors **Réussite du statut de l'ordre de qualité**.
    - **Échec du statut de l'ordre de qualité** - Sélectionnez le statut de stock à attribuer à l'article lorsqu'un ordre de qualité qui inclut ce groupe de tests échoue car il ne respecte pas le niveau de qualité acceptable.
    - **Réussite du statut de l'ordre de qualité** - Sélectionnez le statut de stock à attribuer à l'article lorsqu'un ordre de qualité qui inclut ce groupe de tests réussit car il respecte le niveau de qualité acceptable.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Ajouter un test qualitatif à un groupe de tests

Pour ajouter un test qualitatif à un groupe de tests, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de tests**.
1. Sur l'onglet **Vue d’ensemble** dans la partie supérieure de la page, sélectionnez le groupe de tests auquel vous souhaitez ajouter un test.
1. Dans la partie inférieure de la page, sur l'onglet **Vue d’ensemble**, sélectionnez **Ajouter** dans la barre d'outils pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Numéro de séquence** - Entrez un entier pour spécifier l'ordre dans lequel les tests doivent être effectués. Les tests qui ont des numéros de séquence plus petits seront exécutés avant ceux qui ont des numéros de séquence plus grands.

        > [!NOTE]
        > Nous vous recommandons de laisser un espace entre les numéros de séquence. Par exemple, définissez le champ **Numéro de séquence** sur *10* pour votre premier test, puis incrémentez la valeur de 10 pour chaque test supplémentaire. De cette façon, vous pouvez ajouter de nouveaux tests ultérieurement sans avoir à supprimer et recréer les lignes pour les mettre dans l'ordre souhaité.

    - **Test** – Sélectionnez le test à effectuer. Pour un test qualitatif, sélectionnez un test où le champ **Type** est défini sur *Option*.
    - **Date d’effet** - Sélectionnez la première date de validité du test. Si vous laissez ce champ vide, il n'existe aucune limite.
    - **Expiration** – Sélectionnez la dernière date de validité du test. Si vous laissez ce champ vide ou le définissez sur *Jamais*, il n'existe aucune limite.
    - **Détermination de la valeur de test** - Sélectionnez la manière dont un niveau de qualité acceptable doit être déterminé lorsque plusieurs résultats sont enregistrés pour le même test. Pour un test qualitatif, seul *Manuel* peut être sélectionné. Si vous sélectionnez l'une des autres valeurs (*Moyen*, *Minimum*, ou alors *Maximum*), vous recevrez un message d'erreur au moment d'enregistrer le groupe de tests.
    - **Attribut** - Si vous souhaitez enregistrer les résultats du test sur un attribut de lot, sélectionnez l'attribut ici, puis cochez la case **Mettre à jour l'attribut du lot de stock**.
    - **Mettre à jour l'attribut du lot de stock** – Cochez cette case pour enregistrer les résultats du test pour l'attribut de lot sélectionné dans le champ **Attribut**.

1. Dans la partie inférieure de la page, sélectionnez l'onglet **Général**. Certains des paramètres du test sélectionné sur l'onglet **Vue d'ensemble** sont répétés ici. De plus, vous pouvez définir les champs suivants pour le test :

    - **État du certificat d'analyse** - Définissez cette option sur *Oui* pour indiquer que les résultats du test doivent être imprimés sur le certificat d'analyse (CoA). Cet état peut être généré à partir de l'ordre de qualité.
    - **Action en cas d'échec** - Sélectionnez soit *Réussite* ou alors *Échec* pour indiquer si le test doit réussir ou échouer si le niveau de qualité acceptable correspondant n'est pas atteint.
    - **Niveau de qualité acceptable** - Entrez le pourcentage total de résultats de test qui doivent réussir pour que le test soit considéré comme réussi.

1. Dans la partie inférieure de la page, définissez les champs suivants sur l'onglet **Test** :

    - **Variable** – Sélectionnez la variable de test pour l'enregistrement des résultats d'un test qualitatif.
    - **Résultat par défaut** - Sélectionnez le résultat par défaut à enregistrer pour les résultats du test.
    - **Instrument de test** - Sélectionnez l'appareil à utiliser pour le test. Si un instrument de test est défini, il est automatiquement entré pour le test dans le groupe de tests.

1. Fermez la page.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Ajouter un test quantitatif à un groupe de tests

Pour ajouter un test quantitatif à un groupe de tests, procédez comme suit.

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de tests**.
1. Sur l'onglet **Vue d’ensemble** dans la partie supérieure de la page, sélectionnez le groupe de tests auquel vous souhaitez ajouter un test.
1. Dans la partie inférieure de la page, sur l'onglet **Vue d’ensemble**, sélectionnez **Ajouter** dans la barre d'outils pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Numéro de séquence** - Entrez un entier pour spécifier l'ordre dans lequel les tests doivent être effectués. Les tests qui ont des numéros de séquence plus petits seront exécutés avant ceux qui ont des numéros de séquence plus grands.

        > [!NOTE]
        > Nous vous recommandons de laisser un espace entre les numéros de séquence. Par exemple, définissez le champ **Numéro de séquence** sur *10* pour votre premier test, puis incrémentez la valeur de 10 pour chaque test supplémentaire. De cette façon, vous pouvez ajouter de nouveaux tests ultérieurement sans avoir à supprimer et recréer les lignes pour les mettre dans l'ordre souhaité.

    - **Test** – Sélectionnez le test à effectuer. Pour un test quantitatif, sélectionnez un test où le champ **Type** est défini sur *Fraction* ou *Entier*.
    - **Date d’effet** - Sélectionnez la première date de validité du test. Si vous laissez ce champ vide, il n'existe aucune limite.
    - **Expiration** – Sélectionnez la dernière date de validité du test. Si vous laissez ce champ vide ou le définissez sur *Jamais*, il n'existe aucune limite.
    - **Détermination de la valeur de test** - Sélectionnez la manière dont un niveau de qualité acceptable doit être déterminé lorsque plusieurs résultats sont enregistrés pour le même test. Les options disponibles sont *Moyenne*, *Minimum*, *Maximum* et *Manuel*.
    - **Attribut** - Si vous souhaitez enregistrer les résultats du test sur un attribut de lot, sélectionnez l'attribut ici, puis cochez la case **Mettre à jour l'attribut du lot de stock**.
    - **Mettre à jour l'attribut du lot de stock** – Cochez cette case pour enregistrer les résultats du test pour l'attribut de lot sélectionné dans le champ **Attribut**.

1. Dans la partie inférieure de la page, sélectionnez l'onglet **Général**. Certains des paramètres du test sélectionné sur l'onglet **Vue d'ensemble** sont répétés ici. De plus, vous pouvez définir les champs suivants pour le test :

    - **État du certificat d'analyse** - Définissez cette option sur *Oui* pour indiquer que les résultats du test doivent être imprimés sur le certificat d'analyse (CoA). Cet état peut être généré à partir de l'ordre de qualité.
    - **Action en cas d'échec** - Sélectionnez soit *Réussite* ou alors *Échec* pour indiquer si le test doit réussir ou échouer si le niveau de qualité acceptable correspondant n'est pas atteint.
    - **Niveau de qualité acceptable** - Entrez le pourcentage total de résultats de test qui doivent réussir pour que le test soit considéré comme réussi.

1. Dans la partie inférieure de la page, définissez les champs suivants sur l'onglet **Test** :

    - **Standard** - Entrez le montant (entier ou fraction) attendu pour les résultats du test. La valeur que vous entrez sera entrée par défaut dans les résultats du test. De plus, elle sera automatiquement entrée comme valeur par défaut dans les champs **Min** et **Max**.
    - **Min** - Entrez la valeur minimale autorisée pour les résultats du test. La valeur que vous entrez doit être inférieure au montant défini dans le champ **Standard**. Lorsque vous mettez à jour le champ **Min**, le champ **Tolérance minimale (%)** est automatiquement mis à jour. De la même manière, lorsque vous mettez à jour le champ **Tolérance minimale (%)**, le champ **Min** est automatiquement mis à jour.
    - **Max** - Entrez la valeur maximale autorisée pour les résultats du test. La valeur que vous entrez doit être supérieure au montant défini dans le champ **Standard**. Lorsque vous mettez à jour le champ **Max**, le champ **Tolérance maximale (%)** est automatiquement mis à jour. De la même manière, lorsque vous mettez à jour le champ **Tolérance maximale (%)**, le champ **Max** est automatiquement mis à jour.
    - **Instrument de test** - Sélectionnez l'appareil à utiliser pour le test. Si un instrument de test est défini, il est automatiquement entré pour le test dans le groupe de tests.

1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Instruments de test de gestion de la qualité](quality-management-processes.md)
- [Tests de gestion de la qualité](quality-management-processes.md)
- [Variables de test de gestion de la qualité](quality-management-processes.md)
- [Associations de qualité](quality-management-processes.md)
- [Attributs de lot](/supply-chain/production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
