---
title: '方法: リフレクションを使用せずに印刷システム オブジェクトのプロパティを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: bb906dafd98e75708764b5f0f009900719f6a475
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335200"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="c24e7-102">方法: リフレクションを使用せずに印刷システム オブジェクトのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="c24e7-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="c24e7-103">リフレクションを使用してオブジェクトのプロパティ (およびそれらのプロパティの種類) と、アプリケーションのパフォーマンスが低下することができます。</span><span class="sxs-lookup"><span data-stu-id="c24e7-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="c24e7-104"><xref:System.Printing.IndexedProperties>名前空間でリフレクションを使用して、この情報を取得するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c24e7-105">例</span><span class="sxs-lookup"><span data-stu-id="c24e7-105">Example</span></span>  
 <span data-ttu-id="c24e7-106">これを行うための手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c24e7-106">The steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="c24e7-107">型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-107">Create an instance of the type.</span></span> <span data-ttu-id="c24e7-108">次の例では、型は、<xref:System.Printing.PrintQueue>とほぼ同じコードではなく Microsoft .NET Framework に付属する型から派生した型に対しては機能する必要があります<xref:System.Printing.PrintSystemObject>します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2. <span data-ttu-id="c24e7-109">作成、<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>型から<xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="c24e7-110"><xref:System.Collections.DictionaryEntry.Value%2A>このディクショナリ内の各エントリのプロパティから派生した型の 1 つのオブジェクトである<xref:System.Printing.IndexedProperties.PrintProperty>します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3. <span data-ttu-id="c24e7-111">ディクショナリのメンバーを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c24e7-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="c24e7-112">それらのそれぞれについて、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c24e7-112">For each of them, do the following.</span></span>  
  
4. <span data-ttu-id="c24e7-113">アップ キャストするには、各エントリの値<xref:System.Printing.IndexedProperties.PrintProperty>使用して作成して、<xref:System.Printing.IndexedProperties.PrintProperty>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c24e7-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5. <span data-ttu-id="c24e7-114">型を取得、<xref:System.Printing.IndexedProperties.PrintProperty.Value%2A>のそれぞれの<xref:System.Printing.IndexedProperties.PrintProperty>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c24e7-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="c24e7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c24e7-115">See also</span></span>

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="c24e7-116">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c24e7-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="c24e7-117">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="c24e7-117">Printing Overview</span></span>](printing-overview.md)
