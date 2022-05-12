---
title: Paramètres de facturation de contrat récurrent
description: Cette rubrique explique comment configurer les valeurs par défaut pour les échéanciers de facturation créés dans Facturation de contrat récurrent. Il explique également comment créer des groupes d’échéanciers de facturation.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4c52095aa49962cbfc577faf71ab0d71929a386b
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629409"
---
# <a name="recurring-contract-billing-parameters"></a>Paramètres de facturation de contrat récurrent

Utilisez la page **Paramètres de facturation des contrats récurrents** pour configurer les valeurs par défaut des échéanciers de facturation qui sont créés dans Facturation des contrats récurrents. Tous les échéanciers de facturation que vous créez utiliseront initialement ces valeurs par défaut. Cependant, vous pouvez modifier les valeurs de chaque échéanciers de facturation selon vos besoins.

## <a name="general-tab"></a>Onglet Général

1. Sur la page **Paramètres de facturation des contrats récurrents**, sur l’onglet **Général**, dans le champ **Groupe d’échéancier de facturation**, sélectionnez un groupe d’échéanciers de facturation. Pour plus d’informations sur la configuration des groupes d’échéanciers de facturation, consultez la section [Groupes d’échéanciers de facturation](#set-up-billing-schedule-groups) plus tard dans cette rubrique.
2. Dans le champ **Type de résiliation**, sélectionnez le mode de calcul de la facture finale quand un échéancier de facturation est résilié :

    - **Ajuster l’échéancier** – Coupez l’échéanciers de facturation à la date de résiliation, changez le statut de l’échéancier en **Dernière facturation**, et ajustez l’échéancier de report associé en contrepassant le montant qui ne doit plus être reconnu. Si la date de début de facturation est postérieure à la date de fin, les périodes de facturation restantes sont supprimées.
    - **Facture restante** – Ajoute tout montant restant de l’échéanciers de facturation à la période de résiliation et change le statut de l’échéancier en **Dernière facturation** et met à jour l’échéancier de report. Si la date de début de facturation est postérieure à la date de fin, le montant total de toutes les périodes de facturation restantes est ajouté à la période de facturation et les périodes de facturation restantes sont supprimées.
    - **Aucun ajustement** – Résilie l’échéanciers de facturation à la date de résiliation. Aucun ajustement n’est apporté à l’échéanciers de facturation.

3. Dans le champ **Type d’échéanciers unique**, sélectionnez **Aucun** pour préciser que les clients sont limités à un seul échéanciers de facturation. Sélectionnez **Par client** ou **Par utilisateur final** pour spécifier que les clients sont limités à un échéanciers unique.
4. Définissez l’option **Aligner au mois** sur **Oui** pour aligner les lignes de détail de l’échéancier de facturation sur la fin d’un mois, quand un échéanciers de facturation est créé ou mis à jour. Réglez-le sur **Non** pour utiliser des dates incrémentielles.
5. Met l’option **Prorata des périodes partielles** sur **Oui** pour répartir les montants de facturation en fonction du nombre de jours de la période. Réglez-le sur **Non** pour avoir un montant égal à chaque période de facturation, quel que soit le nombre de jours.
6. Si vous réglez l’option **Prorata des périodes partielles** sur **Oui**, met le champ **Méthode de prorata** sur **Quotidien** pour répartir les montants en fonction du nombre de jours de la période. Réglez-le sur **Mensuel** avoir un montant égal chaque mois.
7. Spécifiez si les échéanciers de facturation créés sont suspendus par défaut.

    > [!NOTE]
    > Pour supprimer la suspension d’un échéanciers de facturation, l’utilisateur doit faire partie d’un groupe d’utilisateurs. Sélectionner **Supprimer le remplacement du groupe d’utilisateurs en attente** pour créer un groupe d’utilisateurs où **Autoriser la suppression de la suspension** est activée.

8. Dans le champ **Type de transaction de facture**, sélectionnez le type de transaction de facture par défaut pour les nouveaux échéanciers de facturation.
9. Met l’option **Aligner le report sur la facturation** sur **Oui** pour aligner l’échéancier de report correspondant afin qu’il utilise les mêmes dates que l’échéanciers de facturation. Réglez-le sur **Non** pour avoir différentes dates.
10. Si vous utilisez la fonctionnalité de fractionnement de produit, définissez l’option **Créer automatiquement un fractionnement de produit** sur **Oui** quand des éléments sont ajoutés à un échéanciers de facturation. La case **Fractionnement de produit** sera automatiquement cochée sur la ligne de l’échéancier de facturation si l’article est configuré en tant qu’article de fractionnement de produit. Définissez l’option sur **Non** si vous voulez cocher manuellement la case **Fractionnement de produit**.
11. Définissez les champs pour la création de la commande client :

    - Les factures peuvent être consolidées par période, client ou article. Toute combinaison de valeurs **Oui** et **Non** peuvent être définies. Les factures peuvent également être fractionnées par groupe d’articles.
    - Les options de comptabilisation suivantes sont disponibles pour les factures :

        - **Créer une commande client** – Créer la commande client uniquement.
        - **Afficher la validation de la facture** – Facturez la commande client et ouvrez une page où vous pouvez valider manuellement la facture.
        - **Créer une facture financière** – Sélectionnez cette option si vous utilisez des factures financières.
        - **Publier la facture automatiquement** – Facturez la commande client et enregistrez-la automatiquement.

    - Met l’option **Ajouter des dates de facturation à la description de l’article** sur **Oui** pour ajouter une description incluant la date de début et la date de fin de facturation.
    - Met l’option **Exclure la consommation zéro** sur **Oui** pour exclure les lignes d’échéancier de facturation qui n’ont pas de consommation. Réglez-le sur **Non** pour inclure ces lignes dans la commande client.
    - Met l’option **Ne pas imprimer les éléments enfants** sur **Oui** si vous ne souhaitez pas imprimer les articles enfants d’une répartition de produit sur la commande client. Seul l’article parent s’affichera sur la facture. Si le montant net des articles enfants (cachés) est une somme non nulle, le montant net de la ligne parent affiche un résumé des lignes enfants. Définissez l’option sur **Non** pour imprimer tous les articles enfants sous l’article parent sur la facture client.

12. Définissez les champs pour le support et les renouvellements :

    - Met l’option **Activer automatiquement le support et le renouvellement** sur **Oui** pour utiliser automatiquement la fonction de support et de renouvellement sur une commande client.
    - Dans le champ **Niveau de support et de renouvellement**, sélectionnez le niveau de support et de renouvellement par défaut.
    - Dans le champ **Quantité de support et de renouvellement**, spécifiez la quantité de support et de renouvellement par défaut.
    - Dans le champ **Assistance par défaut et date de début du renouvellement**, spécifiez la date à utiliser comme date de début par défaut pour le support et les renouvellements :

        - **Date de transaction** : utilisez la date de la transaction comme date de début.
        - **Début du mois en cours** : utilisez le premier du mois en cours comme date de début.
        - **Début du mois suivant** : utilisez le premier du mois suivant comme date de début. Si la date de la transaction est le 1er, le premier jour du mois en cours est utilisé.
        - **Règle de 15**– Utilisez le premier du mois en cours comme date de début si la date de transaction se situe entre le premier et le quinze. Si la date de transaction est entre le seize et la fin du mois, utilisez le premier du mois suivant comme date de début.

    - Met l’option **Inclure la remise dans le calcul** sur **Oui** pour inclure le montant de la réduction dans le montant du support ou du renouvellement. Réglez-le sur **Non** pour exclure le montant de la remise.
    - Dans les champs **Périodicité de support** et **Périodicité de renouvellement**, sélectionnez la périodicité à utiliser quand des articles de support et de renouvellement sont ajoutés à un échéanciers de facturation : **Quotidien**, **Mensuel**, **Trimestriel**, **Semestriel** ou **Annuellement**.
    - Met l’option **Aligner par groupe d’articles** sur **Oui** pour aligner les dates de début et de fin des nouveaux articles sur les articles existants, en fonction du groupe d’articles.
    - Met l’option **Aligner sur la prochaine période non facturée** sur **Oui** pour déterminer la date d’alignement d’un article de renouvellement en fonction de la date de la prochaine période non facturée après le début du renouvellement.
    - Met l’option **Copier le numéro de série** sur **Oui** pour copier le numéro de série de l’article de la ligne de commande client initiale vers la ligne d’échéancier de facturation correspondante.

13. Si vous utilisez l’escalade sur l’échéanciers de facturation, sélectionnez la méthode utilisée pour le calcul de l’indice des prix à la consommation.
14. Met l’option **Suivre l’évolution des prix** sur **Oui** si vous souhaitez un enregistrement des modifications de prix sur les lignes de l’échéancier de facturation. Si une ligne d’échéancier de facturation est modifiée manuellement de standard à forfaitaire et qu’un nouveau prix est entré, les informations d’audit sont suivies sur la ligne d’échéancier de facturation. Définissez l’option sur **Non** si vous ne souhaitez pas suivre ces changements.
15. Spécifiez si les enregistrements sont filtrés par date de début ou date de fin par défaut sur la page **Générer une facture**.
16. Si vous utilisez la méthode **Produit non facturé**, spécifiez les options utilisées :

    - Met l’option **Comptabiliser automatiquement le journal des opérations diverses** sur **Oui** si vous souhaitez que le journal des opérations diverses soit créé et comptabilisé en même temps. Réglez-le sur **Non** si vous souhaitez créer le journal des opérations diverses, puis le comptabiliser manuellement.
    - Dans le champ **Nom du journal par défaut**, sélectionnez le nom du journal par défaut à utiliser à la création du journal des opérations diverses.
    - Dans le champ **Méthode non facturée à court terme**, sélectionnez la méthode non facturée à court terme, si vous en utilisez. Si vous sélectionnez **Aucun**, la fonctionnalité à court terme ne sera pas utilisée avec le produit non facturé. Sélectionner **Périodes glissantes** pour toujours utiliser 12 mois ou **Année fixe** d’utiliser l’exercice restant.

17. Spécifiez les options utilisées quand un échéancier de facturation et ses lignes sont résiliés :

    - **Émettre un avoir** – Crée un avoir quand un calendrier de facturation ou une ligne de calendrier de facturation est résiliée.
    - **Ajustement de crédit** – Crée un ajustement de crédit pour un calendrier de facturation quand une ligne est résiliée. L’ajustement de crédit apparaît dans une période de facturation future pour le calendrier de facturation. L’ajustement de crédit mettra à jour également le montant de la facture pour la période de facturation suivante jusqu’à ce que le crédit ait fini d’être appliqué à l’échéanciers de facturation.
    - **Aucun avoir** – Ne crée pas un ajustement de crédit ni un avoir quand un calendrier de facturation ou une ligne de calendrier de facturation est résiliée. Cette option est disponible uniquement quand vous utilisez l’option **Aucun ajustement** pour résilier un échéanciers de facturation.

## <a name="sequence-number-tab"></a>Onglet Souches de N°

Utilisez l’onglet **Souche de N°** sur les **Paramètres de facturation des contrats récurrents** pour définir la valeur par défaut des numéros de l’échéanciers de facturation. Les valeurs par défaut sont configurées sur les pages **Souches de N°** (**Administration de l’organisation \> Souches de N° \> Souches de N°**).

## <a name="set-up-billing-schedule-groups"></a>Paramétrer des groupes d’échéanciers de facturation

Utilisez la page **Groupe d’échéancier de facturation** pour créer un groupe d’échéanciers de facturation pour la facturation des contrats récurrents. Quand un échéancier de facturation est créé et qu’un groupe d’échéanciers de facturation lui est appliqué, les valeurs définies sur la page **Groupe d’échéancier de facturation** sont entrées comme valeurs par défaut pour l’échéanciers de facturation. Vous pouvez modifier n’importe laquelle des valeurs par défaut pour l’échéanciers de facturation spécifique que vous créez. Vous pouvez configurer plusieurs groupes d’échéanciers de facturation, puis affecter l’un d’eux comme groupe d’échéanciers de facturation par défaut sur la page **Paramètres de facturation des contrats récurrents**.

Pour créer un groupe d’échéanciers de facturation pour la facturation de contrat récurrent, procédez comme suit.

1. Sur la page **Groupe d’échéanciers de facturation**, sélectionnez **Nouveau** pour créer un groupe d’échéanciers de facturation.
2. Dans le champ **Groupe d’échéanciers de facturation**, entrez un identificateur unique pour le groupe de fournisseurs.
3. Entrez une description dans le champ **Description**.
4. Dans le champ **Périodicité de facturation**, spécifiez la périodicité à laquelle l’échéanciers de facturation est facturé à un client : **Une fois**, **Quotidien**, **Mensuel**, **Trimestriel**, **Semestriel** ou **Annuellement**.
5. Dans le champ **Intervalle de facturation**, entrez un intervalle de facturation. Par exemple, définissez le champ **périodicité de facturation** sur **Mensuel** et le champ **Intervalle de facturation** sur **2** à facturer tous les deux mois.
6. Dans le champ **Méthode de tarification**, sélectionnez la méthode de tarification par défaut pour les articles sur l’échéanciers de facturation.

    - **Standard** – Calculez le prix unitaire en fonction de la quantité totale saisie et utilisez le prix standard de la page **Produits lancés** dans Gestion des informations produit.
    - **Fixe** – Appliquer un prix forfaitaire qui est renseigné sur la ligne de l’échéancier de facturation.
    - **Niveau** – Calculer le prix unitaire en utilisant une quantité fixe à différentes fourchettes de prix. Chaque niveau doit être rempli avant de passer à la tranche de prix suivante.
    - **Forfaitaire** – Calculer le prix unitaire en utilisant une quantité fixe et des montants de prix global pour différentes fourchettes de prix. Le prix facturé dans une période de facturation utilise le prix global qui correspond au niveau où la quantité de facturation existe.

7. Dans le champ **Type d’article**, sélectionnez le type d’article pour le groupe de facturation :

    - **Standard** – Sélectionnez cette valeur si la quantité est statique.
    - **Utilisation** – Sélectionnez cette valeur pour les articles au compteur ou de type consommation. Si vous sélectionnez cette valeur, définissez le champ **Option de lecture d’utilisation** sur **Lecture** pour saisir la valeur (lecture) d’une période de facturation sur un compteur ou un appareil. La valeur consommée sera calculée en fonction de la période de facturation précédente et de la lecture actuelle que vous entrez.
    - **Jalon** – Sélectionnez cette valeur pour utiliser la fonctionnalité de facturation jalonnée. Si vous sélectionnez cette valeur, dans le champ **Modèle de jalon**, sélectionnez le modèle de jalon si vous en utilisez.
    - **Consommation** – Sélectionnez cette valeur pour saisir la valeur consommée pour une période de facturation.

8. Met l’option **Facturer séparément** sur **Oui** pour créer une combinaison de factures consolidées et de factures distinctes pour le même client. Par exemple, un client a cinq échéanciers de facturation. Trois d’entre eux seront regroupés sur une seule facture, mais chacun des deux autres nécessite une facture distincte. Définissez l’option sur **Non** pour créer une seule facture consolidée pour le client.
9. Pour renouveler automatiquement un échéanciers de facturation pour la prochaine période de facturation quand la facture est créée, définissez l’option **Renouveler automatiquement** sur **Oui**. Définissez-la sur **Non** pour renouveler manuellement l’échéanciers de facturation. Dans le champ **Lignes à ajouter par renouvellement**, spécifiez le nombre de lignes à ajouter pour chaque renouvellement.
10. Met l’option **Escalade** sur **Oui** pour appliquer *escalades* (augmentations de prix) aux échéanciers de facturation associés à ce groupe d’échéanciers de facturation.
