---
title: Copier une instance
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008968"
---
# <a name="copy-an-instance"></a>Copier une instance

Vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Human Resources dans un environnement de bac à sable. Si vous avez un autre environnement de bac à sable, vous pouvez également copier la base de données de cet environnement vers un environnement cible de bac à sable.

Pour copier une instance, vous devez vous assurer des éléments suivants :

- L'instance Human Resources que vous souhaitez remplacer doit être un environnement de bac à sable.

- Les environnements à partir desquels vous copiez doivent être situés dans la même région. Vous ne pouvez pas copier entre les régions.

- Vous devez être administrateur dans l'environnement cible afin de pouvoir vous y connecter après avoir copié l'instance.

- Lorsque vous copiez la base de données des ressources humaines, vous ne copiez pas les éléments (applications ou données) contenus dans un environnement Microsoft PowerApps. Pour plus d'informations sur la copie d'éléments dans un environnement PowerApps, voir [Copier un environnement](https://docs.microsoft.com/power-platform/admin/copy-environment). L'environnement PowerApps que vous souhaitez remplacer doit être un environnement de bac à sable. Vous devez être un administrateur de locataire global pour basculer un environnement PowerApps de production vers un environnement de bac à sable. Pour plus d'informations sur la modification d'un environnement PowerApps, voir [Basculer une instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Effets de la copie d'une base de données Human Resources

Les événements suivants se produisent lorsque vous copiez une base de données Human Resources :

- Le processus de copie efface la base de données existante dans l'environnement cible. Une fois le processus de copie terminé, vous ne pouvez pas récupérer la base de données existante.

- L'environnement cible ne sera pas disponible tant que le processus de copie n'est pas terminé.

- Les documents dans le stockage Microsoft Azure Blob n'est pas copié d'un environnement à un autre. Par conséquent, tous les documents et modèles joints ne seront pas copiés et resteront dans l'environnement source.

- Tous les utilisateurs sauf l'utilisateur Admin et les autres comptes d'utilisateurs de service interne seront désactivés. Par conséquent, l'utilisateur Admin peut supprimer ou masquer les données avant que d'autres utilisateurs ne soient autorisés à réintégrer le système.

- L'utilisateur Admin doit apporter les modifications de configuration requises, telles que la reconnexion des points de terminaison d'intégration à des services ou URL spécifiques.

## <a name="copy-the-human-resources-database"></a>Copier la base de données Human Resources

Pour terminer cette tâche, vous devez d'abord copier une instance, puis vous connecter au Centre d'administration Microsoft Power Platform pour copier votre environnement PowerApps.

> [!WARNING]
> Lorsque vous copiez une instance, la base de données est effacée dans l'instance cible. L'instance cible n'est pas disponible pendant ce processus.

1. Connectez-vous à LCS et sélectionnez le projet LCS qui contient l'instance que vous souhaitez copier.

2. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Human Resources**.

3. Sélectionnez l'instance à copier, puis sélectionnez **Copier**.

4. Dans le volet des tâches **Copier une instance**, sélectionnez l'instance à remplacer, puis sélectionnez **Copier**. Attendez que la valeur du champ **Statut de la copie** affiche **Terminé**.

   ![[Sélectionner l'instance à remplacer](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Sélectionnez **Power Platform**, et aconnectez-vous au Centre d'administration Microsoft Power Platform.

   ![[Sélectionner Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Sélectionnez l'environnement PowerApps à copier, puis sélectionnez **Copier**.

7. Une fois le processus de copie terminé, connectez-vous à l'instance cible et activez l'intégration Common Data Service. Pour plus d'informations et instructions, voir [Configurer l'intégration Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Éléments de données et statuts

Les éléments de données suivants ne sont pas copiés lorsque vous copiez une instance Human Resources :

- Adresses e-mail dans la table **LogisticsElectronicAddress**

- Historique des traitements par lots dans les tables **BatchJobHistory**, **BatchHistory**, et **BatchConstraintHistory**

- Le mot de passe SMTP (Simple Mail Transfer Protocol) dans la table **SysEmailSMTPPassword**

- Le serveur SMTP Relay dans la table **SysEmailParameters**

- Paramètres de gestion d'impression dans les tables **PrintMgmtSettings** et **PrintMgmtDocInstance**

- Enregistrements spécifiques à l'environnement dans les tables **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, et **BatchServerGroup**

- Pièces jointes dans la table DocuValue. Ces pièces jointes comprennent tous les modèles Microsoft Office qui ont été remplacés dans l'environnement source

- Chaîne de connexion dans la table **PersonnelIntegrationConfiguration**

Certains de ces éléments ne sont pas copiés car ils sont spécifiques à l'environnement. Les exemples comprennent les enregistrements **BatchServerConfig** et **SysCorpNetPrinters**. Les autres éléments ne sont pas copiés en raison du volume des tickets de support. Par exemple, des e-mails en double peuvent être envoyés car SMTP est toujours activé dans l'environnement de test d'acceptation des utilisateurs (bac à sable), des messages d'intégration non valides peuvent être envoyés car les traitements par lots sont toujours activés et les utilisateurs peuvent être activés avant que les administrateurs puissent effectuer des actions de nettoyage post-actualisation.

En outre, les statuts suivants changent lorsque vous copiez une instance :

- Tous les utilisateurs sauf Admin sont définis sur **Désactivé**.

- Tous les traitements par lots, à l'exception de certains traitements système, sont définis sur **Retenir**.

## <a name="environment-admin"></a>Administrateur de l'environnement

Tous les utilisateurs de l'environnement de bac à sable cible, y compris les administrateurs, sont remplacés par les utilisateurs de l'environnement source. Avant de copier une instance, assurez-vous que vous êtes administrateur dans l'environnement cible. Si ce n'est pas le cas, vous ne pourrez pas vous connecter à l'environnement de bac à sable cible une fois la copie terminée.

Tous les utilisateurs non administrateurs de l'environnement de bac à sable cible sont désactivés pour empêcher les connexions indésirables dans l'environnement de bac à sable. Les administrateurs peuvent réactiver les utilisateurs si nécessaire.