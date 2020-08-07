---
title: セキュリティとパブリックの読み取り専用配列フィールド
description: アプリケーションの境界動作またはセキュリティを定義するために、読み取り専用のパブリック配列フィールドの使用を避ける必要がある理由をお読みください。
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 5e499f8052306cd1ad063c9f44a2a0f1d0b365ef
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855739"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="b26b6-103">セキュリティとパブリックの読み取り専用配列フィールド</span><span class="sxs-lookup"><span data-stu-id="b26b6-103">Security and Public Read-only Array Fields</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="b26b6-104">読み取り専用のパブリック配列フィールドを変更できるため、マネージライブラリから読み取り専用パブリック配列フィールドを使用して、アプリケーションの境界動作またはセキュリティを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="b26b6-104">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b26b6-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="b26b6-105">Remarks</span></span>  

<span data-ttu-id="b26b6-106">一部の .NET クラスには、プラットフォーム固有の境界パラメーターを含む読み取り専用のパブリックフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b26b6-106">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="b26b6-107">たとえば、 <xref:System.IO.Path.InvalidPathChars> フィールドは、ファイルパス文字列で許可されていない文字を記述する配列です。</span><span class="sxs-lookup"><span data-stu-id="b26b6-107">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="b26b6-108">多くの同様のフィールドが .NET 全体に存在します。</span><span class="sxs-lookup"><span data-stu-id="b26b6-108">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="b26b6-109">のようなパブリック読み取り専用フィールドの値は、コード <xref:System.IO.Path.InvalidPathChars> またはコードのアプリケーションドメインを共有するコードによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="b26b6-109">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="b26b6-110">アプリケーションの境界動作を定義するには、このような読み取り専用パブリック配列フィールドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b26b6-110">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="b26b6-111">そうすると、悪意のあるコードが境界の定義を変更し、予期しない方法でコードを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b26b6-111">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="b26b6-112">.NET Framework のバージョン2.0 以降では、パブリック配列フィールドを使用する代わりに、新しい配列を返すメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b26b6-112">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="b26b6-113">たとえば、フィールドを使用する代わりに、 <xref:System.IO.Path.InvalidPathChars> メソッドを使用する必要があり <xref:System.IO.Path.GetInvalidPathChars%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b26b6-113">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="b26b6-114">.NET Framework 型では、内部的に境界の種類を定義するためにパブリックフィールドが使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b26b6-114">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="b26b6-115">代わりに、.NET Framework は個別のプライベートフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b26b6-115">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="b26b6-116">これらのパブリックフィールドの値を変更しても、.NET Framework 型の動作は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b26b6-116">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26b6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b26b6-117">See also</span></span>

- [<span data-ttu-id="b26b6-118">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="b26b6-118">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
