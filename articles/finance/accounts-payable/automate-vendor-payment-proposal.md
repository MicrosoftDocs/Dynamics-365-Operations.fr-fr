---
title: Automatiser les propositions de paiement fournisseur
description: Cette rubrique explique comment les organisations qui paient les fournisseurs selon un programme récurrent peuvent automatiser le processus de génération des propositions de paiement fournisseur.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 2b4e6b42326ecbd07efe006afb23931849f5cf58
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4443393"
---
# <a name="automate-vendor-payment-proposals"></a>Automatiser les propositions de paiement fournisseur

[!include [banner](../includes/banner.md)]

Les organisations qui paient les fournisseurs selon un programme récurrent peuvent désormais automatiser le processus de génération des propositions de paiement fournisseur. Les automatisations de proposition de paiement fournisseur définissent les détails suivants :

- Le moment d’exécution des propositions de paiement
- Les critères utilisés pour sélectionner les factures à payer
- Le journal de paiement fournisseur dans lequel les paiements résultants sont enregistrés

Les automatisations de proposition de paiement ne valident pas automatiquement les paiements. Par conséquent, vous pouvez continuer à utiliser tous les processus de validation et de workflow que vous utilisez actuellement pour approuver les paiements créés.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Définir l’occurrence des propositions de paiement fournisseur

Les automatisations de proposition de paiement fournisseur utilisent le cadre Automatisation des processus. Différents processus métier utilisent ce cadre pour définir la récurrence d’un processus sélectionné. Pour les propositions de paiement fournisseur, l’automatisation est accessible à **Comptabilité fournisseur \> Paramétrage des paiements \> Automatisation des processus**.

Tout d’abord, utilisez l’option d’automatisation **Créer un nouveau processus**, puis sélectionnez **Proposition de paiement fournisseur**. Un assistant vous guide ensuite dans le processus de configuration de la proposition de paiement fournisseur.

## <a name="general-page"></a>Page Général

Sur la page **Général** de l’assistant, saisissez le nom de la proposition de paiement fournisseur que vous créez. Par exemple, si vous payez tous les fournisseurs nationaux par chèque le lundi, entrez un nom descriptif tel que **National\_Chèque**. Le nom que vous entrez apparaît dans la vue hebdomadaire d’automatisation des processus dans l’espace de travail **Paiements fournisseur**.

Ensuite, définissez le propriétaire du journal des paiements créé. Le propriétaire est généralement le commis au paiement de la comptabilité fournisseur, qui est responsable du journal des paiements après sa création.

Les autres paramètres de la page sont génériques et sont utilisés pour définir le schéma d’occurrence de cette version de la proposition de paiement fournisseur. Par exemple, si une occurrence concerne les paiements par chèque le lundi, vous pouvez la définir de sorte qu’elle s’exécute chaque semaine et vous pouvez sélectionner le lundi comme jour de la semaine où elle s’exécute. Vous pouvez également saisir une heure de programmation anticipée, telle que 02h00, afin que l’automatisation du processus soit terminée avant le début du jour ouvrable suivant.

Il est important de comprendre que vous utilisez l’assistant pour définir le moment du traitement de la proposition de paiement fournisseur. Vous ne définissez pas le moment de la génération, de l’impression ni de la validation du paiement fournisseur. Dans la vue hebdomadaire, l’automatisation du processus pour les propositions de paiement fournisseur apparaîtra les jours sélectionnés dans le modèle d’occurrence.

Pour plus d’informations sur les autres champs de la page **Général**, voir la documentation de l’automatisation des processus.

## <a name="vendor-payment-proposal-page"></a>Page de proposition de paiement fournisseur

La page suivante de l’assistant est la page **Proposition de paiement fournisseur**. Elle permet de définir les critères de sélection des factures fournisseur à payer. En général, on trouve les mêmes options dans la proposition de paiement et dans le journal des paiements fournisseur. Il existe cependant quelques exceptions. Par exemple, toutes les dates de cette page doivent être définies comme des dates relatives, car la date de la proposition de paiement change à chaque exécution de la proposition.

### <a name="journal-name"></a>Nom de journal

