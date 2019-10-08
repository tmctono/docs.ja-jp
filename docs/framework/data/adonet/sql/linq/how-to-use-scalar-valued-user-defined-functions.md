---
title: '方法: スカラー値のユーザー定義関数を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003240"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="0b333-102">方法: スカラー値のユーザー定義関数を使用する</span><span class="sxs-lookup"><span data-stu-id="0b333-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="0b333-103"><xref:System.Data.Linq.Mapping.FunctionAttribute> 属性を使用することによって、クラスで定義されているクライアント メソッドを、ユーザー定義関数に対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0b333-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="0b333-104">メソッドの本体は、メソッド呼び出しの目的を反映する式を構築し、変換および実行のためにその式を <xref:System.Data.Linq.DataContext> に渡します。</span><span class="sxs-lookup"><span data-stu-id="0b333-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b333-105">直接実行は、関数がクエリの外部で呼び出される場合のみ発生します。</span><span class="sxs-lookup"><span data-stu-id="0b333-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="0b333-106">詳細については、「[方法 :ユーザー定義関数をインライン @ no__t から呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0b333-106">For more information, see [How to: Call User-Defined Functions Inline](how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b333-107">例</span><span class="sxs-lookup"><span data-stu-id="0b333-107">Example</span></span>  
 <span data-ttu-id="0b333-108">次の SQL コードは、スカラー値のユーザー定義関数 `ReverseCustName()` を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b333-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```sql  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="0b333-109">このコードで、次のようなクライアント メソッドを対応付けます。</span><span class="sxs-lookup"><span data-stu-id="0b333-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0b333-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b333-110">See also</span></span>

- [<span data-ttu-id="0b333-111">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="0b333-111">User-Defined Functions</span></span>](user-defined-functions.md)
