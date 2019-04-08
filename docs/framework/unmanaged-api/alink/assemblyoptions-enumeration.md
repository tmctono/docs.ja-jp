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
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085416"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="06ca4-102">AssemblyOptions 列挙体</span><span class="sxs-lookup"><span data-stu-id="06ca4-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="06ca4-103">アセンブリ オプションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="06ca4-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ca4-104">構文</span><span class="sxs-lookup"><span data-stu-id="06ca4-104">Syntax</span></span>  
  
```  
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
  
## <a name="fields"></a><span data-ttu-id="06ca4-105">フィールド</span><span class="sxs-lookup"><span data-stu-id="06ca4-105">Fields</span></span>  
  
|<span data-ttu-id="06ca4-106">フィールド</span><span class="sxs-lookup"><span data-stu-id="06ca4-106">Field</span></span>|<span data-ttu-id="06ca4-107">説明</span><span class="sxs-lookup"><span data-stu-id="06ca4-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="06ca4-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="06ca4-108">optAssemTitle</span></span>|<span data-ttu-id="06ca4-109">文字列 - アセンブリのタイトルを表します。</span><span class="sxs-lookup"><span data-stu-id="06ca4-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="06ca4-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="06ca4-110">optAssemDescription</span></span>|<span data-ttu-id="06ca4-111">文字列 - アセンブリの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="06ca4-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="06ca4-112">optAssemConfig</span></span>|<span data-ttu-id="06ca4-113">文字列 - アセンブリの構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="06ca4-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="06ca4-114">optAssemOS</span></span>|<span data-ttu-id="06ca4-115">-エンコードされた文字列:"dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"。</span><span class="sxs-lookup"><span data-stu-id="06ca4-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="06ca4-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="06ca4-116">optAssemProcessor</span></span>|<span data-ttu-id="06ca4-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="06ca4-117">ULONG</span></span>|  
|<span data-ttu-id="06ca4-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="06ca4-118">optAssemLocale</span></span>|<span data-ttu-id="06ca4-119">文字列 - アセンブリのロケールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="06ca4-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="06ca4-120">optAssemVersion</span></span>|<span data-ttu-id="06ca4-121">文字列 - としてエンコードされます。"Major.Minor.Build.Revision"。</span><span class="sxs-lookup"><span data-stu-id="06ca4-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="06ca4-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="06ca4-122">optAssemCompany</span></span>|<span data-ttu-id="06ca4-123">文字列 - 会社が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="06ca4-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="06ca4-124">optAssemProduct</span></span>|<span data-ttu-id="06ca4-125">文字列 - 製品名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="06ca4-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="06ca4-126">optAssemProductVersion</span></span>|<span data-ttu-id="06ca4-127">文字列 (InformationalVersion とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="06ca4-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="06ca4-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="06ca4-128">optAssemCopyright</span></span>|<span data-ttu-id="06ca4-129">文字列 - 著作権情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="06ca4-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="06ca4-130">optAssemTrademark</span></span>|<span data-ttu-id="06ca4-131">文字列 - 商標に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06ca4-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="06ca4-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="06ca4-132">optAssemKeyFile</span></span>|<span data-ttu-id="06ca4-133">String (ファイル名)。</span><span class="sxs-lookup"><span data-stu-id="06ca4-133">String (file name).</span></span>|  
|<span data-ttu-id="06ca4-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="06ca4-134">optAssemKeyName</span></span>|<span data-ttu-id="06ca4-135">文字列 (キー名)。</span><span class="sxs-lookup"><span data-stu-id="06ca4-135">String (The key name).</span></span>|  
|<span data-ttu-id="06ca4-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="06ca4-136">optAssemAlgID</span></span>|<span data-ttu-id="06ca4-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="06ca4-137">ULONG</span></span>|  
|<span data-ttu-id="06ca4-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="06ca4-138">optAssemFlags</span></span>|<span data-ttu-id="06ca4-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="06ca4-139">ULONG</span></span>|  
|<span data-ttu-id="06ca4-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="06ca4-140">optAssemHalfSign</span></span>|<span data-ttu-id="06ca4-141">Bool (DelaySign とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="06ca4-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="06ca4-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="06ca4-142">optAssemFileVersion</span></span>|<span data-ttu-id="06ca4-143">文字列 -"Major.Minor.Build.Revision"--ProductVersion と同じようにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="06ca4-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="06ca4-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="06ca4-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="06ca4-145">文字列の"Major.Minor.Build.Revision"としてエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="06ca4-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="06ca4-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="06ca4-146">optLastAssemOption</span></span>|<span data-ttu-id="06ca4-147">要素の数のカウンター。</span><span class="sxs-lookup"><span data-stu-id="06ca4-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06ca4-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="06ca4-148">Requirements</span></span>  
 <span data-ttu-id="06ca4-149">**ヘッダー:** alink.h</span><span class="sxs-lookup"><span data-stu-id="06ca4-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="06ca4-150">**ライブラリ**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="06ca4-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ca4-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="06ca4-151">See also</span></span>

- [<span data-ttu-id="06ca4-152">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="06ca4-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
