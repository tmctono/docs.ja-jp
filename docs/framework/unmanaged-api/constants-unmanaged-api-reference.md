---
title: 定数 (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
ms.openlocfilehash: 88dfdfcaee4a53e9b3c6e4b7e8187c8bfd5eaa13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099614"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="8f382-102">定数 (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8f382-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="8f382-103">このトピックでは、言語の種類、言語のベンダー、および CorSym で定義されているドキュメントの種類の定数について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f382-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="8f382-104">言語の種類の定数</span><span class="sxs-lookup"><span data-stu-id="8f382-104">Language Type Constants</span></span>  
 <span data-ttu-id="8f382-105">次の表は、言語の種類の定数を示しています。これは、プログラミング言語を識別する Guid を表します。</span><span class="sxs-lookup"><span data-stu-id="8f382-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="8f382-106">シンボル</span><span class="sxs-lookup"><span data-stu-id="8f382-106">Symbol</span></span>|<span data-ttu-id="8f382-107">説明</span><span class="sxs-lookup"><span data-stu-id="8f382-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8f382-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="8f382-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="8f382-109">C 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="8f382-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="8f382-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="8f382-111">C++言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="8f382-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="8f382-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="8f382-113">C#言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="8f382-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="8f382-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="8f382-115">基本言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="8f382-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="8f382-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="8f382-117">Java 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="8f382-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="8f382-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="8f382-119">COBOL 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="8f382-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="8f382-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="8f382-121">Pascal 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="8f382-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="8f382-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="8f382-123">Microsoft 中間言語 (MSIL) のアセンブリコードを示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="8f382-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="8f382-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="8f382-125">JScript 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="8f382-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="8f382-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="8f382-127">SMC 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="8f382-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="8f382-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="8f382-129">.NET Framework にC++対して有効な言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="8f382-130">言語ベンダ定数</span><span class="sxs-lookup"><span data-stu-id="8f382-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="8f382-131">次の表は、言語ベンダーの定数を示しています。これは、プログラミング言語のベンダーを識別する Guid を表します。</span><span class="sxs-lookup"><span data-stu-id="8f382-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="8f382-132">シンボル</span><span class="sxs-lookup"><span data-stu-id="8f382-132">Symbol</span></span>|<span data-ttu-id="8f382-133">説明</span><span class="sxs-lookup"><span data-stu-id="8f382-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8f382-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="8f382-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="8f382-135">Microsoft を示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="8f382-136">ドキュメント型定数</span><span class="sxs-lookup"><span data-stu-id="8f382-136">Document Type Constants</span></span>  
 <span data-ttu-id="8f382-137">ドキュメントの種類を識別する Guid を表すドキュメント型定数を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="8f382-138">シンボル</span><span class="sxs-lookup"><span data-stu-id="8f382-138">Symbol</span></span>|<span data-ttu-id="8f382-139">説明</span><span class="sxs-lookup"><span data-stu-id="8f382-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8f382-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="8f382-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="8f382-141">テキストドキュメントを示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="8f382-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="8f382-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="8f382-143">テキスト以外のドキュメントを示します。</span><span class="sxs-lookup"><span data-stu-id="8f382-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f382-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f382-144">See also</span></span>

- [<span data-ttu-id="8f382-145">アンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="8f382-145">Unmanaged API Reference</span></span>](index.md)
