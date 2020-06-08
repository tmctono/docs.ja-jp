---
title: .NET での文字列の解析
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: ab446a8f868cabdeff73d1b72e1399b7c2beb1e1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277415"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="56785-102">.NET での文字列の解析</span><span class="sxs-lookup"><span data-stu-id="56785-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="56785-103">解析操作では、.NET の基本データ型を表す文字列をその基本データ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="56785-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="56785-104">たとえば解析操作は、文字列を浮動小数点数や日付と時刻の値に変換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="56785-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="56785-105">解析操作を実行するには、`Parse` メソッドがよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="56785-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="56785-106">解析は書式設定の逆の操作 (基本データ型のその文字列形式への変換を含む) であるため、多くの同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="56785-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="56785-107">カルチャに依存する書式情報を指定するために、書式設定で <xref:System.IFormatProvider> インターフェイスを実装するオブジェクトを使用するのと同じように、解析でも <xref:System.IFormatProvider> インターフェイスを実装するオブジェクトを使用し、文字列形式を解釈する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="56785-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="56785-108">詳細については、[型の書式設定](formatting-types.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56785-108">For more information, see [Formatting Types](formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56785-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56785-109">In This Section</span></span>  
 [<span data-ttu-id="56785-110">数値文字列の解析</span><span class="sxs-lookup"><span data-stu-id="56785-110">Parsing Numeric Strings</span></span>](parsing-numeric.md)  
 <span data-ttu-id="56785-111">文字列を .NET 数値型に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56785-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="56785-112">日付と時刻文字列の解析</span><span class="sxs-lookup"><span data-stu-id="56785-112">Parsing Date and Time Strings</span></span>](parsing-datetime.md)  
 <span data-ttu-id="56785-113">文字列を .NET **DateTime** 型に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56785-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="56785-114">その他の文字列の解析</span><span class="sxs-lookup"><span data-stu-id="56785-114">Parsing Other Strings</span></span>](parsing-other.md)  
 <span data-ttu-id="56785-115">文字列を **Char** 型、**Boolean** 型、**Enum** 型に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56785-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="56785-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="56785-116">Related Sections</span></span>  
 [<span data-ttu-id="56785-117">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="56785-117">Formatting Types</span></span>](formatting-types.md)  
 <span data-ttu-id="56785-118">書式指定子や書式プロバイダーなどの基本書式の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="56785-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="56785-119">.NET での型変換</span><span class="sxs-lookup"><span data-stu-id="56785-119">Type Conversion in .NET</span></span>](type-conversion.md)  
 <span data-ttu-id="56785-120">型に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56785-120">Describes how to convert types.</span></span>
