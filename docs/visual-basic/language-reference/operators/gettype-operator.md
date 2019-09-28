---
title: GetType 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592149"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="b5924-102">GetType 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5924-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="b5924-103">指定された型の @no__t 0 オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b5924-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="b5924-104">@No__t-0 オブジェクトは、そのプロパティ、メソッド、イベントなどの型に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5924-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5924-105">構文</span><span class="sxs-lookup"><span data-stu-id="b5924-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5924-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5924-106">Parameters</span></span>  
  
|<span data-ttu-id="b5924-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5924-107">Parameter</span></span>|<span data-ttu-id="b5924-108">説明</span><span class="sxs-lookup"><span data-stu-id="b5924-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="b5924-109">情報を必要とする型の名前。</span><span class="sxs-lookup"><span data-stu-id="b5924-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5924-110">コメント</span><span class="sxs-lookup"><span data-stu-id="b5924-110">Remarks</span></span>  
 <span data-ttu-id="b5924-111">@No__t-0 演算子は、指定された `typename` の <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b5924-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="b5924-112">任意の定義済みの型の名前を `typename` で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b5924-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="b5924-113">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5924-113">This includes the following:</span></span>  
  
- <span data-ttu-id="b5924-114">@No__t-0 や `Date` などの Visual Basic のデータ型。</span><span class="sxs-lookup"><span data-stu-id="b5924-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="b5924-115">.NET Framework クラス、構造体、モジュール、またはインターフェイス (<xref:System.ArgumentException?displayProperty=nameWithType> や <xref:System.Double?displayProperty=nameWithType> など)。</span><span class="sxs-lookup"><span data-stu-id="b5924-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="b5924-116">アプリケーションで定義されている任意のクラス、構造体、モジュール、またはインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="b5924-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="b5924-117">アプリケーションで定義されている任意の配列。</span><span class="sxs-lookup"><span data-stu-id="b5924-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="b5924-118">アプリケーションで定義されている任意のデリゲート。</span><span class="sxs-lookup"><span data-stu-id="b5924-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="b5924-119">Visual Basic、.NET Framework、またはアプリケーションによって定義された任意の列挙体。</span><span class="sxs-lookup"><span data-stu-id="b5924-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="b5924-120">オブジェクト変数の型オブジェクトを取得する場合は、<xref:System.Type.GetType%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5924-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b5924-121">@No__t-0 演算子は、次のような場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5924-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="b5924-122">実行時には、型のメタデータにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5924-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="b5924-123">@No__t-0 オブジェクトは、型のメンバーや配置情報などのメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5924-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="b5924-124">これは、たとえば、アセンブリを反映するために必要です。</span><span class="sxs-lookup"><span data-stu-id="b5924-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="b5924-125">詳細については、「 <xref:System.Reflection?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5924-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="b5924-126">2つのオブジェクト参照を比較して、同じ型のインスタンスを参照しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5924-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="b5924-127">指定されている場合、`GetType` は同じ <xref:System.Type> オブジェクトへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="b5924-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5924-128">例</span><span class="sxs-lookup"><span data-stu-id="b5924-128">Example</span></span>  
 <span data-ttu-id="b5924-129">次の例は、使用中の `GetType` 演算子を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5924-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="b5924-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5924-130">See also</span></span>

- [<span data-ttu-id="b5924-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="b5924-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b5924-132">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="b5924-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b5924-133">演算子および式</span><span class="sxs-lookup"><span data-stu-id="b5924-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
