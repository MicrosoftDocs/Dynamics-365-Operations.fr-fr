---
title: Problèmes de synchronisation des commandes asynchrones
description: Cet article décrit les raisons courantes de l’échec de la création de commandes asynchrones dans Microsoft Dynamics 365 Commerce et fournit des étapes de dépannage pour aider les utilisateurs du système et les partenaires à comprendre ce qui s’est passé.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815754"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problèmes de synchronisation des commandes asynchrones

[!include [banner](../../includes/banner.md)]

Cet article décrit les raisons courantes de l’échec de la création de commandes asynchrones dans Microsoft Dynamics 365 Commerce et fournit des étapes de dépannage pour aider les utilisateurs du système et les partenaires à comprendre ce qui s’est passé.

## <a name="symptom"></a>Problème

Les commandes asynchrones créées depuis Dynamics 365 Commerce e-commerce ou point de vente (POS) ne sont pas reflétées dans Commerce headquarters.

## <a name="troubleshooting"></a>Résolution des problèmes

La création de commande peut échouer dans headquarters pour différentes raisons, selon l’étape à laquelle le processus de création de commande échoue. Les étapes de résolution des problèmes suivantes passent en revue les causes profondes possibles.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Valider que la transaction liée à la commande asynchrone est parvenue à headquarters

Pour les commandes e-commerce, dans headquarters, accédez à **Commerce et vente de détail \> Recherches et états \> Transactions de magasin en ligne**. Si vous disposez d’un numéro de confirmation pour la commande, filtrez les transactions en le saisissant dans le champ **ID de référence du canal**. Si vous n’avez pas le numéro de confirmation, filtrez les transactions en saisissant le numéro de compte client.

Pour les commandes PDV, ouvrez la page **Opérations en magasin** et filtrez les enregistrements par numéro de reçu ou numéro de compte client. Si la transaction n’est pas trouvée, exécutez la tâche de transactions du canal **P-0001**, qui synchronise les transactions des canaux jusqu’à headquarters. Si la tâche **P-0001** échoue, ouvrez un ticket d’assistance pour l’échec de la tâche. Si la tâche **P-0001** réussit, mais que les transactions n’apparaissent toujours pas dans headquarters, ouvrez un ticket d’assistance qui inclut les informations pertinentes.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Vérifiez l’état de la synchronisation si la transaction est présente dans headquarters, mais n’est pas liée à une commande client

Si la transaction est présente dans headquarters, mais que la commande client n’a pas été créée, ouvrez la page **Transactions de magasin en ligne** et sélectionnez le raccourci **Statut de synchronisation**. Si la tâche **Synchroniser les commandes** a tenté de synchroniser cette transaction, le champ **Statut de commande en attente** doit avoir le statut **Réussite** ou **Échec**. Si le statut est **Réussite**, le champ de la commande client doit être présent sur cette transaction. Si le statut est **Échec**, vous pouvez afficher les détails de l’erreur dans le champ **Détails de l’erreur de commande** sur le raccourci **Statut de synchronisation**. Si aucun de ces statuts n’est affiché, aucune tentative n’a été faite pour traiter la transaction. Dans ce cas, vous pouvez sélectionner **Synchroniser la commande** en haut de la page pour exécuter la tâche de synchronisation.

Assurez-vous que la tâche **Synchroniser les commandes** est planifiée pour une exécution périodique, afin que les transactions asynchrones puissent être créées en tant que commandes dans headquarters.

Les sections suivantes fournissent des informations sur certaines erreurs courantes et leurs correctifs proposés.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>Le champ Détails de l’erreur de commande affiche le message d’erreur suivant : « La séquence de numéros a été dépassée »

Les séquences de numéros sont utilisées pour créer des commandes client dans headquarters. Si tous les numéros autorisés pour une séquence de numéros sont épuisés, le système génère ce message d’erreur. La séquence de numéros utilisée pour créer des commandes client se trouve dans **Paramètres de la comptabilité client \> Séquences de numéros \> Commande client**. Pour résoudre cette erreur, corrigez la séquence de numéros existante ou remplacez-la par une nouvelle séquence de numéros.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>Le champ Détails de l’erreur de commande affiche le message d’erreur suivant : « Un service de paiement par défaut est nécessaire pour traiter les transactions de carte de crédit »

Pour résoudre cette erreur, vérifiez qu’un paiement par défaut est défini dans headquarters. Si aucun paiement par défaut n’est défini, vous devez en définir un. Accédez à **Comptabilité client \> Configuration des paiements \> Services de paiement**, et assurez-vous que l’option **Processeur par défaut des nouvelles cartes de crédit** est définie sur **Oui** pour un service de paiement.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>Le champ Détails de l’erreur de commande affiche un message d’erreur de structure de compte

Le texte du message d’erreur de structure de compte peut varier, comme le montrent les exemples suivants. Cependant, les erreurs partagent une cause première commune liée à la configuration de la structure du compte.

- « Les résultats de publication pour le numéro de lot de journal 0009656328 Bon ARP-000959899 1.00 pour le bon ARP-000959899 dans la société usrt seront validés en tant que trop-perçu ou moins-perçu »
- « Validation des résultats pour le numéro de lot de journal 0009656328 Bon ARP-000959899 Bon ARP-000959901 La structure de compte, pour la combinaison 618160, n’est pas valide pour la comptabilité Compte principal d’entreprise partagé »
- « Validation des résultats pour le numéro de lot de journal 0009656328 Bon ARP-000959899 Bon ARP-000959901 Report à partir des comptes de l’entreprise usrt »
- « Validation des résultats pour le numéro de lot de journal 0009656328 Bon ARP-000959899 La validation a été annulée »
    
Pour corriger ces erreurs, vérifiez l’exactitude des structures de compte. Pour plus d’informations, voir [Configurer des structures de compte](/dynamics365/finance/general-ledger/configure-account-structures).
    
Une fois l’erreur corrigée, sélectionnez la transaction ayant échoué, puis sélectionnez **Synchroniser la commande** en haut de la page pour exécuter la tâche de synchronisation.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Autres types d’erreurs pouvant nécessiter la correction des données de transaction

Pour corriger d’autres types d’erreurs qui pourraient nécessiter la correction des données de transaction, vous pouvez utiliser la fonction « modifier et auditer les transactions ». Pour plus d’informations, voir [Modifier et auditer les transactions](../edit-order-trans.md).
