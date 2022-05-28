---
title: Soumissions sous pli scellé les appels d’offre
description: Cette rubrique explique comment configurer des appels d’offre scellés pour garder secrètes les réponses d’offres des fournisseurs jusqu’à ce qu’elles soient descellées par le personnel chargé des achats.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: dfc19646d6724627c8a25bcfc8a6b2a70a73c261
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675147"
---
# <a name="sealed-bidding-for-rfqs"></a>Soumissions sous pli scellé les appels d’offre

[!include [banner](../includes/banner.md)]

Les appels d’offre scellés gardent secrètes les réponses d’offres des fournisseurs jusqu’à ce qu’elles soient descellées par le personnel chargé des achats. Toutes les offres liées à un appel d’offre sont d’abord disponibles pour être descellées à l’expiration de l’offre. Avant qu’une offre ne soit descellée, seuls les utilisateurs qui ont des rôles d’utilisateur dédiés et qui représentent le fournisseur peuvent y accéder.

> [!IMPORTANT]
> La modification ou l’extension de formulaires, ou la création de nouveaux formulaires ou d’une logique métier peuvent mettre en échec la protection fournie par Microsoft pour les enchères scellées. Vous assumez le risque d’utiliser toute modification, extension, nouveau formulaire ou logique commerciale, ou l’impossibilité d’utiliser la fonction d’enchère scellée en raison de telles modifications, extensions, nouveaux formulaires ou logique commerciale.  Microsoft n’est pas responsable des dommages résultant de modifications ou d’extensions de formulaires, ou de tout nouveau formulaire ou logique métier que vous créez ou que tout tiers crée pour vous. Microsoft ne fournit pas de support technique ou autre pour les modifications, extensions, nouveaux formulaires ou logique métier effectués par vous ou un tiers en votre nom. Vous êtes seul responsable du respect de toutes les lois ou réglementations applicables concernant les offres scellées.

## <a name="how-bids-are-kept-secure"></a>Comment les offres sont sécurisées

Les appels d’offre scellés utilisent un chiffrement asymétrique pour chiffrer la clé de chiffrement de l’offre (KEK) et un chiffrement symétrique pour chiffrer l’offre réelle. Le système s’intègre avec Microsoft Azure Key Vault pour générer et gérer les clés de chiffrement utilisées pour chiffrer les offres scellées. Chaque offre a sa propre clé de chiffrement. Ce chiffrement est conservé en lieu sûr dans un coffre de clés appartenant à l’organisation qui exécute Dynamics 365 Supply Chain Management. Le système accède au coffre de clés à la demande, chaque fois que le chiffrement et le déchiffrement sont requis.

## <a name="setup-and-configuration"></a>Paramétrage et configuration

Cette section décrit les conditions préalables qui doivent être en place avant que vous puissiez envoyer des appels d’offres nécessitant une offre scellée.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Étape 1 : Configurer l’accès des utilisateurs aux appels d’offre scellés

Lorsque vous utilisez les appels d’offre scellés, seuls les utilisateurs définis comme personne de contact pour un fournisseur peuvent afficher, modifier et soumettre des offres pour ce fournisseur jusqu’à l’expiration de la période d’appel d’offre. Ces utilisateurs doivent avoir le rôle **Fournisseur (externe)** et ils doivent être définis en tant que personne de contact pour le compte fournisseur. La personne-ressource doit également avoir la permission de collaborer avec les fournisseurs, comme décrit dans [Configurer et tenir à jour la collaboration avec les fournisseurs](set-up-maintain-vendor-collaboration.md).

Étant donné que les utilisateurs disposant des autorisations appropriées et configurés en tant que contacts fournisseurs peuvent accéder aux appels d’offre scellés d’un fournisseur, il est important de savoir qui sont ces utilisateurs. L’administrateur système qui configure les utilisateurs et les rôles de sécurité est chargé de limiter l’accès aux appels d’offre scellés aux utilisateurs qui sont réellement autorisés à les consulter.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Étape 2 : Activer la fonctionnalité d’appels d’offre scellés

