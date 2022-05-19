---
title: Modifier une devise comptable ou de déclaration
description: Cette rubrique explique comment modifier une devise comptable ou de déclaration (ou ajouter une devise de déclaration à la configuration de la comptabilité).
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff5c38193e8469cb806c525b77809844847d6c92
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710888"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Modifier une devise comptable ou de déclaration

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment modifier une devise comptable ou de déclaration (ou ajouter une devise de déclaration à la configuration de la comptabilité).

## <a name="symptom"></a>Problème

Vous souhaitez modifier une devise comptable ou de déclaration (ou ajouter une devise de déclaration à la configuration de la comptabilité). Cela se produit généralement dans les scénarios suivants :

- La mauvaise devise de comptabilité ou de déclaration a été spécifiée lors de la création d’une entité juridique. Vous voulez maintenant changer cette devise.
- Une devise de déclaration a été spécifiée lors de la configuration d’une entité juridique, mais l’organisation souhaite désormais supprimer cette devise.
- L’organisation procède à une mise à niveau ou à une migration vers Microsoft Dynamics 365 Finance et souhaite modifier la devise comptable ou de déclaration.

Une organisation qui n’utilisait pas auparavant la fonctionnalité de devise double souhaite désormais l’utiliser. Ce problème se produit généralement dans les scénarios suivants :

- Aucune devise de déclaration n’a été spécifiée lors de la création d’une entité juridique. (Une devise de déclaration est facultative.) Vous souhaitez maintenant ajouter une devise de déclaration.

## <a name="resolution"></a>Résolution

La chose la plus importante est de savoir si des transactions (réelles ou budgétaires) ont été enregistrées dans l’entité juridique pour la configuration de la comptabilité. **Vous ne pouvez pas modifier la devise comptable ou de déclaration, ni ajouter une devise de déclaration, si des transactions (réelles ou budgétaires) ont été validées dans l’entité juridique.** Suivez les étapes de l’une des sections suivantes, en fonction de la validation ou non des transactions.

### <a name="no-transactions-have-been-posted"></a>Aucune transaction n’a été validée

1. Dans l’entité juridique pour laquelle vous mettez à jour les devises, accédez à **Comptabilité \> Configuration de la comptabilité \> Comptabilité**.
2. Sur la page **Comptabilité**, sélectionnez **Modifier**.
3. Sur le raccourci **Devise**, sélectionnez la devise comptable et la devise de déclaration à utiliser pour l’entité juridique.
4. Sélectionnez **Enregistrer**.

Si les champs de la devise comptable et de la devise de déclaration ne sont pas disponibles sur la page **Comptabilité**, une ou plusieurs transactions (réelles ou budgétaires) ont été validées dans l’entité juridique. Par conséquent, les devises ne peuvent pas être modifiées. Dans ce cas, suivez les étapes de la section suivante.

### <a name="transactions-have-been-posted"></a>Des transactions ont été validées

**Si des transactions ont été validées dans l’entité juridique, la seule façon de modifier ou d’ajouter des devises de comptabilité et de déclaration est de créer une nouvelle entité juridique avec des devises correctes.** Pour faciliter ce processus, la gestion des données dans le système vous permet de copier les enregistrements de configuration et les enregistrements de base de l’entité juridique actuelle vers une nouvelle entité juridique.

Les modifications des devises de comptabilité et de déclaration sont appliquées partout. Elles affectent non seulement la Comptabilité, mais également tous les livres auxiliaires (Comptabilité client, Comptabilité fournisseur, Stock, Projet, etc.), toutes les solutions de fournisseurs de logiciels indépendants (ISV) et toute extension appliquée pour enregistrer les montants.

Le processus de recherche et de conversion de chaque montant dans une devise différente est sujet à erreur. Par conséquent, l’équipe d’ingénierie n’approuvera pas un script qui modifie ou ajoute des devises de comptabilité et de déclaration. De plus, bien qu’un outil qui était auparavant disponible pour Microsoft Dynamics AX 2012 permet de modifier ou d’ajouter des devises de comptabilité et de déclaration, il est obsolète à la fois pour AX 2012 R3 et Finance.

Suivez ces étapes pour copier la configuration et les données principales de l’entité juridique actuelle vers une nouvelle entité juridique.

1. Accédez à **Espaces de travail \> Gestion des données**.
2. Sélectionnez **Modèles** sous le groupe **Import/Export**.
3. Assurez-vous que les modèles sont disponibles. Si aucun modèle n’est disponible, sélectionnez **Charger les modèles par défaut** et attendez que les modèles soient générés.
4. Revenez dans l’espace de travail **Gestion de données**.
5. Sélectionnez **Copier dans l’entité juridique**.
6. Entrez le nom et la description du groupe.
7. Dans le champ **Entité juridique source**, sélectionnez l’entité juridique à partir de laquelle copier les données.
8. Dans le raccourci **Entités juridiques de destination**, sélectionnez **Créer des entités juridiques** pour créer une nouvelle entité juridique dans laquelle vous pouvez copier les données d’entité juridique source. Sélectionnez **Sélectionner existant** pour copier des données vers une entité juridique existante.
9. Facultatif : définissez le champ **Copier des souches de numéros** sur **Oui**. (Cette étape est recommandée lorsque vous copiez des données.)
10. Dans la zone **Entités sélectionnées**, sélectionnez **Ajouter un modèle**.
11. Sélectionnez les modèles à utiliser. Les modèles suggérés pour une nouvelle entité juridique incluent **025 - Comptabilité** et **Finances**. Nous vous recommandons de consulter tous les autres modèles disponibles pour déterminer si l’un d’entre eux s’applique à vos besoins.
12. Sélectionnez **Copier dans l’entité juridique** pour démarrer un processus de traitement par lots qui créera les entités sélectionnées et les copiera dans l’entité juridique de destination.
13. Une fois le processus terminé, mais avant que toute transaction ne soit validée, accédez à la comptabilité et mettez à jour les devises de comptabilité et de déclaration comme décrit précédemment dans cette rubrique.

Si vous avez créé une nouvelle entité juridique afin de pouvoir modifier la devise comptable ou de déclaration, vérifiez que les soldes de début ont été convertis des devises de l’ancienne entité juridique vers les nouvelles devises.

Pour voir une vidéo sur les étapes précédentes, consultez [Copier dans l’entité juridique](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
