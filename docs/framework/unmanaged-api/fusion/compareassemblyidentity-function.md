---
title: CompareAssemblyIdentity 関数
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55d4e936c8b732e4cc4a60df8c11b37c86c4a415
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778483"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="ab9ae-102">CompareAssemblyIdentity 関数</span><span class="sxs-lookup"><span data-stu-id="ab9ae-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="ab9ae-103">2 つのアセンブリ id と同じかどうかを比較します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab9ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab9ae-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab9ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab9ae-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="ab9ae-106">[in]比較では、最初のアセンブリのテキスト形式の id。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="ab9ae-107">[in]ユーザー指定の統一を示すブール フラグ`pwzAssemblyIdentity1`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="ab9ae-108">[in]比較では、2 番目のアセンブリのテキスト形式の id。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="ab9ae-109">[in]ユーザー指定の統一を示すブール フラグ`pwzAssemblyIdentity2`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="ab9ae-110">[out]2 つのアセンブリが等しいかどうかを示すブール フラグです。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="ab9ae-111">[out][AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)比較に関する詳細情報を含む列挙です。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab9ae-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ab9ae-112">Return Value</span></span>  
 <span data-ttu-id="ab9ae-113">`pfEquivalent` 2 つのアセンブリが等しいかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="ab9ae-114">`pResult` いずれかを返します、`AssemblyComparisonResult`の値の詳細な理由を指定する値、`pfEquivalent`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab9ae-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab9ae-115">Remarks</span></span>  
 <span data-ttu-id="ab9ae-116">`CompareAssemblyIdentity` チェックするかどうか`pwzAssemblyIdentity1`と`pwzAssemblyIdentity2`は同等です。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="ab9ae-117">`pfEquivalent` 設定されている`true`次の条件の 1 つ以上。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="ab9ae-118">2 つのアセンブリ id は同等です。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="ab9ae-119">アセンブリ名、バージョン、公開キー トークン、およびカルチャと同じですが、厳密な名前付きアセンブリのと同等のグループが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="ab9ae-120">単純な名前のアセンブリと同等のグループにはアセンブリ名、およびカルチャに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="ab9ae-121">両方のアセンブリ id は、.NET Framework で実行されるアセンブリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="ab9ae-122">この条件の戻り値`true`場合でも、アセンブリのバージョン番号が一致しません。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="ab9ae-123">2 つのアセンブリは、マネージ アセンブリではありませんが、`fUnified1`または`fUnified2`に設定された`true`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="ab9ae-124">`fUnified`フラグは、厳密な名前付きアセンブリのバージョン番号までのすべてのバージョン番号同等と見なされる厳密な名前付きアセンブリにことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="ab9ae-125">たとえば場合の値`pwzAssemblyIndentity1`が"MyAssembly, バージョン 3.0.0.0, culture = = neutral, publicKeyToken =..."の値と`fUnified1`は`true`、MyAssembly 0.0.0.0 に 3.0.0.0 のバージョンからのすべてのバージョンがあることを示します同等として扱われます。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="ab9ae-126">このような場合は場合、`pwzAssemblyIndentity2`と同じアセンブリを指す`pwzAssemblyIndentity1`、低いバージョン番号があることを除いて、`pfEquivalent`に設定されている`true`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="ab9ae-127">場合`pwzAssemblyIdentity2`上位のバージョン番号を指す`pfEquivalent`に設定されている`true`場合にのみの値`fUnified2`は`true`します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="ab9ae-128">`pResult`パラメーターには、なぜ 2 つのアセンブリは同等または同等ではないと見なされますに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="ab9ae-129">詳細については、次を参照してください。 [AssemblyComparisonResult 列挙型](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab9ae-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab9ae-130">Requirements</span></span>  
 <span data-ttu-id="ab9ae-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9ae-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab9ae-132">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ab9ae-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ab9ae-133">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ab9ae-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab9ae-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab9ae-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9ae-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab9ae-135">See also</span></span>

- [<span data-ttu-id="ab9ae-136">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="ab9ae-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="ab9ae-137">AssemblyComparisonResult 列挙型</span><span class="sxs-lookup"><span data-stu-id="ab9ae-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
