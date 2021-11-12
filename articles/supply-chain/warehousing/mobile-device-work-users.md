---
title: Comptes d’utilisateur d’appareil mobile
description: Cette rubrique explique comment configurer et gérer des comptes d’utilisateur qui permettent aux collaborateurs de se connecter et d’utiliser l’application d’entrepôt.
author: MarkusFogelberg
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9ff6752f303adab6c4c52f2f09eea1c0ae2e8e0a
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647812"
---
# <a name="mobile-device-user-accounts"></a>Comptes d’utilisateur d’appareil mobile

[!include [banner](../includes/banner.md)]

Chaque fois qu’un collaborateur commence à utiliser l’application d’entrepôt, il doit se connecter à l’aide d’un nom d’utilisateur et d’un mot de passe. N’importe quel nombre d’utilisateurs d’applications d’entrepôt peut être associé à chaque collaborateur du système, et les entrepôts sont généralement associés à chacun de ces utilisateurs d’applications d’entrepôt. Différentes options sont également configurées pour chaque collaborateur, afin d’établir des paramètres par défaut et d’autres paramètres pertinents pour l’utilisation de l’application d’entrepôt.

## <a name="set-up-the-required-worker-and-employee-records"></a>Configurer les enregistrements de collaborateur et d’employé

Avant de pouvoir configurer les utilisateurs de l’application d’entrepôt, chaque collaborateur doit déjà exister en tant qu’employé Supply Chain Management ou collaborateur dans le module **Ressources humaines**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Paramétrer des comptes d’utilisateur d’appareil mobile

Une fois que les collaborateurs et les employés requis sont configurés dans le module Ressources humaines, vous pouvez affecter des utilisateurs d’application d’entrepôt à chacun d’eux et configurer d’autres options qui affectent la façon dont ils peuvent utiliser l’application.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Pour modifier un collaborateur existant, sélectionnez-le dans le volet de liste. Pour ajouter un nouvel enregistrement, sélectionnez **Nouveau** dans le volet Action.
1. Si vous configurez un nouveau collaborateur, procédez comme suit :

    1. Dans le champ **Employé**, sélectionnez l’utilisateur cible dans la liste des employés.
    1. Cliquez sur **Sélectionner**.
    1. Dans le volet Actions, sélectionnez **Enregistrer**.

