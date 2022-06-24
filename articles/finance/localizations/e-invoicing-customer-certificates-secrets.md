---
title: Certificats et clés secrètes client
description: Cet article explique comment paramétrer les certificats et clés secrètes client dans la fonctionnalité Facturation électronique.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a4d33135bf352a4c4a245e597e0c3c7467317864
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880658"
---
# <a name="customer-certificates-and-secrets"></a>Certificats et clés secrètes client

[!include [banner](../includes/banner.md)]

Si vous avez déjà une référence Microsoft Azure Key Vault dans Regulatory Configuration Service (RCS), vous pouvez créer des références aux certificats et clés secrètes Key Vault. Si vous n’avez pas encore de référence Key Vault, consultez la rubrique [Environnements de services](e-invoicing-service-environments.md) pour savoir comment le créer.

## <a name="create-certificates-and-secrets"></a>Créer des certificats et clés secrètes

Pour créer et configurer des certificats et des clés secrètes, procédez comme suit.

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Configuration d’environnement**, dans le volet Actions, sélectionnez **Environnements de service**.
4. Sur la page **Environnements de service**, dans le volet Actions, sélectionnez **Paramètres Key Vault**.
5. Sur la page **Paramètres Key Vault**, sélectionnez une référence Key Vault, puis dans la section **Certificats**, sélectionnez **Ajouter**.
6. Dans le champ **Nom**, entrez le nom du certificat ou de la clé secrète Key Vault. Pour plus d’informations, voir [Créer un compte de stockage Azure dans le portail Azure](e-invoicing-create-azure-storage-account-azure-portal.md).
7. Entrez une description dans le champ **Description**.
8. Dans le champ **Type**, sélectionnez **Certificat** si vous faites référence au certificat stocké dans le coffre de clés. Sélectionnez **Clé secrète** si vous faites référence à la clé secrète stockée dans le coffre de clés.
9. Cliquez sur **Enregistrer**.

> [!NOTE]
> Dans certains scénarios, vous devez utiliser des certificats publics portant l’extension de nom de fichier .cer. Cependant, Key Vault ne prend pas en charge l’importation et le stockage de certificats de ce type en tant que certificats Key Vault. Dans ces scénarios, vous devez enregistrer le fichier .cer en tant que chaîne X.509 codée en base 64 (.CER). Ensuite, dans une clé secrète Key Vault, stockez la chaîne qui apparaît entre la ligne **DÉBUT CERTIFICAT** et la ligne **FIN CERTIFICAT** dans le fichier. Dans l’environnement de service, vous devez toujours créer une référence à l’enregistrement Key Vault et définir le champ **Type** sur **Certificat**.

## <a name="create-a-chain-of-certificates"></a>Créer une chaîne de certificats

Si vos factures spécifiques à un pays/une région nécessitent une chaîne de certificats pour appliquer des signatures numériques ou établir une connexion sécurisée (Secure Sockets Layer \[SSL\]) à des services Web externes, créez une chaîne de certificats où les certificats sont dans l’ordre suivant :

1. Certificats racine
2. Certificats intermédiaires
3. Certificats d’utilisateur final

Les autorités de certification racine (CA) sont une source fiable de certificats. Les certificats CA intermédiaires sont des ponts qui relient les certificats d’utilisateur final aux certificats CA racine.

Pour créer et configurer une chaîne de certificats, procédez comme suit.

1. Sur la page **Paramètres Key Vault**, sur le volet Actions, sélectionnez **Chaîne de certificats**.
2. Sélectionnez **Nouveau** pour créer une chaîne de certificats.
3. Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats.
4. Entrez une description dans le champ **Description**.
5. Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.
6. Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne. Conservez le certificat racine de l’autorité de certification en haut de la liste et le certificat de l’utilisateur final en bas.
7. Cliquez sur **Enregistrer**.

Vous pouvez créer autant de références Key Vault dans RCS que vous le souhaitez. N’oubliez pas que la clé secrète du jeton de signature d’accès partagé (SAS) de stockage est utilisé pour lier un environnement de service donné à la référence Key Vault. Vous pouvez référencer les certificats et clés secrètes Key Vault qui sont stockés dans un coffre de clés qui contient également la clé secrète du jeton SAS de stockage que vous utilisez lorsque vous configurez l’environnement de service.