Avant de démarrer la configuration ou l’utilisation de cette fonctionnalité, vous devez vous assurer qu’elle est disponible dans votre système. Les administrateurs peuvent utiliser l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Approvisionnements*
- **Nom de la fonctionnalité :** *Appel d’offre scellé pour l’appel d’offre*

### <a name="step-3-set-up-azure-key-vault"></a>Étape 3 : Configuration d’Azure Key Vault

Supply Chain Management utilise des clés de chiffrement pour protéger tous les appels d’offre scellés et les garder secrètes jusqu’au moment opportun. Il tire parti des capacités de coffre de clés pour générer et gérer les clés requises. Par conséquent, vous devez configurer une connexion de Supply Chain Management à un coffre de clés pour activer le système.

> [!IMPORTANT]
> Les coffres de clés que vous utilisez pour les enchères scellées doivent répondre aux exigences suivantes :
>
> - Si vous utilisez un bac à sable pour le développement et les tests, vous devez disposer d'un coffre de clés dédié pour le bac à sable et d'un autre pour la production.
> - Chaque coffre de clés doit être créé dans un abonnement Azure appartenant à votre organisation (pas l’abonnement sur lequel vous exécutez Supply Chain Management).
> - Chaque coffre à clés doit être utilisé exclusivement pour les enchères scellées. Vous ne devez pas utiliser vos coffres de clés d'enchères scellées à d'autres fins.

Chaque offre récupère sa propre clé secrète. Cette clé est utilisée chaque fois qu’un utilisateur affiche, met à jour ou descelle l’appel d’offre.

Le coffre de clés génère la clé qui est utilisée pour récupérer le secret lorsque le fournisseur sélectionne **Offre d’appel** dans l’interface de collaboration fournisseur. La clé expire alors après un délai fixe que le responsable des achats définit sur la page **Paramètres d’approvisionnements** dans Supply Chain Management. Une fois la clé expirée, personne ne pourra voir, modifier ou desceller l’offre. Par conséquent, il est important de configurer l’expiration de la clé afin qu’il y ait suffisamment de temps pour que le processus d’appel d’offre soit terminé.

Au cours des trois étapes suivantes, vous allez configurer la connexion au coffre de clés. Tout d’abord, vous allez configurer un coffre de clés à utiliser avec des appels d’offre scellés. Ensuite, vous configurerez Supply Chain Management pour communiquer avec le coffre de clés. Enfin, vous définirez le délai d’expiration de la clé.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Étape 4 : Configurer un coffre de clés à utiliser avec des appels d’offre scellés

Pour paramétrer votre coffre de clés, procédez comme suit. L’ordre des étapes est important.

