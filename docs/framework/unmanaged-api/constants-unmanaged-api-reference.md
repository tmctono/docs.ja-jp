---
title: 定数 (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c76db644ffee478003d834460c155c4ec6d0070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944613"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="f863e-102">定数 (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f863e-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="f863e-103">このトピックでは、言語の種類、言語の販売元、および CorSym.idl で定義されているドキュメント型の定数について説明します。</span><span class="sxs-lookup"><span data-stu-id="f863e-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="f863e-104">言語の種類の定数</span><span class="sxs-lookup"><span data-stu-id="f863e-104">Language Type Constants</span></span>  
 <span data-ttu-id="f863e-105">次の表では、プログラミング言語を識別する Guid を表す型定数は、言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="f863e-106">シンボル</span><span class="sxs-lookup"><span data-stu-id="f863e-106">Symbol</span></span>|<span data-ttu-id="f863e-107">説明</span><span class="sxs-lookup"><span data-stu-id="f863e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f863e-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="f863e-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="f863e-109">C 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="f863e-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="f863e-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="f863e-111">C++ 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="f863e-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="f863e-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="f863e-113">示す、C#言語。</span><span class="sxs-lookup"><span data-stu-id="f863e-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="f863e-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="f863e-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="f863e-115">基本的な言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="f863e-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="f863e-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="f863e-117">Java 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="f863e-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="f863e-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="f863e-119">COBOL 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="f863e-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="f863e-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="f863e-121">Pascal 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="f863e-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="f863e-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="f863e-123">Microsoft intermediate language (MSIL) アセンブリのコードを示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="f863e-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="f863e-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="f863e-125">JScript 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="f863e-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="f863e-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="f863e-127">SMC 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="f863e-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="f863e-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="f863e-129">.NET Framework を有効になっている C++ 言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="f863e-130">言語のベンダー定数</span><span class="sxs-lookup"><span data-stu-id="f863e-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="f863e-131">次の表では、ベンダーの定数は、プログラミング言語のベンダーを識別する Guid を表す言語を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="f863e-132">シンボル</span><span class="sxs-lookup"><span data-stu-id="f863e-132">Symbol</span></span>|<span data-ttu-id="f863e-133">説明</span><span class="sxs-lookup"><span data-stu-id="f863e-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f863e-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="f863e-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="f863e-135">Microsoft を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="f863e-136">ドキュメントの種類の定数</span><span class="sxs-lookup"><span data-stu-id="f863e-136">Document Type Constants</span></span>  
 <span data-ttu-id="f863e-137">次の表は、ドキュメントのドキュメントの種類を識別する Guid を表す型の定数を示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="f863e-138">シンボル</span><span class="sxs-lookup"><span data-stu-id="f863e-138">Symbol</span></span>|<span data-ttu-id="f863e-139">説明</span><span class="sxs-lookup"><span data-stu-id="f863e-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f863e-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="f863e-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="f863e-141">テキスト ドキュメントを示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="f863e-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="f863e-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="f863e-143">テキスト以外のドキュメントを示します。</span><span class="sxs-lookup"><span data-stu-id="f863e-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f863e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f863e-144">See also</span></span>

- [<span data-ttu-id="f863e-145">アンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="f863e-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