1. Un profil par défaut peut être utilisé pour guider le magasinier dans le processus requis au poste d’emballage. Le profil par défaut peut également être utilisé pour enregistrer les paramètres de profil préférés pour le collaborateur. Dans l’organisateur **Profil**, définissez les champs suivants :

    - **Stratégie d’emballage de conteneur** – Sélectionnez une stratégie d’emballage de conteneur qui définit la manière dont les conteneurs doivent être traités à la station d’emballage. La stratégie d’emballage de conteneur qui est sélectionnée ici sera présélectionnée pour le collaborateur lorsqu’il ouvrira la station d’emballage. Pour plus d’informations, consultez le billet de blog suivant : [Fonctionnalités d’emballage améliorées](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **ID de profil d’emballage** – Sélectionnez un ID de profil d’emballage qui définit la stratégie d’emballage et les paramètres de conteneur qui sont utilisés. Si l’ID de profil d’emballage sélectionné est associé à une stratégie d’emballage de conteneur, vous ne pourrez pas modifier le paramètre **Stratégie d’emballage de conteneur** sur cette page.

1. Sur le raccourci **Station d’emballage par défaut**, définissez les champs suivants pour définir la station d’emballage par défaut qui s’applique lorsque le collaborateur se connecte. Si nécessaire, le collaborateur peut toujours sélectionner une autre station d’emballage.

    - **Site** – Sélectionnez le site où se trouve la station d’emballage par défaut.
    - **Entrepôt** – Sélectionnez l’entrepôt où se trouve la station d’emballage par défaut.
    - **Emplacement** – Sélectionnez l’emplacement de la station d’emballage par défaut.

1. Le raccourci **Utilisateurs** vous permet de créer n’importe quel nombre de comptes d’utilisateurs d’application d’entrepôt pour le collaborateur sélectionné. Chaque compte est associé à un ou plusieurs entrepôts spécifiques. Utilisez la barre d’outils pour ajouter ou supprimer des comptes d’utilisateur, réinitialiser le mot de passe pour un compte sélectionné ou attribuer des entrepôts à un compte sélectionné. Pour chaque compte d’utilisateur, définissez les champs suivants :

    - **ID utilisateur** – Entrez un ID unique.
    - **Nom d’utilisateur** – Entrez un nom pour l’ID.
    - **Entrepôt par défaut** – Définissez l’entrepôt par défaut où le collaborateur travaille habituellement. Vous pouvez utiliser la barre d’outils pour affecter des entrepôts supplémentaires, et le collaborateur peut basculer entre les entrepôts à l’aide de l’activité indirecte **Modifier l’entrepôt** de l’élément de menu de l’appareil mobile.
    - **Nom du menu** – Sélectionnez le menu racine qui sera la page de démarrage du collaborateur. La possibilité de configurer un menu racine pour chaque collaborateur est utile, car elle vous permet de contrôler la structure de menu que chaque collaborateur peut utiliser. Par exemple, le menu pour les travailleurs qui sont actifs uniquement dans la zone sortante peut être personnalisé pour les tâches liées aux opérations sortantes pour cette zone.
    - **Inactif** – Lorsque la case est cochée, cela indique que le compte d’utilisateur est inactif. Le compte d’utilisateur est automatiquement désactivé si un collaborateur entre cinq fois de suite le mauvais mot de passe dans l’application de l’entrepôt. Cependant, vous pouvez également sélectionner cette case manuellement. Décochez la case pour réactiver l’utilisateur.

1. Dans le raccourci **Travail**, définissez les champs suivants :

    - **Autoriser le remplacement de l’emplacement de prélèvement** – Définissez cette option sur *Oui* pour permettre au collaborateur de remplacer l’emplacement pour les étapes de prélèvement. Cette fonctionnalité peut être utile si l’inventaire physique ne correspond pas à l’emplacement suggéré par le système.
    - **Autoriser le remplacement de l’emplacement de rangement** – Définissez cette option sur *Oui* pour permettre au collaborateur de remplacer l’emplacement pour les étapes de rangement. Cette fonctionnalité peut être utile si l’emplacement de rangement suggéré est actuellement plein ou non disponible, ou si les emplacements intermédiaires ont changé.
    - **Autoriser le prélèvement excessif des ventes** – Définissez cette option sur *Oui* pour permettre au collaborateur d’effectuer un prélèvement excessif lorsque les commandes clients sont prélevées. Pour plus d’informations, voir [Prélèvement excessif pour les commandes client et les ordres de transfert](over-picking-for-sales-and-transfer-orders.md).
    - **Autoriser le prélèvement excessif d’ordre de transfert** – Définissez cette option sur *Oui* pour permettre au collaborateur d’effectuer un prélèvement excessif lorsque les ordres de transfert sont prélevés. Pour plus d’informations, voir [Prélèvement excessif pour les commandes client et les ordres de transfert](over-picking-for-sales-and-transfer-orders.md).
    - **Autoriser les mouvements de stock avec le travail associé** – Définissez cette option sur *Oui* pour permettre au collaborateur de déplacer l’inventaire qui est déjà réservé ou déjà associé à d’autres travaux. Pour plus d’information, voir [Mouvements de stock avec le travail associé dans Warehouse management](move-inventory-associated-work.md).
    - **Autoriser la réaffectation manuelle des articles** – Définissez cette option sur *Oui* pour permettre la réaffectation manuelle pour le collaborateur pendant les prélèvements partiels. La réaffectation des articles guide les collaborateurs pour prélever le stock à un autre emplacement. Bien que la réaffectation automatique soit disponible pour tous les collaborateurs, la réaffectation manuelle nécessite une configuration explicite pour un collaborateur. La possibilité de contrôler la réaffectation manuelle pour chaque collaborateur peut être utile, car elle vous permet de contrôler la visibilité de chaque collaborateur lorsque, par exemple, le prélèvement d’articles dans la zone de quarantaine ou de vrac est limité aux collaborateur de confiance. Pour plus d’informations, consultez le billet de blog suivant : [Réaffectation automatique et manuelle des articles pendant les prélèvements partiels](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Superviseur d’inventaire tournant** – Définissez cette option sur *Oui* pour que le collaborateur devienne un superviseur d’inventaire tournant. Dans ce cas, tous les inventaires tournants que le collaborateur effectue sur l’application d’entrepôt seront immédiatement approuvés. Les champs **Limite maximale du pourcentage**, **Limite maximale de la quantité** et **Limite maximale de la valeur** ne sont pas pris en compte pour les collaborateurs pour lesquels cette option est définie sur *Oui*.
    - **Limite maximale du pourcentage** – Entrez la limite du pourcentage le plus élevé de différence par rapport au nombre prévu pour un inventaire tournant sans demander l’approbation d’un superviseur d’inventaire tournant.
    - **Limite maximale de la quantité** – Saisissez la quantité totale de différence par rapport à la quantité prévue (en unités) pour la quantité saisie sans demander l’approbation d’un superviseur d’inventaire tournant.
    - **Limite maximale de la valeur** – Saisissez le montant maximal selon lequel le coût de l’inventaire peut différer par rapport au coût prévu pour un inventaire tournant sans demander l’approbation d’un superviseur d’inventaire tournant.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Si vous avez ajouté un nouveau compte d’utilisateur, la boîte de dialogue **Définir le mot de passe** s’affiche ; vous pouvez y créer un mot de passe simple que l’utilisateur utilisera pour se connecter à l’application mobile. Saisissez le mot de passe simple deux fois, puis sélectionnez **Enregistrer le mot de passe** pour continuer.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Définir la langue, les formats de numéro et le fuseau horaire pour chaque utilisateur de l’application d’entrepôt

Lorsqu’un collaborateur se connecte à l’application mobile Warehouse Management, la langue, les formats de numéro et le fuseau horaire changent pour correspondre aux préférences de ce collaborateur. Les paramètres de compte pour le collaborateur qui est sélectionné à l’étape 3 dans la section [Paramétrer des comptes d’utilisateur d’appareil mobile](#set-wma-users) détermine les paramètres qui sont utilisés. Si vous avez besoin de paramètres distincts pour chaque utilisateur, utilisez des comptes de collaborateurs différents. La procédure suivante montre comment modifier la langue, les formats de numéro et le fuseau horaire pour chaque utilisateur de l’application d’entrepôt.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Recherchez le nom du collaborateur à configurer. Assurez-vous que le collaborateur dispose de tous les comptes d’utilisateur d’application d’entrepôt requis qui sont répertoriés sur le raccourci **Utilisateurs**. Créez un nouveau collaborateur et/ou ajoutez des comptes d’utilisateur d’application d’entrepôt selon les besoins, en suivant les étapes de la section [Paramétrer des comptes d’utilisateur d’appareil mobile](#set-wma-users).
1. Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.
1. Sélectionnez le compte d’utilisateur où la colonne **Personne** affiche le nom du collaborateur que vous avez trouvé à l’étape 2.

    > [!IMPORTANT]
    > Les valeurs **ID d’utilisateur** qui sont répertoriées sur les pages **Utilisateurs** *ne sont pas* liées aux valeurs qui sont affichées sur le raccourci **Utilisateurs** de la page **Collaborateur** que vous avez ouverte à l’étape 1.

1. Dans le volet Actions, sélectionnez **Options utilisateur**.
1. Dans l’onglet **Préférences**, définissez les champs suivants :

    - **Langue** – Sélectionnez la langue préférée du collaborateur. Ce champ contrôle également le format de date affiché dans l’application d’entrepôt.
    - **Format de date, d’heure et de numéro** – Sélectionnez la langue qui déterminera les formats de numéro affichés dans l’application d’entrepôt. Notez que les formats de date et d’heure affichés dans l’application d’entrepôt sont en fait déterminés par le champ **Langue**, et non par ce champ.
    - **Fuseau horaire** – Sélectionnez le fuseau horaire dans lequel travaille le collaborateur. Ce champ affecte l’horodatage de toutes les inscriptions effectuées par le collaborateur à l’aide de l’application.

> [!NOTE]
> Dans certains cas, l’application d’entrepôt ne pourra pas trouver les paramètres spécifiques au collaborateur qui définissent la langue, les formats de numéro et le fuseau horaire. Les règles suivantes s’appliquent :
>
> - Si l’application n’est pas connectée à un environnement Supply Chain Management (par exemple, la première fois que l’application est lancée après son installation), la langue de l’appareil local est utilisée. Lorsque la langue de l’appareil change, la langue de l’application change également. Pour plus d’informations sur la configuration de la langue de l’appareil local, consultez la documentation de votre appareil et/ou de votre système d’exploitation.
> - Si l’application est connectée à un environnement Supply Chain Management, mais qu’aucune préférence n’est définie pour le collaborateur connecté, la langue, les formats de numéro et le fuseau horaire sont sélectionnés en fonction du compte associé à l’ID client utilisé par l’appareil pour se connecter à Supply Chain Management. Pour plus d’informations voir [Créer et configurer un compte d’utilisateur dans Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Si vous remarquez que des horodatages incorrects sont affichés pour les inscriptions effectuées à l’aide de l’application d’entrepôt, vous devrez peut-être ajuster le fuseau horaire défini pour le compte d’utilisateur que les collaborateurs utilisent pour se connecter à et/ou s’authentifier avec Supply Chain Management. Comme mentionné précédemment, le paramètre de fuseau horaire peut provenir du compte d’utilisateur utilisé pour se connecter à l’application d’entrepôt, tel qu’il est configuré sur la page **Collaborateur**. Sinon, si le compte d’utilisateur n’est pas défini sur la page **Collaborateur**, le fuseau horaire provient du compte d’utilisateur associé à l’ID client utilisé pour l’authentification, tel qu’il est configuré sur la page **[Applications Azure Active Directory](install-configure-warehouse-management-app.md)**.
