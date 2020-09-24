---
title: 縮小変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '<methodname>' はありません <list>
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
ms.openlocfilehash: 0c39f3eab77bd58d4f1f81cd8e7f1c95b0753c7f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079036"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion-list"></a>縮小変換しないで、これらの引数と共に呼び出せるオーバーロードされたアクセス可能な '\<methodname>' はありません\<list>

オーバーロードされたメソッドが呼び出されましたが、メソッドは縮小変換せずに指定された引数のリストと一致しません。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. `Option Strict Off`を指定します。
  
2. オーバーロードされたメソッドのシグネチャと一致するように、引数を変更します。  
  
## <a name="see-also"></a>こちらもご覧ください

- [引数の値渡しと参照渡し](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [拡大変換と縮小変換](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
