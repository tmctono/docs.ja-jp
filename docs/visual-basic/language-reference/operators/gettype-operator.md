---
title: GetType 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840322"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="db70f-102">GetType 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db70f-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="db70f-103">返します、<xref:System.Type>指定した型のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="db70f-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="db70f-104"><xref:System.Type>オブジェクトなど、そのプロパティ、メソッド、およびイベントの種類に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="db70f-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db70f-105">構文</span><span class="sxs-lookup"><span data-stu-id="db70f-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="db70f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db70f-106">Parameters</span></span>  
  
|<span data-ttu-id="db70f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db70f-107">Parameter</span></span>|<span data-ttu-id="db70f-108">説明</span><span class="sxs-lookup"><span data-stu-id="db70f-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="db70f-109">情報を取得する対象の型の名前。</span><span class="sxs-lookup"><span data-stu-id="db70f-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db70f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="db70f-110">Remarks</span></span>  
 <span data-ttu-id="db70f-111">`GetType`演算子を返します、<xref:System.Type>指定したオブジェクト`typename`します。</span><span class="sxs-lookup"><span data-stu-id="db70f-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="db70f-112">定義済みのすべての種類の名前を渡すことができます`typename`します。</span><span class="sxs-lookup"><span data-stu-id="db70f-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="db70f-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="db70f-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="db70f-114">などの任意の Visual Basic データ入力`Boolean`または`Date`します。</span><span class="sxs-lookup"><span data-stu-id="db70f-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="db70f-115">.NET Framework クラス、構造体、モジュール、またはインターフェイスなど<xref:System.ArgumentException?displayProperty=nameWithType>または<xref:System.Double?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="db70f-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="db70f-116">クラス、構造体、モジュール、またはアプリケーションによって定義されたインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="db70f-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="db70f-117">アプリケーションで定義されている配列。</span><span class="sxs-lookup"><span data-stu-id="db70f-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="db70f-118">アプリケーションで定義されているすべてのデリゲート。</span><span class="sxs-lookup"><span data-stu-id="db70f-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="db70f-119">Visual Basic、.NET Framework、またはアプリケーションによって定義されたすべての列挙体。</span><span class="sxs-lookup"><span data-stu-id="db70f-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="db70f-120">オブジェクト変数の型のオブジェクトを取得する場合は、使用、<xref:System.Type.GetType%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="db70f-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="db70f-121">`GetType`演算子は、次の状況で役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="db70f-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="db70f-122">型のメタデータは、実行時にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db70f-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="db70f-123"><xref:System.Type>オブジェクト型のメンバーおよび展開の情報などのメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="db70f-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="db70f-124">必要があります、たとえば、アセンブリを反映するようにします。</span><span class="sxs-lookup"><span data-stu-id="db70f-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="db70f-125">詳細については、「 <xref:System.Reflection?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db70f-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="db70f-126">同じ型のインスタンスを参照しているかどうかを 2 つのオブジェクト参照を比較します。</span><span class="sxs-lookup"><span data-stu-id="db70f-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="db70f-127">場合は、`GetType`同じへの参照を返します<xref:System.Type>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="db70f-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db70f-128">例</span><span class="sxs-lookup"><span data-stu-id="db70f-128">Example</span></span>  
 <span data-ttu-id="db70f-129">次の例に示す、`GetType`演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="db70f-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="db70f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="db70f-130">See also</span></span>

- [<span data-ttu-id="db70f-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="db70f-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="db70f-132">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="db70f-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="db70f-133">演算子および式</span><span class="sxs-lookup"><span data-stu-id="db70f-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
