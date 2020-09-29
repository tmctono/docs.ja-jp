---
title: プロパティ '<propertyname>' は、すべてのコードのパスでは値を返しません。
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 6a80a8275a7b9c5e3cbfa410ee219e0d16ce5918
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870945"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>プロパティ '\<propertyname>' は、すべてのコードのパスでは値を返しません。

プロパティ '\<propertyname>' は、すべてのコードのパスでは値を返しません。 この結果が使用されると、実行時に Null 参照例外が生じる可能性があります。  
  
 プロパティ `Get` プロシージャのコードには、値を返さないパスが少なくとも 1 つ含まれています。  
  
 次のいずれかの方法で、プロパティ `Get` プロシージャから値を返すことができます。  
  
- プロパティ名に値を代入して、`Exit Property` ステートメントを実行します。  
  
- プロパティ名に値を代入して、`End Get` ステートメントを実行します。  
  
- [return ステートメント](../statements/return-statement.md)に値を含めます。  
  
 制御が `Exit Property` または `End Get` に渡され、プロパティ名に何も値を代入していない場合、`Get` プロシージャでは、プロパティのデータ型の既定値が返されます。 詳細については、「[Function ステートメント](../statements/function-statement.md)」の "動作" に関する記述を参照してください。  
  
 既定では、このメッセージは警告です。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。  
  
 **エラー ID:** BC42107  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 制御フロー ロジックをチェックし、戻り値を返すすべてのステートメントの前に値を代入してください。  
  
     常に `Return` ステートメントを使用すれば、プロシージャからのすべての戻り値で、値が返されることを簡単に保証できます。 これを実行する場合、`End Get` の前の最後のステートメントは、`Return` ステートメントでなければなりません。  
  
## <a name="see-also"></a>関連項目

- [Property プロシージャ](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property ステートメント](../statements/property-statement.md)
- [Get ステートメント](../statements/get-statement.md)
