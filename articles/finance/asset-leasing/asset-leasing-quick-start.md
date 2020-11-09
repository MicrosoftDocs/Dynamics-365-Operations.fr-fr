---
title: Démarrer la location d'actifs
description: Cette rubrique décrit la fonctionnalité de location d'actifs, et décrit les étapes de création d'un bail d’immobilisation et l'affichage des informations relatives à ces baux.
author: moaamer
manager: Ann Beebe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9e206569aad3f53a2f6f66e6d6253226e5980078
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022565"
---
# <a name="asset-leasing-get-started"></a>Démarrer la location d'actifs

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité de location d'actifs, et décrit les étapes de création d'un bail d’immobilisation et l'affichage des informations relatives à ces baux. La rubrique définit également la terminologie utilisée dans l'interface utilisateur et la documentation. La location d'actifs est une fonctionnalité avancée de gestion, de suivi et d'automatisation des transactions financières pour les actifs loués dans Microsoft Dynamics 365 Finance. La fonctionnalité de location d'actifs est conforme aux normes comptables internationales (IFRS 16) et aux normes US GAAP (ASC 842). La fonctionnalité de location d'actifs capture et traite les informations sur les baux et contribue à générer les écritures de journal tout au long du cycle de vie du bail, de la comptabilisation initiale aux écritures de journal mensuelles jusqu'à la dépréciation et la résiliation du bail. La fonctionnalité de location d'actifs s'intègre parfaitement aux autres composants de Dynamics 365 Finance, notamment les immobilisations, les comptes fournisseurs et la comptabilité.

Pour plus d'informations sur les normes comptables, reportez-vous à la documentation standard relative aux normes IFRS 16 et US GAAP ASC 842.

## <a name="asset-leasing-elements"></a>Éléments de location d'actifs
Le diagramme suivant illustre les principaux éléments du processus métier pour les baux.

