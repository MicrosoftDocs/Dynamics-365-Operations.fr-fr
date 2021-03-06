---
title: Instantanés de balance âgée des clients
description: Cette rubrique fournit des informations sur les instantanés de balance âgée des clients. Un instantané de balance âgée calcule les balances âgées d'un groupe de clients à un moment donné.
author: JodiChristiansen
ms.date: 05/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b88d3fe97d14d3e2f766367de501148063582000
ms.sourcegitcommit: 16376a301a0f121f384d77f9976638f701f8e88e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6123360"
---
# <a name="customer-aging-snapshots"></a>Instantanés de balance âgée des clients

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les instantanés de balance âgée des clients. Un instantané de balance âgée calcule les balances âgées d'un groupe de clients à un moment donné. Vous pouvez créer des enregistrements d’instantanés de balance âgée pour tous les clients ou pour les clients d’un regroupement de clients.

Les informations relatives aux instantanés de balance âgée s’affichent sur la page de liste **Soldes chronologiques** et sur la page **Recouvrements**. Vous devez créer un instantané de balance âgée avant d’utiliser la page de liste **Soldes chronologiques**. La page de liste affiche uniquement les clients pour lesquels un instantané de balance âgée a été créé.

L'espace de travail **Crédits et relances client** affiche également le vieillissement du client. Pour plus d'informations, consultez [Contenu Power BI sur la gestion des crédits et des relances](credit-collections-power-bi.md).

> [!NOTE]
> Pour réduire le temps nécessaire à la création d'un instantané de balance âgée, activez la fonctionnalité **Amélioration des performances de vieillissement des clients** dans l'espace de travail **Gestion des fonctionnalités**. Cependant, n'utilisez pas de pools de clients lorsque cette fonctionnalité est activée. Si un pool de clients est sélectionné, la fonctionnalité ne fonctionnera pas, mais vous pouvez toujours créer un instantané de balance âgée.

Lorsque vous créez un instantané de vieillissement client, utilisez les champs suivants pour saisir des informations à son sujet :

- **Définition de la plage âgée** – Sélectionnez la définition de plage âgée pour l'instantané de balance âgée. Vous pouvez avoir un instantané de balance âgée pour chaque définition de plage âgée. L'instantané de balance âgée et la définition de la période de vieillissement doivent être créés séparément.
- **ID de regroupement** – Ce champ est facultatif. Vous pouvez utiliser un pool pour définir l'ensemble de clients à traiter dans l'instantané de balance âgée. Si vous sélectionnez un regroupement de clients dans ce champ, un instantané de balance âgée est créé pour les comptes client faisant partie de ce regroupement de clients. Le regroupement de clients sélectionné doit être de type **Instantané de balance âgée**. Si vous laissez ce champ vide, un instantané de balance âgée est créé pour tous les comptes clients.

    > [!NOTE]
    > Si la fonctionnalité **Amélioration des performances de vieillissement des clients** est activée, ne sélectionnez pas de pool de clients.

- **Critères** - L'instantané de balance âgée vieillira en fonction de la date que vous sélectionnez :

    - **Date de transaction** – L'âge de chaque transaction est calculé sur sa date de transaction.
    - **Date d’échéance** : L'âge de chaque transaction est calculé en fonction de sa date d’échéance.
    - **Date de document** : l'âge de chaque transaction se calcule en fonction de sa date de document.

- **Agé tel que** : Permet de sélectionner la date dans le champ **Date du jour** pour l’instantané de balance âgée. Les périodes de balances âgées sont ensuite calculées en fonction de cette date. 

    - **Date du jour** : utilisez la date système. Sélectionnez cette option si le traitement est paramétré pour intervenir dans un traitement par lots récurrent. Ensuite, chaque fois que le lot est exécuté, la date système de cette exécution est utilisée.
    - **Date sélectionnée** : utilisez une date que vous spécifiez. Si vous sélectionnez cette option, vous devez entrer une date de vieillissement.

    Par exemple, la période de vieillissement actuelle est de 30 jours. Si vous sélectionnez **La date d'aujourd'hui** dans ce champ, la période de vieillissement actuelle commence à la date du jour et inclut ensuite les 29 jours précédents. Si vous sélectionnez **Date sélectionnée** dans ce champ et entrez une date, la période de vieillissement actuelle commence à la date spécifiée et inclut ensuite les 29 jours précédents.

- **Mettre à jour l'état de la collection** - Définissez cette option sur **Oui** pour mettre à jour l'état de collection des transactions de la page **Collections** en passant de **Promesse de payer** à **Promesse de payer brisée** si la date de vieillissement dépasse la date du champ **Date de la promesse de paiement**. Définissez cette option sur **Non** pour laisser l'état de la collection inchangé sur la page **Collections**.
- **Inclure les clients avec un solde nul** - Paramétrez cette option sur **Oui** pour inclure tous les clients, quel que soit leur solde. Si vous incluez tous les clients, nous vous recommandons d'activer la fonctionnalité **Amélioration des performances de vieillissement des clients** et que vous n'utilisez pas de pools de clients. Définissez cette option sur **Non** pour n'inclure que les clients qui ont un solde. Ce paramètre permet d'accélérer les performances, car les clients qui n'ont pas de solde sont ignorés.
- **Plage société** - Dans l'onglet **Plage société**, sélectionnez les entités juridiques (sociétés) à inclure dans l'instantané de balance âgée. Seules les entités juridiques paramétrées pour les paiements centralisés sont disponibles pour la sélection. Les transactions des entités juridiques sélectionnées sont ensuite incluses dans les périodes de vieillissement pour les clients qui ont le même ID de partie dans toutes ces entités juridiques. Les montants en devise sont convertis dans la devise de l'entité juridique à laquelle vous êtes connecté lors de la création de l'instantané de balance âgée.

Nous vous recommandons de planifier ce processus pour qu'il s'exécute dans un lot.

> [!NOTE]
> Pour améliorer les performances des lots lors de la création d'instantanés vieillissants, saisissez un nombre dans le champ **Nombre maximum de tâches par lots** dans le raccourci **Valeurs par défaut des collections** au sein de l'onglet **Collections** sur la page **Paramètres de la comptabilité client**. Dans le champ **Soldes client échus**, nous vous recommandons de commencer par la valeur par défaut de **100**, puis ajustez la valeur pour optimiser le traitement en fonction de votre situation.

