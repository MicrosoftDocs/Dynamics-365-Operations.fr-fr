---
title: Migration de type de données de devise pour la double écriture
description: Cette rubrique décrit comment modifier le nombre de décimales prises en charge par la double écriture pour la devise.
author: RamaKrishnamoorthy
ms.date: 12/08/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: e9dc3e6c5fbec9636370b64a9bbdcf8a5834d332
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061834"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migration de type de données de devise pour la double écriture

[!include [banner](../../includes/banner.md)]



Vous pouvez augmenter le nombre de décimales prises en charge pour les valeurs monétaires à un maximum de 10. La limite par défaut est de quatre décimales. En augmentant le nombre de décimales, vous contribuez à éviter la perte de données lorsque vous utilisez la double écriture pour synchroniser les données. L’augmentation du nombre de décimales est un changement disponible. Pour l’implémenter, vous devez demander l’assistance de Microsoft.

Le processus de modification du nombre de décimales comporte deux étapes :

1. Demander la migration à partir de Microsoft.
2. Modifier le nombre d’emplacements des décimales dans Dataverse.

L’application Finances et Opérations et Dataverse doivent prendre en charge le même nombre de décimales dans les valeurs monétaires. Sinon, une perte de données peut se produire lorsque ces informations sont synchronisées entre les applications. Le processus de migration reconfigure la façon dont les devises et les taux de change sont stockés, mais il ne modifie aucune donnée. Une fois la migration terminée, le nombre de décimales pour les codes de devise et la tarification peut être augmenté, et les données que les utilisateurs saisissent et consultent peuvent avoir une précision décimale plus élevée.

La migration est facultative. Si vous pouvez bénéficier de la prise en charge de davantage de décimales, nous vous recommandons d’envisager la migration. Les organisations qui ne nécessitent pas de valeurs comportant plus de quatre décimales n’ont pas à migrer.

## <a name="requesting-migration-from-microsoft"></a>Demande de migration à partir de Microsoft

Le stockage des colonnes de devises existantes dans Dataverse ne peut pas prendre en charge plus de quatre décimales. Par conséquent, pendant le processus de migration, les valeurs monétaires sont copiées dans de nouvelles colonnes internes de la base de données. Ce processus se produit en continu jusqu’à ce que toutes les données aient été migrées. En interne, à la fin de la migration, les nouveaux types de stockage remplacent les anciens types de stockage, mais les valeurs des données restent inchangées. Les colonnes monétaires peuvent alors prendre en charge jusqu’à 10 décimales. Pendant le processus de migration, Dataverse peut continuer à être utilisé sans interruption.

Dans le même temps, les taux de change sont modifiés de sorte qu’ils prennent en charge jusqu’à 12 décimales au lieu de la limite actuelle de 10. Cette modification est nécessaire pour que le nombre de décimales soit le même dans l’application Finances et Opérations et Dataverse.

La migration ne modifie aucune donnée. Une fois les colonnes de devise et de taux de change converties, les administrateurs peuvent configurer le système pour utiliser jusqu’à 10 décimales pour les colonnes de devise en spécifiant le nombre de décimales pour chaque devise de transaction et pour la tarification.

### <a name="request-a-migration"></a>Demander une migration

Pour rendre cette fonctionnalité disponible, envoyez un e-mail à **CDSExpandDecimal@microsoft.com** en fournissant les informations suivantes :

+ **Objet :** Demande d’activation de la prise en charge décimale étendue pour \<organizationID\>
+ **Corps :** Je souhaite activer le support décimal étendu pour mon organisation \<organizationID\>.

Un représentant Microsoft vous contactera dans les deux à trois jours ouvrables pour les prochaines étapes.

Lorsque vous demandez une migration, vous devez connaître les détails suivants et les planifier en conséquence :

+ Le temps requis pour migrer les données dépend de la quantité de données dans le système. La migration de grandes bases de données peut prendre plusieurs jours.
+ La taille de la base de données augmente temporairement pendant la migration, car un espace supplémentaire est nécessaire pour les index. La plupart de l’espace supplémentaire est libéré lorsque la migration est terminée.
+ Au cours du processus de migration, si des erreurs se produisent qui empêchent la migration de se terminer, le système envoie des alertes au support Microsoft, afin que le personnel de support puisse intervenir. Cependant, même si des erreurs se produisent lors de la migration, Dataverse reste entièrement disponible pour une utilisation régulière.
+ Le processus de migration n’est pas réversible.

