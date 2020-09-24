---
title: 引数 'Period' は 'Life' 引数以下でなければなりません
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_PeriodLELife
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
ms.openlocfilehash: 844192f1168e6fef7906ffc133dcc3b5ba40b42c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087038"
---
# <a name="argument-period-must-be-less-than-or-equal-to-argument-life"></a>引数 'Period' は 'Life' 引数以下でなければなりません

資産の減価償却費計算の対象期間を指定する `Period` 引数の値が `Life` 引数の値より大きくなっています。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- `Life` 引数と `Period` 引数の両方が同じ単位で指定されていることを確認します。 たとえば、 `Life` を月単位で指定する場合は、 `Period` も月単位で指定します。  
  
## <a name="see-also"></a>こちらもご覧ください

- [引数の値渡しと参照渡し](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
