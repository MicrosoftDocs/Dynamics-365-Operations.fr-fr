---
title: Flux de travail de client
description: Cette rubrique fournit des informations sur le flux de travail de client. Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l’aide du flux de travail avant de les ajouter au client.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: af66887dda551d3820b744fbb96d7d13c897e71b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236888"
---
# <a name="customer-workflow"></a>Flux de travail de client

[!include [banner](../includes/banner.md)]

Le flux de travail de client a été ajouté à la version 8.0.4. Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l’aide du flux de travail avant de les ajouter au client.

## <a name="set-up-the-customer-workflow"></a>Paramétrer le flux de travail de client

Avant de pouvoir utiliser la fonctionnalité de flux de travail de client, vous devez l’activer.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
2. Dans l’onglet **Général**, sous le raccourci **Approbation du client**, définissez l’option **Activer les approbations de client** sur **Oui** pour activer la fonction.
3. Dans le champ **Comportement de l’entité de données**, sélectionnez le comportement que les entités de données doivent adopter lorsque les données sont importées :

    - **Autoriser les modifications sans approbation** : Une entité peut mettre à jour l’enregistrement client sans le traiter via le flux de travail.
    - **Rejeter les modifications** : Il est impossible d’apporter des modifications à cet enregistrement client. L’importation échouera pour les champs activés pour le flux de travail.
    - **Créer des propositions de modification** : Tous les champs seront modifiés à l’exception des champs activés pour le flux de travail. Les nouvelles valeurs de ces champs seront proposées au client en tant que modifications et le flux de travail sera lancé automatiquement.

4. Dans la liste des champs du client, activez la case à cocher **Activer** pour chaque champ qui doit être approuvé avant que les modifications soient appliquées.
5. Accédez à **Comptabilité client \> Configuration \> Flux de travail de la comptabilité client**.
6. Sélectionnez **Nouveau**.
7. Sélectionnez **Flux de travail des modifications proposées du client**. 
8. Paramétrez le flux de travail afin qu’il corresponde à votre processus d’approbation. L’élément d’approbation de flux de travail **Approbation de flux de travail pour la modification proposée du client** appliquera les modifications au client.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Modifier les informations client et envoyer les modifications au flux de travail

Lorsque vous modifiez un champ qui est activé pour le flux de travail, la page **Modifications proposées** s’affiche. Cette page affiche la valeur initiale du champ et la nouvelle valeur entrée. Le champ que vous avez modifié est rétabli sur sa valeur d’origine. Un message de statut dans la page vous informe que vos modifications n’ont pas été soumises.

Chaque fois que vous modifiez un champ qui est activé pour le flux de travail, il est ajouté à la liste des modifications proposées. Pour ignorer la valeur proposée pour un champ, utilisez le bouton **Ignorer** en regard du champ dans la liste. Pour ignorer toutes les modifications, utilisez le bouton **Ignorer toutes les modifications** en bas de la page. Cliquez sur **OK** pour fermer la page.

Une fois que vous avez au moins une modification proposée, deux menus supplémentaires apparaissent dans le volet Actions : **Modifications proposées** et **Flux de travail**.

1. Sélectionnez **Modifications proposées** pour ouvrir la page **Modifications proposées** et consulter vos modifications.
2. Sélectionnez **Flux de travail \> Soumettre** pour envoyer les modifications au flux de travail.

    Le statut dans la page est remplacé par **Modifications en attente d’approbation**.

Le flux de travail suit le processus de flux de travail standard dans l’application. L’approbateur est dirigé vers la page **Client**, où les modifications peuvent être vérifiées sur la page **Modifications proposées**, puis il doit sélectionner **Flux de travail \> Approuver** pour approuver le flux de travail. Une fois toutes les approbations effectuées, les champs sont mis à jour avec les valeurs que vous avez proposées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]