[![Éléments de location d'actifs](./media/overview-01.png)](./media/overview-01.png)

Un actif loué contient les principaux composants suivants :

- **Contrat de bail** - Le bailleur est propriétaire de l'actif et convient avec le locataire de louer un actif pour une période déterminée en échange de paiements de location périodiques. En plus du contrat légal entre le bailleur et le locataire, le contrat de location comprend les décisions de gestion telles que la probabilité d'exercer une option de renouvellement et le transfert de propriété.

- **Calcul et classement du bail conformément à la législation comptable** - Le calcul et la classification des baux identifient la législation comptable qui sera appliquée lors de l'évaluation initiale et ultérieure, ainsi que le test de classification qui détermine le type de bail. Un bail peut être un contrat de location-financement, un contrat de location simple, un bail à court terme ou un bail de faible valeur. Le système calcule également la valeur actuelle des futurs paiements de location minimum à des fins d'évaluation et de classification.

- **Transactions de bail** - La location d'actifs prend en charge la comptabilisation initiale du droit d'utilisation de l'actif pour les baux sur bilan, ainsi que l'évaluation ultérieure pour les baux sur bilan ou hors bilan. La transaction de comptabilisation initiale mesure la valeur actuelle des futurs paiements de location minimum. Ces données sont utilisées pour déterminer la valeur du droit d'utilisation de l'actif initial et du passif locatif, qui affectent le bilan de l'organisation. L'évaluation ultérieure des transactions de bail mensuelles implique l'accumulation d'intérêts sur le passif locatif, ce qui augmente le passif locatif. Elle mesure également l'accumulation des paiements de location qui diminuent le passif locatif, et qui seront par la suite payés au bailleur. L'évaluation comprend également l'amortissement du droit d'utilisation de l'actif.

  Pour les baux hors bilan, le système calcule les frais de bail linéaires sur la valeur la moins élevée : la durée de vie économique de l'actif ou la durée du bail. Les ajustements de bail mesurent les modifications de contrat telles qu'une prolongation ou une extension du bail, et la transaction de dépréciation qui utilise le droit d'utilisation de l'actif pour des coûts non récupérables.

  La location d'actifs s'intègre à la comptabilité pour garantir que toutes les transactions de bail validées mettent à jour votre plan comptable. La location d'actifs s'intègre à la comptabilité fournisseur pour suivre les factures du bailleur dans la comptabilité fournisseur et en déduire les paiements futurs. L'intégration avec les immobilisations vous permet de suivre les baux dans le registre des immobilisations et de valider les transactions du droit d'utilisation de l'actif, y compris la comptabilisation initiale, l'amortissement et la dépréciation de l'actif, à partir des immobilisations.   

## <a name="asset-leasing-components"></a>Composants de la location d'actifs 
La location d'actifs met en correspondance les informations des baux, les échéanciers de paiement, les dates de début et de fin et la fréquence de paiement. Elle automatise également les calculs de la valeur actuelle, des paiements de location mensuels, des intérêts et de l'amortissement de la location. Le système effectue des tests de classification des baux, en fonction de la configuration. Le système crée et valide également les transactions de bail correspondantes, qui sont basées sur le cadre défini par la norme comptable que vous suivez.

Le diagramme suivant illustre le registre des baux, le bail, l'échéancier de paiement calculé, les tests de classification des baux et des registres des baux et les transactions comptables correspondantes.

[![Location, registre des baux et échéancier de paiement](./media/overview-02.png)](./media/overview-02.png)

- **Registre des baux** - Le registre des baux comprend toutes les informations relatives au contrat d'un bail, comme la durée du bail, la juste valeur et les paiements de location. Il comprend également la norme comptable que vous suivez, le type de bail et les seuils pris en compte dans le test de classification des baux. Le registre des baux contient également les transactions de bail qui ont été validées dans la comptabilité. 
  
- **Bail** - Le bail contient les informations relatives au bail des actifs qui représentent la base de la location d'actifs. La source des informations relatives au bail est le contrat de bail et la décision de gestion, qui ont lieu en dehors de Dynamics 365 Finance. La juste valeur de l'actif est le prix qui serait payé pour un actif lors d'une transaction à la date d'évaluation. Cette valeur peut dépendre du type d'actif, des conditions du marché et d'autres critères pouvant être pris en considération dans l'évaluation. La juste valeur de l'actif sera prise en compte dans l'équation du test de classification.

- **Durée de vie utile des actifs** - Cette durée représente les périodes restantes de la durée de vie utile d'un actif, à compter de la date de début du bail. La durée de vie utile d'un actif sera prise en compte dans l'équation du test de classification. Elle diffère de la durée de vie utile telle que définie dans les immobilisations.

- **Taux d'emprunt marginal** - Il s'agit du taux d'intérêt qui sera utilisé pour calculer la valeur actuelle. Le système utilisera le taux implicite s'il est défini dans les données de bail pour calculer la valeur actuelle des paiements de location. Si le taux implicite n'est pas défini, le système utilisera le taux d'emprunt marginal.

- **Type de rente** - Il s'agit du paiement de location dû soit au début de la période de paiement, soit à la fin de la période. Il peut s'agir d'un paiement anticipé ou d'une rente due (au début de la période de paiement de location), ou d'une rente ordinaire (à la fin de la période de paiement de location).

  Le premier mois sera considéré comme la période numéro zéro pour le paiement à l'avance ; le premier mois sera considéré comme la période un pour les arriérés de paiement.

- **Intervalle de composition** - Représente le nombre de périodes pendant lesquelles les intérêts sont cumulés par an. Il peut être mensuel (12 périodes par an), trimestriel (4 périodes par an), semestriel (2 périodes par an) ou annuel (1 période par an). Le nombre de périodes sera pris en compte dans le calcul de la valeur actuelle.

- **Date de début** - Il s'agit de la date à laquelle le bailleur met l'actif à disposition du locataire. Tous les calculs et transactions du bail seront basés sur la date de début. Pour garantir l'exactitude des calculs ultérieurs, la date de début doit être au début d'une période (le premier du mois). Vous pouvez utiliser le champ **Date de signature du contrat** pour saisir la date réelle de signature du contrat.

- **Durée du bail** - Il s'agit de la durée de la période du bail, en mois.

> [!NOTE] 
> La définition de la durée du bail est basée sur le nombre de périodes, ou d'intervalles, dans les lignes de l'échéancier de paiement. Le nombre d'intervalles défini sera converti en mois.

- **Ligne d'échéancier de paiement** - Capture les paiements de location par période. Il précise également si une période de renouvellement sera exercée et incluse dans l'évaluation initiale de droit d'utilisation de l'actif et du passif locatif. Vous pouvez définir la date de début des paiements de location dus et les intervalles de période qui représentent la durée du bail, en jours, mois ou années.

- **Fréquence de paiement** - Indique si le paiement est mensuel, trimestriel, semestriel ou annuel. La date de fin est calculée automatiquement en fonction de la date de début et du nombre de périodes saisies.

- **Échéancier de paiement** - Valeur actuelle calculée, basée sur la durée couverte par les paiements de location, le montant des paiements, les périodes de composition et le type de rente.

- **Périodes** - Périodes de location qui reflètent le type de composition interne et de rente. L'intervalle de composition détermine comment les périodes seront divisées. Vous pouvez définir les intervalles de composition suivants :

  - Mensuel, 12 périodes par an
  - Trimestriel, 4 périodes par an
  - Semestriel, 2 périodes par an
  - Annuel, 1 période par an

La première période commencera avec la période zéro, si le type de rente est Rente due. Sinon, la première période commencera avec la période un, si le type de rente est Arriérés de paiement.

- **Mois** - Indique le nombre de mois calendaires sur la durée du bail. Le montant du paiement est le montant dû tel que défini dans la fréquence de paiement. La valeur actuelle calculée est le paiement de location basé sur la valeur actuel par période, les intervalles de composition et le taux d'emprunt marginal.

> [!NOTE] 
> La valeur actuelle est calculée en fonction de l'équation des flux de trésorerie avec remise.

- **Registres** - Il s'agit de la configuration préconfigurée qui sera associée à chaque bail. Le registre définit la norme comptable appliquée, les types de bail et le seuil utilisé comme base pour les tests de classification. Les tests de classification sont utilisés pour spécifier automatiquement le type de bail.

- **Cadre comptable** - Affiche la norme comptable sélectionnée, soit IFRS 16 et ASC 842, que vous prenez en charge. La norme comptable est indiquée sur le registre associé au bail. La norme comptable déterminera les comptes généraux spécifiés dans le profil de validation.

- **Types de bail** Indique lequel des deux types de contrats de bail sera utilisé, soit un contrat de location-financement soit un contrat de location simple. Dans le cadre d'un contrat de location-financement, les risques et avantages liés à l'actif loué sont transférés au locataire. Dans le cadre d'un contrat de location simple, les risques et avantages liés à l'actif loué incombent au bailleur. Une troisième option est une identification automatisée du type de contrat de location, qu'il soit financier ou opérationnel, en fonction des seuils définis dans le registre. Cette identification automatique est effectuée lors du test de reclassification des baux.

- **Seuils** - Utilisé dans les tests de classification des baux pour déterminer si l'actif est classé comme l'un des éléments suivants :

  - **Durée du bail** - Il s'agit du pourcentage de la durée de vie utile à utiliser dans le test de classification. Le système classera le bail comme financement si le type de bail est défini sur automatique et si la durée du bail sur la durée de vie utile de l'actif est supérieure ou égale au pourcentage défini ici.

  - **Valeur actuelle** - Il s'agit du pourcentage de la juste valeur de l'actif à utiliser dans le test de classification. Le système classera le bail comme financement si le type de bail est défini sur automatique et si la valeur présente des paiements de location futurs sur la juste valeur de l'actif est supérieure ou égale au pourcentage défini ici.

  - **Bail à court terme** - Si la durée du bail est inférieure ou égale à la valeur définie, le bail sera classé comme un bail à court terme.

  - **Faible valeur** - Si la juste valeur de l'actif est inférieure ou égale à la valeur définie, le bail sera classé comme un bail de faible valeur.

  - **Classification et transactions de bail** La classification des baux est un processus automatisé permettant de classer les baux en fonction des seuils définis dans les registres en plus d'autres critères de test de classification pour identifier si le bail est un contrat de location-financement, un contrat de location simple, un bail à court terme ou un bail de faible valeur. Elle est également utilisée pour déterminer si le processus de loyer reporté est suivi.

Les tests de classification incluent le transfert de propriété, l'option d'achat, la durée du bail, la valeur actuelle et l'actif unique. Le diagramme suivant illustre les tests de classification des baux.

[![Tests de classification des baux](./media/overview-03.png)](./media/overview-03.png)

Chaque type de bail gère la comptabilité différemment pour différentes transactions de bail. Les transactions comprennent la comptabilisation initiale, les charges d'intérêts, les paiements de location dus et l'amortissement du bail. Elles sont basées sur les normes comptables que vous suivez (IFRS 16 ou ASC 842). Les comptes généraux sont définis sous le profil de validation des baux pour chaque type de transaction et structure de comptabilité.

## <a name="asset-leasing-transactions"></a>Transactions de location d'actifs

#### <a name="initial-recognition"></a>Reconnaissance initiale 
La comptabilisation initiale d'un actif loué utilise la valeur actuelle calculée afin qu'elle puisse être déclarée au bilan. L'écriture comptable correspondante est générée automatiquement. Cette transaction débite le compte de droit d'utilisation de l'actif et crédite le compte de passif de location simple comme suit. Si un actif fixe est associé au bail, l'écriture de comptabilisation initiale sera reflétée comme une acquisition d'immobilisation. Dans ce scénario, vous devez définir un profil de comptabilisation des immobilisations à enregistrer dans le compte de droit d'utilisation de l'actif. 

> [!NOTE]
> Les contrats de location simple sont pris en charge uniquement par US GAAP ASC 842.

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Location simple selon US GAAP              |     Droit d'utilisation de l'actif      |     Location simple       |
|     Contrat de location-financement selon les IFRS et US GAAP        |     Droit d'utilisation de l'actif      |     Location simple       |

#### <a name="lease-liability-amortization-interest-expense"></a>Amortissement du passif locatif (charges d'intérêts) 
Les intérêts d'un bail sont comptabilisés en calculant les intérêts pour le solde d'ouverture du bail, le paiement de la période de location, le taux d'intérêt de l'emprunt et les périodes d'intervalle de composition par an. Le montant des intérêts augmente le compte de passif de location simple en le créditant, ce qui sera reflété dans le bilan de l'organisation. La transaction comprend également une entrée de débit dans le compte de charges d'intérêts, qui est reflétée dans le compte de résultat pour les contrats de location-financement, et dans le compte de charges de location pour les contrats de location simple.

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrée de passif de location simple selon US GAAP ASC 842    |     Dépenses d'intérêts          |     Passif locatif simple         |
|     Entrée de contrat de location-financement selon IFRS and US GAAP      |     Dépenses d'intérêts          |     Contrat de location-financement           |

#### <a name="accrued-lease-payment"></a>Paiement de location accumulé
Un paiement de location accumulé est reconnu comme un paiement futur de location qui doit être traité comme une transaction de paiement à partir de la banque ou des comptes de disponibilités. Le paiement de location dû diminue le passif locatif en débitant le compte de passif de location du journal de comptabilité auxiliaire du fourisseur dans le cas où le bailleur est défini comme fournisseur, ou en validant le crédit sur un compte général des effets à payer, le paiement sera alors exécuté à l'attention du fournisseur ou des effets à payer.

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Location simple selon US GAAP              |  Passif locatif simple    |   Passif du fournisseur (comptabilité auxiliaire) / Effets à payer  |
|     Contrat de location-financement selon les IFRS et US GAAP        |  Contrat de location-financement      |   Passif du fournisseur (comptabilité auxiliaire) / Effets à payer  |

#### <a name="asset-depreciation"></a>Amortissement des actifs
Le droit d'utilisation de l'actif est amorti sur la valeur la moins élevée - la durée de vie utile de l'actif ou la durée du bail. La méthode de calcul de l'amortissement selon les normes US GAAP (ASC 842) est basée sur la différence entre les frais de bail linéaires et le montant des intérêts. Les intérêts sur les contrats de location-financement sont calculés selon une méthode linéaire standard. L'amortissement du bail affecte le relevé de compte de résultat en débitant les charges d'intérêts. Le bilan est affecté par le crédit du compte du droit d'utilisation de l'actif cumulé pour les contrats de location-financement. Pour les contrats de location simple, l'amortissement est au crédit du compte de charges de location. Si le bail est lié à une immobilisation, les transactions d'amortissement seront exécutées à partir du module des immobilisations uniquement. 

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Location simple selon US GAAP              |  Dépense de bail                |   Amortissement cumulé du droit d'utilisation de l'actif     |
|     Contrat de location-financement selon les IFRS et US GAAP        |   Amortissement de la charge du droit d'utilisation de l'actif   |   Amortissement cumulé du droit d'utilisation de l'actif    |

#### <a name="short-term-lease"></a>Bail à court terme
Un contrat de location à court terme est comptabilisé comme une charge, ce qui affectera le compte de résultat d'une organisation. Le paiement de location dû généré débitera le compte de charges de location et créditera les effets à payer ou le compte auxiliaire du fournisseur.

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrée du bail à court terme selon IFRS and US GAAP     |  Dépense de bail                |   Passif du fournisseur (comptabilité auxiliaire) / Effets à payer  |

#### <a name="low-value-lease"></a>Bail de faible valeur
Un bail de faible valeur est comptabilisé comme une charge qui affectera le compte de résultat de votre organisation. Le paiement de location dû généré débitera le compte de charges de location et créditera les effets à payer ou le compte auxiliaire du fournisseur.

|     Type                                          |     Débit                     |     Crédit                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrée du de faible valeur selon IFRS and US GAAP      |  Dépense de bail                |   Passif du fournisseur (comptabilité auxiliaire) / Effets à payer  |


#### <a name="index-revaluation"></a>Réévaluation de l'indexation
Il s'agit du compte de location d'actifs pour les paiements de location variables mesurés par un taux d'indexation. Les changements des paiements de location causés par les fluctuations du taux d'indexation constituent un ajustement de bail selon IFRS 16. Le passif locatif et les droits d'utilisation de l'actif seront ajustés pour tenir compte des nouveaux paiements. 

|     Type                                          |     Débit                             |     Crédit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrée de réévaluation d'index selon IFRS en cas d'augmentation  |  Droit d'utilisation de l'actif       |   Passif locatif simple |
|   Entrée de réévaluation d'index selon IFRS en cas de réduction  |  Passif locatif simple  |   Droit d'utilisation de l'actif      |

Lorsque les paiements changent en raison d'un changement du taux d'indexation, seuls les paiements variables changeront sauf en cas de changements supplémentaires dans les flux de trésorerie, comme une modification de la durée du bail liée aux taux d'intérêt selon US GAAP ASC 842.

#### <a name="lease-adjustment"></a>Ajustement de bail
La location d'actifs permet d'ajuster les baux si la durée du bail est modifiée, si le bail est prolongé ou s'il existe des circonstances supplémentaires qui nécessitent d'ajuster un bail. Les ajustements d'un bail sont validés pour augmenter ou diminuer le droit d'utilisation de l'actif et le passif locatif. Le processus d'ajustement prend en charge le report des soldes de clôture de l'amortissement du passif et du solde de l'actif à la date d'ajustement. Lorsqu'un bail est lié à une immobilisation, l'ajustement du droit d'utilisation est validé à l'aide de l'ID attribué dans Immobilisations. 

|     Type                                          |     Débit                             |     Crédit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrée d'ajustement de bail selon IFRS et US GAAP en cas d'augmentation     |  Droit d'utilisation de l'actif       |   Passif locatif simple |
|   Entrée d'ajustement de bail selon IFRS et US GAAP en cas de réduction     |  Passif locatif simple  |   Droit d'utilisation de l'actif      |


#### <a name="lease-impairment"></a>Dépréciation du bail
Cela représente le report de la réduction du solde de l'actif du droit d'utilisation de l'actif. Identifiez le montant de la dépréciation, la date de la transaction et les périodes restantes. Le solde du droit d'utilisation de l'actif sera amorti de façon linéaire. La logique de dépréciation du bail prend en compte la valeur de report des actifs qui existe dans le programme d'amortissement des actifs.  

|     Type                                          |     Débit                             |     Crédit                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Dépréciation selon IFRS et US GAAP           |  Dépense de dépréciation                   |    Droit d'utilisation de l'actif     |

>[!NOTE]
> Si le bail est lié à une immobilisation, la dépréciation du bail doit être comptabilisée à partir des immobilisations car l'amortissement des immobilisations est exécuté à partir du module Immobilisations.

**Devise double** Les transactions de bail peuvent être enregistrées dans une devise autre que la devise comptable et de déclaration. Le taux de change de la devise est défini dans la comptabilité à la date de début. Vous pouvez modifier les taux de change en définissant le champ **Taux fixe** sur **Oui** lorsque vous créez le bail. Lorsque vous saisissez des transactions de bail, la comptabilisation initiale et les transactions d'amortissement ultérieures utiliseront le taux de change à la date de début. Les opérations de paiement et d'intérêts ultérieures utiliseront le taux de change actif actuel. 

## <a name="create-an-asset-lease"></a>Créer un bail d'actif
Procédez comme suit pour créer un bail. 

1. Pour utiliser la fonctionnalité **Locations d'actifs** , vous devez l'activer dans l'espace de travail **Gestion des fonctionnalités**. Dans l'espace de travail **Gestion des fonctionnalités** , sélectionnez **Tout** afin que toutes les fonctionnalités soient répertoriées sur la page. Sélectionnez **Location d'actifs** , puis **Activer maintenant**.
2. Accédez à **Location d'actifs> Commun> Récapitulatif du bail**. Renseignez les champs requis dans le raccourci **Général**. 
   - **Détails du bail**
   - **Durée de vie utile de l’actif (mois)**
   - **Groupe de baux**
   - **Taux d'emprunt marginal (%)**
   - **Intervalle de composition**
   - **Type d'annuité**
   - **Devise**
   - **Date d'entrée en vigueur**

3. Accédez au raccourci **Lignes d’échéancier de paiement** et saisissez une ligne de paiement, puis sélectionnez **Créer des échéanciers**.

4. Sélectionnez **Registres**. 

5. Accédez au raccourci **Général**. Les valeurs **Droit d'utilisation de l'actif initial** et **Passif locatif** sont calculées. 

6. Accédez au raccourci **Test de classification des baux** pour vérifier la valeur du champ **Type de bail**. 

   Le **Type de bail** automatique est classé en fonction des critères définis sur lea page **Registres**.

7.  Accédez à **Échéancier de paiement** dans la section **Fonction**.  

   La page **Échéancier de paiement** répertorie les futurs échéanciers de paiement pour un ID de bail. Sélectionnez **Confirmer l'échancier** pour pouvoir valider les transactions **Comptabilisation initiale**. 

[![Fonction de comptabilisation initiale](./media/overview-13.png)](./media/overview-13.png)

8. Sélectionnez **Comptabilisation initiale** pour créer un journal de comptabilisation initiale. 

9. Sélectionnez **Journaux de location d'actifs** pour valider la transaction de comptabilisation initiale. 

   À partir de l'échéancier de paiement, vous pouvez ouvrir une page détaillée qui répertorie les transactions du droit d'utilisation de l'actif. 
 
   L' **échéancier de l'amortissement du passif locatif** indique le montant des intérêts calculé pour chaque période.
   
10. Créez le journal, puis accédez à **Journaux de location d'actifs**. L' **échéancier de l'amortissement du passif locatif** affiche également dans les transactions d'intérêt.

   La page **Programme d'amortissement des actifs** affiche les transactions d'amortissement pour l'ID de bail sélectionné. 

   [![Page des transactions du droit d'utilisation de l'actif](./media/overview-20.png)](./media/overview-20.png)

   La page **Transactions du droit d'utilisation de l'actif** répertorie la comptabilisation initiale, l'amortissement cumulé et le solde de l'actif. 

   La page **Transactions du passif locatif** affiche la comptabilisation initiale, le paiement des intérêts de location, le paiement de location et le solde du passif locatif. 