1. Si vous n’avez pas encore configuré un abonnement Azure distinct de l’abonnement sur lequel vous exécutez Supply Chain Management, configurez-le.
1. Configurez un coffre de clés dans votre stockage Azure séparé. Pour plus d’informations, voir [Gestion du stockage Azure Key Vault](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Configurez votre application Supply Chain Management pour qu’elle fonctionne en tant que client pour votre coffre de clés. Pour plus d’informations, voir [Configuration du client Azure Key Vault](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Étape 5 : Configurer les paramètres du coffre de clés dans Supply Chain Management

Pour configurer Supply Chain Management afin qu’il communique avec le coffre de clés pendant les appels d’offre scellés, procédez comme suit.

1. Connectez-vous à Supply Chain Management et accédez à **Administration système \> Configurer \> Paramètres du coffre de clés**.
1. Sélectionnez **Nouveau** pour créer un enregistrement et définir les champs suivants pour celui-ci :

    - **Nom** – Entrez un nom.
    - **Description** – Entrez une description.
    - **URL du coffre de clés** – Saisissez l’URL par défaut de votre coffre de clés.
    - **Client du coffre de clés** – Entrez l’ID client interactif de l’application Active Directory associée à un coffre de clés à des fins d’authentification.
    - **Clé secrète du coffre à clés** – Saisissez la référence secrète du certificat.
    - **Activé pour les appels d’offre scellés** – Définissez cette option sur *Oui*.

![Page des paramètres du coffre de clés](media/sealed-bidding-key-vault-param.png "Page des paramètres du coffre de clés")

> [!NOTE]
> Vous ne pouvez activer qu’une seule configuration de coffre de clés pour les appels d’offre scellés à la fois. Avant de désactiver une configuration de coffre de clés existante, vous devez vous assurer que tous les appels d’offre scellés qui l’utilisent sont descellées. Inspectez chaque cas d’appel d’offres du type *Scellé* et assurez-vous que toutes les réponses sont descellées.

### <a name="step-6-set-the-key-expiration-time"></a>Étape 6 : Définir le délai d’expiration de la clé

Pour définir le délai d’expiration appliqué à la clé générée pour chaque nouvelle offre, procédez comme suit.

1. Accédez à **Paramètres d’approvisionnements \> Paramétrage \> Paramètres d’approvisionnements**.
1. Sur l’onglet **Appel d’offre**, dans le champ **Contrepartie des jours**, entrez le nombre de jours que la période de demande de devis doit durer. Lorsqu’un appel d’offres est créé, le nombre de jours que vous saisissez ici est ajouté à la date système pour définir la date d’expiration par défaut de l’appel d’offres.
1. Dans le champ **Contrepartie de jour d’expiration de la clé de chiffrement**, saisissez le nombre de jours pendant lesquels chaque clé de chiffrement doit être valide après son émission. Une fois la clé de chiffrement expirée, personne ne pourra voir, modifier ou desceller l’appel d’offre qui l’utilise.

> [!TIP]
> La valeur du champ **Contrepartie du jour d’expiration de la clé de chiffrement** ne doit pas être inférieur à la valeur du champ **Contrepartie de jour**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Étape 7 : Définir le type d’appel d’offre par défaut

Chaque cas d’appel d’offre a un type d’offre. Le type d’offre définit si ce dossier d’appel d’offres propose une offre ouverte ou scellée.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Cas d’appel d’offres qui n’ont pas de type de sollicitation

Pour définir le type d’offre par défaut attribué aux nouveaux dossiers d’appel d’offres auxquels aucun type de sollicitation n’est attribué lors de leur création, procédez comme suit.

1. Accédez à **Paramètres d’approvisionnements \> Paramétrage \> Paramètres d’approvisionnements**.
1. Sur l’onglet **Appel d’offre**, définissez le champ **Type d’offre** sur *Scellé*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Cas d’appel d’offres avec un type de sollicitation

Pour définir le type d’offre par défaut attribué aux nouveaux dossiers d’appel d’offres auxquels un type de sollicitation est attribué lors de leur création, procédez comme suit.

1. Allez dans **Approvisionnements \> Paramétrage \> Appel d’offre \> Type de sollicitation**.
1. Créez un type de sollicitation ou sélectionnez un type de sollicitation existant pour lequel vous souhaitez utiliser un type d’offre de *Scellé*.
1. Définissez le champ **Type d’offre** sur *Scellé*.
1. Répétez ces étapes pour chaque type de sollicitation supplémentaire pour lequel vous souhaitez mettre en œuvre une offre scellée.

> [!TIP]
> Il n’est pas nécessaire d’attribuer un type de sollicitation lors de la création d’un appel d’offre. Si un type de sollicitation est attribué, le type d’offre par défaut d’un appel d’offre peut le récupérer. Sinon, le type de sollicitation par défaut défini dans Paramètres d’approvisionnements peut être utilisé.

## <a name="the-sealed-bidding-process"></a>Le processus d’appel d’offre scellé

L’appel d’offre scellé suit presque le même processus qui est décrit dans [Présentation des devis (appel d’offre)](request-quotations.md). La principale différence est que les données de l’offre et ses pièces jointes sont conservées chiffrées jusqu’à ce que l’offre soit descellée.

> [!IMPORTANT]
> Les [questionnaires](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) ne sont pas cryptés et ne doivent pas être utilisés pour collecter des informations sensibles

Voici une description du processus :

1. Vous créez et envoyez un appel d’offre à un ou plusieurs fournisseurs.
1. Les fournisseurs répondent en soumettant leur offre scellée.
1. Vous descellez les offres après l’heure d’expiration de la saisie des offres.
1. Les offres deviennent visibles et vous pouvez les évaluer et les comparer.
1. Une fois qu’une offre est acceptée, vous générez une commande fournisseur, générez un contrat d’achat ou mettez à jour une demande d’achat.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Créer un dossier d’appel d’offre qui utilise des appels d’offre scellés

Le processus de création d’un dossier d’appel d’offre pour un appel d’offre scellé est presque le même que le processus pour un appel d’offre non scellée. Pour plus d’informations sur la création des deux types de dossiers d’appel d’offres, voir [Créer un appel d’offre](tasks/create-request-quotation.md). Cette section met en évidence quelques considérations importantes lorsque vous créez un appel d’offres pour une offre scellée.

Les dossiers d’appel d’offres pour les appels d’offres scellés doivent avoir une valeur **Type d’appel d’offre** de *Scellé*. Il existe trois manières d’affecter cette valeur à un dossier d’appel d’offre :

- Définissez la valeur directement sur le dossier d’appel d’offre après l’avoir créé.
- Définissez l’appel d’offre scellé comme type d’appel d’offre par défaut pour tous les appels d’offres dans les paramètres d’approvisionnements. (Voir la section [Définir le type d’appel d’offre par défaut](#set-default-bid-type) plus haut dans cette rubrique.)
- Lorsque vous créez un dossier d’appel d’offres, sélectionnez un type de sollicitation configuré pour l’appel d’offres scellé. (Voir la section [Définir le type d’appel d’offre par défaut](#set-default-bid-type).)

Pour les appels d’offres scellés, la valeur **Date et heure d’expiration** du dossier d’appel d’offre établit quand les offres soumises peuvent être descellées. La valeur **Date et heure d’expiration** sur chaque ligne correspondra à la valeur sur l’en-tête.

Vous ne pouvez pas modifier le type d’appel d’offre après l’envoi d’un dossier d’appel d’offre.

### <a name="vendors-respond-to-an-rfq"></a>Les fournisseurs répondent à un appel d’offre

Les fournisseurs qui répondent à un appel d’offre scellé utilisent la même procédure qu’ils utilisent pour répondre aux appels d’offre ouverts, comme indiqué dans [Utiliser les appels d’offre dans l’espace de travail d’appel d’offre du fournisseur](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Pour des instructions détaillées sur la façon de travailler avec les appels d’offre ouverts et les appels d’offre scellés, voir [Saisie et comparaison des appels d’offre et attribution des contrats](tasks/enter-compare-rfq-bids-award-contracts.md). La seule différence entre le traitement des appels d’offre scellés et le traitement des appels d’offre ouverts est que, jusqu’à l’expiration de la période d’appel d’offres, les professionnels de l’approvisionnement ne peuvent pas ouvrir l’appel d’offre scellé d’un fournisseur. Seule une personne de contact pour le fournisseur peut ouvrir l’appel d’offre scellé de ce fournisseur.

> [!IMPORTANT]
> Pour les appels d’offre scellés, les fournisseurs peuvent charger les pièces jointes uniquement au format PDF. Aucun autre format ne sera accepté.

Après qu’un utilisateur de fournisseur enregistré a sélectionné **Appel d’offre** sur un appel d’offre scellé, il peut saisir leurs données d’offre, et ces données seront conservées en toute sécurité. Les fournisseurs peuvent enregistrer leur travail pendant qu’ils préparent une offre, y revenir aussi souvent que nécessaire, puis la soumettre lorsqu’elle est prête. Les vendeurs peuvent également voir leur offre après l’avoir soumise. Si les fournisseurs doivent modifier leur offre après l’avoir soumise, ils peuvent la rappeler, la mettre à jour et la resoumettre à tout moment jusqu’à l’expiration de la période d’appel d’offre.

Les conditions suivantes s’appliquent lors des appels d’offre scellés :

- Lors d’un appel d’offre scellé, le système crée un journal *Appel d’offre*.
- Lorsqu’un fournisseur soumet une offre, des journaux d’appels d’offre sans lignes sont créés avec un prix scellé.
- Une fois le dossier descellé, des journaux d’appels d’offre sont créés avec un prix et un montant. Vous pouvez accéder à ce journal en sélectionnant **Journaux d’appels d’offre** sur la page **Toutes les demandes de devis**.
- Le système stocke un journal de chaque action que les utilisateurs effectuent sur un appel d’offre scellé. Ces actions incluent l’affichage, la modification et l’enregistrement de l’offre. Ce journal est visible à la fois pour le fournisseur et pour les professionnels de l’approvisionnement qui ont accès à l’offre.
- Au fur et à mesure de l’avancement de l’appel d’offre, les professionnels de l’approvisionnement peuvent consulter son statut. Le statut passe ensuite à *L’acheteur effectue une mise à jour* ou à *Soumis par le fournisseur*.
- Le statut des lignes dans un appel d’offre scellé reste *Expédié* jusqu’à ce que l’offre soit descellée.
- Si le vendeur choisit de décliner une offre, l’offre aura un statut **Progrès de la réponse** de *Refusé par le fournisseur*. Ce statut sera visible par le personnel chargé des achats.
- Les réponses aux questionnaires **ne sont pas** stockées sous forme chiffrées dans la base de données. Par conséquent, ils ne sont pas scellées. Cependant, ils ne seront pas visibles dans l’interface utilisateur de l’appel d’offre tant que le dossier n’est pas descellé.

### <a name="all-sealed-bid-activities-are-logged"></a>Toutes les activités d’appels d’offre scellés sont enregistrées

Un journal détaillé enregistre toutes les activités et actions des utilisateurs pour une offre. Le journal d’activité permet aux organisations de déterminer qui a mis à jour une offre au cours de sa durée de vie et quelles étaient les mises à jour. Il permet également aux organisations de confirmer que seules les personnes autorisées ont accédé à un appel d’offre scellé. Le journal d’activité est disponible sur chaque page **Activité** de l’appel d’offre.

### <a name="review-rfq-activity"></a>Examiner l’activité de l’appel d’offre

Chaque interaction avec l’offre est enregistrée et peut être consultée sur la page **Activité**. L’illustration suivante présente un exemple.

![Exemple de la page Activité](media/sealed-bidding-rfq-activity.png "Exemple de la page Activité")

Les fournisseurs peuvent accéder à la page **Activité** en sélectionnant **Activité** sur la page **Appel d’offre scellé**. Le personnel chargé des achats peut y accéder en sélectionnant **Activité** sur la page **Appel d’offre**. Le journal d’activité offre une visibilité complète aux fournisseurs et au personnel chargé des achats qui ont accédé à l’offre. Par conséquent, il peut révéler tout accès non autorisé.

### <a name="unseal-sealed-bids"></a>Desceller les offres scellées

Quand la valeur **Date et heure d’expiration** configurée pour un dossier d’appel d’offre avec appel d’offre scellé est dépassée, le bouton **Desceller** devient disponible. Sélectionnez **Desceller** pour desceller tous les appels d’offre pour le dossier d’appel d’offre sélectionné. Toutes les données d’appel d’offre et les pièces jointes deviennent alors visibles afin que les réponses au dossier puissent être gérées. De plus, des journaux sont créés qui contiennent les données d’offre soumises.

L’événement de descellement est enregistrée et peut être consultée sur la page **Activité**.

### <a name="process-accepted-bids"></a>Traiter les offres acceptées

Le processus de comparaison et d’approbation des appels d’offre préalablement scellées est le même que celui des appels d’offre ouvertes. Pour plus d’informations sur la notation, la comparaison, le rejet et l’acceptation des appels d’offre non scellés, consultez [Saisie et comparaison des appels d’offre et attribution des contrats](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>Le journal d’activité d’appel d’offre ne peut jamais être supprimé

Personne, pas même les administrateurs et le support Microsoft, ne peut modifier ou supprimer le journal d’activité des appels d’offre. Cette restriction contribue à garantir l’équité du processus d’appel d’offre scellé. Cela permet également de s’assurer qu’une piste d’audit précise est maintenue.
