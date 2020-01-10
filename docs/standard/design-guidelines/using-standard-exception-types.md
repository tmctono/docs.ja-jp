---
title: 標準例外型の使用
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708985"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="3f4a6-102">標準例外型の使用</span><span class="sxs-lookup"><span data-stu-id="3f4a6-102">Using Standard Exception Types</span></span>
<span data-ttu-id="3f4a6-103">このセクションでは、フレームワークによって提供される標準の例外とその使用法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="3f4a6-104">リストは、完全な手段ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="3f4a6-105">他のフレームワークの例外の種類の使用方法については、.NET Framework リファレンスドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="3f4a6-106">Exception および SystemException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-106">Exception and SystemException</span></span>  
 <span data-ttu-id="3f4a6-107">**X DO NOT** スロー<xref:System.Exception?displayProperty=nameWithType>または<xref:System.SystemException?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3f4a6-108">**X DO NOT** キャッチ`System.Exception`または`System.SystemException`framework コードで再スローする場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="3f4a6-109">**X AVOID** キャッチ`System.Exception`または`System.SystemException`、トップレベルの例外ハンドラーでは可します。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="3f4a6-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-110">ApplicationException</span></span>  
 <span data-ttu-id="3f4a6-111">**X DO NOT** スロー サービスまたはそれから派生<xref:System.ApplicationException>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="3f4a6-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-112">InvalidOperationException</span></span>  
 <span data-ttu-id="3f4a6-113">**✓ DO** スロー、<xref:System.InvalidOperationException>オブジェクトが不適切な状態である場合。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="3f4a6-114">ArgumentException、System.argumentnullexception、ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="3f4a6-115">**✓ DO** スロー<xref:System.ArgumentException>またはメンバーに無効な引数が渡された場合は、そのサブタイプのいずれか。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="3f4a6-116">最も派生した例外の種類を優先します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="3f4a6-117">**✓ DO** 設定、`ParamName`プロパティのサブクラスのいずれかをスローするときに`ArgumentException`です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="3f4a6-118">このプロパティは、例外がスローされる原因となったパラメーターの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="3f4a6-119">プロパティは、コンストラクターのオーバーロードのいずれかを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="3f4a6-120">**✓ DO** 使用`value`プロパティ set アクセス操作子の暗黙的な値パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="3f4a6-121">NullReferenceException、IndexOutOfRangeException、および Access Ationexception</span><span class="sxs-lookup"><span data-stu-id="3f4a6-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="3f4a6-122">**X DO NOT** 明示的または暗黙的にスローする、api で公開されている呼び出し可能<xref:System.NullReferenceException>、 <xref:System.AccessViolationException>、または<xref:System.IndexOutOfRangeException>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="3f4a6-123">これらの例外は、実行エンジンによって予約およびスローされ、ほとんどの場合、バグを示します。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="3f4a6-124">これらの例外をスローしないように引数をチェックします。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="3f4a6-125">これらの例外をスローすると、時間の経過と共に変化する可能性のあるメソッドの実装の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="3f4a6-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-126">StackOverflowException</span></span>  
 <span data-ttu-id="3f4a6-127">**X DO NOT** を明示的にスロー<xref:System.StackOverflowException>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="3f4a6-128">例外は、CLR によってのみ明示的にスローされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="3f4a6-129">**X DO NOT** キャッチ`StackOverflowException`です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="3f4a6-130">任意のスタックオーバーフローの有無に一貫性を持たせるマネージコードを記述することはほとんど不可能です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="3f4a6-131">CLR のアンマネージ部分は、プローブを使用してスタックオーバーフローを適切に定義された場所に移動することによって一貫性を保ちます。これは、任意のスタックオーバーフローからのバックアップではありません。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="3f4a6-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="3f4a6-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="3f4a6-133">**X DO NOT** を明示的にスロー<xref:System.OutOfMemoryException>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="3f4a6-134">この例外は、CLR インフラストラクチャによってのみスローされます。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="3f4a6-135">ComException、SEHException、および System.executionengineexception</span><span class="sxs-lookup"><span data-stu-id="3f4a6-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="3f4a6-136">**X DO NOT** を明示的にスロー <xref:System.Runtime.InteropServices.COMException>、 <xref:System.ExecutionEngineException>、および<xref:System.Runtime.InteropServices.SEHException>です。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="3f4a6-137">これらの例外は、CLR インフラストラクチャによってのみスローされます。</span><span class="sxs-lookup"><span data-stu-id="3f4a6-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="3f4a6-138">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="3f4a6-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3f4a6-139">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="3f4a6-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4a6-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f4a6-140">See also</span></span>

- [<span data-ttu-id="3f4a6-141">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3f4a6-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3f4a6-142">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3f4a6-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