Le champ **Nom du journal** définit le nom du journal dans lequel les paiements fournisseur sont créés. Les résultats de l’automatisation des propositions de paiement fournisseur créeront des paiements dans le journal défini, mais le journal ne sera pas validé.

### <a name="from-date-and-to-date"></a>Date de début et de fin

Au lieu de définir une date de début et une date de fin pour sélectionner les factures en fonction de leur date d’échéance ou de leur date d’escompte, vous devez utiliser l’option **Définir des critères de date de début** et le champ **Ajustement du nombre de jours pour la date de début** pour définir la date de début. Il n’existe pas de concept de date de début dans les automatisations des proposition de paiement.

Par défaut, l’option **Définir des critères de date de début** est définie sur **Non**. Si vous utilisez cette valeur par défaut, le processus sélectionnera toutes les factures à payer lors de son exécution, car aucune date de fin n’a été définie.

Si vous définissez l’option **Définir des critères de date de début** sur **Oui**, utilisez le champ **Ajustement du nombre de jours pour la date de début** pour définir la date à laquelle les factures sont sélectionnées comme le nombre de jours spécifié avant ou après la date d’exécution du processus. Le nombre peut être positif, négatif ou nul (zéro). Le système paiera alors les factures dont les dates d’échéance ou les dates d’escompte, sont le nombre de jours spécifié avant ou après la date d’exécution du processus. Par exemple, pour toutes les factures qui sont dues le vendredi ou avant, la série de paiements crée des paiements à tous les fournisseurs par chèque le mercredi. Dans ce cas, définissez le champ **Ajustement du nombre de jours pour la date de début** sur **2**. Lorsque l’occurrence de la proposition de paiement est exécutée le mercredi 25 mars, toutes les factures dont la date d’échéance ou la date d’escompte est le 27 mars ou avant seront sélectionnées pour le paiement.

### <a name="minimum-payment-date"></a>Date de paiement minimale

La date de paiement minimale définit la date la plus proche utilisée lors de la création des paiements. Vous devez d’abord définir l’option **Définir des critères de date de paiement minimum** sur **Oui**. Ce paramètre vous permet d’utiliser la fonctionnalité de date de paiement minimale. Si l’option est définie sur **Oui**, utilisez le champ **Ajustement du nombre de jours pour la date de paiement minimum** pour définir la date de paiement minimum comme le nombre de jours spécifié avant ou après la date d’exécution du processus. Le nombre peut être positif, négatif ou nul (zéro). Par exemple, la série de paiements génère des paiements le mercredi pour inclure tous les paiements dont la date de paiement minimale est le lundi précédent. Dans ce cas, définissez le champ **Ajustement du nombre de jours pour la date de paiement minimum** sur **-2**.

Voici un exemple qui montre comment les champs correspondant à la date de début et à la date de paiement minimum fonctionnent ensemble. L’automatisation des propositions de paiement est configurée pour s’exécuter le mercredi. Le champ **Ajustement du nombre de jours pour la date de début** est défini sur **1** pour définir la date de début en fonction de la date d’échéance. Le champ **Ajustement du nombre de jours pour la date de paiement minimum** est défini sur **-2**. Si l’automatisation du processus de paiement commence le mercredi 25 mars, toutes les factures dues le 26 mars ou avant seront incluses dans la proposition de paiement. Les propositions de paiement seront générées de la manière suivante :

- Toutes les factures qui sont dues au plus tard le 23 mars auront une date de paiement le 23 mars.
- Les factures qui sont dues le 24 mars auront une date de paiement le 24 mars.
- Les factures qui sont dues le 25 mars auront une date de paiement le 25 mars.
- Les factures qui sont dues le 26 mars auront une date de paiement le 26 mars.

### <a name="summarized-payment-date"></a>Date de paiement récapitulative

La date de paiement récapitulative n’est utilisée que lorsque le champ **Période** est défini sur **Total** pour le mode de paiement des factures. Si le champ **Période** est défini sur **Total** pour vos modes de paiement, vous devez définir l’option **Définir des critères de date de paiement récapitulative** sur **Oui**. Si l’option est définie sur **Oui**, utilisez le champ **Ajustement du nombre de jours pour la date de paiement récapitulative** pour définir la date de paiement récapitulative comme le nombre de jours spécifié avant ou après la date d’exécution du processus. Le nombre peut être positif, négatif ou nul (zéro). Par exemple, la série génère des paiements le mercredi et la société souhaite créer un paiement récapitulatif le mercredi. Dans ce cas, définissez le champ **Ajustement du nombre de jours pour la date de paiement récapitulative** sur **0**.

