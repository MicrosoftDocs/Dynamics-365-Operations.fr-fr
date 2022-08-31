---
title: Fonctionnalité de caisse enregistreuse pour la Norvège
description: Cet article donne un aperçu de la fonctionnalité de caisse enregistreuse disponible pour la Norvège dans Microsoft Dynamics 365 Commerce, et fournit des instructions pour la configuration de la fonctionnalité.
author: EvgenyPopovMBS
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 30bd5ad8c1513c3d56cc4aa0a77b70fe38d31e0a
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346016"
---
# <a name="cash-register-functionality-for-norway"></a>Fonctionnalité de caisse enregistreuse pour la Norvège

[!include[banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de la fonctionnalité de caisse enregistreuse disponible pour la Norvège dans Dynamics 365 Commerce. Elle fournit également des instructions pour paramétrer la fonctionnalité. Cette fonctionnalité contient les parties suivantes :

- Les fonctionnalités de point de vente (PDV) courantes disponibles pour les clients de tous les pays ou régions. Les exemples incluent une option qui vous permet d’empêcher l’impression d’une copie d’un reçu plusieurs fois.
- Des fonctionnalités spécifiques pour la Norvège, telles que les signatures numériques pour les transactions de vente.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Aperçu de la fonctionnalité de caisse enregistreuse pour la Norvège

### <a name="common-pos-features"></a>Fonctionnalités de PDV courantes

Pour connaître les fonctionnalités de PDV disponibles pour les clients de tous les pays ou régions, voir la documentation [Aider les ressources pour Dynamics 365 Retail](../index.md).

Les fonctionnalités de localisation PDV suivantes implémentées précédemment et rendues disponibles pour les clients de tous les pays ou régions peuvent désormais être utilisées spécifiquement pour la Norvège :

- **Imprimez les champs de texte sur un reçu dans une grande taille de police.** Vous pouvez utiliser le paramètre **Taille de police** dans le concepteur de format de reçu pour spécifier que la grande taille de police doit être utilisée pour un champ dans le format de reçu. (La grande taille de police est environ le double de la taille de police habituelle.) Par exemple, vous pouvez utiliser ce paramètre pour imprimer l’indicateur "Copie" sur une copie d’un reçu en gros caractères.
- **Enregistrez l’impression des copies de reçus dans le journal des événements d’audit du PDV.** Vous pouvez utiliser le paramètre **Audit** dans le profil de fonctionnalité PDV pour permettre l’impression de copies de reçus et l’enregistrement d’autres événements d’audit PDV. Les événements d’audit sont enregistrés dans la base de données des canaux et au siège. Vous pouvez afficher les événements d’audit sur la page **Auditer les événements**.
- **Empêcher une copie d’un reçu d’être imprimée plus d’une fois.** Quand le paramètre **Audit** dans le profil de fonctionnalité PDV est activé, l’autorisation PDV **Autoriser l’impression de copies de reçus** contrôle si les copies des reçus peuvent être imprimées. Il existe aussi une option qui vous permet d’empêcher l’impression d’une copie d’un reçu plusieurs fois.

De plus, la fonctionnalité de point de vente suivante a été implémentée pour la Norvège, mais mise à la disposition des clients dans tous les pays ou régions :

- **Enregistrer des événements supplémentaires dans le journal d’événements d’audit du PDV.** Si le paramètre **Audit** dans le profil de fonctionnalité du PDV est activé, les événements suivants sont enregistrés dans le journal d’événements d’audit du PDV :

    - Vérifications de prix
    - Remplacements de taxe
    - Corrections des quantités de ligne
    - Effacement des transactions de la base de données des canaux

### <a name="norway-specific-pos-features"></a>Fonctionnalités du PDV spécifiques à la Norvège

Les fonctionnalités du PDV spécifiques à la Norvège sont activées lorsque le paramètre **Code ISO** dans le profil de fonctionnalité du PDV est défini sur **No**.

#### <a name="digital-signing-of-sales-transactions"></a>Signature numérique des transactions de vente

Chaque transaction de vente est signée numériquement. La signature est créée puis enregistrée dans la feuille transactions PDV lorsque la transaction est finalisée. La signature est également disponible dans le journal qui est exporté à des fins d’audit.

Seules les transactions pour les ventes en espèces sont signées. Voici quelques exemples de transactions exclues du processus de signature :

- Acomptes (dépôt sur comptes client)
- Acomptes pour les commandes client (dépôt sur commandes client)
- Émission d’une carte cadeau
- Transactions hors ventes (entrée de fond de caisse, vidage de caisse, etc.)

Les données signées sont une chaîne de texte composée des champs de données suivants. Les champs de données sont séparés par des points-virgules.

1. Signature précédente pour le même PDV (Un zéro \[**0**\] est utilisé pour la première transaction.)
2. Date de la transaction
3. Heure de transaction
4. Numéro de transaction signé séquentiel
5. Montant de la transaction TTC
6. Montant de la transaction HT

Le processus de signature numérique utilise une clé RSA 1024 bits dotée d’une fonction de hachage SHA-1 (RSA-SHA1-1024). Un certificat installé sur Commerce Scale Unit est utilisé pour la signature. L’identificateur unique du certificat (empreinte) est enregistré avec la signature.

La signature est stockée dans la base de données du magasin et dans la base de données du siège social (HQ) avec les données de transaction. Vous pouvez afficher la signature de transaction, avec les données de transaction utilisées pour la générer, sous le raccourci **Transactions fiscales** de la page **Transactions de magasin**.

#### <a name="receipts"></a>Réceptions

Les tickets de caisse pour la Norvège peuvent inclure des informations supplémentaires implémentées à l’aide de champs personnalisés :

- **Titre du reçu** – Vous pouvez ajouter un champ à une mise en page du format de ticket de caisse pour identifier le type de reçu. Par exemple, un ticket de caisse inclut le texte « Reçu ventes ».
- **Numéro séquentiel de la transaction signée** – Le numéro d’ordre d’une transaction signée peut apparaître sur le ticket de caisse pour associer un ticket de caisse imprimé à une signature numérique dans la base de données.
- **Totaux des reçus** – Les champs personnalisés des totaux de tickets de caisse excluent les montants hors ventes des montants de transaction totaux. Les montants hors ventes incluent les montants des opérations suivantes :

    - Acomptes (dépôt sur comptes client)
    - Acomptes pour les commandes client (dépôt sur commandes client)
    - Émission d’une carte cadeau
    - Ajout de fonds à une carte cadeau

#### <a name="x-and-z-reports"></a>États X et Z

Les informations qui sont incluses dans les états X et Z sont basées sur les besoins norvégiens. Par example, les montants **Ventes au comptant totales** incluent uniquement les montants des transactions de vente au comptant et excluent les opérations d’émission de cartes-cadeaux et les acomptes. Le total des ventes au comptant est également répertorié par groupe d’articles et mode de paiement. De plus, les montants **Ventes totales** et **Rendements totaux généraux** cumulatifs sont conservés et imprimés.

#### <a name="saf-t-cash-register-audit-file"></a>Fichier d’audit de la caisse enregistreuse SAF-T

Vous pouvez exporter le journal des transactions PDV dans le format de caisse enregistreuse prédéfini Fichier d’audit standard – Taxe (SAF-T). Le fichier d’audit comprend des informations sur l’organisation, les données de base pertinentes (telles que les groupes d’articles, les articles et les codes de taxe), les données de transaction de vente en espèces ainsi que les signatures pour ces transactions, les données d’événement non liées à la vente et les données de rapport de fin de date.

Le fichier d’audit peut être exporté pour les scénarios suivants :

- Par magasin
- Tous les magasins
- Par terminal
- Tous les terminaux

Vous pouvez également envoyer un rapport d’une entité juridique au nom d’une autre entité juridique. Dans ce cas, vous devez exécuter l’exportation à partir de l’entité juridique d’exploitation et spécifier l’entité juridique déclarante comme expéditeur du rapport.

Le format de caisse enregistreuse SAF-T est mis en œuvre au siège en utilisant [Déclaration électronique](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Configuration de Commerce pour la Norvège

Cette section décrit les paramètres spécifiques et recommandés pour la Norvège. Pour plus d’informations, voir [Ressources d’aide pour Dynamics 365 Retail](../index.md).

Pour utiliser la fonctionnalité spécifique pour la Norvège, vous devez effectuer les tâches suivantes :

- Définissez le champ **Pays/région** sur **NOR** (Norvège) dans l’adresse principale de l’entité juridique.
- Définissez le champ **Code ISO** sur **NO** (Norvège) dans le profil de fonctionnalité du PDV de chaque magasin situé en Norvège.

Vous devez également spécifier les paramètres suivants pour la Norvège.

### <a name="enable-features-for-norway"></a>Activer les fonctionnalités pour la Norvège

Vous devez activer les fonctionnalités suivantes dans l’espace de travail **Gestion des fonctionnalités** de Commerce headquarters :

- (Norvège) Activer les événements d’audit supplémentaires dans le PDV
- (Norvège) Activer des informations supplémentaires dans des relevés générés en fin de journée dans le PDV

### <a name="set-up-the-legal-entity"></a>Paramétrer l’entité juridique

Assurez-vous que le nom de l’entité juridique est spécifié. Ce nom sera imprimé sur les rapports X et Z.

Depuis, sur le raccourci **Informations sur le compte en banque**, dans le champ **Numéro d’acheminement**, spécifiez le numéro de l’organisation.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Configurer la taxe sur la valeur ajoutée (TVA) selon les exigences norvégiennes


Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation de la taxe, voir [Vue d’ensemble des taxes](../../finance/general-ledger/indirect-taxes-overview.md).

Vous devez également spécifier des groupes de taxe et activer l’option **Prix, taxe incluse** pour les magasins situés en Norvège.

### <a name="set-up-functionality-profiles"></a>Paramétrage des profils de fonctionnalité

Vous devez activer l’audit et configurer la numérotation des reçus.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Mettre à jour les groupes d’autorisations PDV et les paramètres d’autorisation individuels pour les employés du magasin

Définissez l’autorisation **Autoriser l’impression d’une copie du reçu** sur une valeur appropriée :

- **Autoriser toujours** – L’opérateur peut imprimer une copie d’un reçu plusieurs fois.
- **Autoriser une seule fois** – L’opérateur peut imprimer une copie d’un reçu une seule fois.
- **Autoriser une seule fois, et seulement si HQ DB est disponible** – L’opérateur ne peut imprimer une copie d’un reçu qu’une seule fois, et uniquement si la base de données HQ est disponible via Commerce Data Exchange : Service en temps réel, afin que le système puisse vérifier qu’aucune copie du reçu n’a été imprimée auparavant dans aucun magasin.
- **Jamais** – L’opérateur peut pas imprimer une copie d’un reçu.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins.

| ID langue | Texte                   | ID texte |
|-------------|------------------------|---------|
| fr-FR       | Titre du ticket de caisse          | 900011  |
| fr-FR       | Carte cadeau           | 900012  |
| fr-FR       | Total (ventes)          | 900013  |
| fr-FR       | Total des taxes (ventes)      | 900014  |
| fr-FR       | Total avec taxe (ventes) | 900015  |
| fr-FR       | Montant de taxe (ventes)     | 900016  |
| fr-FR       | ID de transaction des disponibilités    | 900017  |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère**.

| Name                            | Type    | ID texte de la légende |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Récépissé | 900011          |
| IsGiftCard                      | Récépissé | 900012          |
| SalesTotalExt                   | Récépissé | 900013          |
| TaxTotalExt                     | Récépissé | 900014          |
| TotalWithTaxExt                 | Récépissé | 900015          |
| AmountPerTaxExt                 | Récépissé | 900016          |
| CashTransactionSequentialNumber | Récépissé | 900017          |

> [!NOTE]
> Il est important que vous spécifiiez des noms de champs personnalisés corrects, comme indiqué dans le tableau ci-dessus. Un nom de champ personnalisé incorrect entraînera des données manquantes dans les reçus.

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour tous les formats de ticket de caisse nécessaires, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer** pour le format du reçu.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

1. En-tête :

    - **Titre du reçu** – Ce champ identifie le type de ticket de caisse.
    - **ID transaction au comptant** – Ce champ imprimer le numéro séquentiel de la transaction au comptant signée.

2. Lignes :

    - **Est une carte-cadeau** – Ce champ marque la ligne du reçu comme étant liée à l’opération Émettre une carte-cadeau ou Ajouter à la carte-cadeau.

3. Pied de page :

    - **Total (ventes)** – Ce champ permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant est hors taxe. Les acomptes et les opérations de carte cadeau sont exclues.
    - **Taxe totale (ventes)** – Ce champ permet d’imprimer le montant total des taxes des ventes de disponibilités. Les acomptes et les opérations de carte cadeau sont exclues.
    - **Total TTC (ventes)** – Ce champ permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant inclue la taxe. Les acomptes et les opérations de carte cadeau sont exclues.
    - **Montant de la taxe (ventes)** – Ce champ permet d’imprimer le montant des taxes du reçu pour les ventes au comptant par code de taxe. Les acomptes et les opérations de carte cadeau sont exclues.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Configurer le format d’exportation de la caisse enregistreuse SAF-T

La configuration de la caisse enregistreuse SAF-T est disponible en téléchargement sur Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Vous devez télécharger les configurations suivantes :

- **Canal de vente Retail data.version.1** – Configuration du modèle données.
- **Canal Retail DMM data.version.1.14** – Configuration du mappage du modèle données.
- **NO SAF T Cash Register.version.1.20** – La configuration des formats.

Après l’importation des configurations, dans la page **Paramètres Commerce**, sous l’onglet **Documents électroniques**, dans le champ **Format d’exportation de la caisse enregistreuse SAF-T**, sélectionnez le nom de la configuration du format importé.

Vous devez également mapper les données de base requises aux codes standard SAF-T prédéfinis. Pour plus d’informations, consultez la documentation de la caisse enregistreuse SAF-T fournie par l’administration fiscale norvégienne. Pour créer le mappage, vous devez définir le nouveau champ **Code de caisse SAF-T** sur les pages suivantes :

- Groupes d’articles
- Modes de paiement
- Codes taxe

### <a name="configure-channel-components"></a>Configurer des composants de canal

Pour activer la fonctionnalité spécifique à la Norvège, vous devez configurer les composants de canal. Pour plus d’informations, voir les [instructions de déploiement](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
