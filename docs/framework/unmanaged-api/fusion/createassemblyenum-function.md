---
title: CreateAssemblyEnum 関数
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c56b0168df6e4aee69b5d3e5fbbe027ca2c8974a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778449"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="00ac5-102">CreateAssemblyEnum 関数</span><span class="sxs-lookup"><span data-stu-id="00ac5-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="00ac5-103">ポインターを取得、 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)インスタンスの指定したアセンブリ内のオブジェクトを列挙できる[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="00ac5-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ac5-104">構文</span><span class="sxs-lookup"><span data-stu-id="00ac5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="00ac5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00ac5-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="00ac5-106">[out]含む、要求されたメモリ位置へのポインター`IAssemblyEnum`ポインター。</span><span class="sxs-lookup"><span data-stu-id="00ac5-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="00ac5-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="00ac5-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="00ac5-108">`pUnkReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ac5-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="00ac5-109">[in]`IAssemblyName`の要求されたアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="00ac5-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="00ac5-110">この名前は、列挙型をフィルター処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="00ac5-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="00ac5-111">グローバル アセンブリ キャッシュ内のすべてのアセンブリを列挙する場合は null になります。</span><span class="sxs-lookup"><span data-stu-id="00ac5-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="00ac5-112">[in]列挙子の動作を変更するためのフラグ。</span><span class="sxs-lookup"><span data-stu-id="00ac5-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="00ac5-113">このパラメーターには正確に 1 ビットが含まれています、 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="00ac5-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="00ac5-114">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="00ac5-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="00ac5-115">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ac5-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00ac5-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="00ac5-116">Remarks</span></span>  
 <span data-ttu-id="00ac5-117">`dwFlags`パラメーターにはから厳密に 1 ビットが含まれています、`ASM_CACHE_FLAGS`列挙体。</span><span class="sxs-lookup"><span data-stu-id="00ac5-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00ac5-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="00ac5-118">Requirements</span></span>  
 <span data-ttu-id="00ac5-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00ac5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ac5-120">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="00ac5-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="00ac5-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="00ac5-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00ac5-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ac5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ac5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="00ac5-123">See also</span></span>

- [<span data-ttu-id="00ac5-124">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00ac5-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="00ac5-125">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00ac5-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="00ac5-126">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="00ac5-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
