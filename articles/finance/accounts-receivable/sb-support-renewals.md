---
title: Support et renouvellements
description: Cet article explique comment configurer et utiliser le processus de support et de renouvellement sur les commandes client afin de créer un échéancier de facturation pour les articles de renouvellement.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: b40e0136883d909755480a3ce101627297bd9ffb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896519"
---
# <a name="support-and-renewals"></a>Support et renouvellements 

Cet article explique comment saisir des articles de support ou des articles de renouvellement lorsque vous saisissez des commandes client. Ces articles sont utilisés pour calculer le montant des frais pour le contrat de support d’origine et/ou le montant du renouvellement qui est utilisé lorsqu’un échéancier de facturation est créé dans la facturation des abonnements. Par exemple, votre entreprise vend un serveur à un client et vous offrez un abonnement de sauvegarde des données pour la première année et la possibilité de renouveler cet abonnement chaque année. Le champ *article de support* est l’abonnement pour la première année, et le champ *article de renouvellement* est le renouvellement pour chaque année successive.

Vous pouvez entrer des informations pour le contrat de support, le contrat de renouvellement ou les deux. Lorsque vous saisissez les informations du contrat de support, seul l’article de support est ajouté à la commande client. Lorsque vous saisissez les informations sur le contrat de renouvellement, l’article de renouvellement est utilisé pour créer un échéancier de facturation.

## <a name="support-and-renewal-setup"></a>Configuration du support et du renouvellement

Sur la page **Niveaux de support et de renouvellement**, vous pouvez configurer différents niveaux de support pour les articles de support et de renouvellement. Le support ou le renouvellement peut être un pourcentage du montant de l’article d’origine, ou il peut s’agir d’un montant standard.

Vous pouvez sélectionner les niveaux de support par défaut sur la page **Paramètres de facturation des contrats récurrents**.

Par exemple, une entreprise peut proposer les niveaux de support et de renouvellement suivants.

| Niveau du support | Pourcentage de support | Pourcentage de renouvellement |
|---|---|---|
| Illimité | 40 % | 30 % |
| Doré | 25 % | 18 % |
| Argent | 20 % | 14 % |
| Bronze | 15 % | 10 % |

Pour créer un niveau de support ou de renouvellement, procédez comme suit.

1. Sur la page **Niveaux de support et de renouvellement**, sélectionnez **Nouveau**.
2. Dans le champ **Niveau de support**, saisissez un nom unique.
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Méthode calcul du support**, sélectionnez la méthode de calcul du support. Si vous sélectionnez **Pour cent**, saisissez un pourcentage de support dans le champ **Pourcentage de support**.
5. Dans le champ **Méthode calcul du renouvellement**, sélectionnez la méthode de calcul du renouvellement. Si vous sélectionnez **Pour cent**, saisissez un pourcentage de renouvellement dans le champ **Pourcentage de renouvellement**.
6. Cliquez sur **Enregistrer**.

### <a name="fields"></a>Champs

La page **Niveaux de support et de renouvellement** contient les champs suivants.

| Champ | Description |
|---|---|
| Niveau du support | Un identifiant unique pour le niveau de support ou de renouvellement (par exemple, **Or** ou **Argent**). |
| Description | Une description du niveau de support ou de renouvellement. |
| Mode de calcul du support | Sélectionnez la méthode de calcul du support pour le niveau : **Pour cent** ou **Montant standard**. |
| Pourcentage de support | Si vous avez sélectionné **Pour cent** comme méthode de calcul du support, spécifiez le pourcentage utilisé pour calculer le prix de l’article de support. Si vous avez sélectionné **Montant standard** comme méthode de calcul, le montant est précisé lors de la création de la transaction. |
| Mode de calcul du renouvellement | Sélectionnez la méthode de calcul du renouvellement pour le niveau : **Pour cent** ou **Montant standard**. |
| Pourcentage de renouvellement | Si vous avez sélectionné **Pour cent** comme méthode de calcul du renouvellement, spécifiez le pourcentage utilisé pour calculer le prix de l’article de renouvellement. Si vous avez sélectionné **Montant standard** comme méthode de calcul, le montant est précisé lors de la création de la transaction. |

## <a name="support-and-renewal-process"></a>Processus de support et de renouvellement

La fonctionnalité de support et de renouvellement peut appliquer différents niveaux de support aux articles et mettre à jour les informations de renouvellement dans la facturation des abonnements.

Avant d’utiliser la fonctionnalité de support et de renouvellement, les tâches suivantes doivent être effectuées.

1. Sur la page **Niveaux de support et de renouvellement**, créez au moins un niveau de support ou de renouvellement.
2. Sur la page **Configuration de l’article**, associez un article avec des articles de support et de renouvellement. Cette tâche est requise uniquement si vous souhaitez configurer des valeurs par défaut pour les articles de support et/ou de renouvellement.
3. Sur la page **Paramètres de facturation des contrats récurrents**, spécifiez les paramètres de support et de renouvellement par défaut pour les nouveaux échéanciers de facturation.

Pour appliquer différents niveaux de support aux articles et mettre à jour les informations de renouvellement, procédez comme suit.