## <a name="changing-the-number-of-decimal-places"></a>Modification du nombre d’emplacements des décimales

Une fois la migration terminée, Dataverse peut stocker des nombres qui ont plus de décimales. Les administrateurs peuvent choisir le nombre de décimales à utiliser pour des codes de devise spécifiques et pour la tarification. Les utilisateurs de Microsoft Power Apps, Power BI et Power Automate peuvent alors afficher et utiliser des nombres qui ont plus de décimales.

Pour effectuer cette modification, vous devez mettre à jour les paramètres suivants dans Power Apps :

+ **Paramètres système : précision des devises pour la tarification** – La colonne **Définir la précision de la devise utilisée pour la tarification dans tout le système** définit le comportement de la devise pour l’organisation lorsque **Précision de tarification** est sélectionné.
+ **Gestion d’entreprise : Devises** – La colonne **Précision des devises** vous permet de spécifier un nombre personnalisé de décimales pour une devise spécifique. Il y a un repli dans le cadre à l’échelle de l’organisation.

Il existe certaines limitations :

+ Vous ne pouvez pas configurer la colonne de devise sur une table.
+ Vous pouvez spécifier plus de quatre décimales uniquement aux niveaux **Tarification** et **Devise de la transaction**.

### <a name="system-settings-currency-precision-for-pricing"></a>Paramètres système : précision des devises pour la tarification

Une fois la migration terminée, les administrateurs peuvent définir la précision de la devise. Accédez à **Paramètres \> Administration** et sélectionnez **Paramètres système**. Ensuite, dans l’onglet **Général**, modifiez la valeur de la colonne **Définir la précision de la devise utilisée pour la tarification dans tout le système**, comme indiqué dans l’illustration suivante.

![Paramètres système pour la devise.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Gestion d’entreprise : Devises

Si vous souhaitez que la précision de la devise pour une devise spécifique diffère de la précision de la devise utilisée pour la tarification, vous pouvez la modifier. Accédez à **Paramètres \> Gestion d’entreprise**, sélectionnez **Devises** et sélectionnez la devise à modifier. Ensuite définissez la colonne **Précision des devises** sur le nombre de décimales souhaité, comme indiqué dans l’illustration suivante.

![Paramètres de devise pour un environnement local spécifique.](media/specific-currency.png)

### <a name="tables-currency-column"></a>Tables : colonne Devise

Le nombre de décimales pouvant être configuré pour des colonnes de devise spécifiques est limité à quatre.

### <a name="default-currency-decimal-precision"></a>Précision décimale de la devise par défaut
Pour connaître le comportement attendu de la précision décimale de la devise par défaut dans les scénarios de migration et de non-migration, reportez-vous au tableau suivant. 

| Date de création  | Champ Décimale devise    | Organisation existante (champ Devise non migré) | Organisation existante (champ Devise migré) | Nouvelle organisation créée après la build 9.2.21062.00134 |
|---------------------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Champ de devise créé avant la build 9.2.21111.00146  |     |  |       |
|    | Précision maximale visible dans l’interface utilisateur   | 4 chiffres    | 10 chiffres    | S/O    |
| | Précision maximale visible dans l’interface utilisateur des résultats de la base de données et des requêtes de base de données         | 4 chiffres   | 10 chiffres   | S/O    |
| Champ de devise créé après la build 9.2.21111.00146 |    |  |     |   |
|   | Précision décimale maximale visible dans l’interface utilisateur     | 4 chiffres   | 10 chiffres   | 10 chiffres     |
|          | Précision décimale maximale dans l’interface utilisateur des résultats de la base de données et des requêtes de base de données | 10 chiffres. Cependant, seuls 4 sont significatifs avec tous les zéros au-delà des 4 chiffres décimaux. Cela permet une migration plus simple et plus rapide de l’organisation, si nécessaire. | 10 chiffres      | 10 chiffres     |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
