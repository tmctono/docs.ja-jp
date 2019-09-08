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
ms.openlocfilehash: b52d3af38bd09ce5864c25d27e148dbd7f4639b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795446"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="c65d2-102">CompareAssemblyIdentity 関数</span><span class="sxs-lookup"><span data-stu-id="c65d2-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="c65d2-103">2つのアセンブリ id を比較して、それらが等しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c65d2-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c65d2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c65d2-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="c65d2-106">から比較対象の最初のアセンブリのテキスト id。</span><span class="sxs-lookup"><span data-stu-id="c65d2-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="c65d2-107">からのユーザー指定の統一を示すブール型の`pwzAssemblyIdentity1`フラグ。</span><span class="sxs-lookup"><span data-stu-id="c65d2-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="c65d2-108">から比較対象の2番目のアセンブリのテキスト id。</span><span class="sxs-lookup"><span data-stu-id="c65d2-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="c65d2-109">からのユーザー指定の統一を示すブール型の`pwzAssemblyIdentity2`フラグ。</span><span class="sxs-lookup"><span data-stu-id="c65d2-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="c65d2-110">入出力2つのアセンブリが等しいかどうかを示すブール型のフラグ。</span><span class="sxs-lookup"><span data-stu-id="c65d2-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="c65d2-111">入出力比較に関する詳細情報を含む[AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)列挙です。</span><span class="sxs-lookup"><span data-stu-id="c65d2-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c65d2-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c65d2-112">Return Value</span></span>  
 <span data-ttu-id="c65d2-113">`pfEquivalent`2つのアセンブリが等しいかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="c65d2-114">`pResult`値の`AssemblyComparisonResult` 1 つを返し、の`pfEquivalent`値のより詳細な理由を指定します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c65d2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="c65d2-115">Remarks</span></span>  
 <span data-ttu-id="c65d2-116">`CompareAssemblyIdentity`とが`pwzAssemblyIdentity1`等価`pwzAssemblyIdentity2`かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="c65d2-117">`pfEquivalent`は、次`true`の条件の1つ以上でに設定されます。</span><span class="sxs-lookup"><span data-stu-id="c65d2-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="c65d2-118">2つのアセンブリ id は同等です。</span><span class="sxs-lookup"><span data-stu-id="c65d2-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="c65d2-119">厳密な名前が付けられたアセンブリの場合、等価性には、アセンブリ名、バージョン、公開キートークン、およびカルチャが同一である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65d2-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="c65d2-120">単純な名前付きアセンブリの場合、等価性にはアセンブリ名とカルチャの一致が必要です。</span><span class="sxs-lookup"><span data-stu-id="c65d2-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="c65d2-121">どちらのアセンブリ id も、.NET Framework で実行されるアセンブリを参照します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="c65d2-122">この条件は`true` 、アセンブリのバージョン番号が一致しない場合でもを返します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="c65d2-123">2つのアセンブリはマネージアセンブリでは`fUnified1`あり`fUnified2`ませんが`true`、またはがに設定されています。</span><span class="sxs-lookup"><span data-stu-id="c65d2-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="c65d2-124">フラグ`fUnified`は、厳密な名前が付けられたアセンブリのバージョン番号までのすべてのバージョン番号が、厳密に名前が付けられたアセンブリと同等であると見なされることを示します。</span><span class="sxs-lookup"><span data-stu-id="c65d2-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="c65d2-125">たとえば、の`pwzAssemblyIndentity1`値が "MyAssembly, version = 3.0.0.0, culture = ニュートラル, publicKeyToken =..." で、の値が`true`の`fUnified1`場合、バージョン0.0.0.0 から3.0.0.0 のすべてのバージョンの MyAssembly がである必要があることを示します。同等として扱われます。</span><span class="sxs-lookup"><span data-stu-id="c65d2-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="c65d2-126">このような`pwzAssemblyIndentity2`場合、 `pfEquivalent`がと`pwzAssemblyIndentity1`同じアセンブリを参照している場合は、バージョン番号が低い点がに`true`設定されます。</span><span class="sxs-lookup"><span data-stu-id="c65d2-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="c65d2-127">が`pwzAssemblyIdentity2`より上位のバージョン番号を参照`pfEquivalent`している`true`場合、の`fUnified2`値が`true`である場合にのみがに設定されます。</span><span class="sxs-lookup"><span data-stu-id="c65d2-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="c65d2-128">パラメーター `pResult`には、2つのアセンブリが同等であるかどうかについての特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c65d2-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="c65d2-129">詳細については、「 [AssemblyComparisonResult 列挙型](assemblycomparisonresult-enumeration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65d2-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65d2-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="c65d2-130">Requirements</span></span>  
 <span data-ttu-id="c65d2-131">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65d2-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c65d2-132">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c65d2-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c65d2-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c65d2-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c65d2-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65d2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65d2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c65d2-135">See also</span></span>

- [<span data-ttu-id="c65d2-136">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="c65d2-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="c65d2-137">AssemblyComparisonResult 列挙型</span><span class="sxs-lookup"><span data-stu-id="c65d2-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
