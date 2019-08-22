---
title: Paramètres de gestion des dépenses
description: Les paramètres suivants contrôlent le comportement dans Gestion des dépenses.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c1bc754b92e647f0fdac6799564273fb6ea6fb20
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841079"
---
# <a name="expense-management-parameters"></a>Paramètres de gestion des dépenses

[!include [banner](../includes/banner.md)]

-----------------------------

Les paramètres contrôlent le comportement général dans Gestion des dépenses.

### <a name="general"></a>Général

| **Champ**                                                | **Description**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Taux standard de kilométrage**                             | Entrez le taux de remboursement pour les dépenses kilométriques. Le taux est multiplié par le kilométrage entré dans la dépense pour calculer le montant remboursé pour les frais de déplacement.                       |
|**Dépenses personnelles payées par**                             | Sélectionnez le responsable du paiement de tous les montants de transaction par carte de crédit catégorisés comme personnels.                                                                                                     |
|**Afficher l'état de dépenses intégral lors d'un zoom**               | Sélectionnez cette option pour afficher toutes les dépenses pour un état de dépenses en affichant les détails du document d'origine pour un N° document spécifique qui a été généré lorsque l'état des dépenses a été validé.              |
|**Pré-autorisation de voyage est obligatoire**                 | Sélectionnez cette option pour exiger l'envoi et l'approbation d'une demande de déplacement avant que l'employé ne puisse envoyer un état de dépenses.                                                                    |
|**Autoriser la modification des distributions avant validation**            | Sélectionnez si les répartitions d'un état des dépenses peuvent être modifiées avant la validation.                                                                                                                 |
|**Évaluer les stratégies de gestion des dépenses**                     | Sélectionnez le moment les dépenses sont évaluées pour déterminer si une stratégie des dépenses n'a pas été respectée. Les dépenses peuvent être vérifiées pour les violations lorsque la saisie de dépenses est entrée et enregistrée ou lorsque la dépense est soumise pour approbation. Les règles de stratégie pour les réceptions requises sont vérifiées lorsque la ligne de dépense est enregistrée.                   |
|**Autoriser les lignes de dépense intersociétés**                         | Sélectionnez si la saisie des dépenses pour d'autres entités juridiques dans un état de dépenses est autorisée.                                                                                                          |
|**Autoriser la modification du taux de change pour les dépenses de carte de crédit** | Sélectionnez cette option pour permettre à l'utilisateur de modifier le taux de change des dépenses importées de carte de crédit.                                                                        |
|**Champs de hiérarchie multiniveau à afficher**                  | Sélectionnez les champs d'approbateur pour afficher à quel moment le type d'affectation de workflow d'état de dépenses est défini comme étant hiérarchique et la sélection de hiérarchie est définie pour utiliser la hiérarchie multiniveau d'approbation des dépenses. Lorsque la hiérarchie multiniveau d'approbation est utilisée pour le workflow, les champs sélectionnés sont affichés et modifiables dans l'état de dépenses. |
|**Entrer le numéro de carte de crédit de l'employé (mise à jour de juillet 2017)**     | Sélectionnez si un numéro de 15 ou 16 caractères maximum peut être entré et enregistré dans le champ **ID carte** de la page **Cartes de crédit** d'un employé.                                                                          |

### <a name="financial"></a>Rapport financier