1. Dans la page **Toutes les commandes client**, créez une commande client.
2. Dans l’organisateur **Lignes de commande client**, ajoutez un article.
3. Sur l’onglet **Facture**, sélectionnez **Support et renouvellement \> Ajouter le support et le renouvellement**.
4. Sur la page **Processus de support et renouvellement**, la section d’en-tête est mise à jour avec les paramètres de la page **Paramètres de facturation des contrats récurrents**. Ces valeurs s’appliquent à tous les articles de support et de renouvellement. (Par exemple, si la fréquence de facturation est définie sur **Annuellement**, toutes les lignes de vente créées avec un article de renouvellement ont une fréquence annuelle.) Pour associer la commande client à un échéancier de facturation existant, sélectionnez une valeur dans le champ **Numéro de l’échéancier de facturation**.
5. Pour modifier la date de début du support ou du renouvellement, définissez l’option **Remplacer la date de début** sur **Oui**.
6. Pour ajouter ou modifier l’élément de support, cochez la case **Support**, puis entrez un article de support dans le champ **Article de support**. L’article est ajouté à la commande client.
7. Pour ajouter ou modifier l’article de renouvellement, cochez la case **Renouvellement**, puis entrez un article de renouvellement dans le champ **Article de renouvellement**. Lorsque la commande client est facturée, un échéancier de facturation incluant l’article est créé.
8. Cliquez sur **OK**.
9. Sous l’onglet **Générer**, sélectionnez **Facture**. Lorsque la commande client est validée, l’échéancier de facturation est créé. Une notification incluant les informations sur l’échéancier de facturation s’affiche dans les détails du message.
10. Sur la page de liste **Tous/Calendriers de facturation actifs**, sélectionnez le numéro de l’échéancier de facturation pour en examiner les détails sur la page **Échéanciers de facturation**.
11. Dans l’organisateur **Lignes d’échéancier de facturation**, sélectionnez **Support et renouvellement** pour examiner les détails des lignes qui ont été créées.

> [!NOTE]
> Si la date de début de renouvellement d’une ligne d’échéancier de facturation doit être modifiée, vous pouvez modifier la valeur **Date de début** de la ligne sur la page **Échéanciers de facturation**. Lorsque vous ouvrez la page **Afficher les détails de facturation** pour la ligne, le champ **Date de début de facturation** est mis à jour avec la nouvelle date. La valeur **Date de fin de facturation** est recalculée en fonction de la fréquence de facturation. La date de début du renouvellement ne peut être mise à jour que si la première facture de l’échéancier de facturation du renouvellement n’a pas été créée et validée. Une fois la première facture créée et validée, la date de début ne peut plus être modifiée.

Le processus de support et de renouvellement est disponible pour la commande client uniquement. Lorsque vous ajoutez des articles de support et de renouvellement à une commande client, vous pouvez créer un nouvel échéancier de facturation ou ajouter l’article de renouvellement à un échéancier de facturation existant.

## <a name="support-and-renewal-audit"></a>Audit du support et du renouvellement

Sur la page **Audit du support et du renouvellement**, vous pouvez consulter les détails des lignes d’échéancier de facturation créées à partir de l’article de renouvellement sur une commande client. Cette option est disponible uniquement lorsque l’article de ligne de l’échéancier de facturation est un article de renouvellement.

Pour modifier les informations de support et de renouvellement d’une ligne d’échéancier de facturation, procédez comme suit.

1. Sur la page **Tous les calendriers de facturation**, sélectionnez le numéro de l’échéancier de facturation.
2. Dans la section **Lignes d’échéancier de facturation**, sélectionnez une ligne, puis sélectionnez **Support et renouvellement**.
3. Passez en revue toutes les informations relatives à l’article de support ou de renouvellement.
4. Apportez les modifications requises au niveau de support, au pourcentage ou au montant de renouvellement, puis saisissez une valeur dans le champ **Motif de la modification**.
5. Sélectionnez **Traiter**.

### <a name="fields"></a>Champs

La page **Audit du support et du renouvellement** contient les champs suivants.

| Champ | Description |
|-------|-------------|
| Numéro d’article | Numéro d’article de la ligne de l’échéancier de facturation. |
| Nom produit | Le nom du produit. |
| Niveau de plan de support | Affichez ou modifiez le niveau de support pour l’article de renouvellement. |
| Pourcentage de renouvellement | Entrez le pourcentage de renouvellement utilisé lorsque le prix unitaire est calculé pour un article de renouvellement dans un échéancier de facturation. |
| Montant du renouvellement | Entrez le montant de renouvellement utilisé lorsque le prix unitaire est calculé pour un article de renouvellement dans un échéancier de facturation. |
| Motif de la modification | Entrez la raison pour laquelle vous modifiez les informations de support et de renouvellement. Vous devez entrer une raison lorsque vous modifiez la valeur **Pourcentage de renouvellement**, **Montant du renouvellement**, ou **Niveau du plan de support**. |
| Article vendu d’origine | Le numéro d’article de vente d’origine provenant de la commande client. |
| Montant net d’origine | Le montant original net de l’article. |
| Niveau de support d’origine | Le niveau de support original pour l’article. |
| Pourcentage de renouvellement d’origine | Le pourcentage de renouvellement original pour l’article. |
| Montant de renouvellement d’origine | Le montant de renouvellement original pour l’article. |
| **Grille** | |
| Niveau de support d’origine | Le niveau de support précédent. |
| Pourcentage de renouvellement d’origine | Le pourcentage de renouvellement précédent. |
| Montant de renouvellement d’origine | Le montant de renouvellement précédent. |
| Modifié(e) par | Le nom d’utilisateur de la personne qui a procédé à la modification. |
| Date et heure de modification | La date de survenue de la modification. |
| Motif | Le motif de la modification. |
