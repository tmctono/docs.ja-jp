---
title: "'Extension' 属性は 'Module'、'Sub'、または 'Function' の各宣言にのみ適用できます"
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 2ed3a10cdf941bb8d1d7c00379736e04e8cad4d7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583179"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="d651e-102">'Extension' 属性は 'Module'、'Sub'、または 'Function' の各宣言にのみ適用できます</span><span class="sxs-lookup"><span data-stu-id="d651e-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="d651e-103">Visual Basic でデータ型を拡張する唯一の方法は、標準モジュール内で拡張メソッドを定義することです。</span><span class="sxs-lookup"><span data-stu-id="d651e-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="d651e-104">拡張メソッドには、`Sub` プロシージャまたは `Function` プロシージャを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d651e-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="d651e-105">すべての拡張メソッドは、<xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 名前空間の拡張属性 `<Extension()>` でマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d651e-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d651e-106">必要に応じて、拡張メソッドを含むモジュールを同じ方法でマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d651e-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="d651e-107">その他の拡張属性の使用は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d651e-107">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="d651e-108">**エラー ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="d651e-108">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d651e-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d651e-109">To correct this error</span></span>

- <span data-ttu-id="d651e-110">拡張属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="d651e-110">Remove the extension attribute.</span></span>

- <span data-ttu-id="d651e-111">外側のモジュールで定義されているメソッドとして拡張機能を再設計します。</span><span class="sxs-lookup"><span data-stu-id="d651e-111">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="d651e-112">例</span><span class="sxs-lookup"><span data-stu-id="d651e-112">Example</span></span>

<span data-ttu-id="d651e-113">次の例では、`String` データ型の `Print` メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="d651e-113">The following example defines a `Print` method for the `String` data type.</span></span>

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a><span data-ttu-id="d651e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d651e-114">See also</span></span>

- [<span data-ttu-id="d651e-115">属性の概要</span><span class="sxs-lookup"><span data-stu-id="d651e-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="d651e-116">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="d651e-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="d651e-117">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="d651e-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
