---
title: Configurer un canal de messagerie
description: Cet article explique comment configurer un canal de messagerie pour recevoir des factures électroniques.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 19339cbcc59e93289609690363b0dd9195a66f6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279868"
---
# <a name="configure-an-email-channel"></a>Configurer un canal de messagerie

[!include [banner](../includes/banner.md)]

Si la fonctionnalité de facturation électronique que vous avez créée importe des factures fournisseur électroniques à partir de fichiers joints reçus par e-mail, vous devez configurer un canal de compte par e-mail.

1. Dans Regulatory Configuration Service (RCS), sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la version dont le statut est défini sur **Brouillon**.
2. Dans l’onglet **Configurations**, sélectionnez **Ajouter**.
3. Dans la boîte de dialogue déroulante **Créer une configuration de fonctionnalité**, dans le groupe de champs **Nouveau**, sélectionnez l’option **Configuration personnalisée**.
4. Dans le groupe de champ **Type de configuration**, sélectionnez l’option **Canal de données**.
5. Dans le champ **Sélectionner le canal de données**, entrez **E-mail entrant**.
6. Cliquez sur **Créer**.
7. Sélectionnez la ligne créée, puis sélectionnez **Modifier**.
8. Sur l’onglet **Canal de données**, dans la section **Paramètres**, définissez les champs obligatoires suivants.

    | Champ                | Description |
    |----------------------|-------------|
    | Canal de données         | Entrez un nom unique pour identifier le canal de données. Le nom peut avoir un maximum de 10 caractères. Il sera référencé dans les règles d’applicabilité et dans les applications connectées lors du processus de communication. |
    | Adresse du serveur       | Saisissez l’adresse du serveur du fournisseur du compte de messagerie électronique. Par exemple, l’adresse du serveur pour le fournisseur `https://outlook.live.com` est imap-mail.outlook.com. |
    | Port du serveur          | Saisissez le numéro du port utilisé par le fournisseur de compte de messagerie. Par exemple, le port du serveur pour le fournisseur `https://outlook.live.com` est 993. |
    | Secret du nom d’utilisateur     | Saisissez le nom de la clé secrète Microsoft Azure Key Vault qui contient l’ID du compte d’utilisateur de messagerie. Cette clé secrète doit être créée dans Key Vault et configurée dans votre environnement de service. |
    | Secret du mot de passe de l’utilisateur | Saisissez le nom de la clé secrète Key Vault qui contient le mot de passe du compte d’utilisateur de messagerie. |
    | Délai d’attente              | Délai maximal, en millisecondes (ms), pendant lequel le système doit attendre une réponse. La valeur par défaut est de 10 000 ms (10 secondes). |
    | Dossier principal          | Spécifiez la source d’importation des e-mails ou le dossier à partir duquel le service doit traiter les e-mails. |
    | Dossier d’archivage       | Spécifiez le dossier dans lequel les e-mails traités doivent être stockés. Si vous ne spécifiez pas ce dossier, le système le créera automatiquement. |
    | Dossier d’erreurs         | Spécifiez le dossier dans lequel le système doit déplacer les e-mails si le traitement échoue. Si vous ne spécifiez pas ce dossier, le système le créera automatiquement. |
    | Taille maximale du message     | Entrez la taille maximale, en octets, d’un seul message qui est traité. La valeur par défaut est 20 000 000 octets. |
    | Nombre maximal de messages   | Saisissez le nombre maximal de messages à traiter pour une action unique. Si vous ne souhaitez pas limiter le nombre de messages, définissez la valeur sur **0** (zéro). |
    | Filtre De          | Entrez une chaîne pour filtrer par adresse d’expéditeur. Seuls les e-mails dont l’adresse de l’expéditeur correspond au filtre seront traités. Ce champ est facultatif. Pour spécifier plusieurs adresses d’expéditeur, utilisez des points-virgules (;) comme séparateurs. |
    | Filtre Objet       | Entrez une chaîne pour filtrer par objet. Seuls les e-mails dont l’objet correspond au filtre seront traités. Ce champ est facultatif. Un simple masque tel que **\*smth\*.ext** est pris en charge, où chaque astérisque (\*) représente zéro ou plusieurs occurrences de n’importe quel caractère. |
    | Filtre de date          | Spécifiez une date pour définir l’âge maximum, en jours, des messages qui sont traités. Ce champ est facultatif. La valeur par défaut est de 30 jours. |
    | Mode de traitement      | <p>Sélectionnez l’une des options suivantes pour spécifier si toutes les pièces jointes d’un e-mail peuvent être traitées ensemble ou si chaque pièce jointe doit être traitée séparément :</p><ul><li><b>Par pièce jointe</b> – Un nouveau document électronique sera créé pour chaque pièce jointe dans le courrier électronique. Par exemple, si un e-mail comprend plusieurs fichiers contenant des données de facturation électronique, chaque fichier sera considéré comme une nouvelle facture électronique dans le système.</li><li><b>Par e-mail</b> – Une pièce jointe sera considérée comme une pièce jointe de base et une facture électronique sera créée dans le système. D’autres pièces jointes peuvent être utilisées comme fichiers de support.</li></ul> |

9. Dans la section **Filtre des pièces jointes**, ajoutez les informations de filtrage de fichier. Seules les pièces jointes qui satisfont au filtre défini seront traitées. Par exemple, **\*.xml** filtrera les pièces jointes qui ont l’extension de nom de fichier .xml. Le nom de la pièce jointe est utilisé dans Dynamics 365 Finance ou Dynamics 365 Supply Chain Management lors de la configuration.

    - Si vous définissez le champ **Mode de traitement** sur **Par e-mail** à l’étape précédente, vous pouvez ajouter plusieurs filtres ici. Le nom identifiera le document spécifique.
    - Si vous définissez le champ **Mode de traitement** sur **Par pièce jointe**, vous ne pouvez ajouter qu’un seul filtre.

10. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. La valeur du champ **Canal** doit être égal à la valeur que vous avez saisie dans le champ **Canal de données** à l’étape 8.
11. Cliquez sur **Enregistrer**, puis fermez la page.