| **Champ**                                                            | **Description**     |
|----------------------------------------------------------------------|------------------------------------|
|**Nom de journal comptable**                                         | Sélectionnez le nom du journal comptable dans lequel valider les états de dépenses approuvés.            |
|**Activer le recouvrement fiscal pour les dépenses**                                  | Sélectionnez cette option pour autoriser le recouvrement fiscal de dépense pour les dépenses admissibles. Cette option ne peut pas être activée si les taxes et règles de taxe d'utilisation des États-Unis sont activées.      |
|**Valider immédiatement des avances de disponibilités**                                     | Sélectionnez cette option pour valider une avance de disponibilités approuvée lorsque le processus de paiement et de transfert est terminé. Si cette option n'est pas activée, le processus de paiement et de transfert génère un journal des opérations diverses non validées. |
|**Date comptable correcte durant la validation**                             | Sélectionnez cette option pour mettre à jour la date comptable lors de la validation des dépenses si la période actuelle est en attente ou clôturée. La date comptable est définie sur la période en cours suivante.   |
|**Autoriser le regroupement des transactions basées sur un compte de contrepartie spécifié dans la méthode de paiement**      | Sélectionnez cette option pour récapituler les transactions de dépenses d'un état de dépenses, selon le compte de contrepartie spécifié dans le mode de paiement pour les dépenses.   
|**Taxe incluse**                                                   | Sélectionnez cette option pour inclure la taxe dans le montant des dépenses par défaut.             |
|**Débloquer les engagements à la clôture des demandes de voyage**            | Sélectionnez cette option pour libérer des fonds engagés lors de la clôture d'une demande de voyage approuvée.                                                                                   |
|**Autoriser l'approbation de demandes de voyage sur le dépassement de budget pour le registre budgétaire et le budget de projet** | Sélectionnez cette option pour autoriser les employés à envoyer des demandes de voyage pour approbation dépassant le budget alloué défini dans le registre budgétaire ou pour un projet.            |
|**Autoriser la soumission des états de dépenses sur le dépassement de budget pour le registre budgétaire et le budget de projet**    | Sélectionnez cette option pour autoriser les employés à envoyer des états de dépenses pour approbation dépassant le budget alloué défini dans le registre budgétaire ou pour un projet.                |
|**Autoriser l'approbation des états de dépenses sur le dépassement de budget pour le registre budgétaire uniquement**                | Sélectionnez cette option pour autoriser les approbateurs à approuver des états de dépenses dépassant uniquement le budget alloué défini dans le registre budgétaire.                                                                       |

### <a name="per-diem"></a>Indemnité journalière

| **Champ**                             | **Description**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Heures minimales pour l'indemnité journalière**           | Permet d'entrer le nombre d'heures minimal par défaut pendant lequel un employé doit travailler chaque jour afin de bénéficier d'une indemnité journalière pour les dépenses liées à un déplacement.  Cette valeur est utilisée uniquement comme valeur par défaut pour le champ Heures minimales des niveaux d'indemnités journalières.                                                                                      |
|**Pourcentage de repas**                          | Entrez le pourcentage par défaut des indemnités journalières pour les repas utilisé pour les premier et dernier jours de la dépense liée au déplacement lorsque le champ **Calculer la réduction de repas par** est défini sur **Type de repas par jour** ou **Nombre de repas par jour**. Le jour de travail des premier et dernier jours peut être plus court que le jour de travail standard. C'est pourquoi, le montant des indemnités journalières de ces jours peut différer du montant standard. Si le pourcentage est défini sur 0, les déductions du premier et du dernier jour sera de 0,00. |
|**Pourcentage d'hébergement**                        | Permet d'entrer le pourcentage par défaut des indemnités journalières pour les hôtels utilisé pour les premier et dernier jours de la dépense liée au déplacement. Le jour de travail des premier et dernier jours peut être plus court que le jour de travail standard. C'est pourquoi, le montant des indemnités journalières de ces jours peut différer du montant standard. Si le pourcentage est défini sur 0, les déductions du premier et du dernier jour sera de 0,00.                                              |
|**Autres pourcentages**                        | Permet d'entrer le pourcentage par défaut des indemnités journalières pour les dépenses diverses utilisé pour les premier et dernier jours de la dépense liée au déplacement. Le jour de travail des premier et dernier jours peut être plus court que le jour de travail standard. C'est pourquoi, le montant des indemnités journalières de ces jours peut différer du montant standard. Si le pourcentage est défini sur 0, les déductions du premier et du dernier jour sera de 0,00.                                                                                                     |
|**Réduction du pourcentage pour le petit-déjeuner** | Permet d'entrer le montant déduit de l'indemnité journalière pour le petit-déjeuner. Par exemple, si un employé reçoit un petit-déjeuner gratuit, vous pouvez réduire le montant de l'indemnité journalière de 10 %.                               |
|**Réduction du pourcentage pour le déjeuner**    | Permet d'entrer le montant déduit de l'indemnité journalière pour le déjeuner. Par exemple, si un employé reçoit un déjeuner gratuit, vous pouvez réduire le montant de l'indemnité journalière de 15 %.                                       |
|**Réduction du pourcentage pour le dîner**   | Permet d'entrer le montant déduit de l'indemnité journalière pour le dîner. Par exemple, si un employé reçoit un dîner gratuit, vous pouvez réduire le montant de l'indemnité journalière de 25 %.                                     |
|**Calculer la réduction de repas par**         | Permet d'indiquer comment le système doit calculer l'indemnité journalière de réduction des frais de restauration en sélectionnant si la réduction est basée sur le type de repas par déplacement ou par jour, ou si la réduction est basée sur le nombre de repas autorisé par jour.|
|**Arrondi des indemnités journalières**                  | Permet de sélectionner le type d'arrondi utilisé pour les dépenses d'indemnités journalières. Si vous sélectionnez un arrondi normal, les dépenses d'indemnités journalières égales à 0,50 sont arrondies à 1,00 et les dépenses d'indemnités journalières inférieures à 0,50 sont arrondies à 0,00.                                                                                              |
|**Baser le calcul par jour sur**         | Permet d'indiquer si le montant des indemnités journalières est basé sur un jour civil ou une période de 24 heures.       |

