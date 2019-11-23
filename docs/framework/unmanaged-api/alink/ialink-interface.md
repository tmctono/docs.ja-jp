---
title: IALink インターフェイス
ms.date: 03/30/2017
f1_keywords:
- IALink
helpviewer_keywords:
- IALink interface
ms.assetid: 50abd02d-6488-4815-999b-4fb89af4d568
ms.openlocfilehash: 73b6bb9eac3f706df5cb1fd63b2f67c9791c8ed2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441820"
---
# <a name="ialink-interface"></a><span data-ttu-id="703ae-102">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="703ae-102">IALink Interface</span></span>
<span data-ttu-id="703ae-103">Helps in constructing .NET Framework assemblies.</span><span class="sxs-lookup"><span data-stu-id="703ae-103">Helps in constructing .NET Framework assemblies.</span></span> <span data-ttu-id="703ae-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span><span class="sxs-lookup"><span data-stu-id="703ae-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="703ae-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="703ae-105">In This Section</span></span>  
 [<span data-ttu-id="703ae-106">AddFile Method</span><span class="sxs-lookup"><span data-stu-id="703ae-106">AddFile Method</span></span>](addfile-method.md)  
  
 [<span data-ttu-id="703ae-107">AddImport Method</span><span class="sxs-lookup"><span data-stu-id="703ae-107">AddImport Method</span></span>](addimport-method.md)  
  
 [<span data-ttu-id="703ae-108">CloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-108">CloseAssembly Method</span></span>](closeassembly-method.md)  
  
 [<span data-ttu-id="703ae-109">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-109">CloseEnum Method</span></span>](closeenum-method.md)  
  
 [<span data-ttu-id="703ae-110">EmbedResource メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-110">EmbedResource Method</span></span>](embedresource-method.md)  
  
 [<span data-ttu-id="703ae-111">EmitAssemblyCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-111">EmitAssemblyCustomAttribute Method</span></span>](emitassemblycustomattribute-method.md)  
  
 [<span data-ttu-id="703ae-112">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-112">EmitManifest Method</span></span>](emitmanifest-method.md)  
  
 [<span data-ttu-id="703ae-113">EndMerge メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-113">EndMerge Method</span></span>](endmerge-method.md)  
  
 [<span data-ttu-id="703ae-114">EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-114">EnumCustomAttributes Method</span></span>](enumcustomattributes-method.md)  
  
 [<span data-ttu-id="703ae-115">EnumImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-115">EnumImportTypes Method</span></span>](enumimporttypes-method.md)  
  
 [<span data-ttu-id="703ae-116">ExportNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-116">ExportNestedType Method</span></span>](exportnestedtype-method.md)  
  
 [<span data-ttu-id="703ae-117">ExportNestedTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-117">ExportNestedTypeForwarder Method</span></span>](exportnestedtypeforwarder-method.md)  
  
 [<span data-ttu-id="703ae-118">ExportType メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-118">ExportType Method</span></span>](exporttype-method.md)  
  
 [<span data-ttu-id="703ae-119">ExportTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-119">ExportTypeForwarder Method</span></span>](exporttypeforwarder-method.md)  
  
 [<span data-ttu-id="703ae-120">FreeWin32ResBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-120">FreeWin32ResBlob Method</span></span>](freewin32resblob-method.md)  
  
 [<span data-ttu-id="703ae-121">GetAssemblyRefHash メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-121">GetAssemblyRefHash Method</span></span>](getassemblyrefhash-method.md)  
  
 [<span data-ttu-id="703ae-122">GetResolutionScope メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-122">GetResolutionScope Method</span></span>](getresolutionscope-method.md)  
  
 [<span data-ttu-id="703ae-123">GetScope Method</span><span class="sxs-lookup"><span data-stu-id="703ae-123">GetScope Method</span></span>](getscope-method.md)  
  
 [<span data-ttu-id="703ae-124">GetWin32ResBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-124">GetWin32ResBlob Method</span></span>](getwin32resblob-method.md)  
  
 [<span data-ttu-id="703ae-125">ImportFile メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-125">ImportFile Method</span></span>](importfile-method.md)  
  
 [<span data-ttu-id="703ae-126">ImportFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-126">ImportFile2 Method</span></span>](importfile2-method.md)  
  
 [<span data-ttu-id="703ae-127">ImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-127">ImportTypes Method</span></span>](importtypes-method.md)  
  
 <span data-ttu-id="703ae-128">"Init Method"</span><span class="sxs-lookup"><span data-stu-id="703ae-128">"Init Method"</span></span>  
  
 [<span data-ttu-id="703ae-129">LinkResource メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-129">LinkResource Method</span></span>](linkresource-method.md)  
  
 [<span data-ttu-id="703ae-130">PreCloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-130">PreCloseAssembly Method</span></span>](precloseassembly-method.md)  
  
 [<span data-ttu-id="703ae-131">SetAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-131">SetAssemblyFile Method</span></span>](setassemblyfile-method.md)  
  
 [<span data-ttu-id="703ae-132">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-132">SetAssemblyProps Method</span></span>](setassemblyprops-method.md)  
  
 [<span data-ttu-id="703ae-133">SetNonAssemblyFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="703ae-133">SetNonAssemblyFlags Method</span></span>](setnonassemblyflags-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="703ae-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="703ae-134">See also</span></span>

- [<span data-ttu-id="703ae-135">ALink API</span><span class="sxs-lookup"><span data-stu-id="703ae-135">ALink API</span></span>](index.md)
- [<span data-ttu-id="703ae-136">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="703ae-136">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="703ae-137">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="703ae-137">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
