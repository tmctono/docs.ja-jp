---
title: AssemblyOptions 列挙体
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e7b73559e8def890f8df8f596fbe8ad5bb5d3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777485"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="cd681-102">AssemblyOptions 列挙体</span><span class="sxs-lookup"><span data-stu-id="cd681-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="cd681-103">アセンブリオプションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cd681-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd681-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd681-104">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="cd681-105">フィールド</span><span class="sxs-lookup"><span data-stu-id="cd681-105">Fields</span></span>  
  
|<span data-ttu-id="cd681-106">フィールド</span><span class="sxs-lookup"><span data-stu-id="cd681-106">Field</span></span>|<span data-ttu-id="cd681-107">説明</span><span class="sxs-lookup"><span data-stu-id="cd681-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cd681-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="cd681-108">optAssemTitle</span></span>|<span data-ttu-id="cd681-109">String-アセンブリのタイトルを表します。</span><span class="sxs-lookup"><span data-stu-id="cd681-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="cd681-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="cd681-110">optAssemDescription</span></span>|<span data-ttu-id="cd681-111">String-アセンブリの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd681-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="cd681-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="cd681-112">optAssemConfig</span></span>|<span data-ttu-id="cd681-113">String-アセンブリ構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd681-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="cd681-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="cd681-114">optAssemOS</span></span>|<span data-ttu-id="cd681-115">"DwOSPlatformId" としてエンコードされた文字列。</span><span class="sxs-lookup"><span data-stu-id="cd681-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="cd681-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="cd681-116">optAssemProcessor</span></span>|<span data-ttu-id="cd681-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="cd681-117">ULONG</span></span>|  
|<span data-ttu-id="cd681-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="cd681-118">optAssemLocale</span></span>|<span data-ttu-id="cd681-119">String-アセンブリロケールを格納します。</span><span class="sxs-lookup"><span data-stu-id="cd681-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="cd681-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="cd681-120">optAssemVersion</span></span>|<span data-ttu-id="cd681-121">文字列エンコードの形式:"メジャー. マイナー. ビルド. リビジョン"。</span><span class="sxs-lookup"><span data-stu-id="cd681-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cd681-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="cd681-122">optAssemCompany</span></span>|<span data-ttu-id="cd681-123">文字列-会社を含みます。</span><span class="sxs-lookup"><span data-stu-id="cd681-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="cd681-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="cd681-124">optAssemProduct</span></span>|<span data-ttu-id="cd681-125">文字列-製品名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd681-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="cd681-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="cd681-126">optAssemProductVersion</span></span>|<span data-ttu-id="cd681-127">文字列 (InformationalVersion とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="cd681-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="cd681-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="cd681-128">optAssemCopyright</span></span>|<span data-ttu-id="cd681-129">文字列-著作権情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd681-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="cd681-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="cd681-130">optAssemTrademark</span></span>|<span data-ttu-id="cd681-131">String-商標情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd681-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="cd681-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="cd681-132">optAssemKeyFile</span></span>|<span data-ttu-id="cd681-133">文字列 (ファイル名)。</span><span class="sxs-lookup"><span data-stu-id="cd681-133">String (file name).</span></span>|  
|<span data-ttu-id="cd681-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="cd681-134">optAssemKeyName</span></span>|<span data-ttu-id="cd681-135">文字列 (キー名)。</span><span class="sxs-lookup"><span data-stu-id="cd681-135">String (The key name).</span></span>|  
|<span data-ttu-id="cd681-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="cd681-136">optAssemAlgID</span></span>|<span data-ttu-id="cd681-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="cd681-137">ULONG</span></span>|  
|<span data-ttu-id="cd681-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="cd681-138">optAssemFlags</span></span>|<span data-ttu-id="cd681-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="cd681-139">ULONG</span></span>|  
|<span data-ttu-id="cd681-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="cd681-140">optAssemHalfSign</span></span>|<span data-ttu-id="cd681-141">Bool (DelaySign とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="cd681-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="cd681-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="cd681-142">optAssemFileVersion</span></span>|<span data-ttu-id="cd681-143">"Major. Minor. Build. Revision" としてエンコードされた文字列。 ProductVersion と同じです。</span><span class="sxs-lookup"><span data-stu-id="cd681-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="cd681-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="cd681-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="cd681-145">"Major. Minor. Build. Revision" としてエンコードされた文字列。</span><span class="sxs-lookup"><span data-stu-id="cd681-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cd681-146">optlastassemoopt</span><span class="sxs-lookup"><span data-stu-id="cd681-146">optLastAssemOption</span></span>|<span data-ttu-id="cd681-147">要素数のカウンター。</span><span class="sxs-lookup"><span data-stu-id="cd681-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd681-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd681-148">Requirements</span></span>  
 <span data-ttu-id="cd681-149">**ヘッダー:** alink</span><span class="sxs-lookup"><span data-stu-id="cd681-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="cd681-150">**ライブラリ**: alink</span><span class="sxs-lookup"><span data-stu-id="cd681-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd681-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd681-151">See also</span></span>

- [<span data-ttu-id="cd681-152">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="cd681-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