### <a name="fax-cover-pages"></a>Faxer les pages de garde

| **Champ**                      | **Description**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Instructions**                   | Permet d'entrer les instructions que les employés doivent suivre lorsqu'ils créent une page de garde pour une télécopie servant à envoyer des reçus en relation avec un état de dépenses. Cliquez sur le bouton **Traductions** pour entrer un texte spécifique à une langue qui sera affiché en fonction de la langue d'utilisateur. |
|**ID utilisateur (informations du code-barres)** | Sélectionnez cette option pour stocker l'identificateur unique d'un employé dans le code-barres utilisé sur la page de garde de la télécopie.                 |
|**Code-barres**                      | Permet de sélectionner le code-barres utilisé sur la page de garde de la télécopie. Les codes-barres 39 et 128 sont pris en charge avec la gestion des dépenses.               |

### <a name="anti-corruption"></a>Anticorruption

|                 <strong>Champ</strong>                 |                                                                                                                                                                                            <strong>Description</strong>                                                                                                                                                                                             |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Afficher l'attestation anticorruption</strong>  | Sélectionnez cette option pour afficher le texte anti-corruption en créant un état de dépenses. Des catégories de dépenses spécifiques peuvent ensuite être activées qui nécessitent l'attestation anticorruption à sélectionner dans l'état de dépenses. Par exemple, une catégorie de cadeau associée à une dépense officielle du gouvernement peut nécessiter de l'employé qu'il confirme que la dépense respecte la stratégie de la société liée aux fonctionnaires gouvernementaux. |
| <strong>Message anticorruption pour l'auteur de l'envoi</strong> |                                                                                             Entrez le texte qui sera affiché à l'employé lorsque vous créez un état de dépenses. Cliquez sur le bouton <strong>Traductions</strong> pour entrer un texte spécifique à une langue qui sera affiché en fonction de la langue d'utilisateur.                                                                                             |
| <strong>Message anticorruption pour l'approbateur</strong>  |                                                                                             Entrez le texte qui sera affiché à l'approbateur lorsque vous créez un état de dépenses. Cliquez sur le bouton <strong>Traductions</strong> pour entrer un texte spécifique à une langue qui sera affiché en fonction de la langue d'utilisateur.                                                                                             |