### <a name="records-to-include"></a>Enregistrements à inclure

Les options de filtrage peuvent toujours être définies pour la proposition de paiement. Si un filtre est défini, les critères de filtre ne sont pas affichés sur la page de l’assistant. Cependant, ils peuvent être visualisés en rouvrant le filtre.

Les autres champs de la proposition fonctionnent exactement comme ils le font pour la proposition de paiement dans le journal des paiements fournisseur. Pour plus d’informations sur les autres champs, voir [Création de paiements fournisseur via une proposition de paiement](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Certains champs spécifiques à un pays ou à une région et certains champs du secteur public ne sont pas encore disponibles dans les automatisations des propositions de paiement fournisseur.

Nous vous recommandons d’évaluer si l’automatisation sera bénéfique à votre organisation, en fonction de vos besoins.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Afficher les résultats d’une automatisation de proposition de paiement fournisseur

Une fois la série d’automatisations des propositions de paiement fournisseur créée, les occurrences de chaque paiement sont affichées dans la vue hebdomadaire de l’automatisation des processus. Pour les paiements fournisseur, la vue hebdomadaire d’automatisation des processus a été ajoutée à la fois à l’espace de travail **Paiements fournisseur** et **Automatisation des processus**.

[![Vue hebdomadaire de l’automatisation des processus dans l’espace de travail Paiements fournisseur](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

La vue hebdomadaire de l’automatisation des processus dans l’espace de travail **Paiements fournisseur** affiche uniquement les automatisations des propositions de paiement fournisseur. Elle affiche toutes les occurrences des paiements de la semaine en cours, pour toutes les entités juridiques pour lesquelles l’utilisateur connecté dispose d’autorisations de sécurité. Par exemple, si le commis aux paiements de la comptabilité fournisseur est responsable des paiements dans les sociétés USMF et USSI, il verra les occurrences des automatisations de proposition de paiement fournisseur pour ces deux sociétés, mais pas pour d’autres.

[![Vue hebdomadaire de l’automatisation des processus pour les sociétés USMF et USSI](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Chaque occurrence affiche la société dans laquelle le journal des paiements a été créé ou le sera. Si les paiements sont créés à l’aide de paiements centralisés, la société qui s’affiche est celle dans laquelle les paiements seront créés. L’occurrence ne montre pas nécessairement quelles factures de la société seront payées.

Le nom de chaque occurrence est également affiché pour aider à identifier la proposition de paiement.

De plus, l’état de chaque occurrence est affiché. Les statuts suivants sont utilisées :

- **Programmé** – La proposition de paiement est programmée, mais elle n’a pas encore été exécutée.
- **Erreur** – La proposition de paiement a été exécutée, mais une erreur s’est produite. Vous pouvez afficher les erreurs en sélectionnant le bouton **Afficher les résultats**.
- **Terminé** – La proposition de paiement a été exécutée avec succès. Vous pouvez afficher les paiements en sélectionnant le lien **Afficher les paiements**. Ce lien ouvre le journal des paiements créé par l’occurrence.

Une fois les paiements créés, vous pouvez afficher les montants des paiements dans le journal. Les montants sont indiqués dans les devises des transactions. Par exemple, si le journal des paiements contient des paiements en dollars américains et en dollars canadiens, le total des paiements pour chaque devise est affiché. 

Le journal des paiements peut être supprimé après sa création via l’automatisation du processus. Si un paiement est complètement supprimé, les événements suivants se produisent :

- Le statut de l’automatisation des processus pour la semaine reste **Terminé**.
- Le processus supprime les totaux des paiements et le lien **Afficher les paiements** est remplacé par un bouton **Afficher les résultats**.
- Lorsque vous affichez les résultats, vous recevez un message indiquant que le journal d’origine a été supprimé.

Après la suppression d’un paiement, les factures seront à nouveau ouvertes pour le paiement. Une nouvelle occurrence peut alors être créée pour payer à nouveau les factures.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Modifier l’automatisation des propositions de paiement fournisseur

Le cadre d’automatisation des processus vous permet de modifier le paiement, la série et les occurrences créées pour la proposition de paiement. La série peut être éditée à partir de la page **Automatisation des processus** ou de la vue hebdomadaire de l’automatisation des processus. Par exemple, si le responsable de la comptabilité fournisseur décide de générer tous les chèques pour les fournisseurs nationaux le mercredi au lieu du lundi, il peut rechercher une occurrence dans la vue hebdomadaire et sélectionner **Afficher/Modifier – Série**. Si vous modifiez une série, le système vous invite à spécifier si la modification doit être apportée à toutes les occurrences existantes ou uniquement aux nouvelles occurrences. Les occurrences historiques qui ont déjà le statut **Terminé**, ou qui ont about à un statut **Erreur** ne seront pas modifiées.

Vous pouvez également ajouter une nouvelle occurrence ou modifier une occurrence existante. Par exemple, la prochaine occurrence de proposition de paiement doit avoir lieu le mercredi 1er janvier, mais cette date est un jour férié. Vous pouvez modifier l’occurrence à partir de la vue hebdomadaire de l’automatisation des processus ou de la page **Automatisation des processus**. Une page s’ouvre qui affiche les détails de la programmation et critères des propositions de paiement. Ici, vous pouvez modifier l’heure et la date programmées. Vous pouvez également modifier les critères de proposition de paiement, si des modifications sont nécessaires. Par exemple, si vous modifiez la date programmée de l’occurrence de paiement du 1er janvier au 2 janvier, vous souhaiterez peut-être également modifier les dates relatives de la date de début.

Vous pouvez également désactiver une occurrence ou une série. Pour désactiver une occurrence et suspendre son traitement, sélectionnez-la dans la vue hebdomadaire de l’automatisation des processus, puis sélectionnez **Désactiver**. Vous pouvez désactiver une série sur la page **Automatisation des processus**.

## <a name="security-for-payment-proposal-automations"></a>Sécurité de l’automatisation des propositions de paiement

Les responsabilités et privilèges suivants ont été ajoutés pour les automatisations de proposition de paiement fournisseur. Ces responsabilités et privilèges sont les paramètres de sécurité par défaut, mais ils peuvent être modifiés en fonction des exigences de votre organisation. Par exemple, si non seulement le responsable de la comptabilité fournisseur, mais aussi le commis aux paiements sont capables de modifier et créer une périodicité programmée, affectez la responsabilité **Gérer les occurrences du programme** à la personne affectée au rôle de commis aux paiements de la compatibilité fournisseur.

| Responsabilité                              | Rôle                                                                       | Privilèges |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Gérer la série du programme          | Responsable Comptabilité fournisseur                                                   | Cette responsabilité accorde les droits de création et de gestion de la série et des occurrences d’automatisation des propositions de paiement et via les privilèges suivants :<ul><li>Gérer les occurrences du programme</li><li>Gérer la série du programme</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Afficher la vue hebdomadaire des occurrences</li></ul> |
| Rechercher des occurrences du programme | Commis au paiement de la comptabilité fournisseur, Commis au paiement centralisé de la comptabilité fournisseur | Cette responsabilité accorde les droits d’affichage des occurrences d’automatisation des propositions de paiement et via les privilèges suivants :<ul><li>Afficher les occurrences du programme</li><li>Afficher la vue hebdomadaire des occurrences</li></ul> |
| Rechercher des séries du programme      | None                                                                       | Cette responsabilité accorde les droits d’affichage des paramètres de la série et des occurrences via les privilèges suivants :<ul><li>Afficher les occurrences du programme</li><li>Afficher la page de liste des occurrences</li><li>Afficher la vue hebdomadaire des occurrences</li></ul>|
| Gérer les occurrences du programme     | None                                                                       | Cette responsabilité accorde les droits de création et de gestion d’une occurrence via les privilèges suivants :<ul><li>Gérer les occurrences du programme</li><li>Afficher la vue hebdomadaire des occurrences</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]