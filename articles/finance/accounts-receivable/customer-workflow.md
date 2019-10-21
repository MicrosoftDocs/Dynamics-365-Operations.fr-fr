---
title: Workflow de client
description: Cette rubrique fournit des informations sur le workflow de client. Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l'aide du workflow avant de les ajouter au client.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8ff91a1df82d6195da266b97c347ef27afec662d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175931"
---
# <a name="customer-workflow"></a>Workflow de client

[!include [banner](../includes/banner.md)]

Le workflow de client a été ajouté à la version 8.0.4. Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l'aide du workflow avant de les ajouter au client.

## <a name="set-up-the-customer-workflow"></a>Paramétrer le workflow de client

Avant de pouvoir utiliser la fonctionnalité de workflow de client, vous devez l'activer.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
2. Dans l'onglet **Général**, sous l'organisateur **Approbation du client**, définissez l'option **Activer les approbations de client** sur **Oui** pour activer la fonction.
3. Dans le champ **Comportement de l'entité de données**, sélectionnez le comportement que les entités de données doivent adopter lorsque les données sont importées :

    - **Autoriser les modifications sans approbation** : Une entité peut mettre à jour l'enregistrement client sans le traiter via le workflow.
    - **Rejeter les modifications** : Il est impossible d'apporter des modifications à cet enregistrement client. L'importation échouera pour les champs activés pour le workflow.
    - **Créer des propositions de modification** : Tous les champs seront modifiés à l'exception des champs activés pour le workflow. Les nouvelles valeurs de ces champs seront proposées au client en tant que modifications et le workflow sera lancé automatiquement.

4. Dans la liste des champs du client, activez la case à cocher **Activer** pour chaque champ qui doit être approuvé avant que les modifications soient appliquées.
5. Accédez à **Comptabilité client \> Configuration \> Workflows de la comptabilité client**.
6. Sélectionnez **Nouveau**.
7. Sélectionnez **Workflow des modifications proposées du client**. 
8. Paramétrez le workflow afin qu'il corresponde à votre processus d'approbation. L'élément d'approbation de workflow **Approbation de workflow pour la modification proposée du client** appliquera les modifications au client.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Modifier les informations client et envoyer les modifications au workflow

Lorsque vous modifiez un champ qui est activé pour le workflow, la page **Modifications proposées** s'affiche. Cette page affiche la valeur initiale du champ et la nouvelle valeur entrée. Le champ que vous avez modifié est rétabli sur sa valeur d'origine. Un message de statut dans la page vous informe que vos modifications n'ont pas été soumises.

Chaque fois que vous modifiez un champ qui est activé pour le workflow, il est ajouté à la liste des modifications proposées. Pour ignorer la valeur proposée pour un champ, utilisez le bouton **Ignorer** en regard du champ dans la liste. Pour ignorer toutes les modifications, utilisez le bouton **Ignorer toutes les modifications** en bas de la page. Cliquez sur **OK** pour fermer la page.

Une fois que vous avez au moins une modification proposée, deux menus supplémentaires apparaissent dans le volet Actions : **Modifications proposées** et **Workflow**.

1. Sélectionnez **Modifications proposées** pour ouvrir la page **Modifications proposées** et consulter vos modifications.
2. Sélectionnez **Workflow \> Soumettre** pour envoyer les modifications au workflow.

    Le statut dans la page est remplacé par **Modifications en attente d'approbation**.

Le workflow suit le processus de workflow standard dans l'application. L'approbateur est dirigé vers la page **Client**, où il peut revoir les modifications sur la page **Modifications proposées**, puis sélectionner **Workflow \> Approuver** pour approuver le workflow. Une fois toutes les approbations effectuées, les champs sont mis à jour avec les valeurs que vous avez proposées.
